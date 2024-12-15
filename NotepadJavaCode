import javax.swing.*;  // Import Swing components
import java.awt.*;    // Import layout and container classes
import java.awt.event.*; // Import event handling classes
import java.io.*;     // Import file handling classes

public class Notepad {

    // Main frame of the Notepad application
    private JFrame frame;

    // Text area for writing content
    private JTextArea textArea;

    // Constructor to initialize the Notepad application
    public Notepad() {
        // Create the frame
        frame = new JFrame("Notepad");

        // Create a text area with a default font and size
        textArea = new JTextArea();
        textArea.setFont(new Font("Arial", Font.PLAIN, 14));

        // Add scroll support for the text area
        JScrollPane scrollPane = new JScrollPane(textArea);

        // Add the scroll pane to the frame
        frame.add(scrollPane);

        // Create the menu bar
        JMenuBar menuBar = new JMenuBar();

        // Create the 'File' menu
        JMenu fileMenu = new JMenu("File");
        
        // Add menu items: New, Open, Save, Exit
        JMenuItem newItem = new JMenuItem("New");
        JMenuItem openItem = new JMenuItem("Open");
        JMenuItem saveItem = new JMenuItem("Save");
        JMenuItem exitItem = new JMenuItem("Exit");

        // Add action listeners to menu items
        newItem.addActionListener(e -> newFile());
        openItem.addActionListener(e -> openFile());
        saveItem.addActionListener(e -> saveFile());
        exitItem.addActionListener(e -> System.exit(0)); // Exit the application

        // Add the items to the 'File' menu
        fileMenu.add(newItem);
        fileMenu.add(openItem);
        fileMenu.add(saveItem);
        fileMenu.addSeparator(); // Add a separator line
        fileMenu.add(exitItem);

        // Add the 'File' menu to the menu bar
        menuBar.add(fileMenu);

        // Set the menu bar for the frame
        frame.setJMenuBar(menuBar);

        // Set frame properties
        frame.setSize(600, 400); // Width: 600px, Height: 400px
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setLocationRelativeTo(null); // Center the frame on the screen
        frame.setVisible(true); // Make the frame visible
    }

    // Create a new file (clear the text area)
    private void newFile() {
        int response = JOptionPane.showConfirmDialog(frame, "Do you want to save the current file before creating a new one?", "Confirm", JOptionPane.YES_NO_OPTION);
        if (response == JOptionPane.YES_OPTION) {
            saveFile();
        }
        textArea.setText("");
    }

    // Open an existing file
    private void openFile() {
        JFileChooser fileChooser = new JFileChooser();
        int option = fileChooser.showOpenDialog(frame);
        if (option == JFileChooser.APPROVE_OPTION) {
            File file = fileChooser.getSelectedFile();
            try (BufferedReader reader = new BufferedReader(new FileReader(file))) {
                textArea.read(reader, null);
            } catch (IOException ex) {
                JOptionPane.showMessageDialog(frame, "Error opening file: " + ex.getMessage());
            }
        }
    }

    // Save the current file
    private void saveFile() {
        JFileChooser fileChooser = new JFileChooser();
        int option = fileChooser.showSaveDialog(frame);
        if (option == JFileChooser.APPROVE_OPTION) {
            File file = fileChooser.getSelectedFile();
            try (BufferedWriter writer = new BufferedWriter(new FileWriter(file))) {
                textArea.write(writer);
            } catch (IOException ex) {
                JOptionPane.showMessageDialog(frame, "Error saving file: " + ex.getMessage());
            }
        }
    }

    // Main method to run the application
    public static void main(String[] args) {
        SwingUtilities.invokeLater(Notepad::new); // Run on the Event Dispatch Thread
    }
}
