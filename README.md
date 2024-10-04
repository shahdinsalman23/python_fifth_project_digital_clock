# Python Digital Clock

This project is a **Digital Clock** application developed using Python's Tkinter library. It displays the current time and date in a visually appealing manner, making it a perfect addition to any desktop environment.

## Features

- Displays:
  - Current time in **hours**, **minutes**, and **seconds** (12-hour format with AM/PM)
  - Current date (formatted as **MM/DD/YY**)
- Automatically updates every second to show real-time clock
- Simple and intuitive graphical user interface using Tkinter
- Customizable background and text color for personalization

## How It Works

1. The application initializes a Tkinter window titled **"Digital Clock."**
2. It defines a function named `time()`, which:
   - Retrieves the current time and date using the `strftime()` function from the `time` module.
   - Updates the label text every second using `label.after()`.
3. The clock is displayed in a label styled with a specific font and colors.

## Code Example

Here is the complete code for the Digital Clock application:

```python
import tkinter as tk
from time import strftime

# Create the main application window
root = tk.Tk()
root.title("Digital Clock")  # Set the title of the window

def time():
    """Update the label with the current time and date."""
    string = strftime('%H:%M:%S %p \n %D')  # Format the time and date
    label.config(text=string)  # Update the label text
    label.after(1000, time)  # Schedule the function to run again after 1 second

# Create a label to display the time and date
label = tk.Label(root, font=('calibri', 50, 'bold'), background='gray', foreground='black')
label.pack(anchor='center')  # Center the label in the window

time()  # Start the clock

root.mainloop()  # Run the application
