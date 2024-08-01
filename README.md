import javax.swing.*;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;

public class GUI {
    public static void main(String[] args) {
        JFrame frame = new JFrame("3 JCheckBoxes Example");
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setSize(300, 200);
        frame.setLayout(new BoxLayout(frame.getContentPane(), BoxLayout.Y_AXIS));

        JCheckBox checkBox1 = new JCheckBox("Im gay");
        JCheckBox checkBox2 = new JCheckBox("Im gay too");
        JCheckBox checkBox3 = new JCheckBox("Yes,Im gay");

        ActionListener checkBoxListener = new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                JCheckBox source = (JCheckBox) e.getSource();
                if (source.isSelected()) {
                    System.out.println(source.getText() + " is selected.");
                } else {
                    System.out.println(source.getText() + " is not selected.");
                }
            }
        };

        checkBox1.addActionListener(checkBoxListener);
        checkBox2.addActionListener(checkBoxListener);
        checkBox3.addActionListener(checkBoxListener);

        JPanel panel = new JPanel();
        panel.add(checkBox1);
        panel.add(checkBox2);
        panel.add(checkBox3);

        frame.getContentPane().add(panel);

        frame.setVisible(true);
    }
}
