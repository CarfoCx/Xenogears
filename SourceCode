import tkinter as tk

class ScrollTextApp:
    def __init__(self, root):
        self.root = root
        self.root.title("")
        self.root.configure(bg="black")
        self.root.attributes("-fullscreen", True)  # Make the window fullscreen
        self.root.attributes("-topmost", True)  # Keep the window on top of others

        # Determine screen resolution
        screen_width = self.root.winfo_screenwidth()
        screen_height = self.root.winfo_screenheight()

        # Set the window to full screen
        self.root.geometry(f"{screen_width}x{screen_height}")

        # Set transparency for black background
        self.root.wm_attributes("-transparentcolor", "black")

        # Create a frame for the text label
        self.frame = tk.Frame(root, bg='black', bd=0, highlightthickness=0)
        self.frame.pack(fill="both", expand=True)

        # Set initial text
        self.text = ""  # Text to scroll
        self.index = 0  # Index of the current letter
        self.label = tk.Label(self.frame, text="", font=("Arial", 28), fg="red", bg="black", anchor=tk.SW, justify='left', wraplength=screen_width, bd=0)
        self.label.pack(fill="both", expand=True)  # Fill and expand label to fill the frame

        # Force focus to ensure CTRL+C works
        self.root.focus_force()

        # Animate text
        self.animate_text()

        # Bind CTRL+C to close window (directly to root)
        self.root.bind("<Control-c>", self.close_window)

    def animate_text(self):
        self.text += "You shall be as gods "[self.index]
        self.label.config(text=self.text)
        self.index = (self.index + 1) % len("You shall be as gods ")
        self.root.after(30, self.animate_text)

    def close_window(self, event):
        self.root.destroy()

if __name__ == "__main__":
    root = tk.Tk()
    app = ScrollTextApp(root)
    root.mainloop()
