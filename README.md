/* my serach engine */


package CA;

import java.awt.FlowLayout;
import javax.swing.JButton;
import javax.swing.JFrame;
import javax.swing.JPanel;
import javax.swing.JTextField;

public class Search extends JFrame implement ActionListener{
	JPanel panel1 =new JPanel(); 
	JTextField t1 = new JTextField("Keywords",15);
	JButton b1 = new JButton("Search");	
	
	
	
	Search(String title) {
		super(title);
		setSize(300,300);
		setLayout(new FlowLayout());
		
		
		b1.setToolTipText("Click to search document");
		t1.setToolTipText("Enter key word for search");
	
		add(b1);
		add(t1);
		
		setVisible(true);

	}
}

