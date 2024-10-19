import java.awt.*;

import java.awt.event.*;



class Stupanel extends Panel implements ActionListener,ItemListener

{

String s1,s2,s3;

TextField t3,t4,t5,t6,t7;

Button tot,avg;

Checkbox c1,c2,c3,c4,m,f;

CheckboxGroup cbg;

Panel p1,p2,p3,p4;

public Stupanel()

{

s3=" ";

tot=new Button("Total");

avg=new Button("Average");

c1=new Checkbox("CSE",true);

c2=new Checkbox("ECE");

c3=new Checkbox("IT");

c4=new Checkbox("EEE");

cbg=new CheckboxGroup();

m=new Checkbox("Male",cbg,false);

f=new Checkbox("Female",cbg,true);

p1=new Panel();

p1.setLayout(new GridLayout(2,2));

p1.add(new Label("Student Number "));

p1.add(new TextField(5));

p1.add(new Label("Student Name "));

p1.add(new TextField(15));

add(p1);

p2=new Panel();

p2.setLayout(new GridLayout(1,3));

p2.add(new Label("Gender"));

p2.add(m);

p2.add(f);

add(p2);

p3=new Panel();

p3.setLayout(new GridLayout(1,5));

p3.add(new Label("Degree"));

p3.add(c1); p3.add(c2); p3.add(c3); p3.add(c4);

add(p3);

p4=new Panel();

p4.setLayout(new GridLayout(6,2));

p4.add(new Label("Marks in OOPS"));

t3=new TextField(3); p4.add(t3);

p4.add(new Label("Marks in DS"));

t4=new TextField(3); p4.add(t4);

p4.add(new Label("Marks In DM"));

t5=new TextField(3); p4.add(t5);



p4.add(new Label("Total"));

t6=new TextField(3); p4.add(t6);

p4.add(new Label(" Average"));

t7=new TextField(3); p4.add(t7);

p4.add(tot); p4.add(avg);

tot.addActionListener(this);

avg.addActionListener(this);

c1.addItemListener(this);

c2.addItemListener(this);

c3.addItemListener(this);

c4.addItemListener(this);

m.addItemListener(this);

f.addItemListener(this);

add(p4);

}

public void actionPerformed(ActionEvent e)

{

int no,m1,m2,m3,total;

float average=0.0f;

no=m1=m2=m3=total=0;

m1=Integer.parseInt(t3.getText());

m2=Integer.parseInt(t4.getText());

m3=Integer.parseInt(t5.getText());

total=m1+m2+m3;

average= total/3;

s1=String.valueOf(total);

s2=String.valueOf(average);

s3=e.getActionCommand();

if(s3.equals("Total"))

{

t6.setText(s1);

}

if(s3.equals("Average"))

{

t7.setText(s2);

}

}

public void itemStateChanged(ItemEvent e)

{

}

}

class Student extends Frame {

public Student() {

setLayout(new BorderLayout());

add(new Stupanel(),BorderLayout.CENTER);

setVisible(true);

setSize(500,500);

addWindowListener(new WindowAdapter() {

public void windowClosing(WindowEvent e) {

dispose();

}

});

}

}

public class MarkSheet {

public static void main(String[] args) {

new Student();

}

}



