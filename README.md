# Xoxo
Here is the old school game , which people might have spent a lot of time in...
import java.util.Scanner;
import java.awt.event.*;
import java.awt.*;

class Xoxo extends Frame implements ActionListener
{
	Button t1,t2,t3,t4,t5,t6,t7,t8,t9,b1,b2;
	Label l1;
	int i=9;
	String msg="Hello! Ready to play??";
	public Xoxo()
	{
		setVisible(true);
		setSize(1000,1000);
		setFont(new Font("Arial", Font.BOLD,50));
		setTitle("SHRAVAN");
		addWindowListener(new w());
		l1=new Label("XOXO",Label.LEFT);
		l1.setBackground(Color.lightGray);
		setLayout(null);
		add(l1);
		t1=new Button();
 		t2=new Button();
		t3=new Button();
		t4=new Button();
		t5=new Button();
		t6=new Button();
		t7=new Button();
		t8=new Button();
		t9=new Button();
		b1=new Button("RESET");
		b1.setBackground(Color.blue);
		b2=new Button("START");
		b2.setBackground(Color.green);


		add(t1);
		add(t2);
		add(t3);
		add(t4);
		add(t5);
		add(t6);
		add(t7);
		add(t8);
		add(t9);
		add(b1);
		add(b2);



		b1.addActionListener(this);
		b2.addActionListener(this);
		t1.addActionListener(this); 
		t2.addActionListener(this); 
		t3.addActionListener(this); 
		t4.addActionListener(this); 
		t5.addActionListener(this); 
		t6.addActionListener(this); 
		t7.addActionListener(this); 
		t8.addActionListener(this); 
		t9.addActionListener(this); 




		l1.setBounds(375,150,150,100);
		t1.setBounds(300,300,100,100);
		t2.setBounds(400,300,100,100);
		t3.setBounds(500,300,100,100);
		t4.setBounds(300,400,100,100);
		t5.setBounds(400,400,100,100);
		t6.setBounds(500,400,100,100);
		t7.setBounds(300,500,100,100);
		t8.setBounds(400,500,100,100);
		t9.setBounds(500,500,100,100);
		b2.setBounds(240,650,160,50);
		b1.setBounds(500,650,160,50);


		t1.setBackground(Color.pink);
		t2.setBackground(Color.orange);
		t3.setBackground(Color.pink);
		t4.setBackground(Color.orange);
		t5.setBackground(Color.pink);
		t6.setBackground(Color.orange);
		t7.setBackground(Color.pink);
		t8.setBackground(Color.orange);
		t9.setBackground(Color.pink);


		setBackground(Color.lightGray);
	}





	private class w extends WindowAdapter
	{
		public void windowClosing(WindowEvent e)
		{
			setVisible(false);
			dispose();
		}
	}
	
	public void actionPerformed(ActionEvent e) 
	{
	
		
		if(e.getSource()==b1)
		{
			t1.setLabel("");
			t2.setLabel("");
			t3.setLabel("");
			t4.setLabel("");
			t5.setLabel("");
			t6.setLabel("");
			t7.setLabel("");
			t8.setLabel("");
			t9.setLabel("");
			msg="Hello! Ready to play??";
			repaint();
		}
		if(e.getSource()==b2 )
		{
			msg="It's my turn";
			repaint();
			t5.setLabel("O");
			msg="It's yours turn";
			repaint();
			
		}
		
		
		//CASE OF T1
		if(e.getSource()==t1)
		{


			//warning to ask to press Start
			if(!t5.getLabel().equals("O"))
			{
			setBackground(Color.red);
			msg="Invalid!! Press Start to Start";
			repaint();
			setBackground(Color.lightGray);
			}

			//When user presses t1 in Case 1
			if(t1.getLabel().equals("")&&t2.getLabel().equals("")&&t3.getLabel().equals("")&&t4.getLabel().equals("") &&t5.getLabel().equals("O")&&t6.getLabel().equals("")&&t7.getLabel().equals("")&&t8.getLabel().equals("")&&t9.getLabel().equals(""))
			{
				t1.setLabel("X");
				msg="It's my turn";
				repaint();
				t7.setLabel("O");
				msg="It's your turn";
				repaint();	
			
			}

			//When user presses t1 in Case 2 as a second entry
			if(t1.getLabel().equals("")&&t2.getLabel().equals("X")&&t3.getLabel().equals("")&&t4.getLabel().equals("") &&t5.getLabel().equals("O")&&t6.getLabel().equals("")&&t7.getLabel().equals("O")&&t8.getLabel().equals("")&&t9.getLabel().equals(""))
			{
				t1.setLabel("X");
				msg="It's my turn";
				repaint();
				t3.setLabel("O");
				msg="I WON !!!";
				repaint();	
			}


			//When user presses t1 in Case 3 as a second entry
			if(t1.getLabel().equals("")&&t2.getLabel().equals("")&&t3.getLabel().equals("X")&&t4.getLabel().equals("") &&t5.getLabel().equals("O")&&t6.getLabel().equals("")&&t7.getLabel().equals("")&&t8.getLabel().equals("")&&t9.getLabel().equals("O"))
			{
				t1.setLabel("X");
				msg="It's my turn";
				repaint();
				t2.setLabel("O");
				msg="It's your turn";
				repaint();	
			}

			//When user presses t1 in Case 4 as a second entry
			if(t1.getLabel().equals("")&&t2.getLabel().equals("")&&t3.getLabel().equals("")&&t4.getLabel().equals("X") &&t5.getLabel().equals("O")&&t6.getLabel().equals("")&&t7.getLabel().equals("O")&&t8.getLabel().equals("")&&t9.getLabel().equals(""))
			{
				t1.setLabel("X");
				msg="It's my turn";
				repaint();
				t3.setLabel("O");
				msg="I WON !!!";
				repaint();
			}

			//When user presses t1 in Case 4 as a Third entry
			if(t1.getLabel().equals("")&&t2.getLabel().equals("")&&t3.getLabel().equals("X")&&t4.getLabel().equals("X") &&t5.getLabel().equals("O")&&t6.getLabel().equals("")&&t7.getLabel().equals("O")&&t8.getLabel().equals("")&&t9.getLabel().equals("O"))
			{
				t1.setLabel("X");
				msg="It's my turn";
				repaint();
				t8.setLabel("O");
				msg="I WON!!!";
				repaint();	
			}

			//When user presses t1 in Case6 as a second entry
			if(t1.getLabel().equals("")&&t2.getLabel().equals("")&&t3.getLabel().equals("")&&t4.getLabel().equals("") &&t5.getLabel().equals("O")&&t6.getLabel().equals("X")&&t7.getLabel().equals("")&&t8.getLabel().equals("")&&t9.getLabel().equals("O"))
			{
				t1.setLabel("X");
				msg="It's my turn";
				repaint();
				t7.setLabel("O");
				msg="It's your turn";
				repaint();
			}
			//When user presses t1 in Case 7 as a second entry
			if(t1.getLabel().equals("")&&t2.getLabel().equals("")&&t3.getLabel().equals("")&&t4.getLabel().equals("") &&t5.getLabel().equals("O")&&t6.getLabel().equals("")&&t7.getLabel().equals("X")&&t8.getLabel().equals("")&&t9.getLabel().equals("O"))
			{
				t1.setLabel("X");
				msg="It's my turn";
				repaint();
				t4.setLabel("O");
				msg="It's your turn";
				repaint();	
			}
			//When user presses t1 in Case 9 as Second entry
			if(t1.getLabel().equals("")&&t2.getLabel().equals("")&&t3.getLabel().equals("")&&t4.getLabel().equals("") &&t5.getLabel().equals("O")&&t6.getLabel().equals("")&&t7.getLabel().equals("O")&&t8.getLabel().equals("")&&t9.getLabel().equals("X"))
			{
				t1.setLabel("X");
				msg="It's my turn";
				repaint();
				t3.setLabel("O");
				msg="I WON!!!";
				repaint();
			}
			//When user presses t1 in Case 9 as Third entry
			if(t1.getLabel().equals("")&&t2.getLabel().equals("")&&t3.getLabel().equals("X")&&t4.getLabel().equals("") &&t5.getLabel().equals("O")&&t6.getLabel().equals("O")&&t7.getLabel().equals("O")&&t8.getLabel().equals("")&&t9.getLabel().equals("X"))
			{
				t1.setLabel("X");
				msg="It's my turn";
				repaint();
				t4.setLabel("O");
				msg="I WON!!!";
				repaint();
			}
			//When user presses t1 in Case 9 as Fourth entry
			if(t1.getLabel().equals("")&&t2.getLabel().equals("")&&t3.getLabel().equals("X")&&t4.getLabel().equals("X") &&t5.getLabel().equals("O")&&t6.getLabel().equals("O")&&t7.getLabel().equals("O")&&t8.getLabel().equals("O")&&t9.getLabel().equals("X"))
			{
				t1.setLabel("X");
				msg="It's my turn";
				repaint();
				t2.setLabel("O");
				msg="I WON!!!";
				repaint();
			}
		}


		//CASE-2
		if(e.getSource()==t2)
		{

			//warning to ask to press Start
			if(!t5.getLabel().equals("O"))
			{
			msg="Invalid!! Press Start to Start";
			repaint();
			}


			//When user presses t2 in Case 1 as a second entry
			if(t1.getLabel().equals("X")&&t2.getLabel().equals("")&&t3.getLabel().equals("")&&t4.getLabel().equals("") &&t5.getLabel().equals("O")&&t6.getLabel().equals("")&&t7.getLabel().equals("O")&&t8.getLabel().equals("")&&t9.getLabel().equals(""))
			{
				t2.setLabel("X");
				msg="It's my turn";
				repaint();
				t3.setLabel("O");
				msg="I WON !!!";
				repaint();	
			}

			//When user presses t2 in Case 2 as First entry
			if(t1.getLabel().equals("")&&t2.getLabel().equals("")&&t3.getLabel().equals("")&&t4.getLabel().equals("") &&t5.getLabel().equals("O")&&t6.getLabel().equals("")&&t7.getLabel().equals("")&&t8.getLabel().equals("")&&t9.getLabel().equals(""))
			{
				t2.setLabel("X");
				msg="It's my turn";
				repaint();
				t7.setLabel("O");
				msg="It's your turn";
			}	repaint();	
			


			//When user presses t2 in Case 3 as a second entry
			if(t1.getLabel().equals("")&&t2.getLabel().equals("")&&t3.getLabel().equals("X")&&t4.getLabel().equals("") &&t5.getLabel().equals("O")&&t6.getLabel().equals("")&&t7.getLabel().equals("")&&t8.getLabel().equals("")&&t9.getLabel().equals("O"))
			{
				t2.setLabel("X");
				msg="It's my turn";
				repaint();
				t1.setLabel("O");
				msg="I WON!!!";
				repaint();	
			}


			//When user presses t2 in Case 4 as a second entry
			if(t1.getLabel().equals("")&&t2.getLabel().equals("")&&t3.getLabel().equals("")&&t4.getLabel().equals("X") &&t5.getLabel().equals("O")&&t6.getLabel().equals("")&&t7.getLabel().equals("O")&&t8.getLabel().equals("")&&t9.getLabel().equals(""))
			{
				t2.setLabel("X");
				msg="It's my turn";
				repaint();
				t3.setLabel("O");
				msg="I WON !!!";
				repaint();
			}

			//When user presses t2 in Case 4 as a Third entry
			if(t1.getLabel().equals("")&&t2.getLabel().equals("")&&t3.getLabel().equals("X")&&t4.getLabel().equals("X") &&t5.getLabel().equals("O")&&t6.getLabel().equals("")&&t7.getLabel().equals("O")&&t8.getLabel().equals("")&&t9.getLabel().equals("O"))
			{
				t2.setLabel("X");
				msg="It's my turn";
				repaint();
				t8.setLabel("O");
				msg="I WON!!!";
				repaint();	
			}

			//When user presses t2 in Case6 as a second entry
			if(t1.getLabel().equals("")&&t2.getLabel().equals("")&&t3.getLabel().equals("")&&t4.getLabel().equals("") &&t5.getLabel().equals("O")&&t6.getLabel().equals("X")&&t7.getLabel().equals("")&&t8.getLabel().equals("")&&t9.getLabel().equals("O"))
			{
				t2.setLabel("X");
				msg="It's my turn";
				repaint();
				t1.setLabel("O");
				msg="I WON!!!";
				repaint();
			}
			//When user presses t2 in Case6 as a Third entry
			if(t1.getLabel().equals("X")&&t2.getLabel().equals("")&&t3.getLabel().equals("")&&t4.getLabel().equals("") &&t5.getLabel().equals("O")&&t6.getLabel().equals("X")&&t7.getLabel().equals("O")&&t8.getLabel().equals("")&&t9.getLabel().equals("O"))
			{
				t2.setLabel("X");
				msg="It's my turn";
				repaint();
				t8.setLabel("O");
				msg="I WON!!!";
				repaint();
			}

			//When user presses t2 in Case 7 as a second entry
			if(t1.getLabel().equals("")&&t2.getLabel().equals("")&&t3.getLabel().equals("")&&t4.getLabel().equals("") &&t5.getLabel().equals("O")&&t6.getLabel().equals("")&&t7.getLabel().equals("X")&&t8.getLabel().equals("")&&t9.getLabel().equals("O"))
			{
				t2.setLabel("X");
				msg="It's my turn";
				repaint();
				t1.setLabel("O");
				msg="I WON!!!";
				repaint();	
			}
			//When user presses t2 in Case 7 as a Third entry
			if(t1.getLabel().equals("X")&&t2.getLabel().equals("")&&t3.getLabel().equals("")&&t4.getLabel().equals("O") &&t5.getLabel().equals("O")&&t6.getLabel().equals("")&&t7.getLabel().equals("X")&&t8.getLabel().equals("")&&t9.getLabel().equals("O"))
			{
				t2.setLabel("X");
				msg="It's my turn";
				repaint();
				t6.setLabel("O");
				msg="I WON!!!";
				repaint();	
			}
			//When user presses t2 in Case 7 as a Fourth entry
			if(t1.getLabel().equals("X")&&t2.getLabel().equals("")&&t3.getLabel().equals("")&&t4.getLabel().equals("O") &&t5.getLabel().equals("O")&&t6.getLabel().equals("X")&&t7.getLabel().equals("X")&&t8.getLabel().equals("O")&&t9.getLabel().equals("O"))
			{
				t2.setLabel("X");
				msg="It's my turn";
				repaint();
				t3.setLabel("O");
				msg="TOUGH NUT!!!";
				repaint();	
			}
			//When user presses t2 in Case 8 as a second entry
			if(t1.getLabel().equals("O")&&t2.getLabel().equals("")&&t3.getLabel().equals("")&&t4.getLabel().equals("") &&t5.getLabel().equals("O")&&t6.getLabel().equals("")&&t7.getLabel().equals("")&&t8.getLabel().equals("X")&&t9.getLabel().equals(""))
			{
				t2.setLabel("X");
				msg="It's my turn";
				repaint();
				t9.setLabel("O");
				msg="I WON!!!";
				repaint();
			}
			//When user presses t2 in Case 8 as a Third entry
			if(t1.getLabel().equals("O")&&t2.getLabel().equals("")&&t3.getLabel().equals("")&&t4.getLabel().equals("") &&t5.getLabel().equals("O")&&t6.getLabel().equals("")&&t7.getLabel().equals("O")&&t8.getLabel().equals("X")&&t9.getLabel().equals("X"))
			{
				t2.setLabel("X");
				msg="It's my turn";
				repaint();
				t4.setLabel("O");
				msg="I WON!!!";
				repaint();
			}
			//When user presses t2 in Case 9 as Second entry
			if(t1.getLabel().equals("")&&t2.getLabel().equals("")&&t3.getLabel().equals("")&&t4.getLabel().equals("") &&t5.getLabel().equals("O")&&t6.getLabel().equals("")&&t7.getLabel().equals("O")&&t8.getLabel().equals("")&&t9.getLabel().equals("X"))
			{
				t2.setLabel("X");
				msg="It's my turn";
				repaint();
				t3.setLabel("O");
				msg="I WON!!!";
				repaint();
			}
			//When user presses t2 in Case 9 as Third entry
			if(t1.getLabel().equals("")&&t2.getLabel().equals("")&&t3.getLabel().equals("X")&&t4.getLabel().equals("") &&t5.getLabel().equals("O")&&t6.getLabel().equals("O")&&t7.getLabel().equals("O")&&t8.getLabel().equals("")&&t9.getLabel().equals("X"))
			{
				t2.setLabel("X");
				msg="It's my turn";
				repaint();
				t4.setLabel("O");
				msg="I WON!!!";
				repaint();
			}
			//When user presses t2 in Case 9 as Fourth entry
			if(t1.getLabel().equals("")&&t2.getLabel().equals("")&&t3.getLabel().equals("X")&&t4.getLabel().equals("X") &&t5.getLabel().equals("O")&&t6.getLabel().equals("O")&&t7.getLabel().equals("O")&&t8.getLabel().equals("O")&&t9.getLabel().equals("X"))
			{
				t2.setLabel("X");
				msg="It's my turn";
				repaint();
				t1.setLabel("O");
				msg="TOUGH NUT!!!";
				repaint();
			}
		}


		//CASE-3
		if(e.getSource()==t3)
		{



			//warning to ask to press Start
			if(!t5.getLabel().equals("O"))
			{
			msg="Invalid!! Press Start to Start";
			repaint();
			}
			//When user presses t3 in Case 1 as a second entry
			if(t1.getLabel().equals("X")&&t2.getLabel().equals("")&&t3.getLabel().equals("")&&t4.getLabel().equals("") &&t5.getLabel().equals("O")&&t6.getLabel().equals("")&&t7.getLabel().equals("O")&&t8.getLabel().equals("")&&t9.getLabel().equals(""))
			{
				t3.setLabel("X");
				msg="It's my turn";
				repaint();
				t2.setLabel("O");
				msg="It's your turn";
				repaint();	
			}

			//When user presses t3 in Case 2 as a second entry
			if(t1.getLabel().equals("")&&t2.getLabel().equals("X")&&t3.getLabel().equals("")&&t4.getLabel().equals("") &&t5.getLabel().equals("O")&&t6.getLabel().equals("")&&t7.getLabel().equals("O")&&t8.getLabel().equals("")&&t9.getLabel().equals(""))
			{
				t3.setLabel("X");
				msg="It's my turn";
				repaint();
				t1.setLabel("O");
				msg="It's your turn";
				repaint();	
			}


			//When user presses t3 in Case 3 as First entry
			if(t1.getLabel().equals("")&&t2.getLabel().equals("")&&t3.getLabel().equals("")&&t4.getLabel().equals("") &&t5.getLabel().equals("O")&&t6.getLabel().equals("")&&t7.getLabel().equals("")&&t8.getLabel().equals("")&&t9.getLabel().equals(""))
			{
				t3.setLabel("X");
				msg="It's my turn";
				repaint();
				t9.setLabel("O");
				msg="It's your turn";
				repaint();	
			}

			//When user presses t3 in Case 4 as a second entry
			if(t1.getLabel().equals("")&&t2.getLabel().equals("")&&t3.getLabel().equals("")&&t4.getLabel().equals("X") &&t5.getLabel().equals("O")&&t6.getLabel().equals("")&&t7.getLabel().equals("O")&&t8.getLabel().equals("")&&t9.getLabel().equals(""))
			{
				t3.setLabel("X");
				msg="It's my turn";
				repaint();
				t9.setLabel("O");
				msg="It's your turn";
				repaint();
			}
			//When user presses t3 in Case6 as a second entry
			if(t1.getLabel().equals("")&&t2.getLabel().equals("")&&t3.getLabel().equals("")&&t4.getLabel().equals("") &&t5.getLabel().equals("O")&&t6.getLabel().equals("X")&&t7.getLabel().equals("")&&t8.getLabel().equals("")&&t9.getLabel().equals("O"))
			{
				t3.setLabel("X");
				msg="It's my turn";
				repaint();
				t1.setLabel("O");
				msg="I WON!!!";
				repaint();
			}
			//When user presses t3 in Case6 as a Third entry
			if(t1.getLabel().equals("X")&&t2.getLabel().equals("")&&t3.getLabel().equals("")&&t4.getLabel().equals("") &&t5.getLabel().equals("O")&&t6.getLabel().equals("X")&&t7.getLabel().equals("O")&&t8.getLabel().equals("")&&t9.getLabel().equals("O"))
			{
				t3.setLabel("X");
				msg="It's my turn";
				repaint();
				t8.setLabel("O");
				msg="I WON!!!";
				repaint();
			}
			//When user presses t3 in Case 7 as a second entry
			if(t1.getLabel().equals("")&&t2.getLabel().equals("")&&t3.getLabel().equals("")&&t4.getLabel().equals("") &&t5.getLabel().equals("O")&&t6.getLabel().equals("")&&t7.getLabel().equals("X")&&t8.getLabel().equals("")&&t9.getLabel().equals("O"))
			{
				t3.setLabel("X");
				msg="It's my turn";
				repaint();
				t1.setLabel("O");
				msg="I WON!!!";
				repaint();	
			}
			//When user presses t3 in Case 7 as a Third entry
			if(t1.getLabel().equals("X")&&t2.getLabel().equals("")&&t3.getLabel().equals("")&&t4.getLabel().equals("O") &&t5.getLabel().equals("O")&&t6.getLabel().equals("")&&t7.getLabel().equals("X")&&t8.getLabel().equals("")&&t9.getLabel().equals("O"))
			{
				t3.setLabel("X");
				msg="It's my turn";
				repaint();
				t6.setLabel("O");
				msg="I WON!!!";
				repaint();	
			}
			//When user presses t3 in Case 7 as a Fourth entry
			if(t1.getLabel().equals("X")&&t2.getLabel().equals("")&&t3.getLabel().equals("")&&t4.getLabel().equals("O") &&t5.getLabel().equals("O")&&t6.getLabel().equals("X")&&t7.getLabel().equals("X")&&t8.getLabel().equals("O")&&t9.getLabel().equals("O"))
			{
				t3.setLabel("X");
				msg="It's my turn";
				repaint();
				t2.setLabel("O");
				msg="I WON!!!";
				repaint();	
			}
			//When user presses t3 in Case 8 as a second entry
			if(t1.getLabel().equals("O")&&t2.getLabel().equals("")&&t3.getLabel().equals("")&&t4.getLabel().equals("") &&t5.getLabel().equals("O")&&t6.getLabel().equals("")&&t7.getLabel().equals("")&&t8.getLabel().equals("X")&&t9.getLabel().equals(""))
			{
				t3.setLabel("X");
				msg="It's my turn";
				repaint();
				t9.setLabel("O");
				msg="I WON!!!";
				repaint();
			}
			//When user presses t3 in Case 8 as a Third entry
			if(t1.getLabel().equals("O")&&t2.getLabel().equals("")&&t3.getLabel().equals("")&&t4.getLabel().equals("") &&t5.getLabel().equals("O")&&t6.getLabel().equals("")&&t7.getLabel().equals("O")&&t8.getLabel().equals("X")&&t9.getLabel().equals("X"))
			{
				t3.setLabel("X");
				msg="It's my turn";
				repaint();
				t4.setLabel("O");
				msg="I WON!!!";
				repaint();
			}
			//When user presses t3 in Case 9 as Second entry
			if(t1.getLabel().equals("")&&t2.getLabel().equals("")&&t3.getLabel().equals("")&&t4.getLabel().equals("") &&t5.getLabel().equals("O")&&t6.getLabel().equals("")&&t7.getLabel().equals("O")&&t8.getLabel().equals("")&&t9.getLabel().equals("X"))
			{
				t3.setLabel("X");
				msg="It's my turn";
				repaint();
				t6.setLabel("O");
				msg="It's your turn";
				repaint();
			}
		}



		//CASE-4
		if(e.getSource()==t4)
		{


			//warning to ask to press Start
			if(!t5.getLabel().equals("O"))
			{
			msg="Invalid!! Press Start to Start";
			repaint();
			}
			//When user presses t4 in Case 1 as a second entry
			if(t1.getLabel().equals("X")&&t2.getLabel().equals("")&&t3.getLabel().equals("")&&t4.getLabel().equals("") &&t5.getLabel().equals("O")&&t6.getLabel().equals("")&&t7.getLabel().equals("O")&&t8.getLabel().equals("")&&t9.getLabel().equals(""))
			{
				t4.setLabel("X");
				msg="It's my turn";
				repaint();
				t3.setLabel("O");
				msg="I WON !!!";
				repaint();	
			}
			
			//When user presses t4 in Case 1 as a Third entry
			if(t1.getLabel().equals("X")&&t2.getLabel().equals("O")&&t3.getLabel().equals("X")&&t4.getLabel().equals("") &&t5.getLabel().equals("O")&&t6.getLabel().equals("")&&t7.getLabel().equals("O")&&t8.getLabel().equals("")&&t9.getLabel().equals(""))
			{
				t4.setLabel("X");
				msg="It's my turn";
				repaint();
				t8.setLabel("O");
				msg="I WON !!!";
				repaint();	
			}

			//When user presses t4 in Case 2 as a second entry
			if(t1.getLabel().equals("")&&t2.getLabel().equals("X")&&t3.getLabel().equals("")&&t4.getLabel().equals("") &&t5.getLabel().equals("O")&&t6.getLabel().equals("")&&t7.getLabel().equals("O")&&t8.getLabel().equals("")&&t9.getLabel().equals(""))
			{
				t4.setLabel("X");
				msg="It's my turn";
				repaint();
				t3.setLabel("O");
				msg="I WON !!!";
				repaint();	
			}

			//When user presses t4 in Case 2 as a Third entry
			if(t1.getLabel().equals("O")&&t2.getLabel().equals("X")&&t3.getLabel().equals("X")&&t4.getLabel().equals("") &&t5.getLabel().equals("O")&&t6.getLabel().equals("")&&t7.getLabel().equals("O")&&t8.getLabel().equals("")&&t9.getLabel().equals(""))
			{
				t4.setLabel("X");
				msg="It's my turn";
				repaint();
				t9.setLabel("O");
				msg="I WON !!!";
				repaint();	
			}

			//When user presses t4 in Case 3 as a second entry
			if(t1.getLabel().equals("")&&t2.getLabel().equals("")&&t3.getLabel().equals("X")&&t4.getLabel().equals("") &&t5.getLabel().equals("O")&&t6.getLabel().equals("")&&t7.getLabel().equals("")&&t8.getLabel().equals("")&&t9.getLabel().equals("O"))
			{
				t4.setLabel("X");
				msg="It's my turn";
				repaint();
				t1.setLabel("O");
				msg="I WON!!!";
				repaint();	
			}
			//When user presses t4 in Case 3 as a Third entry
			if(t1.getLabel().equals("X")&&t2.getLabel().equals("O")&&t3.getLabel().equals("X")&&t4.getLabel().equals("") &&t5.getLabel().equals("O")&&t6.getLabel().equals("")&&t7.getLabel().equals("")&&t8.getLabel().equals("")&&t9.getLabel().equals("O"))
			{
				t4.setLabel("X");
				msg="It's my turn";
				repaint();
				t8.setLabel("O");
				msg="I WON!!!";
				repaint();	
			}

			//When user presses t4 in Case 4 as First entry
			if(t1.getLabel().equals("")&&t2.getLabel().equals("")&&t3.getLabel().equals("")&&t4.getLabel().equals("") &&t5.getLabel().equals("O")&&t6.getLabel().equals("")&&t7.getLabel().equals("")&&t8.getLabel().equals("")&&t9.getLabel().equals(""))
			{
				t4.setLabel("X");
				msg="It's my turn";
				repaint();
				t7.setLabel("O");
				msg="It's your turn";
				repaint();
			}	
			//When user presses t4 in Case6 as a second entry
			if(t1.getLabel().equals("")&&t2.getLabel().equals("")&&t3.getLabel().equals("")&&t4.getLabel().equals("") &&t5.getLabel().equals("O")&&t6.getLabel().equals("X")&&t7.getLabel().equals("")&&t8.getLabel().equals("")&&t9.getLabel().equals("O"))
			{
				t4.setLabel("X");
				msg="It's my turn";
				repaint();
				t1.setLabel("O");
				msg="I WON!!!";
				repaint();
			}
			//When user presses t4 in Case6 as a Third entry
			if(t1.getLabel().equals("X")&&t2.getLabel().equals("")&&t3.getLabel().equals("")&&t4.getLabel().equals("") &&t5.getLabel().equals("O")&&t6.getLabel().equals("X")&&t7.getLabel().equals("O")&&t8.getLabel().equals("")&&t9.getLabel().equals("O"))
			{
				t4.setLabel("X");
				msg="It's my turn";
				repaint();
				t8.setLabel("O");
				msg="I WON!!!";
				repaint();
			}
			//When user presses t4 in Case 7 as a second entry
			if(t1.getLabel().equals("")&&t2.getLabel().equals("")&&t3.getLabel().equals("")&&t4.getLabel().equals("") &&t5.getLabel().equals("O")&&t6.getLabel().equals("")&&t7.getLabel().equals("X")&&t8.getLabel().equals("")&&t9.getLabel().equals("O"))
			{
				t4.setLabel("X");
				msg="It's my turn";
				repaint();
				t1.setLabel("O");
				msg="I WON!!!";
				repaint();	
			}
			//When user presses t4 in Case 8 as a second entry
			if(t1.getLabel().equals("O")&&t2.getLabel().equals("")&&t3.getLabel().equals("")&&t4.getLabel().equals("") &&t5.getLabel().equals("O")&&t6.getLabel().equals("")&&t7.getLabel().equals("")&&t8.getLabel().equals("X")&&t9.getLabel().equals(""))
			{
				t4.setLabel("X");
				msg="It's my turn";
				repaint();
				t9.setLabel("O");
				msg="I WON!!!";
				repaint();
			}
			//When user presses t4 in Case 8 as a Third entry
			if(t1.getLabel().equals("O")&&t2.getLabel().equals("")&&t3.getLabel().equals("")&&t4.getLabel().equals("") &&t5.getLabel().equals("O")&&t6.getLabel().equals("")&&t7.getLabel().equals("O")&&t8.getLabel().equals("X")&&t9.getLabel().equals("X"))
			{
				t4.setLabel("X");
				msg="It's my turn";
				repaint();
				t3.setLabel("O");
				msg="I WON!!!";
				repaint();
			}
			//When user presses t4 in Case 9 as Second entry
			if(t1.getLabel().equals("")&&t2.getLabel().equals("")&&t3.getLabel().equals("")&&t4.getLabel().equals("") &&t5.getLabel().equals("O")&&t6.getLabel().equals("")&&t7.getLabel().equals("O")&&t8.getLabel().equals("")&&t9.getLabel().equals("X"))
			{
				t4.setLabel("X");
				msg="It's my turn";
				repaint();
				t3.setLabel("O");
				msg="I WON!!!";
				repaint();
			}
			//When user presses t4 in Case 9 as Third entry
			if(t1.getLabel().equals("")&&t2.getLabel().equals("")&&t3.getLabel().equals("X")&&t4.getLabel().equals("") &&t5.getLabel().equals("O")&&t6.getLabel().equals("O")&&t7.getLabel().equals("O")&&t8.getLabel().equals("")&&t9.getLabel().equals("X"))
			{
				t4.setLabel("X");
				msg="It's my turn";
				repaint();
				t8.setLabel("O");
				msg="It's your turn";
				repaint();
			}
		}



		//CASE-6
		if(e.getSource()==t6)
		{


			//warning to ask to press Start
			if(!t5.getLabel().equals("O"))
			{
			msg="Invalid!! Press Start to Start";
			repaint();
			}

			//When user presses t6 in Case 1 as a second entry
			if(t1.getLabel().equals("X")&&t2.getLabel().equals("")&&t3.getLabel().equals("")&&t4.getLabel().equals("") &&t5.getLabel().equals("O")&&t6.getLabel().equals("")&&t7.getLabel().equals("O")&&t8.getLabel().equals("")&&t9.getLabel().equals(""))
			{
				t6.setLabel("X");
				msg="It's my turn";
				repaint();
				t3.setLabel("O");
				msg="I WON !!!";
				repaint();	
			}

			//When user presses t6 in Case 1 as a Third entry
			if(t1.getLabel().equals("X")&&t2.getLabel().equals("O")&&t3.getLabel().equals("X")&&t4.getLabel().equals("") &&t5.getLabel().equals("O")&&t6.getLabel().equals("")&&t7.getLabel().equals("O")&&t8.getLabel().equals("")&&t9.getLabel().equals(""))
			{
				t6.setLabel("X");
				msg="It's my turn";
				repaint();
				t8.setLabel("O");
				msg="I WON !!!";
				repaint();	
			}

			//When user presses t6 in Case 2 as a second entry
			if(t1.getLabel().equals("")&&t2.getLabel().equals("X")&&t3.getLabel().equals("")&&t4.getLabel().equals("") &&t5.getLabel().equals("O")&&t6.getLabel().equals("")&&t7.getLabel().equals("O")&&t8.getLabel().equals("")&&t9.getLabel().equals(""))
			{
				t6.setLabel("X");
				msg="It's my turn";
				repaint();
				t3.setLabel("O");
				msg="I WON !!!";
				repaint();	
			}

			//When user presses t6 in Case 2 as a Third entry
			if(t1.getLabel().equals("O")&&t2.getLabel().equals("X")&&t3.getLabel().equals("X")&&t4.getLabel().equals("") &&t5.getLabel().equals("O")&&t6.getLabel().equals("")&&t7.getLabel().equals("O")&&t8.getLabel().equals("")&&t9.getLabel().equals(""))
			{
				t6.setLabel("X");
				msg="It's my turn";
				repaint();
				t4.setLabel("O");
				msg="I WON !!!";
				repaint();	
			}

			//When user presses t6 in Case 3 as a second entry
			if(t1.getLabel().equals("")&&t2.getLabel().equals("")&&t3.getLabel().equals("X")&&t4.getLabel().equals("") &&t5.getLabel().equals("O")&&t6.getLabel().equals("")&&t7.getLabel().equals("")&&t8.getLabel().equals("")&&t9.getLabel().equals("O"))
			{
				t6.setLabel("X");
				msg="It's my turn";
				repaint();
				t1.setLabel("O");
				msg="I WON!!!";
				repaint();	
			}

			//When user presses t6 in Case 3 as a Third entry
			if(t1.getLabel().equals("X")&&t2.getLabel().equals("O")&&t3.getLabel().equals("X")&&t4.getLabel().equals("") &&t5.getLabel().equals("O")&&t6.getLabel().equals("")&&t7.getLabel().equals("")&&t8.getLabel().equals("")&&t9.getLabel().equals("O"))
			{
				t6.setLabel("X");
				msg="It's my turn";
				repaint();
				t8.setLabel("O");
				msg="I WON!!!";
				repaint();	
			}

			//When user presses t6 in Case 3 as a Fourth entry
			if(t1.getLabel().equals("X")&&t2.getLabel().equals("O")&&t3.getLabel().equals("X")&&t4.getLabel().equals("O") &&t5.getLabel().equals("O")&&t6.getLabel().equals("")&&t7.getLabel().equals("")&&t8.getLabel().equals("X")&&t9.getLabel().equals("O"))
			{
				t6.setLabel("X");
				msg="It's my turn";
				repaint();
				t7.setLabel("O");
				msg="Tough Nut!!!";
				repaint();	
			}

			//When user presses t6 in Case 4 as a second entry
			if(t1.getLabel().equals("")&&t2.getLabel().equals("")&&t3.getLabel().equals("")&&t4.getLabel().equals("X") &&t5.getLabel().equals("O")&&t6.getLabel().equals("")&&t7.getLabel().equals("O")&&t8.getLabel().equals("")&&t9.getLabel().equals(""))
			{
				t6.setLabel("X");
				msg="It's my turn";
				repaint();
				t3.setLabel("O");
				msg="I WON !!!";
				repaint();
			}

			//When user presses t6 in Case 4 as a Third entry
			if(t1.getLabel().equals("")&&t2.getLabel().equals("")&&t3.getLabel().equals("X")&&t4.getLabel().equals("X") &&t5.getLabel().equals("O")&&t6.getLabel().equals("")&&t7.getLabel().equals("O")&&t8.getLabel().equals("")&&t9.getLabel().equals("O"))
			{
				t6.setLabel("X");
				msg="It's my turn";
				repaint();
				t8.setLabel("O");
				msg="I WON!!!";
				repaint();	
			}

			//When user presses t6 in Case 6 as First entry
			if(t1.getLabel().equals("")&&t2.getLabel().equals("")&&t3.getLabel().equals("")&&t4.getLabel().equals("") &&t5.getLabel().equals("O")&&t6.getLabel().equals("")&&t7.getLabel().equals("")&&t8.getLabel().equals("")&&t9.getLabel().equals(""))
			{
				t6.setLabel("X");
				msg="It's my turn";
				repaint();
				t9.setLabel("O");
				msg="It's your turn";
				repaint();	
			}
			//When user presses t6 in Case 7 as a second entry
			if(t1.getLabel().equals("")&&t2.getLabel().equals("")&&t3.getLabel().equals("")&&t4.getLabel().equals("") &&t5.getLabel().equals("O")&&t6.getLabel().equals("")&&t7.getLabel().equals("X")&&t8.getLabel().equals("")&&t9.getLabel().equals("O"))
			{
				t6.setLabel("X");
				msg="It's my turn";
				repaint();
				t1.setLabel("O");
				msg="I WON!!!";
				repaint();	
			}
			//When user presses t6 in Case 7 as a Third entry
			if(t1.getLabel().equals("X")&&t2.getLabel().equals("")&&t3.getLabel().equals("")&&t4.getLabel().equals("O") &&t5.getLabel().equals("O")&&t6.getLabel().equals("")&&t7.getLabel().equals("X")&&t8.getLabel().equals("")&&t9.getLabel().equals("O"))
			{
				t6.setLabel("X");
				msg="It's my turn";
				repaint();
				t8.setLabel("O");
				msg="It's your turn";
				repaint();	
			}
			//When user presses t6 in Case 8 as a second entry
			if(t1.getLabel().equals("O")&&t2.getLabel().equals("")&&t3.getLabel().equals("")&&t4.getLabel().equals("") &&t5.getLabel().equals("O")&&t6.getLabel().equals("")&&t7.getLabel().equals("")&&t8.getLabel().equals("X")&&t9.getLabel().equals(""))
			{
				t6.setLabel("X");
				msg="It's my turn";
				repaint();
				t9.setLabel("O");
				msg="I WON!!!";
				repaint();
			}
			//When user presses t6 in Case 8 as a Third entry
			if(t1.getLabel().equals("O")&&t2.getLabel().equals("")&&t3.getLabel().equals("")&&t4.getLabel().equals("") &&t5.getLabel().equals("O")&&t6.getLabel().equals("")&&t7.getLabel().equals("O")&&t8.getLabel().equals("X")&&t9.getLabel().equals("X"))
			{
				t6.setLabel("X");
				msg="It's my turn";
				repaint();
				t4.setLabel("O");
				msg="I WON!!!";
				repaint();
			}
			//When user presses t6 in Case 9 as Second entry
			if(t1.getLabel().equals("")&&t2.getLabel().equals("")&&t3.getLabel().equals("")&&t4.getLabel().equals("") &&t5.getLabel().equals("O")&&t6.getLabel().equals("")&&t7.getLabel().equals("O")&&t8.getLabel().equals("")&&t9.getLabel().equals("X"))
			{
				t6.setLabel("X");
				msg="It's my turn";
				repaint();
				t3.setLabel("O");
				msg="I WON!!!";
				repaint();
			}
		}




		//CASE-7
		if(e.getSource()==t7)
		{


			//warning to ask to press Start
			if(!t5.getLabel().equals("O"))
			{
			msg="Invalid!! Press Start to Start";
			repaint();
			}


			//When user presses t7 in Case 1 as a second entry
			if(t1.getLabel().equals("X")&&t2.getLabel().equals("")&&t3.getLabel().equals("")&&t4.getLabel().equals("") &&t5.getLabel().equals("O")&&t6.getLabel().equals("")&&t7.getLabel().equals("O")&&t8.getLabel().equals("")&&t9.getLabel().equals(""))
			{
				msg="Invalid";
				repaint();
	
			}

			//When user presses t7 in Case 3 as a second entry
			if(t1.getLabel().equals("")&&t2.getLabel().equals("")&&t3.getLabel().equals("X")&&t4.getLabel().equals("") &&t5.getLabel().equals("O")&&t6.getLabel().equals("")&&t7.getLabel().equals("")&&t8.getLabel().equals("")&&t9.getLabel().equals("O"))
			{
				t7.setLabel("X");
				msg="It's my turn";
				repaint();
				t1.setLabel("O");
				msg="I WON!!!";
				repaint();	
			}
			//When user presses t7 in Case 3 as a Third entry
			if(t1.getLabel().equals("X")&&t2.getLabel().equals("O")&&t3.getLabel().equals("X")&&t4.getLabel().equals("") &&t5.getLabel().equals("O")&&t6.getLabel().equals("")&&t7.getLabel().equals("")&&t8.getLabel().equals("")&&t9.getLabel().equals("O"))
			{
				t7.setLabel("X");
				msg="It's my turn";
				repaint();
				t8.setLabel("O");
				msg="I WON!!!";
				repaint();	
			}

			//When user presses t7 in Case 3 as a Fourth entry
			if(t1.getLabel().equals("X")&&t2.getLabel().equals("O")&&t3.getLabel().equals("X")&&t4.getLabel().equals("O") &&t5.getLabel().equals("O")&&t6.getLabel().equals("")&&t7.getLabel().equals("")&&t8.getLabel().equals("X")&&t9.getLabel().equals("O"))
			{
				t7.setLabel("X");
				msg="It's my turn";
				repaint();
				t6.setLabel("O");
				msg="I WON!!!";
				repaint();	
			}
			//When user presses t7 in Case6 as a second entry
			if(t1.getLabel().equals("")&&t2.getLabel().equals("")&&t3.getLabel().equals("")&&t4.getLabel().equals("") &&t5.getLabel().equals("O")&&t6.getLabel().equals("X")&&t7.getLabel().equals("")&&t8.getLabel().equals("")&&t9.getLabel().equals("O"))
			{
				t7.setLabel("X");
				msg="It's my turn";
				repaint();
				t1.setLabel("O");
				msg="I WON!!!";
				repaint();
			}

			//When user presses t7 in Case 7 as First entry
			if(t1.getLabel().equals("")&&t2.getLabel().equals("")&&t3.getLabel().equals("")&&t4.getLabel().equals("") &&t5.getLabel().equals("O")&&t6.getLabel().equals("")&&t7.getLabel().equals("")&&t8.getLabel().equals("")&&t9.getLabel().equals(""))
			{
				t7.setLabel("X");
				msg="It's my turn";
				repaint();
				t9.setLabel("O");
				msg="It's your turn";
				repaint();
			}
			//When user presses t7 in Case 8 as a second entry
			if(t1.getLabel().equals("O")&&t2.getLabel().equals("")&&t3.getLabel().equals("")&&t4.getLabel().equals("") &&t5.getLabel().equals("O")&&t6.getLabel().equals("")&&t7.getLabel().equals("")&&t8.getLabel().equals("X")&&t9.getLabel().equals(""))
			{
				t7.setLabel("X");
				msg="It's my turn";
				repaint();
				t9.setLabel("O");
				msg="I WON!!!";
				repaint();
			}
		}


		//CASE-8
		if(e.getSource()==t8)
		{



			//warning to ask to press Start
			if(!t5.getLabel().equals("O"))
			{
			msg="Invalid!! Press Start to Start";
			repaint();
			}


			//When user presses t8 in Case 1 as a second entry
			if(t1.getLabel().equals("X")&&t2.getLabel().equals("")&&t3.getLabel().equals("")&&t4.getLabel().equals("") &&t5.getLabel().equals("O")&&t6.getLabel().equals("")&&t7.getLabel().equals("O")&&t8.getLabel().equals("")&&t9.getLabel().equals(""))
			{
				t8.setLabel("X");
				msg="It's my turn";
				repaint();
				t3.setLabel("O");
				msg="I WON !!!";
				repaint();	
			}

			//When user presses t8 in Case 1 as a Third entry
			if(t1.getLabel().equals("X")&&t2.getLabel().equals("O")&&t3.getLabel().equals("X")&&t4.getLabel().equals("") &&t5.getLabel().equals("O")&&t6.getLabel().equals("")&&t7.getLabel().equals("O")&&t8.getLabel().equals("")&&t9.getLabel().equals(""))
			{
				t8.setLabel("X");
				msg="It's my turn";
				repaint();
				t9.setLabel("O");
				msg="Tough Nut!!!";
				repaint();	
			}

			//When user presses t8 in Case 2 as a second entry
			if(t1.getLabel().equals("")&&t2.getLabel().equals("X")&&t3.getLabel().equals("")&&t4.getLabel().equals("") &&t5.getLabel().equals("O")&&t6.getLabel().equals("")&&t7.getLabel().equals("O")&&t8.getLabel().equals("")&&t9.getLabel().equals(""))
			{
				t8.setLabel("X");
				msg="It's my turn";
				repaint();
				t3.setLabel("O");
				msg="I WON!!!";
				repaint();	
			}

			//When user presses t8 in Case 2 as a Third entry
			if(t1.getLabel().equals("O")&&t2.getLabel().equals("X")&&t3.getLabel().equals("X")&&t4.getLabel().equals("") &&t5.getLabel().equals("O")&&t6.getLabel().equals("")&&t7.getLabel().equals("O")&&t8.getLabel().equals("")&&t9.getLabel().equals(""))
			{
				t8.setLabel("X");
				msg="It's my turn";
				repaint();
				t4.setLabel("O");
				msg="I WON!!!";
				repaint();	
			}


			//When user presses t8 in Case 3 as a second entry
			if(t1.getLabel().equals("")&&t2.getLabel().equals("")&&t3.getLabel().equals("X")&&t4.getLabel().equals("") &&t5.getLabel().equals("O")&&t6.getLabel().equals("")&&t7.getLabel().equals("")&&t8.getLabel().equals("")&&t9.getLabel().equals("O"))
			{
				t8.setLabel("X");
				msg="It's my turn";
				repaint();
				t1.setLabel("O");
				msg="I WON!!!";
				repaint();	
			}


			//When user presses t8 in Case 3 as a Third entry
			if(t1.getLabel().equals("X")&&t2.getLabel().equals("O")&&t3.getLabel().equals("X")&&t4.getLabel().equals("") &&t5.getLabel().equals("O")&&t6.getLabel().equals("")&&t7.getLabel().equals("")&&t8.getLabel().equals("")&&t9.getLabel().equals("O"))
			{
				t8.setLabel("X");
				msg="It's my turn";
				repaint();
				t4.setLabel("O");
				msg="It's your turn";
				repaint();	
			}
			//When user presses t8 in Case 4 as a second entry
			if(t1.getLabel().equals("")&&t2.getLabel().equals("")&&t3.getLabel().equals("")&&t4.getLabel().equals("X") &&t5.getLabel().equals("O")&&t6.getLabel().equals("")&&t7.getLabel().equals("O")&&t8.getLabel().equals("")&&t9.getLabel().equals(""))
			{
				t8.setLabel("X");
				msg="It's my turn";
				repaint();
				t3.setLabel("O");
				msg="I WON!!!";
				repaint();
			}

			//When user presses t8 in Case 4 as a Third entry
			if(t1.getLabel().equals("")&&t2.getLabel().equals("")&&t3.getLabel().equals("X")&&t4.getLabel().equals("X") &&t5.getLabel().equals("O")&&t6.getLabel().equals("")&&t7.getLabel().equals("O")&&t8.getLabel().equals("")&&t9.getLabel().equals("O"))
			{
				t8.setLabel("X");
				msg="It's my turn";
				repaint();
				t1.setLabel("O");
				msg="I WON!!!";
				repaint();	
			}
			//When user presses t8 in Case6 as a second entry
			if(t1.getLabel().equals("")&&t2.getLabel().equals("")&&t3.getLabel().equals("")&&t4.getLabel().equals("") &&t5.getLabel().equals("O")&&t6.getLabel().equals("X")&&t7.getLabel().equals("")&&t8.getLabel().equals("")&&t9.getLabel().equals("O"))
			{
				t8.setLabel("X");
				msg="It's my turn";
				repaint();
				t1.setLabel("O");
				msg="I WON!!!";
				repaint();
			}
			//When user presses t8 in Case6 as a Third entry
			if(t1.getLabel().equals("X")&&t2.getLabel().equals("")&&t3.getLabel().equals("")&&t4.getLabel().equals("") &&t5.getLabel().equals("O")&&t6.getLabel().equals("X")&&t7.getLabel().equals("O")&&t8.getLabel().equals("")&&t9.getLabel().equals("O"))
			{
				t8.setLabel("X");
				msg="It's my turn";
				repaint();
				t3.setLabel("O");
				msg="I WON!!!";
				repaint();
			}
			//When user presses t8 in Case 7 as a second entry
			if(t1.getLabel().equals("")&&t2.getLabel().equals("")&&t3.getLabel().equals("")&&t4.getLabel().equals("") &&t5.getLabel().equals("O")&&t6.getLabel().equals("")&&t7.getLabel().equals("X")&&t8.getLabel().equals("")&&t9.getLabel().equals("O"))
			{
				t8.setLabel("X");
				msg="It's my turn";
				repaint();
				t1.setLabel("O");
				msg="I WON!!!";
				repaint();	
			}
			//When user presses t8 in Case 7 as a Third entry
			if(t1.getLabel().equals("X")&&t2.getLabel().equals("")&&t3.getLabel().equals("")&&t4.getLabel().equals("O") &&t5.getLabel().equals("O")&&t6.getLabel().equals("")&&t7.getLabel().equals("X")&&t8.getLabel().equals("")&&t9.getLabel().equals("O"))
			{
				t8.setLabel("X");
				msg="It's my turn";
				repaint();
				t6.setLabel("O");
				msg="I WON!!!";
				repaint();	
			}
			//When user presses t8 in Case 8 as First entry
			if(t1.getLabel().equals("")&&t2.getLabel().equals("")&&t3.getLabel().equals("")&&t4.getLabel().equals("") &&t5.getLabel().equals("O")&&t6.getLabel().equals("")&&t7.getLabel().equals("")&&t8.getLabel().equals("")&&t9.getLabel().equals(""))
			{
				t8.setLabel("X");
				msg="It's my turn";
				repaint();
				t1.setLabel("O");
				msg="It's your turn";
				repaint();
			}
			//When user presses t8 in Case 9 as Second entry
			if(t1.getLabel().equals("")&&t2.getLabel().equals("")&&t3.getLabel().equals("")&&t4.getLabel().equals("") &&t5.getLabel().equals("O")&&t6.getLabel().equals("")&&t7.getLabel().equals("O")&&t8.getLabel().equals("")&&t9.getLabel().equals("X"))
			{
				t8.setLabel("X");
				msg="It's my turn";
				repaint();
				t3.setLabel("O");
				msg="I WON!!!";
				repaint();
			}
			//When user presses t8 in Case 9 as Third entry
			if(t1.getLabel().equals("")&&t2.getLabel().equals("")&&t3.getLabel().equals("X")&&t4.getLabel().equals("") &&t5.getLabel().equals("O")&&t6.getLabel().equals("O")&&t7.getLabel().equals("O")&&t8.getLabel().equals("")&&t9.getLabel().equals("X"))
			{
				t8.setLabel("X");
				msg="It's my turn";
				repaint();
				t4.setLabel("O");
				msg="I WON!!!";
				repaint();
			}
		}


		//CASE-9
		if(e.getSource()==t9)
		{
			//warning to ask to press Start
			if(!t5.getLabel().equals("O"))
			{
			msg="Invalid!! Press Start to Start";
			repaint();
			}


			//When user presses t9 in Case 1 as a second entry
			if(t1.getLabel().equals("X")&&t2.getLabel().equals("")&&t3.getLabel().equals("")&&t4.getLabel().equals("") &&t5.getLabel().equals("O")&&t6.getLabel().equals("")&&t7.getLabel().equals("O")&&t8.getLabel().equals("")&&t9.getLabel().equals(""))
			{
				t9.setLabel("X");
				msg="It's my turn";
				repaint();
				t3.setLabel("O");
				msg="I WON!!!";
				repaint();	
			}
			//When user presses t9 in Case 1 as a Third entry
			if(t1.getLabel().equals("X")&&t2.getLabel().equals("O")&&t3.getLabel().equals("X")&&t4.getLabel().equals("") &&t5.getLabel().equals("O")&&t6.getLabel().equals("")&&t7.getLabel().equals("O")&&t8.getLabel().equals("")&&t9.getLabel().equals(""))
			{
				t9.setLabel("X");
				msg="It's my turn";
				repaint();
				t8.setLabel("O");
				msg="I WON!!!";
				repaint();	
			}

			//When user presses t9 in Case 2 as a second entry
			if(t1.getLabel().equals("")&&t2.getLabel().equals("X")&&t3.getLabel().equals("")&&t4.getLabel().equals("") &&t5.getLabel().equals("O")&&t6.getLabel().equals("")&&t7.getLabel().equals("O")&&t8.getLabel().equals("")&&t9.getLabel().equals(""))
			{
				t9.setLabel("X");
				msg="It's my turn";
				repaint();
				t3.setLabel("O");
				msg="I WON!!!";
				repaint();	
			}

			//When user presses t9 in Case 2 as a Third entry
			if(t1.getLabel().equals("O")&&t2.getLabel().equals("X")&&t3.getLabel().equals("X")&&t4.getLabel().equals("") &&t5.getLabel().equals("O")&&t6.getLabel().equals("")&&t7.getLabel().equals("O")&&t8.getLabel().equals("")&&t9.getLabel().equals(""))
			{
				t9.setLabel("X");
				msg="It's my turn";
				repaint();
				t4.setLabel("O");
				msg="I WON!!!";
				repaint();	
			}
			//When user presses t9 in Case 4 as a second entry
			if(t1.getLabel().equals("")&&t2.getLabel().equals("")&&t3.getLabel().equals("")&&t4.getLabel().equals("X") &&t5.getLabel().equals("O")&&t6.getLabel().equals("")&&t7.getLabel().equals("O")&&t8.getLabel().equals("")&&t9.getLabel().equals(""))
			{
				t9.setLabel("X");
				msg="It's my turn";
				repaint();
				t3.setLabel("O");
				msg="I WON!!!";
				repaint();
			}
			//When user presses t9 in Case 8 as a second entry
			if(t1.getLabel().equals("O")&&t2.getLabel().equals("")&&t3.getLabel().equals("")&&t4.getLabel().equals("") &&t5.getLabel().equals("O")&&t6.getLabel().equals("")&&t7.getLabel().equals("")&&t8.getLabel().equals("X")&&t9.getLabel().equals(""))
			{
				t9.setLabel("X");
				msg="It's my turn";
				repaint();
				t7.setLabel("O");
				msg="It's your turn";
				repaint();
			}
			//When user presses t9 in Case 9 as First entry
			if(t1.getLabel().equals("")&&t2.getLabel().equals("")&&t3.getLabel().equals("")&&t4.getLabel().equals("") &&t5.getLabel().equals("O")&&t6.getLabel().equals("")&&t7.getLabel().equals("")&&t8.getLabel().equals("")&&t9.getLabel().equals(""))
			{
				t9.setLabel("X");
				msg="It's my turn";
				repaint();
				t7.setLabel("O");
				msg="It's your turn";
			}	repaint();
		}
	}
	public void paint(Graphics g)
	{
		g.setFont(new Font("Arial",Font.BOLD,26));
		g.drawString(msg,300,750);
	}
	public static void main(String arg[])
	{
         	Xoxo o=new Xoxo();
        }

	
}
