# Buffer

Unlike some editors, when you open a file in Emacs it does not stay ''open'' the entire time you're working with it. Instead, Emacs reads the file into a buffer in memory. While you're editing the buffer and working with the data nothing is changed on disk. Only when you actually save the buffer does the file on disk get updated. There are advantages and disadvantages to this approach but it is only important that you understand that it works this way.

As a consequence, you will see the term ''buffer'' used in Emacs documentation, modes, packages, and so on. Just realize that buffer means ''a copy of the file that is currently in memory.'' Oh, it's worth pointing out that a buffer doesn't always have to refer to a specific file on disk. Often times Emacs will create buffers as the result of commands you run. Such buffers may contain the result of the command, a list of selections to pick from, and so on.

1. How to switch between buffers?
    * You can’t see the other buffers until you tell Emacs to view them through a window. To do this, use the C-x b key combination. This will move the point to the mini-buffer and display a message that looks like “Switch to buffer (default *scratch*)”:
    * You will frequently want to know all the buffers that are currently open so you can choose the correct one to switch to. To do this, just press the tab key from the mini-buffer prompt:
    * Type a buffer name into the mini-buffer (for example, *scratch*) and hit enter. This will close the window displaying the *Completions* buffer and open the *scratch* buffer in the window that had previously displayed the GNU Emacs buffer.
    * You can also cycle through buffers sequentially with the key combos C-x right and C-x left.

2. How to go back to the last buffer?

3. How to save a buffer to a file?
    * C-x C-s

4. How to read a file into a buffer?
    * To open a file and load it into a buffer, use C-x C-f, which will open a prompt in the mini-buffer that says “Find file: ~/path/to/current/directory/”. Just as with switching buffers, you can press the tab key to list the files in the directory you have specified if you need to.
    * You can then type in the name (and/or change the path) of the file you want:
    * Press enter, and a new buffer will be created with the file you specified:



# Point and Region

In Emacs lingo, you'll often hear or see references to the point. In general terms the point is the cursor. The actual distinction between the point and cursor probably isn't important when you're first starting out with Emacs. But if you are curious, think about it this way. The cursor is the visual representation of the point. The cursor is always ''on'' a particular character position in the current buffer. The point, on the other hand, lives in the space between characters on in the buffer. So you might say that if the cursor is on the letter 'h' in the word ''the'' then the point is between the 't' and the 'h'.

Like many modern editors, Emacs allows to perform operations (indent, spell-check, reformat, cut, copy, paste, ...) on a section of the current buffer. You can highlight (or ``mark'') a block of text using the keyboard or mouse and then perform operations on just the selected block of text. In Emacs, that block of text is called a region.


# Mini-buffer

1. If you want to cancel the current operation, i.e. you decide you don’t want to switch buffers after all, you can use C-g to quit the mini-buffer.


# Window

Okay, this will be a bit confusing to anyone who has ever used a GUI interface before. Just remember that Emacs was developed long before GUI interfaces and window managers were popular.

A window in Emacs is an area of the screen in which a buffer is displayed. When Emacs is first started, you have one window on your screen. Some Emacs functions (such as the help and documentation) often [temporarily] open up additional windows in your Emacs screen.

Emacs windows have nothing to do with X windows in the GUI sense. You can open up additional X windows to display Emacs buffers, maybe to compare two files side by side. Those new X windows are referred to as frames in Emacs lingo. Read on.

Revisiting the concept of windows: they are essentially just views into a buffer. You can open up multiple windows in the same frame (I usually use two vertical windows) and you can have multiple windows displaying the same buffer:

There are a few relevant key commands for manipulating windows:

C-x 0 : close the active window
C-x 1 : close all windows except the active window
C-x 2 : split the active window vertically into two horizontal windows
C-x 3 : split the active window horizontally into two vertical windows
C-x o : change active window to next window

Note that closing a window does NOT mean that the buffer it is displaying is closed.


# Frames

In Emacs, a frame is a separate X window in which an Emacs buffer is displayed. But both are part of the same Emacs session. The behavior is somewhat (but not too much) like what happens if you hit Alt+N in Netscape Navigator.
