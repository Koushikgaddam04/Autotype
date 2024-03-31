# Autotype
# Neocolab C/C++ Typing Automation

## Description
This Python script automates the typing of text copied to the clipboard specifically for Neocolab C/C++ language typing. It waits for 5 seconds after the program starts and then begins typing the content copied to the clipboard.

## Dependencies
- [pyautogui](https://pyautogui.readthedocs.io/en/latest/index.html): Python library for GUI automation
- [clipboard](https://pypi.org/project/clipboard/): Python library for accessing clipboard content
- [sys](https://docs.python.org/3/library/sys.html): Python system-specific parameters and functions

## How to Use
1. Copy the text you want to type.
2. Run the program.
3. Follow the instructions printed on the console.

## Usage Instructions
1. The program waits for 5 seconds after starting before it begins typing.
2. It types the content character by character with a typing speed calculated to be approximately 70 words per minute (wpm).
3. Special keys such as 'Enter' and 'Down' are pressed as needed to simulate realistic typing behavior.
4. To stop the program, press 'Q' and then Enter when prompted.

## Code Explanation
- The `clip_to_type` function extracts the content from the clipboard, waits for the specified time, and then types the content character by character.
- Special handling is provided for newline characters and curly braces to maintain correct indentation.
- The `main` function controls the overall execution of the program, allowing it to be rerun if desired.

