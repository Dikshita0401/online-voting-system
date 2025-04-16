# online-voting-system
import javax.sql.*;
import java.sql.*;
import java.awt.*;
import java.util.*;
import java.awt.event.*;
import java.awt.print.*;
import javax.swing.*;
import javax.swing.event.*;
public class myproject0 extends Thread
{
myproject0() throws Exception
{
Class.forName("oracle.jdbc.driver.OracleDriver");
JFrame jf1=new JFrame("My Project");
JPanel jp1=new JPanel();
JPanel jp2=new JPanel();
JButton jb=new JButton("Click>>>");
 ImageIcon icon=new ImageIcon("vote1.JPG");
JLabel jl1=new JLabel("On-line Voting System",icon,JLabel.CENTER);
ImageIcon icon1=new ImageIcon("vote2.JPG");
JLabel jl2=new JLabel(icon1,JLabel.CENTER);
jl1.setVerticalTextPosition(JLabel.BOTTOM);
jl1.setFont(new Font("NJ",Font.ITALIC,50));
jb.setFont(new Font("NJ",Font.ITALIC,30));
jb.setForeground(Color.blue);
jb.setBackground(Color.green);
final JProgressBar jpb=new JProgressBar();
jf1.setLayout(new GridLayout(2,1,0,0));
jf1.add(jp1);
jf1.add(jp2);
jp1.setBackground(Color.pink);
jp1.setForeground(Color.magenta);
jp2.setBackground(Color.gray);
jp1.setLayout(new FlowLayout());
jp2.setLayout(new GridBagLayout());
GridBagConstraints c=new GridBagConstraints();
jp1.add(jl1);
jp2.add(jl2,c);
c.ipadx=100;
c.ipady=30;
c.gridx=0;
c.gridy=0;
jp2.add(jpb,c);
c.ipadx=0;
c.ipady=35;
c.gridx=3;
c.gridy=0;
jp2.add(jb,c);
c.ipadx=100;
c.ipady=50;
c.gridx=10;
c.gridy=2;
jb.addActionListener(new ActionListener()
{
public void actionPerformed(ActionEvent e)
{
try
{
for(int i=0;i<=100;i=i+20)
{
jpb.setValue(jpb.getValue()  + (+i));
sleep(1000);
}
}
catch(Exception ex)
{
}
}
});
                       //adding voter's ,candidates's,result's menu item form.
jpb.addChangeListener(new ChangeListener()
{
public void stateChanged(ChangeEvent e1)
{
if(jpb.getMaximum()==100)
{
JFrame jf1=new JFrame();
JPanel jp1=new JPanel();
jf1.setLayout(new GridLayout(1,1,0,0));
jf1.add(jp1);
jp1.setBackground(Color.darkGray);
jp1.setLayout(new GridBagLayout());
ImageIcon icon=new ImageIcon("vote4.JPG");
JLabel jl1=new JLabel(icon,JLabel.CENTER);
ImageIcon icon1=new ImageIcon("vote3.PNG");
JLabel jl2=new JLabel(icon1,JLabel.CENTER);
GridBagConstraints c=new GridBagConstraints();
JMenuBar jmb=new JMenuBar();
jmb.setLayout(new GridBagLayout());
GridBagConstraints c1=new GridBagConstraints();
jmb.setBackground(Color.blue);
jmb.setForeground(Color.green);
JMenu voter=new JMenu("Voter");
voter.setFont(new Font("NJ",Font.BOLD,30));
final JMenuItem jmi1=new JMenuItem("Add New Voter");
final JMenuItem jmi2=new JMenuItem("Edit Voter");
final JMenuItem jmi3=new JMenuItem("Delete Voter");
final JMenuItem jmi31=new JMenuItem("Search Name In Voter List");
voter.add(jmi1);
voter.add(jmi2);
voter.add(jmi3);
voter.add(jmi31);
c1.ipadx=100;
c1.ipady=30;
c1.weighty=1;
c1.weightx=1;
jmb.add(voter,c1);
JMenu candi=new JMenu("Candidate");
candi.setFont(new Font("NJ",Font.BOLD,30));
final JMenuItem jmi4=new JMenuItem("Add New Candidate");
final JMenuItem jmi5=new JMenuItem("Edit Candidate");
final JMenuItem jmi6=new JMenuItem("Delete Candidate");
candi.add(jmi4);
candi.add(jmi5);
candi.add(jmi6);
c1.ipady=30;
c1.ipadx=200;
c1.weighty=1;
c1.weightx=1;
jmb.add(candi,c1);
JMenu vote=new JMenu("Vote");
vote.setFont(new Font("NJ",Font.BOLD,30));
final JMenuItem jmi7=new JMenuItem("Caste Your Vote");
vote.add(jmi7);
c1.ipadx=100;
c1.ipady=30;
c1.weighty=1;
c1.weightx=1;
jmb.add(vote,c1);
JMenu result=new JMenu("Result");
result.setFont(new Font("NJ",Font.BOLD,30));
final JMenuItem jmi8=new JMenuItem("Winner");
final JMenuItem jmi9=new JMenuItem("Candidate Wise");
result.add(jmi8);
result.add(jmi9);
c1.ipadx=100;
c1.ipady=30;
c1.weighty=1;
c1.weightx=1;
jmb.add(result,c1);
c.ipady=80;
c.ipadx=800;
c.weighty=1;
c.weightx=1;
c.gridx=0;
c.gridy=0;
//c.insets=new Insets(10,10,0,0);
jp1.add(jmb,c);
c.gridx=0;
c.gridy=2;
jp1.add(jl1,c);
c.gridx=1;
c.gridy=2;
jp1.add(jl2,c);
                                                           //adding new voter form.
jmi1.addActionListener(new ActionListener()
{
public void actionPerformed(ActionEvent e4)
{
final JFrame jf1=new JFrame();
final JPanel jp1=new JPanel();
JLabel jl1=new JLabel("Name :");
JLabel jl2=new JLabel("Father's Name :");
JLabel jl3=new JLabel("Sex :");
JLabel jl4=new JLabel("Address :");
JLabel jl5=new JLabel("Contact :");
JLabel jl6=new JLabel("Emailid :");
JLabel jl7=new JLabel("Voterid/UID no :");
JLabel jl8=new JLabel("Age on 01/01/2016");
final JTextField jt1=new JTextField();
final JTextField jt2=new JTextField();
final JTextField jt3=new JTextField();
final JTextField jt4=new JTextField();
final JTextField jt5=new JTextField();
final JTextField jtt6=new JTextField();
final JTextField jt7=new JTextField();
final JButton jb1=new JButton("Reset");
final JButton jb2=new JButton("Save");
/*final JButton jb3=new JButton("Browse");
ImageIcon icon=new ImageIcon();
JLabel  l =new JLabel(icon,JLabel.CENTER);*/
final JRadioButton b1=new JRadioButton("Male");
final JRadioButton b2=new JRadioButton("Female");
jf1.setLayout(new GridLayout(1,1,0,0));
jl1.setFont(new Font("NJ",Font.BOLD,20));
jl2.setFont(new Font("NJ",Font.BOLD,20));
jl3.setFont(new Font("NJ",Font.BOLD,20));
jl4.setFont(new Font("NJ",Font.BOLD,20));
jl5.setFont(new Font("NJ",Font.BOLD,20));
jl6.setFont(new Font("NJ",Font.BOLD,20));
jl7.setFont(new Font("NJ",Font.BOLD,20));
jl8.setFont(new Font("NJ",Font.BOLD,20));
//l.setBackground(Color.blue);
jb2.setBackground(Color.pink);
jb2.setForeground(Color.green);
jb1.setBackground(Color.red);
jb1.setForeground(Color.cyan);
jf1.add(jp1);
jp1.setBackground(Color.gray);
jp1.setLayout(new GridBagLayout());
GridBagConstraints c=new GridBagConstraints();
c.ipadx=100;
c.ipady=20;
c.gridx=0;
c.gridy=0;
jp1.add(jl1,c);
c.ipadx=500;
c.ipady=20;
c.gridx=1;
c.gridy=0;
jp1.add(jt1,c);
/*c.ipadx=200;
c.ipady=60;
c.gridx=2;
c.gridy=0;
jp1.add(l,c);*/
c.ipadx=100;
c.ipady=20;
c.gridx=0;
c.gridy=1;
jp1.add(jl2,c);
c.ipadx=500;
c.ipady=20;
c.gridx=1;
c.gridy=1;
jp1.add(jt2,c);
c.ipadx=100;
c.ipady=20;
c.gridx=0;
c.gridy=2;
jp1.add(jl4,c);
c.ipadx=500;
c.ipady=20;
c.gridx=1;
c.gridy=2;
jp1.add(jt3,c);
/*c.ipadx=50;
c.ipady=20;
c.gridx=3;
c.gridy=2;
jp1.add(jb3,c);*/
c.ipadx=50;
c.ipady=20;
c.gridx=0;
c.gridy=3;
jp1.add(jl3,c);
c.ipadx=30;
c.ipady=20;
c.gridx=1;
c.gridy=3;
jp1.add(b1,c);
c.ipadx=30;
c.ipady=20;
c.gridx=2;
c.gridy=3;
jp1.add(b2,c);
c.ipadx=100;
c.ipady=20;
c.gridx=0;
c.gridy=4;
jp1.add(jl5,c);
c.ipadx=500;
c.ipady=20;
c.gridx=1;
c.gridy=4;
jp1.add(jt4,c);
c.ipadx=100;
c.ipady=20;
c.gridx=0;
c.gridy=5;
jp1.add(jl6,c);
c.ipadx=500;
c.ipady=20;
c.gridx=1;
c.gridy=5;
jp1.add(jt5,c);
c.ipadx=100;
c.ipady=20;
c.gridx=0;
c.gridy=6;
jp1.add(jl7,c);
c.ipadx=500;
c.ipady=20;
c.gridx=1;
c.gridy=6;
jp1.add(jtt6,c);
c.ipadx=100;
c.ipady=20;
c.gridx=0;
c.gridy=7;
jp1.add(jl8,c);
c.ipadx=50;
c.ipady=20;
c.gridx=1;
c.gridy=7;
jp1.add(jt7,c);
c.ipady=20;
c.ipadx=50;
c.gridx=0;
c.gridy=8;
jp1.add(jb2,c);
c.ipady=20;
c.ipadx=50;
c.gridx=1;
c.gridy=8;
jp1.add(jb1,c);
ButtonGroup bg=new ButtonGroup();
bg.add(b1);
bg.add(b2);
/*jb3.addActionListener(new ActionListener()
{
public void actionPerformed(ActionEvent e)
{
JFileChooser jfc=new JFileChooser();
jfc.showOpenDialog(jp1);
}
});*/
jb1.addActionListener(new ActionListener()
{
public void actionPerformed(ActionEvent e11)
{
jt1.setText("");
jt2.setText("");
jt3.setText("");
jt4.setText("");
jt5.setText("");
jtt6.setText("");
jt7.setText("");
}
});
jb2.addActionListener(new ActionListener()
{
public void actionPerformed(ActionEvent e12)
{
JFrame jf1=new JFrame("UserId & Password");
JPanel jp1=new JPanel();
jp1.setBackground(Color.gray);
JLabel jl1=new JLabel(" Dear voter your UserID is :");
JLabel jl2=new JLabel(" and Password is :");
JButton jb1=new JButton("print");
JTextField jtt1=new JTextField();
JTextField jtt2=new JTextField();
jl1.setFont(new Font(" nj",Font.BOLD,20));
jl2.setFont(new Font(" nj",Font.BOLD,20));
jf1.setLayout(new GridLayout(1,1,0,0));
jp1.setLayout(new GridBagLayout());
GridBagConstraints c=new GridBagConstraints();
c.ipadx=60;
c.ipady=30;
c.gridx=1;
c.gridy=1;
jp1.add(jl1,c);
c.ipadx=300;
c.ipady=30;
c.gridx=2;
c.gridy=1;
jp1.add(jtt1,c);
c.ipadx=60;
c.ipady=30;
c.gridx=1;
c.gridy=2;
jp1.add(jl2,c);
c.ipadx=300;
c.ipady=30;
c.gridx=2;
c.gridy=2;
jp1.add(jtt2,c);
c.ipadx=60;
c.ipady=30;
c.gridx=2;
c.gridy=4;
Random rand=new Random();
int lrand=rand.nextInt(999999999);
jtt2.setText(String.valueOf(lrand));
jtt1.setText(jtt6.getText());
jp1.add(jb1,c);
jf1.add(jp1);
              String nm,fn,ad,ei,vu,pas,cn;
String sx=new String();
float ag;
nm=jt1.getText();
fn=jt2.getText();
ad=jt3.getText();
ei=jt5.getText();
vu=jtt6.getText();
pas=jtt2.getText();
ag=Float.parseFloat(jt7.getText());
cn=jt4.getText();
if(b1.isSelected())
sx="Male";
else if(b2.isSelected())
sx="Female";
try
{
Connection con=DriverManager.getConnection("jdbc:odbc:njdsn","nj","nityanand");
Statement st=con.createStatement();
int row=st.executeUpdate("insert into Voter values('"+nm+"','"+fn+"','"+sx+"','"+ad+"','"+cn+"','"+ei+"','"+vu+"','"+ag+"','"+pas+"')");
con.close();
}
catch(Exception ex)
{
}
              jb1.addActionListener(new ActionListener()
{
public void actionPerformed(ActionEvent e20)
{
PrinterJob pj=PrinterJob.getPrinterJob();
if(pj.printDialog())
{
try
{
pj.print();
}
catch(PrinterException ex)
{
System.out.println(ex);
}
}
}
});
jt1.setText("");
jt2.setText("");
jt3.setText("");
jt4.setText("");
jt5.setText("");
jtt6.setText("");
jt7.setText("");
jf1.setSize(400,400);
jf1.setVisible(true);
}
});
jf1.setVisible(true);
jf1.setSize(400,400);
}
});
                                                          //adding Edit Voter form.
jmi2.addActionListener(new ActionListener()
{
public void actionPerformed(ActionEvent e12)
{
JFrame jf1=new JFrame("Voter Login");
JPanel jp1=new JPanel();
jp1.setBackground(Color.gray);
JLabel jl1=new JLabel("Voter ID no :");
JLabel jl2=new JLabel("Password :");
final JTextField jt1=new JTextField();
final JPasswordField jt2=new JPasswordField();
jt2.setEchoChar('$');
JButton jb1=new JButton("Login");
JButton jb2=new JButton("Reset");
jl1.setFont(new Font(" nj",Font.BOLD,30));
jl2.setFont(new Font(" nj",Font.BOLD,30));
jb1.setFont(new Font(" nj",Font.BOLD,20));
jb2.setFont(new Font(" nj",Font.BOLD,20));
jb1.setBackground(Color.pink);
jb2.setBackground(Color.magenta);
jl1.setForeground(Color.blue);
jl2.setForeground(Color.blue);
jf1.setLayout(new GridLayout(1,1,0,0));
jf1.add(jp1);
jp1.setLayout(new GridBagLayout());
GridBagConstraints c=new GridBagConstraints();
c.gridx=1;
c.gridy=1;
c.ipadx=50;
c.ipady=10;
jp1.add(jl1,c);
c.gridx=2;
c.gridy=1;
c.ipadx=300;
c.ipady=20;
jp1.add(jt1,c);
c.gridx=1;
c.gridy=3;
c.ipadx=50;
c.ipady=20;
jp1.add(jl2,c);
c.gridx=2;
c.gridy=3;
c.ipadx=300;
c.ipady=20;
jp1.add(jt2,c);
c.gridx=1;
c.gridy=4;
c.ipadx=50;
c.ipady=20;
jp1.add(jb1,c);
c.gridx=2;
c.gridy=4;
c.ipadx=50;
c.ipady=20;
jp1.add(jb2,c);
		  
	final JFrame jf3=new JFrame();
final JButton jb31=new JButton("Reset Password");
final JLabel jl31=new JLabel("The password you entered is wrong");
jf3.setLayout(new GridBagLayout());
GridBagConstraints c3=new GridBagConstraints();
jf3.getContentPane().setBackground(Color.darkGray);
jb31.setBackground(Color.pink);
jl31.setForeground(Color.blue);
jl31.setFont(new Font(" nj",Font.BOLD,30));
jb31.setFont(new Font(" nj",Font.BOLD,20));
c3.ipadx=200;
c3.ipady=30;
c3.gridx=1;
c3.gridy=1;
jf3.add(jl31,c3);
c3.ipadx=50;
c3.ipady=30;
c3.gridx=1;
c3.gridy=2;
jf3.add(jb31,c3);
jl31.setFont(new Font("NJ",Font.BOLD,20));
jb31.addActionListener(new ActionListener()
{
public void actionPerformed(ActionEvent ee3)
{
final JFrame jf4=new JFrame("Reset Password");
JLabel jl41=new JLabel("User ID");
final JTextField jt41=new JTextField();
JButton jb41=new JButton("OK");
JButton jb42=new JButton("Reset");
jf4.setLayout(new GridBagLayout());
jf4.getContentPane().setBackground(Color.pink);
jb41.setBackground(Color.darkGray);
jb42.setBackground(Color.darkGray);
jl41.setForeground(Color.blue);
jb41.setForeground(Color.white);
jb42.setForeground(Color.white);
jl41.setFont(new Font(" nj",Font.BOLD,20));
jb41.setFont(new Font(" nj",Font.BOLD,20));
jb42.setFont(new Font(" nj",Font.BOLD,20));
GridBagConstraints cc=new GridBagConstraints();
cc.ipadx=50;
cc.ipady=20;
cc.gridx=0;
cc.gridy=1;
jf4.add(jl41,cc);
cc.ipadx=600;
cc.ipady=20;
cc.gridx=1;
cc.gridy=1;
jf4.add(jt41,cc);
cc.ipadx=50;
cc.ipady=20;
cc.gridx=1;
cc.gridy=2;
jf4.add(jb41,cc);
cc.ipadx=50;
cc.ipady=20;
cc.gridx=2;
cc.gridy=2;
jf4.add(jb42,cc);
jf4.setVisible(true);
jf4.setSize(900,900);
jb42.addActionListener(new ActionListener()
{
public void actionPerformed(ActionEvent ee22)
{
jt41.setText("");
}});
jb41.addActionListener(new ActionListener()
{
public void actionPerformed(ActionEvent ee22)
{
Random rand=new Random();
int lrand=rand.nextInt(999999999);
String id,pas;
int i=0;
pas=String.valueOf(lrand);
id=jt41.getText();
try
{
Connection con=DriverManager.getConnection("jdbc:odbc:njdsn","nj","nityanand");
Statement st=con.createStatement();
ResultSet rs=st.executeQuery("select * from Voter");
while(rs.next())
{
if(id.equals(rs.getString(7)))
{
int row=st.executeUpdate("update Voter set Password='"+pas+"' where V_UId='"+id+"' ");
JOptionPane.showMessageDialog(jf4,"Your new Password is"+pas);
break;
}
else
i=1;
}
if(i==1)
JOptionPane.showMessageDialog(jf4,"User ID Not Matched !");
con.close();
}
catch(Exception ex)
{
}
}});
}});
		final JFrame jf2=new JFrame("Edit Voter");
final JPanel jp11=new JPanel();
JLabel jl11=new JLabel("Name :");
JLabel jl12=new JLabel("Father's Name :");
JLabel jl13=new JLabel("Sex :");
JLabel jl14=new JLabel("Address :");
JLabel jl15=new JLabel("Contact :");
JLabel jl16=new JLabel("Emailid :");
JLabel jl17=new JLabel("Voterid/UID no :");
JLabel jl18=new JLabel("Age on 01/01/2016");
final JTextField jt11=new JTextField();
final JTextField jt12=new JTextField();
final JTextField jt13=new JTextField();
final JTextField jt14=new JTextField();
final JTextField jt15=new JTextField();
final JTextField jtt16=new JTextField();
final JTextField jt17=new JTextField();
final JButton jb12=new JButton("Save");
final JRadioButton b11=new JRadioButton("Male");
final JRadioButton b12=new JRadioButton("Female");
jf2.setLayout(new GridLayout(1,1,0,0));
jl11.setFont(new Font("NJ",Font.BOLD,20));
jl12.setFont(new Font("NJ",Font.BOLD,20));
jl13.setFont(new Font("NJ",Font.BOLD,20));
jl14.setFont(new Font("NJ",Font.BOLD,20));
jl15.setFont(new Font("NJ",Font.BOLD,20));
jl16.setFont(new Font("NJ",Font.BOLD,20));
jl17.setFont(new Font("NJ",Font.BOLD,20));
jl18.setFont(new Font("NJ",Font.BOLD,20));
jb12.setBackground(Color.pink);
jb12.setForeground(Color.green);
jf2.add(jp11);
jp11.setBackground(Color.gray);
jp11.setLayout(new GridBagLayout());
GridBagConstraints c1=new GridBagConstraints();
c1.ipadx=100;
c1.ipady=20;
c1.gridx=0;
c1.gridy=0;
jp11.add(jl11,c1);
c1.ipadx=500;
c1.ipady=20;
c1.gridx=1;
c1.gridy=0;
jp11.add(jt11,c1);
c1.ipadx=100;
c1.ipady=20;
c1.gridx=0;
c1.gridy=1;
jp11.add(jl12,c1);
c1.ipadx=500;
c1.ipady=20;
c1.gridx=1;
c1.gridy=1;
jp11.add(jt12,c1);
c1.ipadx=100;
c1.ipady=20;
c1.gridx=0;
c1.gridy=2;
jp11.add(jl14,c1);
c1.ipadx=500;
c1.ipady=20;
c1.gridx=1;
c1.gridy=2;
jp11.add(jt13,c1);
c1.ipadx=50;
c1.ipady=20;
c1.gridx=0;
c1.gridy=3;
jp11.add(jl13,c1);
c1.ipadx=30;
c1.ipady=20;
c1.gridx=1;
c1.gridy=3;
jp11.add(b11,c1);
c1.ipadx=30;
c1.ipady=20;
c1.gridx=2;
c1.gridy=3;
jp11.add(b12,c1);
c1.ipadx=100;
c1.ipady=20;
c1.gridx=0;
c1.gridy=4;
jp11.add(jl15,c1);
c1.ipadx=500;
c1.ipady=20;
c1.gridx=1;
c1.gridy=4;
jp11.add(jt14,c1);
c1.ipadx=100;
c1.ipady=20;
c1.gridx=0;
c1.gridy=5;
jp11.add(jl16,c1);
c1.ipadx=500;
c1.ipady=20;
c1.gridx=1;
c1.gridy=5;
jp11.add(jt15,c1);
c1.ipadx=100;
c1.ipady=20;
c1.gridx=0;
c1.gridy=6;
jp11.add(jl17,c1);
c1.ipadx=500;
c1.ipady=20;
c1.gridx=1;
c1.gridy=6;
jp11.add(jtt16,c1);
c1.ipadx=100;
c1.ipady=20;
c1.gridx=0;
c1.gridy=7;
jp11.add(jl18,c1);
c1.ipadx=50;
c1.ipady=20;
c1.gridx=1;
c1.gridy=7;
jp11.add(jt17,c1);
c1.ipady=20;
c1.ipadx=50;
c1.gridx=0;
c1.gridy=8;
jp11.add(jb12,c1);
ButtonGroup bg1=new ButtonGroup();
bg1.add(b11);
bg1.add(b12);
jb12.addActionListener(new ActionListener()
{
public void actionPerformed(ActionEvent e12)
{
                        String nm,fn,ad,ei,vu,pas,cn;
String sx=new String();
float ag;
nm=jt11.getText();
fn=jt12.getText();
ad=jt13.getText();
ei=jt15.getText();
vu=jtt16.getText();
ag=Float.parseFloat(jt17.getText());
cn=jt14.getText();
if(b11.isSelected())
sx="Male";
else if(b12.isSelected())
sx="Female";
try
{
Connection con9=DriverManager.getConnection("jdbc:odbc:njdsn","nj","nityanand");
Statement st9=con9.createStatement();
int row=st9.executeUpdate("UPDATE VOTER SET Name='"+nm+"',F_name='"+fn+"',Sex='"+sx+"',Address='"+ad+"',Contact='"+cn+"',Email_Id='"+ei+"',Age='"+ag+"' where V_UId='"+vu+"' ");
con9.close();
}
catch(Exception ex)
{
}
jt11.setText("");
jt12.setText("");
jt13.setText("");
jt14.setText("");
jt15.setText("");
jtt16.setText("");
jt17.setText("");
jf2.setVisible(false);
}
});
jb2.addActionListener(new ActionListener()
{
public void actionPerformed(ActionEvent e27)
{
jt1.setText("");
jt2.setText("");
}
});
jb1.addActionListener(new ActionListener()
{
public void actionPerformed(ActionEvent e)
{
try
{ 
String nm,fn,ad,ei,sx,pas,m,f,cn;
String vu=new String();
float ag;
String str1=new String();
String str2=new String();
str1=jt1.getText();
str2=jt2.getText();
m="Male";
f="Female";
int count=0;
Connection con1=DriverManager.getConnection("jdbc:odbc:oradsn","nj","nityanand");
Statement st1=con1.createStatement();
ResultSet rs=st1.executeQuery("select * from Voter");
while(rs.next())
{
nm=rs.getString(1);fn=rs.getString(2);sx=rs.getString(3);ad=rs.getString(4);cn=rs.getString(5);
ei=rs.getString(6);vu=rs.getString(7);ag=rs.getInt(8);pas=rs.getString(9);
if((str1.equals(vu))&&(str2.equals(pas)))
{
count=1;
jf2.setVisible(true);
jf2.setSize(1200,1200);
jt11.setText(nm);
jt12.setText(fn);
jt13.setText(ad);
if(sx.equalsIgnoreCase(m))
b11.setSelected(true);
if(sx.equalsIgnoreCase(f))
b12.setSelected(true);
jt14.setText(cn);
jt15.setText(ei);
jtt16.setText(vu);
jt17.setText(String.valueOf(ag));
break;
}
}
if(count!=1)
{
jf3.setVisible(true);
jf3.setSize(400,400);
}
con1.close();
}
catch(Exception ex)
{
}
jt1.setText("");
jt2.setText("");
}
});
jf1.setSize(400,400);
jf1.setVisible(true);
}
});
                                                      //Delete voter form.
jmi3.addActionListener(new ActionListener()
{
public void actionPerformed(ActionEvent e13)
{
final JFrame jf1=new JFrame("Voter Login");
JPanel jp1=new JPanel();
jp1.setBackground(Color.gray);
JLabel jl1=new JLabel("Voter ID no :");
JLabel jl2=new JLabel("Password :");
final JTextField jt1=new JTextField();
final JPasswordField jt2=new JPasswordField();
jt2.setEchoChar('$');
JButton jb1=new JButton("Login");
JButton jb2=new JButton("Reset");
jl1.setFont(new Font(" nj",Font.BOLD,30));
jl2.setFont(new Font(" nj",Font.BOLD,30));
jb1.setFont(new Font(" nj",Font.BOLD,20));
jb2.setFont(new Font(" nj",Font.BOLD,20));
jb1.setBackground(Color.pink);
jb2.setBackground(Color.green);
jl1.setForeground(Color.blue);
jl2.setForeground(Color.blue);
jf1.setLayout(new GridLayout(1,1,0,0));
jf1.add(jp1);
jp1.setLayout(new GridBagLayout());
GridBagConstraints c=new GridBagConstraints();
c.gridx=1;
c.gridy=1;
c.ipadx=50;
c.ipady=20;
jp1.add(jl1,c);
c.gridx=2;
c.gridy=1;
c.ipadx=300;
c.ipady=20;
jp1.add(jt1,c);
c.gridx=1;
c.gridy=3;
c.ipadx=50;
c.ipady=20;
jp1.add(jl2,c);
c.gridx=2;
c.gridy=3;
c.ipadx=300;
c.ipady=20;
jp1.add(jt2,c);
c.gridx=1;
c.gridy=4;
c.ipadx=50;
c.ipady=30;
jp1.add(jb1,c);
c.gridx=2;
c.gridy=4;
c.ipadx=50;
c.ipady=30;
jp1.add(jb2,c);
jb1.addActionListener(new ActionListener()
{
public void actionPerformed(ActionEvent ee2)
{
int i=0;
String str1=new String();
String str2=new String();
String id=new String();
String pas=new String();
try
{
str1=jt1.getText();
str2=jt2.getText();
Connection con1=DriverManager.getConnection("jdbc:odbc:oradsn","nj","nityanand");
Statement st1=con1.createStatement();
ResultSet rs=st1.executeQuery("select * from Voter");
while(rs.next())
{
id=rs.getString(7);
pas=rs.getString(9);
if((str1.equalsIgnoreCase(id))&&(str2.equalsIgnoreCase(pas)))
{
i=1;
int row=st1.executeUpdate("delete from Voter where V_UID='"+id+"' ");
jt2.setText("");
jt1.setText("");
JOptionPane.showMessageDialog(jf1,"Record Deleted Successfully");
break;
}
}
if(i!=1)
{
JOptionPane.showMessageDialog(jf1,"You Entered A Wrong User Id or Password");
jt2.setText("");
jt1.setText("");
}
con1.close();
}
catch(Exception exx)
{
}
}});
jb2.addActionListener(new ActionListener()
{
public void actionPerformed(ActionEvent e27)
{
jt1.setText("");
jt2.setText("");
}
});
jf1.setSize(400,400);
jf1.setVisible(true);
}
});
		//Search Voter
jmi31.addActionListener(new ActionListener()
{
public void actionPerformed(ActionEvent e28)
{
final JFrame jf1=new JFrame("Search Name In Voter List");
final JTextField jt1=new JTextField();
final JTextField jt2=new JTextField();
JLabel jl1=new JLabel("Name :");
JLabel jl2=new JLabel("Voter/U ID :");
JButton jb1=new JButton("Search");
JButton jb2=new JButton("Reset");
jf1.setLayout(new GridBagLayout());
GridBagConstraints c=new GridBagConstraints();
c.gridx=0;
c.gridy=1;
c.ipadx=50;
c.ipady=20;
jf1.add(jl1,c);
c.gridx=1;
c.gridy=1;
c.ipadx=300;
c.ipady=20;
jf1.add(jt1,c);
c.gridx=0;
c.gridy=2;
c.ipadx=50;
c.ipady=20;
jf1.add(jl2,c);
c.gridx=1;
c.gridy=2;
c.ipadx=300;
c.ipady=20;
jf1.add(jt2,c);
c.gridx=0;
c.gridy=4;
c.ipadx=50;
c.ipady=20;
jf1.add(jb1,c);
c.gridx=1;
c.gridy=4;
c.ipadx=50;
c.ipady=20;
jf1.add(jb2,c);
jl1.setForeground(Color.blue);
jl2.setForeground(Color.blue);
jb1.setBackground(Color.magenta);
jb2.setBackground(Color.cyan);
jl1.setFont(new Font(" nj",Font.BOLD,30));
jl2.setFont(new Font(" nj",Font.BOLD,30));
jb1.setFont(new Font(" nj",Font.BOLD,30));
jb2.setFont(new Font(" nj",Font.BOLD,30));
jf1.getContentPane().setBackground(Color.pink);
jb2.addActionListener(new ActionListener()
{
public void actionPerformed(ActionEvent e222)
{
jt1.setText("");
jt2.setText("");
}});
jb1.addActionListener(new ActionListener()
{
public void actionPerformed(ActionEvent e222)
{
int i=0;
String str1=new String();
String str2=new String();
String nm=new String();
String id=new String();
try
{
str1=jt1.getText();
str2=jt2.getText();
Connection con1=DriverManager.getConnection("jdbc:odbc:oradsn","nj","nityanand");
Statement st1=con1.createStatement();
ResultSet rs=st1.executeQuery("select * from Voter");
while(rs.next())
{
nm=rs.getString(1);
id=rs.getString(7);
if((str1.equalsIgnoreCase(nm))&&(str2.equalsIgnoreCase(id)))
{
i=1;
jt2.setText("");
jt1.setText("");
JOptionPane.showMessageDialog(jf1,"This name and Id Exist In Voter List ");
break;
}
}
if(i!=1)
{
JOptionPane.showMessageDialog(jf1,"Name and Id not Exist In Voter List");
jt1.setText("");
jt2.setText("");
}
con1.close();
}
catch(Exception exx)
{
}
}});
jf1.setVisible(true);
jf1.setSize(800,800);
}});
                                                     //adding new candidate form. 
jmi4.addActionListener(new ActionListener()
{
public void actionPerformed(ActionEvent e5)
{
JFrame jf1=new JFrame("Candidate");
final JPanel jp1=new JPanel();
final JTextField jtt1=new JTextField();
final JTextField jt2=new JTextField();
final JTextField jt3=new JTextField();
final JTextField jt4=new JTextField();
final JTextField jt5=new JTextField();
final JTextField jt6=new JTextField();
final JTextField jt7=new JTextField();
final JTextField jt8=new JTextField();
final JTextField jt9=new JTextField();
final JTextField jt10=new JTextField();
final JTextField jt11=new JTextField();
JLabel jl1=new JLabel("Candidate VoterID or UId no :");
JLabel jl2=new JLabel("Name :");   
JLabel jl3=new JLabel("Husband/Father's Name :");
JLabel jl4=new JLabel("Mother's Name :");
JLabel jl5=new JLabel("Sex :");
JLabel jl6=new JLabel("Current Asset :");      
JLabel jl7=new JLabel("Annual Income :");    
JLabel jl8=new JLabel("Age on 01/01/2016 :");
JLabel jl11=new JLabel("Address :");
JLabel jl12=new JLabel("Contact :");
JLabel jl13=new JLabel("Email ID :");
JLabel jl14=new JLabel("Party Name :");
final JRadioButton jr1=new JRadioButton("Male");
final JRadioButton jr2=new JRadioButton("Female");
JButton jb3=new JButton("Submit");
JButton jb4=new JButton("Reset");
jl1.setFont(new Font("NJ",Font.BOLD,30));
jl2.setFont(new Font("NJ",Font.BOLD,30));
jl3.setFont(new Font("NJ",Font.BOLD,30));
jl4.setFont(new Font("NJ",Font.BOLD,30));
jl5.setFont(new Font("NJ",Font.BOLD,30));
jl6.setFont(new Font("NJ",Font.BOLD,30));
jl7.setFont(new Font("NJ",Font.BOLD,30));
jl8.setFont(new Font("NJ",Font.BOLD,30));
jl11.setFont(new Font("NJ",Font.BOLD,30));
jl12.setFont(new Font("NJ",Font.BOLD,30));
jl13.setFont(new Font("NJ",Font.BOLD,30));
jl14.setFont(new Font("NJ",Font.BOLD,30));
jp1.setBackground(Color.lightGray);
jf1.setLayout(new GridLayout(1,1,0,0));
jf1.add(jp1);
jp1.setLayout(new GridBagLayout());
GridBagConstraints c=new GridBagConstraints();
c.ipadx=100;
c.ipady=10;
c.gridx=0;
c.gridy=0;
jp1.add(jl1,c);
c.ipadx=500;
c.ipady=10;
c.gridx=1;
c.gridy=0;
jp1.add(jtt1,c);
c.ipadx=100;
c.ipady=10;
c.gridx=0;
c.gridy=1;
jp1.add(jl2,c);
c.ipadx=500;
c.ipady=10;
c.gridx=1;
c.gridy=1;
jp1.add(jt2,c);
c.ipadx=100;
c.ipady=10;
c.gridx=0;
c.gridy=2;
jp1.add(jl3,c);
c.ipadx=500;
c.ipady=10;
c.gridx=1;
c.gridy=2;
jp1.add(jt3,c);
c.ipadx=100;
c.ipady=10;
c.gridx=0;
c.gridy=3;
jp1.add(jl4,c);
c.ipadx=500;
c.ipady=10;
c.gridx=1;
c.gridy=3;
jp1.add(jt4,c);
c.ipadx=100;
c.ipady=10;
c.gridx=0;
c.gridy=4;
jp1.add(jl6,c);
c.ipadx=500;
c.ipady=10;
c.gridx=1;
c.gridy=4;
jp1.add(jt5,c);
c.ipadx=100;
c.ipady=10;
c.gridx=0;
c.gridy=5;
jp1.add(jl5,c);
c.ipadx=50;
c.ipady=10;
c.gridx=1;
c.gridy=5;
jp1.add(jr1,c);
c.ipadx=50;
c.ipady=10;
c.gridx=2;
c.gridy=5;
jp1.add(jr2,c);
c.ipadx=100;
c.ipady=10;
c.gridx=0;
c.gridy=6;
jp1.add(jl7,c);
c.ipadx=500;
c.ipady=10;
c.gridx=1;
c.gridy=6;
jp1.add(jt6,c);
c.ipadx=100;
c.ipady=10;
c.gridx=0;
c.gridy=7;
jp1.add(jl8,c);
c.ipadx=50;
c.ipady=10;
c.gridx=1;
c.gridy=7;
jp1.add(jt7,c);
c.ipadx=100;
c.ipady=10;
c.gridx=0;
c.gridy=8;
jp1.add(jl11,c);
c.ipadx=500;
c.ipady=10;
c.gridx=1;
c.gridy=8;
jp1.add(jt8,c);
c.ipadx=100;
c.ipady=10;
c.gridx=0;
c.gridy=9;
jp1.add(jl12,c);
c.ipadx=500;
c.ipady=10;
c.gridx=1;
c.gridy=9;
jp1.add(jt9,c);
c.ipadx=100;
c.ipady=10;
c.gridx=0;
c.gridy=10;
jp1.add(jl13,c);
c.ipadx=500;
c.ipady=10;
c.gridx=1;
c.gridy=10;
jp1.add(jt10,c);
c.ipadx=100;
c.ipady=10;
c.gridx=0;
c.gridy=11;
jp1.add(jl14,c);
c.ipadx=500;
c.ipady=10;
c.gridx=1;
c.gridy=11;
jp1.add(jt11,c);
c.ipadx=50;
c.ipady=10;
c.gridx=0;
c.gridy=13;
jp1.add(jb3,c);
c.ipadx=50;
c.ipady=10;
c.gridx=1;
c.gridy=13;
jp1.add(jb4,c);
ButtonGroup bg=new ButtonGroup();
bg.add(jr1);
bg.add(jr2);
jb4.addActionListener(new ActionListener()
{
public void actionPerformed(ActionEvent e)
{
jtt1.setText("");
jt2.setText("");
jt3.setText("");
jt4.setText("");
jt5.setText("");
jt6.setText("");
jt7.setText("");
jt8.setText("");
jt9.setText("");
jt10.setText("");
jt11.setText("");
jr1.setSelected(false);
jr2.setSelected(false);
}
});
jb3.addActionListener(new ActionListener()
{
public void actionPerformed(ActionEvent e23)
{
JFrame jf1=new JFrame("Candidate UserId & Password");
JPanel jp1=new JPanel();
jp1.setBackground(Color.gray);
JLabel jl1=new JLabel(" Dear Candidate yuor UserID is :");
JLabel jl2=new JLabel(" and Password is :");
JButton jb1=new JButton("Print");
JTextField jt1=new JTextField();
JTextField jtt2=new JTextField();
jl1.setFont(new Font(" nj",Font.BOLD,20));
jl2.setFont(new Font(" nj",Font.BOLD,20));
jf1.setLayout(new GridLayout(1,1,0,0));
jp1.setLayout(new GridBagLayout());
GridBagConstraints c=new GridBagConstraints();
c.ipadx=60;
c.ipady=30;
c.gridx=1;
c.gridy=1;
jp1.add(jl1,c);
c.ipadx=300;
c.ipady=30;
c.gridx=2;
c.gridy=1;
jp1.add(jt1,c);
c.ipadx=60;
c.ipady=30;
c.gridx=1;
c.gridy=2;
jp1.add(jl2,c);
c.ipadx=300;
c.ipady=30;
c.gridx=2;
c.gridy=2;
jp1.add(jtt2,c);
c.ipadx=60;
c.ipady=30;
c.gridx=2;
c.gridy=4;
Random rand=new Random();
int lrand=rand.nextInt(999999999);
jtt2.setText(String.valueOf(lrand));
jt1.setText(jtt1.getText());
jp1.add(jb1,c);
jf1.add(jp1);
String vu,nm,hfn,mn,pas,ei,add,ar,cn;
String sx=new String();
float curr,ann,ag;
vu=jtt1.getText();
nm=jt2.getText();
hfn=jt3.getText();
mn=jt4.getText();
pas=jtt2.getText();
ei=jt10.getText();
add=jt8.getText();
ar=jt11.getText();
cn=jt9.getText();
curr=Float.parseFloat(jt5.getText());
ann=Float.parseFloat(jt6.getText());
ag=Float.parseFloat(jt7.getText());
if(jr1.isSelected())
sx="Male";
if(jr2.isSelected())
sx="Female";
try
{
Connection con=DriverManager.getConnection("jdbc:odbc:njdsn","nj","nityanand");
Statement st=con.createStatement();
int row=st.executeUpdate("insert into Candidate values('"+vu+"','"+nm+"','"+hfn+"','"+mn+"','"+curr+"','"+sx+"','"+ann+"','"+ag+"','"+pas+"','"+add+"','"+cn+"','"+ei+"','"+ar+"')");
con.close();
}
catch(Exception ex)
{
}
jtt1.setText("");
jt2.setText("");
jt3.setText("");
jt4.setText("");
jt5.setText("");
jt6.setText("");
jt7.setText("");
jt8.setText("");
jt9.setText("");
jt10.setText("");
jt11.setText("");
jr1.setSelected(false);
jr2.setSelected(false);
jb1.addActionListener(new ActionListener()
{
public void actionPerformed(ActionEvent e22)
{
PrinterJob pj=PrinterJob.getPrinterJob();
if(pj.printDialog())
{
try
{
pj.print();
}
catch(PrinterException ex)
{
System.out.println(ex);
}
}
}
});
jf1.setSize(400,400);
jf1.setVisible(true);
}
});
jf1.setSize(400,400);
jf1.setVisible(true);
}
});
                                             //Edit Candidate form.
jmi5.addActionListener(new ActionListener()
{
public void actionPerformed(ActionEvent e24)
{
JFrame jf2=new JFrame("Candidate Edit");
JPanel jp21=new JPanel();
jp21.setBackground(Color.gray);
JLabel jl21=new JLabel("Candidate ID no :");
JLabel jl22=new JLabel("Password :");
final JTextField jt21=new JTextField();
final JPasswordField jt22=new JPasswordField();
jt22.setEchoChar('$');
JButton jb21=new JButton("Login");
JButton jb22=new JButton("Reset");
jl21.setFont(new Font(" nj",Font.BOLD,30));
jl22.setFont(new Font(" nj",Font.BOLD,30));
jb21.setFont(new Font(" nj",Font.BOLD,20));
jb22.setFont(new Font(" nj",Font.BOLD,20));
jb21.setBackground(Color.green);
jb22.setBackground(Color.red);
jl21.setForeground(Color.blue);
jl22.setForeground(Color.blue);
jf2.setLayout(new GridLayout(1,1,0,0));
jf2.add(jp21);
jp21.setLayout(new GridBagLayout());
GridBagConstraints c1=new GridBagConstraints();
c1.gridx=1;
c1.gridy=1;
c1.ipadx=50;
c1.ipady=30;
jp21.add(jl21,c1);
c1.gridx=2;
c1.gridy=1;
c1.ipadx=300;
c1.ipady=30;
jp21.add(jt21,c1);
c1.gridx=1;
c1.gridy=3;
c1.ipadx=50;
c1.ipady=30;
jp21.add(jl22,c1);
c1.gridx=2;
c1.gridy=3;
c1.ipadx=300;
c1.ipady=30;
jp21.add(jt22,c1);
c1.gridx=1;
c1.gridy=4;
c1.ipadx=50;
c1.ipady=30;
jp21.add(jb21,c1);
c1.gridx=2;
c1.gridy=4;
c1.ipadx=50;
c1.ipady=30;
jp21.add(jb22,c1);

final JFrame jf3=new JFrame();
final JButton jb31=new JButton("Reset Password");
final JLabel jl31=new JLabel("The password you entered is wrong");
jf3.setLayout(new GridBagLayout());
GridBagConstraints c3=new GridBagConstraints();
c3.ipadx=200;
c3.ipady=30;
c3.gridx=1;
c3.gridy=1;
jf3.add(jl31,c3);
c3.ipadx=50;
c3.ipady=30;
c3.gridx=1;
c3.gridy=2;
jf3.add(jb31,c3);
jl31.setFont(new Font("NJ",Font.BOLD,20));
jb31.addActionListener(new ActionListener()
{
public void actionPerformed(ActionEvent ee3)
{
final JFrame jf4=new JFrame("Reset Password");
JLabel jl41=new JLabel("User ID");
final JTextField jt41=new JTextField();
JButton jb41=new JButton("OK");
JButton jb42=new JButton("Reset");
jf4.setLayout(new GridBagLayout());
GridBagConstraints cc=new GridBagConstraints();
cc.ipadx=50;
cc.ipady=20;
cc.gridx=0;
cc.gridy=1;
jf4.add(jl41,cc);
cc.ipadx=600;
cc.ipady=20;
cc.gridx=1;
cc.gridy=1;
jf4.add(jt41,cc);
cc.ipadx=50;
cc.ipady=20;
cc.gridx=1;
cc.gridy=2;
jf4.add(jb41,cc);
cc.ipadx=50;
cc.ipady=20;
cc.gridx=2;
cc.gridy=2;
jf4.add(jb42,cc);
jf4.setVisible(true);
jf4.setSize(900,900);
jb42.addActionListener(new ActionListener()
{
public void actionPerformed(ActionEvent ee23)
{
jt41.setText("");
}});
jb41.addActionListener(new ActionListener()
{
public void actionPerformed(ActionEvent ee22)
{
Random rand=new Random();
int lrand=rand.nextInt(999999999);
String id,pas;
int i=0;
pas=String.valueOf(lrand);
id=jt41.getText();
try
{
Connection con=DriverManager.getConnection("jdbc:odbc:njdsn","nj","nityanand");
Statement st=con.createStatement();
ResultSet rs=st.executeQuery("select * from Candidate");
while(rs.next())
{
if(id.equals(rs.getString(1)))
{
i=1;
int row=st.executeUpdate("update candidate set Password='"+pas+"' where V_UId='"+id+"' ");
JOptionPane.showMessageDialog(jf4,"Your new Password is"+pas);
jt41.setText("");
break;
}
}
if(i!=1)
{
JOptionPane.showMessageDialog(jf4,"User ID Not Matched");
jt41.setText("");
}
con.close();
}
catch(Exception ex)
{
}
}});
}});
	final JFrame jf1=new JFrame("Edit Candidate");
final JPanel jp1=new JPanel();
final JTextField jtt1=new JTextField();
final JTextField jt2=new JTextField();
final JTextField jt3=new JTextField();
final JTextField jt4=new JTextField();
final JTextField jt5=new JTextField();
final JTextField jt6=new JTextField();
final JTextField jt7=new JTextField();
final JTextField jt8=new JTextField();
final JTextField jt9=new JTextField();
final JTextField jt10=new JTextField();
final JTextField jt11=new JTextField();
JLabel jl1=new JLabel("Candidate VoterID or UId no :");
JLabel jl2=new JLabel("Name :");   
JLabel jl3=new JLabel("Husband/Father's Name :");
JLabel jl4=new JLabel("Mother's Name :");
JLabel jl5=new JLabel("Sex :");
JLabel jl6=new JLabel("Current Asset :");      
JLabel jl7=new JLabel("Annual Income :");    
JLabel jl8=new JLabel("Age on 01/01/2016 :");
JLabel jl11=new JLabel("Address :");
JLabel jl12=new JLabel("Contact :");
JLabel jl13=new JLabel("Email ID :");
JLabel jl14=new JLabel("Party Name :");
final JRadioButton jr1=new JRadioButton("Male");
final JRadioButton jr2=new JRadioButton("Female");
JButton jb3=new JButton("Submit");
jl1.setFont(new Font("NJ",Font.BOLD,30));
jl2.setFont(new Font("NJ",Font.BOLD,30));
jl3.setFont(new Font("NJ",Font.BOLD,30));
jl4.setFont(new Font("NJ",Font.BOLD,30));
jl5.setFont(new Font("NJ",Font.BOLD,30));
jl6.setFont(new Font("NJ",Font.BOLD,30));
jl7.setFont(new Font("NJ",Font.BOLD,30));
jl8.setFont(new Font("NJ",Font.BOLD,30));
jl11.setFont(new Font("NJ",Font.BOLD,30));
jl12.setFont(new Font("NJ",Font.BOLD,30));
jl13.setFont(new Font("NJ",Font.BOLD,30));
jl14.setFont(new Font("NJ",Font.BOLD,30));
jp1.setBackground(Color.lightGray);
jf1.setLayout(new GridLayout(1,1,0,0));
jf1.add(jp1);
jp1.setLayout(new GridBagLayout());
GridBagConstraints c=new GridBagConstraints();
c.ipadx=100;
c.ipady=10;
c.gridx=0;
c.gridy=0;
jp1.add(jl1,c);
c.ipadx=500;
c.ipady=10;
c.gridx=1;
c.gridy=0;
jp1.add(jtt1,c);
c.ipadx=100;
c.ipady=10;
c.gridx=0;
c.gridy=1;
jp1.add(jl2,c);
c.ipadx=500;
c.ipady=10;
c.gridx=1;
c.gridy=1;
jp1.add(jt2,c);
c.ipadx=100;
c.ipady=10;
c.gridx=0;
c.gridy=2;
jp1.add(jl3,c);
c.ipadx=500;
c.ipady=10;
c.gridx=1;
c.gridy=2;
jp1.add(jt3,c);
c.ipadx=100;
c.ipady=10;
c.gridx=0;
c.gridy=3;
jp1.add(jl4,c);
c.ipadx=500;
c.ipady=10;
c.gridx=1;
c.gridy=3;
jp1.add(jt4,c);
c.ipadx=100;
c.ipady=10;
c.gridx=0;
c.gridy=4;
jp1.add(jl6,c);
c.ipadx=500;
c.ipady=10;
c.gridx=1;
c.gridy=4;
jp1.add(jt5,c);
c.ipadx=100;
c.ipady=10;
c.gridx=0;
c.gridy=5;
jp1.add(jl5,c);
c.ipadx=50;
c.ipady=10;
c.gridx=1;
c.gridy=5;
jp1.add(jr1,c);
c.ipadx=50;
c.ipady=10;
c.gridx=2;
c.gridy=5;
jp1.add(jr2,c);
c.ipadx=100;
c.ipady=10;
c.gridx=0;
c.gridy=6;
jp1.add(jl7,c);
c.ipadx=500;
c.ipady=10;
c.gridx=1;
c.gridy=6;
jp1.add(jt6,c);
c.ipadx=100;
c.ipady=10;
c.gridx=0;
c.gridy=7;
jp1.add(jl8,c);
c.ipadx=50;
c.ipady=10;
c.gridx=1;
c.gridy=7;
jp1.add(jt7,c);
c.ipadx=100;
c.ipady=10;
c.gridx=0;
c.gridy=8;
jp1.add(jl11,c);
c.ipadx=500;
c.ipady=10;
c.gridx=1;
c.gridy=8;
jp1.add(jt8,c);
c.ipadx=100;
c.ipady=10;
c.gridx=0;
c.gridy=9;
jp1.add(jl12,c);
c.ipadx=500;
c.ipady=10;
c.gridx=1;
c.gridy=9;
jp1.add(jt9,c);
c.ipadx=100;
c.ipady=10;
c.gridx=0;
c.gridy=10;
jp1.add(jl13,c);
c.ipadx=500;
c.ipady=10;
c.gridx=1;
c.gridy=10;
jp1.add(jt10,c);
c.ipadx=100;
c.ipady=10;
c.gridx=0;
c.gridy=11;
jp1.add(jl14,c);
c.ipadx=500;
c.ipady=10;
c.gridx=1;
c.gridy=11;
jp1.add(jt11,c);
c.ipadx=50;
c.ipady=10;
c.gridx=0;
c.gridy=13;
jp1.add(jb3,c);
ButtonGroup bg=new ButtonGroup();
bg.add(jr1);
bg.add(jr2);
jb3.addActionListener(new ActionListener()
{
public void actionPerformed(ActionEvent e23)
{
String vu,nm,hfn,mn,ei,add,pr,cn;
String sx=new String();
float ag;
double curr,ann;
vu=jtt1.getText();
nm=jt2.getText();
hfn=jt3.getText();
mn=jt4.getText();
ei=jt10.getText();
add=jt8.getText();
pr=jt11.getText();
cn=jt9.getText();
curr=Float.parseFloat(jt5.getText());
ann=Float.parseFloat(jt6.getText());
ag=Float.parseFloat(jt7.getText());
if(jr1.isSelected())
sx="Male";
if(jr2.isSelected())
sx="Female";
try
{
Connection con=DriverManager.getConnection("jdbc:odbc:njdsn","nj","nityanand");
Statement st=con.createStatement();
int row=st.executeUpdate("update Candidate set Name='"+nm+"',HF_Name='"+hfn+"',M_Name='"+mn+"',Curr_Asst='"+curr+"',Sex='"+sx+"',Ann_Inc='"+ann+"',Age='"+ag+"',Adds='"+add+"',Contact='"+cn+"',Email='"+ei+"',Party='"+pr+"' where V_UId='"+vu+"' ");
con.close();
}
catch(Exception ex)
{
}
jf1.setVisible(false);
}
});
jb21.addActionListener(new ActionListener()
{
public void actionPerformed(ActionEvent e27)
{
try
{
int cou=0;
String vu,pas,nm,hfn,mn,sx,ad,ei,pr,cn;
double ca,ai;
float ag;
String m,f;
m="Male";
f="Female";
String str1,str2; 
str1=jt21.getText();
str2=jt22.getText();
Connection con1=DriverManager.getConnection("jdbc:odbc:oradsn","nj","nityanand");
Statement st1=con1.createStatement();
ResultSet rs=st1.executeQuery("select * from Candidate");
while(rs.next())
{
vu=rs.getString(1);
nm=rs.getString(2);
hfn=rs.getString(3);
mn=rs.getString(4);
ca=rs.getInt(5);
sx=rs.getString(6);
ai=rs.getInt(7);
ag=rs.getInt(8);
pas=rs.getString(9);
ad=rs.getString(10);
cn=rs.getString(11);
ei=rs.getString(12);
pr=rs.getString(13);
if((str1.equals(vu))&&(str2.equals(pas)))
{
cou=1;
jf1.setVisible(true);
jf1.setSize(900,900);
jtt1.setText(vu);jt2.setText(nm);jt3.setText(hfn);jt4.setText(mn);
jt5.setText(String.valueOf(ca));jt6.setText(String.valueOf(ai));
jt7.setText(String.valueOf(ag));jt8.setText(ad);jt9.setText(cn);
jt10.setText(ei);jt11.setText(pr);
if(sx.equalsIgnoreCase(m))
jr1.setSelected(true);
if(sx.equalsIgnoreCase(f))
jr2.setSelected(true);
break;
}
}
con1.close();
if(cou!=1)
{
jf3.setVisible(true);
jf3.setSize(900,900);
}
}
catch(Exception exe)
{
}
jt21.setText("");
jt22.setText("");
}});
jb22.addActionListener(new ActionListener()
{
public void actionPerformed(ActionEvent e27)
{
jt21.setText("");
jt22.setText("");
}
});
jf2.setSize(400,400);
jf2.setVisible(true);
}
});
                                                 //Candidate Delete Form.
jmi6.addActionListener(new ActionListener()
{
public void actionPerformed(ActionEvent e25)
{
final JFrame jf1=new JFrame("Candidate Delete");
JPanel jp1=new JPanel();
jp1.setBackground(Color.gray);
JLabel jl1=new JLabel("Candidate ID no :");
JLabel jl2=new JLabel("Password :");
final JTextField jt1=new JTextField();
final JPasswordField jt2=new JPasswordField();
jt2.setEchoChar('$');
JButton jb1=new JButton("Login");
JButton jb2=new JButton("Reset");
jl1.setFont(new Font(" nj",Font.BOLD,30));
jl2.setFont(new Font(" nj",Font.BOLD,30));
jb1.setFont(new Font(" nj",Font.BOLD,20));
jb2.setFont(new Font(" nj",Font.BOLD,20));
jb1.setBackground(Color.pink);
jb2.setBackground(Color.cyan);
jl1.setForeground(Color.blue);
jl2.setForeground(Color.blue);
jf1.setLayout(new GridLayout(1,1,0,0));
jf1.add(jp1);
jp1.setLayout(new GridBagLayout());
GridBagConstraints c=new GridBagConstraints();
c.gridx=1;
c.gridy=1;
c.ipadx=50;
c.ipady=20;
jp1.add(jl1,c);
c.gridx=2;
c.gridy=1;
c.ipadx=300;
c.ipady=20;
jp1.add(jt1,c);
c.gridx=1;
c.gridy=3;
c.ipadx=50;
c.ipady=20;
jp1.add(jl2,c);
c.gridx=2;
c.gridy=3;
c.ipadx=300;
c.ipady=20;
jp1.add(jt2,c);
c.gridx=1;
c.gridy=4;
c.ipadx=50;
c.ipady=30;
jp1.add(jb1,c);
c.gridx=2;
c.gridy=4;
c.ipadx=50;
c.ipady=30;
jp1.add(jb2,c);
jb1.addActionListener(new ActionListener()
{
public void actionPerformed(ActionEvent e26)
{
String str1=new String();
String str2=new String();
String id=new String();
String pas=new String();
int i=0;
try
{
str1=jt1.getText();
str2=jt2.getText();
Connection con1=DriverManager.getConnection("jdbc:odbc:oradsn","nj","nityanand");
Statement st1=con1.createStatement();
ResultSet rs=st1.executeQuery("select * from Candidate");
while(rs.next())
{
id=rs.getString(1);
pas=rs.getString(9);
if((str1.equals(id))&&(str2.equals(pas)))
{
int row=st1.executeUpdate("delete from Candidate where V_UID='"+id+"' ");
jt2.setText("");
JOptionPane.showMessageDialog(jf1,"Candidate's Records Successfully deleted");
jt1.setText("");
break;
}
else
{
i=1;
jt2.setText("");
jt1.setText("");
}
}
if(i==1)
JOptionPane.showMessageDialog(jf1,"Candidate's User ID or Password Not Matched");
con1.close();
}
catch(Exception exx)
{
}

}});
jb2.addActionListener(new ActionListener()
{
public void actionPerformed(ActionEvent e26)
{
jt1.setText("");
jt2.setText("");
}
});
jf1.setSize(400,400);
jf1.setVisible(true);
}
});
                                  //adding voter login form for casting vote.
jmi7.addActionListener(new ActionListener()
{
public void actionPerformed(ActionEvent e6)
{
final JFrame jf2=new JFrame("Voter Login");
JPanel jp21=new JPanel();
jp21.setBackground(Color.gray);
JLabel jl21=new JLabel("Voter ID no :");
JLabel jl22=new JLabel("Password :");
 final JTextField jt21=new JTextField();
final JPasswordField jt22=new JPasswordField();
jt22.setEchoChar('$');
final JButton jb21=new JButton("Login");
final JButton jb22=new JButton("Reset");
jl21.setFont(new Font(" nj",Font.BOLD,30));
jl22.setFont(new Font(" nj",Font.BOLD,30));
jb21.setFont(new Font(" nj",Font.BOLD,20));
jb22.setFont(new Font(" nj",Font.BOLD,20));
jb21.setBackground(Color.pink);
jb22.setBackground(Color.red);
jl21.setForeground(Color.blue);
jl22.setForeground(Color.blue);
jf2.setLayout(new GridLayout(1,1,0,0));
jf2.add(jp21);
jp21.setLayout(new GridBagLayout());
GridBagConstraints c1=new GridBagConstraints();
c1.gridx=1;
c1.gridy=1;
c1.ipadx=50;
c1.ipady=30;
jp21.add(jl21,c1);
c1.gridx=2;
c1.gridy=1;
c1.ipadx=300;
c1.ipady=30;
jp21.add(jt21,c1);
c1.gridx=1;
c1.gridy=3;
c1.ipadx=50;
c1.ipady=30;
jp21.add(jl22,c1);
c1.gridx=2;
c1.gridy=3;
c1.ipadx=300;
c1.ipady=30;
jp21.add(jt22,c1);
c1.gridx=1;
c1.gridy=4;
c1.ipadx=50;
c1.ipady=30;
jp21.add(jb21,c1);
c1.gridx=2;
c1.gridy=4;
c1.ipadx=50;
c1.ipady=30;
jp21.add(jb22,c1);
jb22.addActionListener(new ActionListener()
{
public void actionPerformed(ActionEvent e7)
{
jt21.setText("");
jt22.setText("");
}
});
                              //adding voting form
final JFrame jf1=new JFrame("Caste Your Vote");
JPanel jp1=new JPanel();
JPanel jp2=new JPanel();
jp1.setBackground(Color.gray);
jp2.setBackground(Color.darkGray);
final JRadioButton jr[]=new JRadioButton [10];
for(int i=0;i<10;i++)
jr[i]=new JRadioButton(" ");
final JLabel jl[]=new JLabel [10];
for(int i=0;i<10;i++)
{
jl[i]=new JLabel();
jl[i].setForeground(Color.blue);
jl[i].setFont(new Font("nj",Font.BOLD,20));
}
JButton jb1=new JButton("submit");
jf1.setLayout(new BorderLayout());
jf1.add(jp1,BorderLayout.CENTER);
jf1.add(jp2,BorderLayout.SOUTH);
jp1.setLayout(new GridBagLayout());
GridBagConstraints c=new GridBagConstraints();
c.gridx=0;
c.gridy=0;
c.ipadx=100;
c.ipady=30;
jp1.add(jr[0],c);
c.gridx=2;
c.gridy=0;
c.ipadx=100;
c.ipady=30;
jp1.add(jl[0],c);
c.gridx=0;
c.gridy=1;
c.ipadx=100;
c.ipady=30;
jp1.add(jr[1],c);
c.gridx=2;
c.gridy=1;
c.ipadx=100;
c.ipady=30;
jp1.add(jl[1],c);
c.gridx=0;
c.gridy=2;
c.ipadx=100;
c.ipady=30;
jp1.add(jr[2],c);
c.gridx=2;
c.gridy=2;
c.ipadx=100;
c.ipady=30;
jp1.add(jl[2],c);
c.gridx=0;
c.gridy=3;
c.ipadx=100;
c.ipady=30;
jp1.add(jr[3],c);
c.gridx=2;
c.gridy=3;
c.ipadx=100;
c.ipady=30;
jp1.add(jl[3],c);
c.gridx=0;
c.gridy=4;
c.ipadx=100;
c.ipady=30;
jp1.add(jr[4],c);
c.gridx=2;
c.gridy=4;
c.ipadx=100;
c.ipady=30;
jp1.add(jl[4],c);
c.gridx=0;
c.gridy=5;
c.ipadx=100;
c.ipady=30;
jp1.add(jr[5],c);
c.gridx=2;
c.gridy=5;
c.ipadx=100;
c.ipady=30;
jp1.add(jl[5],c);
c.gridx=0;
c.gridy=6;
c.ipadx=100;
c.ipady=30;
jp1.add(jr[6],c);
c.gridx=2;
c.gridy=6;
c.ipadx=100;
c.ipady=30;
jp1.add(jl[6],c);
c.gridx=0;
c.gridy=7;
c.ipadx=100;
c.ipady=30;
jp1.add(jr[7],c);
c.gridx=2;
c.gridy=7;
c.ipadx=100;
c.ipady=30;
jp1.add(jl[7],c);
c.gridx=0;
c.gridy=8;
c.ipadx=100;
c.ipady=30;
jp1.add(jr[8],c);
c.gridx=2;
c.gridy=8;
c.ipadx=100;
c.ipady=30;
jp1.add(jl[8],c);
c.gridx=0;
c.gridy=9;
c.ipadx=100;
c.ipady=30;
jp1.add(jr[9],c);
c.gridx=2;
c.gridy=9;
c.ipadx=100;
c.ipady=30;
jp1.add(jl[9],c);
jp2.add(jb1);
ButtonGroup bg=new ButtonGroup();
for(int j=0;j<10;j++)
bg.add(jr[j]);
int k=0;
String nm,pn;
try
{
Connection con=DriverManager.getConnection("jdbc:odbc:oradsn","nj","nityanand");
Statement st=con.createStatement();
ResultSet rs=st.executeQuery("select * from candidate");
while(rs.next())
{
nm=rs.getString(2);
pn=rs.getString(13);
jr[k].setText(nm);
jl[k].setText(pn);
k=k+1;
}
con.close();
}
catch(Exception exxx)
{
}
String str;
str=" ";
for(int i=0;i<10;i++)
{
if(str.equals(jr[i].getText()))
jr[i].setVisible(false);
}
jb21.addActionListener(new ActionListener()
{
public void actionPerformed(ActionEvent e8)
{
try
{
int flag=0;
int flag1=0;
String id,pas,id1,pas1,id2,pas2;
id=jt21.getText();
pas=jt22.getText();
Connection con1=DriverManager.getConnection("jdbc:odbc:oradsn","nj","nityanand");
Statement st1=con1.createStatement();
ResultSet rs2=st1.executeQuery("select * from Log_In");
while(rs2.next())
{
id2=rs2.getString(1);
pas2=rs2.getString(2);
if((id.equals(id2))&&(pas.equals(pas2)))
{
flag1=1;
break;
}
}
ResultSet rs1=st1.executeQuery("select * from Voter");
while(rs1.next())
{
id1=rs1.getString(7);
pas1=rs1.getString(9);
if((id.equals(id1))&&(pas.equals(pas1)))
{
flag=1;
break;
}
}
if(flag==0)
JOptionPane.showMessageDialog(jf2,"You Entered A Wrong User Id or Password");
else if((flag==1)&&(flag1!=1))
{
jf1.setSize(400,400);
jf1.setVisible(true);
int row=st1.executeUpdate("insert into Log_in values('"+id+"','"+pas+"')");
flag=0;
flag1=0;
}
else if(flag1==1)
JOptionPane.showMessageDialog(jf2,"Sorry! You alredy casted your Vote");
con1.close();
}
catch(Exception exx)
{
}
jt21.setText("");
jt22.setText("");
}
});
jb1.addActionListener(new ActionListener()
{
public void actionPerformed(ActionEvent e22)
{
String nm,pr;
try 
{
Connection con2=DriverManager.getConnection("jdbc:odbc:oradsn","nj","nityanand");
Statement st2=con2.createStatement();
for(int i=0;i<10;i++)
{
if(jr[i].isSelected())
{
String ids=new String();
nm=jr[i].getText();
pr=jl[i].getText();
ResultSet rs1=st2.executeQuery("select V_UId from Candidate where Name='"+nm+"' AND Party='"+pr+"' ");
while(rs1.next())
{
ids=rs1.getString("V_UID");
}
int row1=st2.executeUpdate("insert into Vote values('"+nm+"','"+ids+"','"+pr+"')");
}
}
}
catch(Exception exx1)
{
}
for(int i=0;i<10;i++)
jr[i].setSelected(false);
jf1.setVisible(false);
}});
jf2.setSize(400,400);
jf2.setVisible(true);
}});
                        //adding winner form on result menu.
jmi8.addActionListener(new ActionListener()
{
public void actionPerformed(ActionEvent e9)
{
JFrame jf1=new JFrame("WINNER");
try
{
Connection con=DriverManager.getConnection("jdbc:odbc:oradsn","nj","nityanand");
Statement st=con.createStatement();
JPanel jp1=new JPanel();
JLabel jl1=new JLabel("Congratulations!");
jl1.setForeground(Color.blue);
jl1.setFont(new Font("nj",Font.BOLD,30));
jp1.setBackground(Color.pink);
jf1.setLayout(new GridLayout(1,1,0,0));
jf1.add(jp1);
jp1.setLayout(new FlowLayout());
jp1.add(jl1);
String nm,pr;
int mx;
ResultSet rs=st.executeQuery("select Name,Party_Name,No_Votes from Winner where No_Votes=(select max(NO_Votes) from Winner)");
while(rs.next())
{
nm=rs.getString("Name");
pr=rs.getString("Party_Name");
mx=rs.getInt("No_Votes");
jl1.setText("Congratulation!   "+nm+"   from Party  "+pr+" is Winner & gets "+mx+"  votes  !");
}
con.close();
}
catch(Exception exx1)
{
}
jf1.setSize(400,400);
jf1.setVisible(true);
}
});
                           //adding candidate wise vote form on result menu.
jmi9.addActionListener(new ActionListener()
{
public void actionPerformed(ActionEvent e10)
{
JFrame jf1=new JFrame("Candidate wise Vote");
JPanel jp1=new JPanel();
JLabel jl1[]=new JLabel[10];
JLabel jl2[]=new JLabel[10];
JLabel jl3[]=new JLabel[10];
for(int i=0;i<10;i++)
{
jl1[i]=new JLabel();
jl2[i]=new JLabel();
jl3[i]=new JLabel(); 
jl1[i].setForeground(Color.blue);
jl1[i].setFont(new Font("nj",Font.BOLD,40));
jl2[i].setForeground(Color.red);
jl2[i].setFont(new Font("nj",Font.BOLD,40));
jl3[i].setForeground(Color.magenta);
jl3[i].setFont(new Font("nj",Font.BOLD,40));
}
jp1.setLayout(new GridLayout(10,3,5,10));
for(int i=0;i<10;i++)
{
jp1.add(jl1[i]);
jp1.add(jl2[i]);
jp1.add(jl3[i]);
}
jp1.setBackground(Color.pink);
jf1.setLayout(new GridLayout(1,1,0,0));
jf1.add(jp1);
try
{
String str[]=new String[10];
String str1[]=new String[10];
int i=0;
Connection con=DriverManager.getConnection("jdbc:odbc:oradsn","nj","nityanand");
Statement st=con.createStatement();
ResultSet rs=st.executeQuery("select DISTINCT(Name),(Party_Name) from Vote order by Name ASC");
while(rs.next())
{
str[i]=rs.getString("Name");
str1[i]=rs.getString("Party_Name");
jl1[i].setText(str[i]);
jl2[i].setText(str1[i]);
i=i+1;
}
i=0;
String str2[]=new String[10];
ResultSet rs1=st.executeQuery("select count(ID) AS vo from Vote group by Name order by Name ASC");
while(rs1.next())
{
str2[i]=String.valueOf(rs1.getInt("vo"));
jl3[i].setText( str2[i]);
i++;
}
int row1=st.executeUpdate("delete from Winner");
for(i=0;i<10;i++)
{
if(str[i]!=null&&str1[i]!=null&&str2[i]!=null)
{
int row=st.executeUpdate("insert into Winner values('"+str[i]+"','"+str1[i]+"','"+str2[i]+"')");
}
else
break;
}
con.close();
}
catch(Exception ex1)
{
}
jf1.setSize(400,400);
jf1.setVisible(true);
}
});
jf1.setVisible(true);
jf1.setSize(400,400);
jf1.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
}
}
});
jf1.setVisible(true);
jf1.setSize(400,400);
jf1.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
}
public static void main(String arg[]) throws Exception
{
myproject0 p=new myproject0();
}
}
