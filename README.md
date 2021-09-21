/* my search engine */


package CA;

import java.awt.Color;
import java.awt.FlowLayout;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;
import java.awt.event.MouseEvent;
import java.awt.event.MouseListener;
import java.io.File;
import java.util.Scanner;

import javax.swing.JButton;
import javax.swing.JFrame;
import javax.swing.JTextField;

public class Search extends JFrame implements ActionListener, MouseListener{
	private JTextField t1 = new JTextField("Keywords",15);
	private JButton b1 = new JButton("Search");	
	
	
	
	Search(String title) {
		super(title);
		setSize(300,300);
		setLayout(new FlowLayout());
		
		
		
		t1.addActionListener(this);
		b1.addActionListener(this);
		
		
		b1.setToolTipText("Click to search document");
		t1.setToolTipText("Enter key word for search");
	
		add(b1);
		add(t1);
		
		
		setVisible(true);

	}



	@Override
	public void mouseClicked(MouseEvent e) {
		
		
	}



	@Override
	public void mousePressed(MouseEvent e) {
		// TODO Auto-generated method stub
		
	}



	@Override
	public void mouseReleased(MouseEvent e) {
		// TODO Auto-generated method stub
		
	}



	@Override
	public void mouseEntered(MouseEvent e) {
		// TODO Auto-generated method stub
		
	}



	@Override
	public void mouseExited(MouseEvent e) {
		// TODO Auto-generated method stub
		
	}



	@Override
	public void actionPerformed(ActionEvent e) {
		String word;
		if(e.getSource()==t1) {
			word =e.getActionCommand();
			System.out.println(word);
			
		}
		
		
	}
}


package CA;

public class Fileopen {
	String filename;
	
	
	
	
	Fileopen(String filename){
		this.filename=filename;
	}

}

import java.io.File;
import java.io.FileNotFoundException;
import java.io.PrintWriter;
import java.util.Scanner;

public class FileManager 
{
	String fileName;
	File fileExample;
	Scanner myScanner;
    PrintWriter pwInput;
	
	// Constructor
	FileManager (String fileName)
	{
		
		this.fileName = fileName;
		
	}
	package CA;

import java.awt.FlowLayout;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;

import java.io.BufferedReader;
import java.io.FileReader;
import java.io.IOException;
import java.util.ArrayList;


import javax.swing.JButton;
import javax.swing.JFrame;
import javax.swing.JTextField;



public class Search extends JFrame implements ActionListener{
	private JTextField t1 = new JTextField("Keywords",15);
	private JButton b1 = new JButton("Search");	
	
	
	
	Search(String title) {
		super(title);
		setSize(300,300);
		setLayout(new FlowLayout());
		
		
		
		
		t1.addActionListener(this);
		b1.addActionListener(this);
		
		
		b1.setToolTipText("Click to search document");
		t1.setToolTipText("Enter key word for search");
	
		add(b1);
		add(t1);
		
		
		setVisible(true);

	}



	
	




	public void actionPerformed(ActionEvent e) {
		
		ArrayList<String> text= new ArrayList<String>();
		ArrayList<String> text1= new ArrayList<String>();
		String word;
				
			
		if(e.getSource()==(t1)) {
			word =e.getActionCommand();
			

			BufferedReader input = null;
			BufferedReader input1= null;
			
			
			
			
			
			try {
				input= new BufferedReader(new FileReader("roles.txt"));
				input1= new BufferedReader(new FileReader("test.txt"));
				
			    String line,line2;
			  
				
				while((line= input.readLine() )!= null) {
			                
			             text.add(line);
						
					 }
				
				boolean inFile = text.stream().anyMatch(p->p.equalsIgnoreCase(word));
				
				if (inFile) {
					System.out.println("The word  "+word+ "  matches in the roles file:");
					System.out.println(text);
				}
				else {

					while((line2= input1.readLine() )!= null) {
				                
				             text1.add(line2);
							
						 }
					
					boolean inFile1 = text1.stream().anyMatch(p->p.equalsIgnoreCase(word));
					if (inFile1) {
						System.out.println("The word  "+word+ "  matches in the text file:");
						System.out.println(text1);
					}
					else {
						System.out.println("no match found");
						
					}
				
					
				}
				
				
				
				
		        		
		        	
		        
		        
						
			}
			
				catch (IOException e1) {
				e1.printStackTrace();
			}
			
			
		}
		
	}
}
	

	

