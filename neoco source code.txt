"""
This code starts typing anything that's copied to the clipboard after 5 seconds once the program is started.
This code is specifically written for neocolab C/C++ language typing.
"""

import pyautogui
import time
import clipboard
import sys



def clip_to_type(wait = 5):
    wpm = 70

    print(f"The typing of the copied content in the clipboard is going to start in {wait} seconds.")
    print("Please open the window where you want the keys to be pressed.")

    content = clipboard.paste()

    # content = content.replace('|', ' ') # Uncomment this line to do a typing test on the website 10fastfingers.com

    print(f"Copied content peek: {content[:50]}...")

    time.sleep(wait)

    print("Typing:")

    prev_newline = False
    for i, char in enumerate(content):
        print(char, end="")
        if char == "\n":
            if content[i + 1] == '}':
                continue

            pyautogui.press('enter') # press function is used to press special keys
            prev_newline = True
            continue
        elif char == '}':
            pyautogui.press('down')
            continue
        elif char == ' ' and prev_newline:
            continue

        pyautogui.typewrite(char, _pause=False) # typewrite function is used to type strings of characters
        time.sleep(60 / (wpm * 4.7))
        prev_newline = False


def main():
    loop = True

    while loop:
        print("This program will start typing whatever text is copied in your clipboard.")
        print("So copy the text that you want the program to type and then run the program.")

        input("(Press Enter to start the program...)")

        try:
            clip_to_type(int(sys.argv[1]))
        except IndexError:
            clip_to_type()

        print("\nExecution Completed!")
        choice = input("Press Enter to re-run the program (Hit Q and then Enter to quit)...")

        if choice.lower() == 'q':
            loop = False


if __name__ == '__main__':
    main()
