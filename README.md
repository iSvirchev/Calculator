package Calculators;

import java.awt.EventQueue;

import javax.swing.JFrame;
import javax.swing.JTextField;
import javax.swing.JButton;
import java.awt.Font;
import java.awt.event.ActionListener;
import java.awt.event.ActionEvent;
import javax.swing.SwingConstants;
import java.awt.event.KeyAdapter;
import java.awt.event.KeyEvent;

public class Calculator {

	private JFrame frame;
	private JTextField txtDisplay;
	private JButton btnDel;
	private JButton btnClear;
	private JButton btnPercent;
	private JButton btnDev;
	private JButton btn7;
	private JButton btn8;
	private JButton btn9;
	private JButton btnPlus;
	private JButton btn4;
	private JButton btn5;
	private JButton btn6;
	private JButton btnSub;
	private JButton btn1;
	private JButton btn2;
	private JButton btn3;
	private JButton btnMult;
	private JButton btn0;
	private JButton btnDot;
	private JButton btnPM;
	private JButton btnEquals;
	
	double num1;
	double num2;
	double result;
	String Operations;
	String Answer;

	/**
	 * Launch the application.
	 */
	public static void main(String[] args) {
		EventQueue.invokeLater(new Runnable() {
			public void run() {
				try {
					Calculator window = new Calculator();
					window.frame.setVisible(true);
				} catch (Exception e) {
					e.printStackTrace();
				}
			}
		});
	}

	/**
	 * Create the application.
	 */
	public Calculator() {
		initialize();
	}

	/**
	 * Initialize the contents of the frame.
	 */
	private void initialize() {
		frame = new JFrame();
		frame.setBounds(100, 100, 273, 405);
		frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
		frame.getContentPane().setLayout(null);
		
		txtDisplay = new JTextField();
		txtDisplay.addKeyListener(new KeyAdapter() {
			@Override
			public void keyTyped(KeyEvent e) {
				if (!(e.getKeyChar() >= '0' && e.getKeyChar() <= '9')) {
		            e.consume();
		        }
			}
		});
		txtDisplay.setHorizontalAlignment(SwingConstants.RIGHT);
		txtDisplay.setBounds(10, 11, 237, 38);
		frame.getContentPane().add(txtDisplay);
		txtDisplay.setColumns(10);
		
		
		///// Row 1 /////
		btnDel = new JButton("D");
		btnDel.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) {
				String delete = null;
				
				if(txtDisplay.getText().length()>0) {
					StringBuilder sb = new StringBuilder(txtDisplay.getText());
					sb.deleteCharAt(txtDisplay.getText().length()-1);
					delete = sb.toString();
					txtDisplay.setText(delete);
				}
			}
		});
		btnDel.setFont(new Font("Tahoma", Font.BOLD, 18));
		btnDel.setBounds(10, 60, 55, 50);
		frame.getContentPane().add(btnDel);
		
		btnClear = new JButton("C");
		btnClear.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) {
				txtDisplay.setText(null);
			}
		});
		btnClear.setFont(new Font("Tahoma", Font.BOLD, 18));
		btnClear.setBounds(72, 60, 55, 50);
		frame.getContentPane().add(btnClear);
		
		btnPercent = new JButton("%");
		btnPercent.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) {
				if(txtDisplay.getText().charAt(txtDisplay.getText().length()-1)=='1') {
					txtDisplay.setText(txtDisplay.getText().replace(txtDisplay.getText().charAt(txtDisplay.getText().length()-1), (char) 32));
				}
				num1 = Double.parseDouble(txtDisplay.getText());
				txtDisplay.setText("");
				Operations = "%";
			}
		});
		btnPercent.setFont(new Font("Tahoma", Font.PLAIN, 18));
		btnPercent.setBounds(132, 60, 55, 50);
		frame.getContentPane().add(btnPercent);
		
		btnPlus = new JButton("+");
		btnPlus.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) {
				if(txtDisplay.getText().charAt(txtDisplay.getText().length()-1)=='1') {
					txtDisplay.setText(txtDisplay.getText().replace(txtDisplay.getText().charAt(txtDisplay.getText().length()-1), (char) 32));
				}
				num1 = Double.parseDouble(txtDisplay.getText());
				txtDisplay.setText("");
				Operations = "+";
			}
		});
		btnPlus.setFont(new Font("Tahoma", Font.BOLD, 18));
		btnPlus.setBounds(192, 60, 55, 50);
		frame.getContentPane().add(btnPlus);
		
		///// Row 2 /////
		btn7 = new JButton("7");
		btn7.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent arg0) {
				String EnterNumber = txtDisplay.getText() + btn7.getText();
				txtDisplay.setText(EnterNumber);
			}
		});
		btn7.setFont(new Font("Tahoma", Font.BOLD, 18));
		btn7.setBounds(10, 120, 55, 50);
		frame.getContentPane().add(btn7);
		
		btn8 = new JButton("8");
		btn8.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) {
				String EnterNumber = txtDisplay.getText() + btn8.getText();
				txtDisplay.setText(EnterNumber);
			}
		});
		btn8.setFont(new Font("Tahoma", Font.BOLD, 18));
		btn8.setBounds(72, 120, 55, 50);
		frame.getContentPane().add(btn8);
		
		btn9 = new JButton("9");
		btn9.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) {
				String EnterNumber = txtDisplay.getText() + btn9.getText();
				txtDisplay.setText(EnterNumber);
			}
		});
		btn9.setFont(new Font("Tahoma", Font.BOLD, 18));
		btn9.setBounds(132, 120, 55, 50);
		frame.getContentPane().add(btn9);
		
		btnSub = new JButton("-");
		btnSub.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) {
				if(txtDisplay.getText().charAt(txtDisplay.getText().length()-1)=='1') {
					txtDisplay.setText(txtDisplay.getText().replace(txtDisplay.getText().charAt(txtDisplay.getText().length()-1), (char) 32));
				}
				num1 = Double.parseDouble(txtDisplay.getText());
				txtDisplay.setText("");
				Operations = "-";
			}
		});
		btnSub.setFont(new Font("Tahoma", Font.BOLD, 18));
		btnSub.setBounds(192, 120, 55, 50);
		frame.getContentPane().add(btnSub);
		
		////// Row 3 //////
		btn4 = new JButton("4");
		btn4.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) {
				String EnterNumber = txtDisplay.getText() + btn4.getText();
				txtDisplay.setText(EnterNumber);
			}
		});
		btn4.setFont(new Font("Tahoma", Font.BOLD, 18));
		btn4.setBounds(10, 180, 55, 50);
		frame.getContentPane().add(btn4);
		
		btn5 = new JButton("5");
		btn5.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) {
				String EnterNumber = txtDisplay.getText() + btn5.getText();
				txtDisplay.setText(EnterNumber);
			}
		});
		btn5.setFont(new Font("Tahoma", Font.BOLD, 18));
		btn5.setBounds(72, 180, 55, 50);
		frame.getContentPane().add(btn5);
		
		btn6 = new JButton("6");
		btn6.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) {
				String EnterNumber = txtDisplay.getText() + btn6.getText();
				txtDisplay.setText(EnterNumber);
			}
		});
		btn6.setFont(new Font("Tahoma", Font.BOLD, 18));
		btn6.setBounds(132, 180, 55, 50);
		frame.getContentPane().add(btn6);
		
		btnMult = new JButton("*");
		btnMult.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) {
				if(txtDisplay.getText().charAt(txtDisplay.getText().length()-1)=='1') {
					txtDisplay.setText(txtDisplay.getText().replace(txtDisplay.getText().charAt(txtDisplay.getText().length()-1), (char) 32));
				}
				num1 = Double.parseDouble(txtDisplay.getText());
				txtDisplay.setText("");
				Operations = "*";
			}
		});
		btnMult.setFont(new Font("Tahoma", Font.BOLD, 18));
		btnMult.setBounds(192, 180, 55, 50);
		frame.getContentPane().add(btnMult);
		
		//////  Row 4 //////
		btn1 = new JButton("1");
		btn1.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) {
				String EnterNumber = txtDisplay.getText() + btn1.getText();
				txtDisplay.setText(EnterNumber);
			}
		});
		btn1.setFont(new Font("Tahoma", Font.BOLD, 18));
		btn1.setBounds(10, 240, 55, 50);
		frame.getContentPane().add(btn1);
		
		btn2 = new JButton("2");
		btn2.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) {
				String EnterNumber = txtDisplay.getText() + btn2.getText();
				txtDisplay.setText(EnterNumber);
			}
		});
		btn2.setFont(new Font("Tahoma", Font.BOLD, 18));
		btn2.setBounds(72, 240, 55, 50);
		frame.getContentPane().add(btn2);
		
		btn3 = new JButton("3");
		btn3.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) {
				String EnterNumber = txtDisplay.getText() + btn3.getText();
				txtDisplay.setText(EnterNumber);
			}
		});
		btn3.setFont(new Font("Tahoma", Font.BOLD, 18));
		btn3.setBounds(132, 240, 55, 50);
		frame.getContentPane().add(btn3);
		
		btnDev = new JButton("/");
		btnDev.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) {
				num1 = Double.parseDouble(txtDisplay.getText());
				txtDisplay.setText("");
				Operations = "/";
			}
		});
		btnDev.setFont(new Font("Tahoma", Font.BOLD, 18));
		btnDev.setBounds(192, 240, 55, 50);
		frame.getContentPane().add(btnDev);
		
		////// Row 5 //////
		btn0 = new JButton("0");
		btn0.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) {
				String EnterNumber = txtDisplay.getText() + btn0.getText();
				txtDisplay.setText(EnterNumber);
			}
		});
		btn0.setFont(new Font("Tahoma", Font.BOLD, 18));
		btn0.setBounds(10, 300, 55, 50);
		frame.getContentPane().add(btn0);
		
		btnDot = new JButton(".");
		btnDot.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) {
				txtDisplay.setText(txtDisplay.getText()+".");
			}
		});
		btnDot.setFont(new Font("Tahoma", Font.BOLD, 18));
		btnDot.setBounds(72, 300, 55, 50);
		frame.getContentPane().add(btnDot);
		
		btnPM = new JButton("+/-");
		btnPM.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) {
				num1 = Double.parseDouble(txtDisplay.getText());
				num1 = num1*(-1);
				txtDisplay.setText(displayProperly(num1));
			}
		});
		btnPM.setFont(new Font("Tahoma", Font.PLAIN, 13));
		btnPM.setBounds(132, 300, 55, 50);
		frame.getContentPane().add(btnPM);
		
		btnEquals = new JButton("=");
		btnEquals.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) {
				 num2 = Double.parseDouble(txtDisplay.getText());
				 if(Operations.equals("+")) {
					 result = num1+num2;
					 Answer=displayProperly(result);
					 txtDisplay.setText(Answer);
				 } else if (Operations.equals("-")) {
					 result = num1-num2;
					 Answer=displayProperly(result);
					 txtDisplay.setText(Answer);
				 }else if (Operations.equals("*")) {
					 result = num1*num2;
					 Answer=displayProperly(result);
					 txtDisplay.setText(Answer);
				 }else if (Operations.equals("/")) {
					 result = num1/num2;
					 Answer=displayProperly(result);
					 txtDisplay.setText(Answer);
				 }else if (Operations.equals("%")) {
					 result = num1%num2;
					 Answer=displayProperly(result);
					 txtDisplay.setText(Answer);
				 }
			}
		});
		btnEquals.setFont(new Font("Tahoma", Font.BOLD, 18));
		btnEquals.setBounds(192, 300, 55, 50);
		frame.getContentPane().add(btnEquals);
		
		
		
	}
	public String displayProperly (Double result) { //display values 
		if(result ==Math.round(result)) {
			 Answer = String.format("%.0f", result);
		 }else{
			 Answer = String.format("%.2f", result);
		 }
		
		return Answer;
	}
}
