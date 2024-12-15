# NotepadJAVA
Create a Simple Notepad in Java Swings understand the concept of JButtons,dilogbox, simple GUI just for Fun Create in 20 Minutes
</br>
Here's a simple Java Swing program for creating a basic Notepad application. I'll include a detailed description within the code comments to help you understand its functionality.

### Description of the Program

1. **Main Components**:
   - A `JFrame` for the main application window.
   - A `JTextArea` for writing text, which is wrapped in a `JScrollPane` to allow scrolling.

2. **Menu Bar**:
   - A `JMenuBar` contains a `File` menu with four options: New, Open, Save, and Exit.
   - Each menu item has an associated action listener for handling user input.

3. **Features**:
   - **New**: Clears the text area after prompting the user to save the current content.
   - **Open**: Allows users to select and load a file into the text area using a `JFileChooser`.
   - **Save**: Saves the content of the text area to a selected file.
   - **Exit**: Closes the application.

4. **Error Handling**:
   - Displays error messages using `JOptionPane` when file operations fail.

5. **User-Friendly**:
   - Includes a confirmation dialog when the user attempts to create a new file.

Feel free to test or extend the functionality further, like adding a font changer or search functionality!
