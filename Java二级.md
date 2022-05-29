# 操作题

## 45

### 基本操作

```java
import java.lang.*;
import java.util.*;

public class Java_1 {
    public static void main(String [] args){
        System.out.print("请输入n: ");
        //**********Found**********
        Scanner scan = new Scanner (_________);
        String nstr = scan.next(); 
        //**********Found**********
        int n = Integer._________(nstr);
        int b = 6;
        long sum=0,item=b;
        for(int i=1;i<=n;i++){
            sum += item;
            //**********Found**********
            item = item * 10 + _________;
        }
        System.out.print(n + "项的和为 " + sum);
    }
}
```



System.in

parseInt

b

### 简单应用

```java
import java.lang.*;
abstract class Figure {
    //**********Found**********
    public _______ double area();
}

class Circle extends Figure{
    double r;
    
    Circle(double r){ 
        this.r=r;
    }
    
    public double area(){
        //**********Found**********
        return Math.PI*_________;
    }
}

class Rectangle extends Figure{
    double a,b;
    Rectangle(double a,double b) {
        this.a=a;
        this.b=b;
    }

    public double area() {
        //**********Found**********
        return _________ ;
    }
}

public class Java_2 {

    public static void main(String[] args){
        Figure[] fig=new Figure[3];
        fig[0]=new Circle(1.0);
        fig[1]=new Circle(2.0);
        //**********Found**********
        ___________________________ ;
        for(int i=0;i<3;i++)
        //**********Found**********
            System.out.println("The area of figure "+i+" is:"+ _________ );
    }
}
```



abstract

r*r

a*b

fig[2] = new Rectangle(2.0,3.0)

fig[i].area()

### 综合应用

```java
import javax.swing.*;
import java.awt.*;
import java.awt.event.*;
public class Java_3  extends JFrame implements ActionListener{
    JTextField nval = new JTextField(10);
    //**********Found**********
    JButton calcBtn = _________ ;
    JTextArea result = new JTextArea(10,20);
    void initFrame(){
        Container content = getContentPane();
        JPanel calcPanel = new JPanel();
        calcPanel.add(new JLabel("N值"));
        //**********Found**********
        calcPanel._________;
        calcPanel.add(calcBtn)          ;
        content.add(calcPanel,"North");
        //**********Found**********
        calcBtn._________;       
        content.add(result,"Center");
        result. setEditable(false)  ;    
    }

    public Java_3(){
        super("计算素数");
        setSize(500,200);
        initFrame();
        setVisible(true);
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);    
    }

    public void actionPerformed(ActionEvent e){
        if(e.getSource()==calcBtn){
            int N=Integer.parseInt(nval.getText());
            int [] prime=new int[N/3+2];
            prime[0]=2;prime[1]=3;
            int k=2;
            for(int m=5;m<=N;m+=2){
                int j=1,isprime=1;
                int kk=Math.round((float)Math.sqrt(m));
                while(prime[j]<=kk){
                    if(m%prime[j]==0){
//**********Found**********
                        _________=0;    
                        break;
                    }else    
                        //**********Found**********
                        ___________  ;
                }
                if(isprime==1) prime[k++]=m;
            }
            //**********Found**********
            String str="Total prime number: "+_________ ;
            result.setText("");
            result.append(str );   
        }
    }

    public static void main(String[] args){
        new Java_3();
    }
}

```



new JButton("计算")

add(nval)

addActionListener(this)

isprime

j++

k



## 44

### 基本操作

```java
import java.util.*;
import java.io.*;
public class Java_1 {
        //**********found**********
        static long _________ =0;
        public static void main(String[] args) {
                 //**********found**********
                 for (int ___________ ; counter <= 10; counter++){
                       System.out.printf("%d! = %d\n", counter, factorial(counter));
                       sum=sum+factorial(counter);
                 }
                 System.out.println("sum="+sum);
        }
        //**********found**********
        public static long factorial(long __________ ) {
                 if (number <= 1)
                       return 1;
                 else
                       return number * factorial(number - 1);
        }
}

```



sum

counter= 0

number

### 简单应用

```java
import java.io.*;
public class Java_2 {
    public static void main(String[] args) {
         try {
            //**********found**********
            FileInputStream in = new FileInputStream("____________");
            FileOutputStream out = new FileOutputStream("out.txt");
            BufferedInputStream bufferedIn = new BufferedInputStream(in);
            //**********found**********
            BufferedOutputStream bufferedOut = new ____________(out);
            //**********found**********
            byte[] data = new _____________[1];
            //**********found**********
            _____________ (bufferedIn.read(data) != -1) {
                  bufferedOut.write(data);
            }
            bufferedOut.flush();
            bufferedIn.close();
            //**********found**********
            ___________.close();
        //**********found**********
        } _____________ (ArrayIndexOutOfBoundsException e) {
            e.printStackTrace();
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}

```





in.txt

BufferedOutputStream

byte

while

bufferOut

catch



### 综合应用

```java
import java.awt.*;
import java.awt.event.*;
import javax.swing.*;

//**********found**********
public class Java_3 extends ___________ {
    private JTextField username;
    private JPasswordField password;
    private JLabel jl1;
    private JLabel jl2;
    private JLabel jl3;
    private JLabel jl4;
    private JButton bu1;
    private JButton bu2;
    private JButton bu3;
    private JCheckBox jc1;
    private JCheckBox jc2;
    private JComboBox jcb;
    
    public Java_3() {
        this.setTitle("QQ2022正式版");
        //**********found**********
        _____________();
        this.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        // 设置布局方式为绝对定位
        this.setLayout(null);

        this.setBounds(0, 0, 355, 265);
        // 设置窗体的标题图标
        Image image = new ImageIcon("a.png").getImage();
        this.setIconImage(image);
        // 窗体大小不能改变
        this.setResizable(false);
        // 居中显示
        this.setLocationRelativeTo(null);
        this.setVisible(true);
    }

    public void init() {
        //**********found**********
        Container con = this.______________();
        jl1 = new JLabel();
        // 设置背景图片
        Image image1 = new ImageIcon("background.jpg").getImage();
        jl1.setIcon(new ImageIcon(image1));
        jl1.setBounds(0, 0, 355, 265);

        jl2 = new JLabel();
        Image image2 = new ImageIcon("a.gif").getImage();
        jl2.setIcon(new ImageIcon(image2));
        jl2.setBounds(40, 95, 50, 60);

        username = new JTextField();
        username.setBounds(50, 50, 150, 20);
        jl3 = new JLabel("注册账号");
        jl3.setBounds(210, 50, 70, 20);
        password = new JPasswordField();
        password.setBounds(50, 80, 150, 20);
        jl4 = new JLabel("找回密码");
        jl4.setBounds(210, 80, 70, 20);
        jc1 = new JCheckBox("记住密码");
        jc1.setBounds(125, 135, 80, 15);
        jc2 = new JCheckBox("自动登录");
        jc2.setBounds(215, 135, 80, 15);
        jcb = new JComboBox();
        jcb.addItem("在线");
        jcb.addItem("隐身");
        jcb.addItem("离开");
        jcb.setBounds(40, 135, 55, 20);
        //**********found**********
        bu1 = new ______________("登录");
        bu1.setBounds(250, 200, 65, 20);
        //**********found**********
        bu1._____________________(new ActionListener() {
            public void actionPerformed(ActionEvent e) {
                String str=e.getActionCommand();
                if("登录".equals(str)){
                     String getName =username.getText();
                     JOptionPane.showConfirmDialog(null, "您输入的用户名是"+getName);
                }
            }
        });
        bu2 = new JButton("多账号");
        bu2.setBounds(25, 200, 75, 20);
        bu3 = new JButton("设置");
        bu3.setBounds(140, 200, 65, 20);
        // 所有组件用容器装载
        jl1.add(jl2);
        jl1.add(jl3);
        jl1.add(jl4);
        jl1.add(jc1);
        jl1.add(jc2);
        jl1.add(jcb);
        jl1.add(bu1);
        jl1.add(bu2);
        jl1.add(bu3);
        con.add(jl1);
        con.add(username);
        con.add(password);
    }
    public static void main(String[] args) {
        Java_3 qq = new Java_3();
    }
}

```



JFram

init

getContentPane

JButton

addActionListener



## 43

### 基本操作

```java


public class Java_1 {
    public static void main(String[] args) {
            //found
        _________ arrayOfChars = { ‘A’, ‘B’, ‘A’,‘D’, ‘E’,‘F’,‘G’ };
        char searchfor = ‘A’;

        int i = 0, j = 0;
        //**********found**********
        while (i < arrayOfChars.__________) {
            if (arrayOfChars[i] == searchfor) {
                System.out.println("Found " + searchfor + " at index " + i);
                j++;

            }
           //found
            ________________;
        }
        //found
        if (_______) {
            System.out.println(“The total amount of" + searchfor + "is" + j );
        } else {
            System.out.println(searchfor + " is not in the array”);
        }
    }
}
```



char[]

length

i++

J>0

### 简单应用

```java
                            //found
public class Java_2 extends ____________ {
    public static void main(String[] args) throws Exception {
        int i = 0;
                    //found
        Thread t = new ______________();
            //found
        ____________________;

        while (true) {
            System.out.println(“Good Morning” + i++);
            if (i == 2 && t.isAlive()) {
                System.out.println(“Main waiting for Hello !”);
                //found
                ______________; //等待线程t运行结束
            }
                        //found
            if (i == 5) ______________;
        }

    }

    //**********found**********
    public void ______________
    {
        int i = 0;
        while (true) {
            System.out.println(“Hello” + i++);
            if (i == 5) break;
        }
    }
}
```

Thread

Java_2

t.start()

t.join()

break

run()

### 综合应用

```java
import java.io.;
import java.awt.;
import java.awt.event.*;
//found
import ______________.*;

public class Java_3 implements ActionListener {
    JTextArea ta;
    JFrame f;
    JLabel label;
    JButton bs, br;

    public static void main(String[] args) {
        Java_3 t = new Java_3();
        t.go();
    }

    void go() {
        f = new JFrame(“Save data”);
        f.setSize(20, 400);
//found
        f.______________(new FlowLayout());
        label = new JLabel(“请输入需要保存的文本 ：”);
        ta = new JTextArea(3, 20);
        bs = new JButton(“保存”);
        br = new JButton(“读取”);
        f.add(label);
        f.add(ta);
        f.add(bs);
        f.add(br);
//found
        bs.addActionListener();
//found
        br.addActionListener();

        f.setSize(400, 400);
        f.pack();
        f.setVisible(true);
        f.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
    }

    public void actionPerformed(ActionEvent event) {
        try {
            FileWriter out = new FileWriter("out.txt");
            String str = ta.getText();
            //**********found**********
            out.____________(str);
            out.close();
        } catch (Exception e) {
        }
        ta.setText(" ");
    }
    class ReadFile implements ActionListener {
        public void actionPerformed(ActionEvent event) {
            String cc;
            StringBuffer str = new StringBuffer("");
            try {
                FileReader in = new FileReader("out.txt");
                //**********found**********
                BufferedReader bin = new BufferedReader(_____________);
                while ((cc = bin.readLine()) != null)
                    str.append(cc);
                bin.close();
                ta.setText(str.toString());
            } catch (Exception e) {
            }
        }
    }
}
```

javax.swing

setLayout

this

new ReadFile()

write

in

## 42

### 基本操作

```java
import java.lang.*;
import java.util.*;
public class Java_1 {
    public static void main(String[] args){
        int n;
        double e = 1.0;
        System.out.print("请输入n:  ");
        //***************************Found*********************    
        Scanner scan = new Scanner (__________);
        String nstr = scan.next(); 
        //***************************Found*********************    
        n = Integer.______(nstr);
        double t = 1.0;
        for(int i=1;i<=n;i++){
            //***************************Found*********************    
            t =  _________;
            e = e + t;
        }
        System.out.print("e 的近似值为： "+e);
    }
}
```



System.in

parseInt

t/i

### 简单应用

```java
//***************************Found********************* 
class PrintStrings implements ________{   
   int ind = 0 ;
   //***************************Found********************* 
   ______ strings = { "one", "two", "three", "four", "five"};

   public PrintStrings( int n) {
      if( n < 0)
n = 0;
      else if ( n >= strings.length)
         //***************************Found********************* 
n = ___________ ;
      ind = n;
   }
   //***************************Found********************* 
   public void ____( ){
      while(ind < strings.length){
System.out.print(strings[ind] + "  ");
        //***************************Found********************* 
_____________;

      }
      System.out.println();
   }
}

public class Java_2{
   public static void main(String[] args){
      PrintStrings p = new PrintStrings(-1);
      //***************************Found*********************
      _________;
      t.start( ); 
   }
}

```



Runnable

String[]

strings.length-1

run

ind++

Thread t = new Thread(p)

### 综合应用

```java
import java.awt.*;
import java.awt.event.*;
import javax.swing.*;

//**************found*****************
public class Java_3 extends Frame ____________ ItemListener{
   Color color = Color.blue; 
   CheckboxGroup cg;
   Checkbox cb1,cb2,cb3;

   public Java_3(){
      cg = new CheckboxGroup();
      setSize(300,300);
      cb1 = new Checkbox("blue",cg,true);
      cb2 = new Checkbox("red",cg,true);
      cb3 = new Checkbox("green",cg,true);
      cg.setSelectedCheckbox(cb1);
      add(cb1);  add(cb2);  add(cb3);
      cb1.addItemListener(this);
      cb2.addItemListener(this);
      //**************found*****************
      ____________.addItemListener(this);
   }

   public void itemStateChanged(ItemEvent e){ 
      if(e.getSource()==cb1) 
         color=Color.blue;
      if(e.getSource()==cb2) 
         color=Color.red;
      if(e.getSource()==cb3) 
         color=Color.green;
      repaint();
   } 

   class MyEvent1 extends WindowAdapter { 
      public void windowClosing(WindowEvent e){ 
         System.exit(0); 
     }
   } 

   class MyEvent2 extends ComponentAdapter { 
      public void componentResized(ComponentEvent e){ 
         repaint(); 
      }
   }

   //**************found*****************
   public void ____________(Graphics g) { 
      int w = getWidth(),h=getHeight();
      int x0 = w/2,y0 = h/2; 
      g.setColor(color);
      g.drawLine(x0,0,x0,h);
      g.drawLine(0,y0,w,y0);
      double pi = 3.1415926,angle,rou;
      int r,i,x,y;
      for(r=10;r<200;r+=20){ 
         for(i=0;i<1023;i++){ 

            angle = i * pi/512; 
            rou = r * Math.sin(2*angle);
            x = (int)Math.round(rou*Math.cos(angle));
            y = (int)Math.round(rou*Math.sin(angle));
            g.drawOval(x0+x,y0+y,1,1);
          }
       }
   }

   public static void main(String[] args){  
      Java_3 f = new Java_3(); 
      MyEvent1 me1 = f.new MyEvent1();
      MyEvent2 me2 = f.new MyEvent2();
      //**************found*****************
      f.____________("四叶玫瑰线");  
      f.setLayout(new FlowLayout());  
      f.addWindowListener(me1);
      f.addComponentListener(me2);
      //**************found*****************
      f.____________(true);
   }
}

```



implements

cb3

paint

setTittle

setVisible



## 41

### 基本操作

```java
public class Java_1{
   public static void main(String[] args){
      //**************found*****************
      _________arrayOfInts = { 33, 88, 5, 458, 18, 107, 200, 8, 622, 127 };
      int searchfor = 18;

      int i = 0;
      //**************found*****************
      _________ foundIt = false;

      for ( ; i<arrayOfInts.length; i++){
         //**************found*****************
         if (arrayOfInts[i] == _________ ){
           foundIt = true;
           //**************found*****************           
           _________;
  }
      }

      if (foundIt) {
System.out.println("Found " + searchfor + " at index " + i);
      } else {
System.out.println(searchfor + "not in the array");
      }
   }
}

```

int[]

boolean

searchfor

break

### 简单应用

```java
import java.io.*;
import java.lang.Thread;

//**************found*****************
class MyThread extends _________{
  public int x = 0;

  public void run(){
     //**************found*****************
      System.out.println(_________);
  }
}

//**************found*****************
class R implements _________{
  private int x = 0;
  //**************found*****************
  public void _________(){
    System.out.println(++x);
  }
}

public class Java_2 {
  public static void main(String[] args) throws Exception{
    
    for(int i=0;i<5;i++){
      Thread t = new MyThread();
      t.start();
    }
    Thread.sleep(1000);
    R r = new R();
    //**************found***************** 
    for(int i=0;i< ________;i++){
      Thread t = new Thread(r);
      //**************found*****************
      t._________();
    }
  }
}

```

Thread

1

Runnable

run

i<5

start

### 综合应用

```java
import javax.swing.*;
import java.awt.*;
import java.awt.event.*;
public class Java_3  extends JFrame implements ActionListener{
    private double x = 0;
    private double y = 0;
    JTextField xval = new JTextField(10);
    JButton calcBtn = new JButton("计算");
    JTextArea result = new JTextArea(10,20);
    void initFrame(){
        Container content = getContentPane();
        content.setLayout(new BorderLayout());
        JPanel calcPanel = new JPanel();
        calcPanel.setLayout(new FlowLayout());
        calcPanel.add(new JLabel("角度"));
        calcPanel.add(xval);
        //***************************Found*********************    
        calcPanel._________;
        content.add(calcPanel,"North");
        //***************************Found*********************    
        calcBtn.____________________;       
        content.add(result,"Center");
        //***************************Found*********************    
        result.____________________;
    }
    public Java_3(){
       super("计算正弦函数");
       setSize(500,200);
       initFrame();
       setVisible(true);
       setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
    }
    public void actionPerformed(ActionEvent e){
     //***************************Found*********************   
       if (e.getSource()==___________){
          x = Double.parseDouble(xval.getText())/180*3.14;     
          y = Math.sin(x); 
          //***************************Found*********************           
          String str="sin("+ ___________ +"*3.14/180)= "+y+'\n';   
          //***************************Found*********************    
         result.__________;   
       }
    }
    public static void main(String[] args){
    new Java_3();
    }
}

```

 add(calcBtn) 

 addActionListener(this)

 setEditable(false) 

 calcBtn 

 xval.getText() 

 append(str) 

## 40

### 基本操作

```java
public class Java_1 {

    public static void main(String[] args) {
        int i, k, n;
        //*********Found********
        ____________;
        //*********Found********
        for (i = 0; ____________; i++) {                            
            k = i * 10 + 6;
            //*********Found********
            if (____________) {
                System.out.print(k + "  ");
                n++;
            }
        }
        System.out.println("\n" + "The number is " + n + ".");
    }
}

```

n=0

i<10

k%3==0

### 简单应用

```java
public class Java_2 {

    public static void main(String[] args) {
        Person p = new Person("Zhao",20);
        Student s = new Student("Wang",18,"Cambridge");
        System.out.println(p);
        System.out.println(s);
    }
}

class Person {

    private String name;
    private int age;

    public Person(String name, int age) {
        //*********Found********
        ___________ = name;
        //*********Found********
        ___________ = age;
    }

    public void setName(String n) {
        //*********Found********
        ___________= n;
    }

    public String toString() {
        return "Name: " + name + "     Age: " + age;
    }
}

class Student extends Person {

    private String school;

    public Student(String name, int age, String s) {
        //*********Found********
        ___________;
        school = s;
    }

    public String toString() {
        //*********Found********
        return ___________.toString() + "     School: " + school;
    }
}

```

this.name

this.age

name

super(name,age)

super

### 综合应用

```java
import javax.swing.*;
import java.awt.*;
import java.awt.event.*;

public class Java_3 {

    public static void main(String[] args) {
        JFrame frame = new JFrame("Mouse Demo");
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.getContentPane().add(new MousePanel());
        frame.pack();
        frame.setVisible(true);
    }
}

//*********Found**********
class ___________ extends JPanel {

    private JLabel b;

    public MousePanel() {
        b = new JLabel("  起始状态  ");
        setLayout(new BorderLayout());
        add(b, BorderLayout.SOUTH);

        addMouseMotionListener(new MouseMotion());
        setPreferredSize(new Dimension(300, 200));
    }

    //*********Found**********
    private class MouseMotion extends ___________ {

        public void mouseMoved(MouseEvent e) {
            //*********Found**********
            b.setText(" 鼠标当前位置: "+ e._________+ " , " + e.__________);
        }
    }
}

```

MousePanel

MouseMotionAdapter

getX()

getY()

## 39

### 基本操作

```java
import javax.swing.JOptionPane;
public class Java_1{
   public static void main( String args[] ){
      int x, result;
      String xVal;
      //*********Found**********
      xVal = JOptionPane._____________________(
                "输入1个整数:" );
      //*********Found**********
      x = Integer.___________________( xVal );
      //*********Found**********
      result = ______________;
      JOptionPane.showMessageDialog(null,
         "该数的平方是" + result );
      System.exit( 0 );
   }
}

```

showInputDialog

parseInt

X*X

### 简单应用

```java
import javax.swing.*;
public class Java_2{
   public static void main( String args[] ){
      StringBuffer buf = new StringBuffer( "你好!祝你成功!" );
      String output = "buf = " + buf.toString() +
                      "\nCharacter at 0: " + buf.charAt( 0 ) +
                      "\nCharacter at 4: " + buf.charAt( 4 );
//*********Found**********
      char charArray[] = _____________________ char[ buf.length() ];
//*********Found**********
      ____________.getChars( 0, buf.length(), charArray, 0 );
      output += "\n\n在字符串缓存中的字符是: ";
//*********Found**********
      for ( int i = 0; i < ______________________; ++i )
         output += charArray[ i ];
      buf.setCharAt( 0, '您' );
      buf.setCharAt( 6, '材' );
//*********Found**********
      __________ += "\n\nbuf = " + buf.toString();
      buf.reverse( );
      output += "\n\nbuf = " + buf.toString();
      JOptionPane.showMessageDialog( null, output,
         "字符串缓存的字符相关方法示范",
         JOptionPane.INFORMATION_MESSAGE );
      System.exit( 0 );
   }
}

```

new

buf

charArray.length

output

### 综合应用

```java
import java.awt.*;
import java.awt.event.*;
import javax.swing.*;

//**********found**********
public class _________ extends JFrame {
    private JTextField username;
    private JPasswordField password;
    private JLabel jl1;
    private JLabel jl2;
    private JLabel jl3;
    private JLabel jl4;
    private JButton bu1;
    private JButton bu2;
    private JButton bu3;
    private JCheckBox jc1;
    private JCheckBox jc2;
    private JComboBox jcb;
    
    public Java_3() {
        this.setTitle("QQ2022正式版");        
        init();
        this.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        // 设置布局方式为绝对定位
        this.setLayout(null);

        this.setBounds(0, 0, 355, 265);
        // 设置窗体的标题图标
        Image image = new ImageIcon("a.png").getImage();
        this.setIconImage(image);
        // 窗体大小不能改变
        this.setResizable(false);
        // 居中显示
        this.setLocationRelativeTo(null);
       //**********found**********
        this._______(true);
    }

    public void init() {
        Container con = this.getContentPane();
        jl1 = new JLabel();
        // 设置背景图片
        Image image1 = new ImageIcon("background.jpg").getImage();
        jl1.setIcon(new ImageIcon(image1));
        jl1.setBounds(0, 0, 355, 265);

        jl2 = new JLabel();
        Image image2 = new ImageIcon("a.gif").getImage();
        jl2.setIcon(new ImageIcon(image2));
        jl2.setBounds(40, 95, 50, 60);

        //**********found**********
        username = new ____________();
        username.setBounds(50, 50, 150, 20);
        jl3 = new JLabel("注册账号");
        jl3.setBounds(210, 50, 70, 20);
        password = new JPasswordField();
        password.setBounds(50, 80, 150, 20);
        jl4 = new JLabel("找回密码");
        jl4.setBounds(210, 80, 70, 20);
        jc1 = new JCheckBox("记住密码");
        jc1.setBounds(125, 135, 80, 15);
        jc2 = new JCheckBox("自动登录");
        jc2.setBounds(215, 135, 80, 15);
        jcb = new JComboBox();
        jcb.addItem("在线");
        jcb.addItem("隐身");
        jcb.addItem("离开");
        jcb.setBounds(40, 135, 55, 20);
        bu1 = new JButton("登录");
        bu1.setBounds(250, 200, 65, 20);
        
        bu2 = new JButton("多账号");
        bu2.setBounds(25, 200, 75, 20);
        bu3 = new JButton("设置");
        bu3.setBounds(140, 200, 65, 20);  
        bu3.addActionListener(new ActionListener() {
           //**********found**********
            public void ____________(ActionEvent e) {
                  if (jc1.isSelected()==true)
                        JOptionPane.showConfirmDialog(null,"确定记住密码吗?");
            }
        });
        // 所有组件用容器装载
        jl1.add(jl2);
        jl1.add(jl3);
        jl1.add(jl4);
        jl1.add(jc1);
        jl1.add(jc2);
        jl1.add(jcb);
        jl1.add(bu1);
        jl1.add(bu2);
        jl1.add(bu3);
        con.add(jl1);
        con.add(username);
        con.add(password);
    }
    //**********found**********
    public static void _________ (String[] args) {
        Java_3 qq = new Java_3();
    }
}

```

Java_3

setVisible

 JTextField 

 actionPerformed 

main

## 38

### 基本操作

```java
public class Java_1
{
   //*********Found**********
   public static void main(_________________ args[])
   {
      byte  b = 8;
   //*********Found**********
      ___________  g = 567L;
      float f = 3.1415f;
      double d = 2.789;
      int ii = 207;
      //*********Found**********
      _________________ gg = g+ii;
      float ff = b*f;
      double dd = ff/ii+d;
      //*********Found**********
      System.out.____________("ii= "+ii+" ");
      System.out.println("gg= "+gg);
      System.out.println("ff= "+ff);
      System.out.println("dd= "+dd);
   }
}

```

String

long

long

print

### 简单应用

```java
import javax.swing.*;
import java.awt.event.*;
import java.io.*;
import java.awt.*;

public class Java_2 implements ActionListener {
    private JFrame frame;
    private JButton button,saveButton;
    private JTextArea textArea;
    private JFileChooser dia;
    private JPanel buttonPanel;
    
    public void init() {
        frame=new JFrame("file chooser");
        dia=new JFileChooser();
        button=new JButton("open file");
        button.setActionCommand("open");
        //*********Found**********
        _______________________________(this);
        
        saveButton=new JButton("save file");
        //*********Found**********
        _______________________________(this);
        
        buttonPanel=new JPanel();
        buttonPanel.add(button);
        buttonPanel.add(saveButton);
        
        //*********Found**********  
        textArea=_____________ JTextArea("",10,10);
        //*********Found**********
        frame.getContentPane().add(__________________,BorderLayout.NORTH);
        frame.getContentPane().add(textArea,BorderLayout.CENTER);
        
        frame.setSize(300,300);
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setVisible(true);
    }
    //*********Found**********
    public void ________________________(ActionEvent event) { 
        if(event.getActionCommand().equals("open"))
            dia.showOpenDialog(frame);
        else
            dia.showSaveDialog( frame );
        
        dia.setVisible(true);
        File file=dia.getSelectedFile();
        if (file!=null){
            String fileName=file.getAbsolutePath();
            textArea.append("path of selected file: "+fileName+"\r\n");
        }
    }
    public static void main(String args[]){
        Java_2 example=new Java_2();
        //*********Found**********
        example.________________();
    }
}

```

 button.addActionListener 

 saveButton.addActionListener 

new

buttonPanel 

actionPerformed 

init

### 综合应用

```java
import java.io.*; import java.util.*;

public class Java_3 {    //*********Found**********    public
________________ void main (String args[])  throws IOException {
      FileOutputStream unbufStream = new FileOutputStream("test.one");
      BufferedOutputStream bufStream = new BufferedOutputStream(
      //*********Found**********
        new ____________________ ("test.two"));
      System.out.println();
      System.out.println("这是一个测试缓冲流和非缓冲流速度的程序。");
      System.out.println();
      //*********Found**********
      int ______________ = time(unbufStream)-time(bufStream);
      if(flag > 0) {
         System.out.println("测试结果：缓冲流的传输速度快于非缓冲流。");
         System.out.println();
      }
      else
         System.out.println("测试结果：缓冲流的传输速度慢于非缓冲流。");    }    //*********Found**********    static int _____________(OutputStream out) throws IOException {
      //*********Found**********
      Date then = new ____________();
      for (int i=0; i<1000; i++) {
         out.write(1);
      }
      //*********Found**********
      out._________________ ();
      return (int)((new Date()).getTime() - then.getTime());    } }

```

static

 FileOutputStream 

flag

time

Date

close

## 37

### 基本操作

```java
import javax.swing.*;
public class Java_1{
   public static void main( String args[] ){
      //*********Found**********
      StringBuffer buf = new __________________( "Hello, how are you?" );
      String output = "buf = " + buf.toString() +
                      "\nlength = " + buf.length() +
                      "\ncapacity = " + buf.capacity();
      buf.ensureCapacity( 75 );
      output += "\n\nNew capacity = " + buf.capacity();
      buf.setLength( 10 );
      //*********Found**********
      __________ += "\n\nNew length = " + buf.length() +
                "\nbuf = " + buf.toString();
      JOptionPane.showMessageDialog( null, output,
         "字符串缓存长度和容量的实例",
      //*********Found**********
         _______________.INFORMATION_MESSAGE );
      //*********Found**********
      System.___________________( 0 );
   }
}

   

```

StringBuffer  

output

JOptionPane 

exit

### 简单应用

```java
class Point{
   public int x,y;
   public Point() { 
   }
   public Point(int x,int y){
      this.x = x;
      this.y = y;
   }
   //*********Found**********
   public Point(____________ p){
      x = p.x;
      y = p.y;
   }
   public int getX(){
      return x;
   }
   public int getY(){
      return y;
   }
   public void moveTo(int x,int y){
      this.x = x;
      this.y = y;
   }
   public void moveTo(Point p){
      x = p.x;
      y = p.y;
   }
   public String toString(){
      return "("+ x + ","+ y + ")";
   }
   public void translate(int dx,int dy){ //平移
      this.x += dx;
      //*********Found**********
      ____________;
   }
}

public class Java_2 {
   public static void main(String args[]){
      //*********Found**********
      Point p = new ____________(5,5);
      System.out.println("点的当前坐标：("+p.x + "," + p.y+")");
      p.translate(3,4);
      //*********Found**********
      System.out.println("平移到："+____________());
   }
}

   

```

Point 

this.y +=dy

Point 

p. toString 

### 综合应用

```java
import java.awt.*;
import java.awt.event.* ;
     //*********Found********
import ___________________;   

     //*********Found********
public class Java_3 ________________ ActionListener{
    public static void main(String args[ ]){
        Java_3 tb = new Java_3();
     //*********Found********
        JFrame f = new JFrame("______________");  
        f.setSize(200,100);
        f.setLayout(new FlowLayout(FlowLayout.CENTER));

        JButton b = new JButton("Press the Button!");  /JButton
     //*********Found********
        b._________________(tb); 

     //*********Found********
        ________.add(b);
        f.addWindowListener(new WindowAdapter(){
              public void windowClosing(WindowEvent e){
                 System.exit(0);
              }
        });
        f.setVisible(true) ;
    }

     //*********Found********
    public void ________________(ActionEvent e){
        JFrame fr = new JFrame("An Other");   
        fr.setBackground(Color.green);
        fr.add(new JLabel("This frame shows when "+"pressing the button in Button Test"));
        fr.addWindowListener(new WindowAdapter(){
           public void windowClosing(WindowEvent e){
              System.exit(0);
           }
        });
        fr.pack();
        fr.setVisible(true) ;
    } 
}

```

javax.swing.*

implements 

Button Test 

addActionListener

f

 actionPerformed 

## 36

### 基本操作

```java
import java.io.*;

public class Java_1
{
    public static void main(String args[])
    {
        int a=15,b=25,c=5,m;        
        if(a>b){
        //*********Found**********
            if(_____________)
                m=b;
            else
               //*********Found**********
               m=(a>c)? _____________;
        }else{
           if(a>c)
               //*********Found**********
               _____________;
           else
               m=(b>c)? c:b;
        }
        //*********Found**********
        System.out.println("median = " + ______);        
    }
}

```

b>c

c:a

m=a

m

### 简单应用

```java
import java.awt.*;
import javax.swing.*;

public class Java_2{
    int grades[][] = { { 77, 68, 86, 73 },
                        { 96, 87, 89, 81 },
                        { 70, 90, 86, 81 } };
    int students, exams;
    String output;
    JTextArea outputArea;
    public Java_2(){    
        students = grades.length;
        exams = grades[ 0 ].length;        
        JFrame f = new JFrame();
        f.setSize(300,300);
        f.setVisible(true);
        f.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        //*********Found**********
        outputArea = new ________________();
        Container c = f.getContentPane();
        //*********Found**********
        c.add( ________________ );        
        output = "数组是:";
        buildString();
        output += "\n\n最高分: " + maximum() + "\n";
         //*********Found**********
        for ( int i = 0; i < ________________; i++ )
            output += "\n第" + (i+1) + "个学生的平均分是: " +
                    average( grades[ i ] );
         //*********Found**********
        outputArea.________________( output );
    }     
    //找最高分
    public int maximum(){
        int highGrade = 0;
        for ( int i = 0; i < students; i++ )
            for ( int j = 0; j < exams; j++ )
                if ( grades[ i ][ j ] > highGrade )
                     //*********Found**********
                    highGrade = ________________;
        return highGrade;
    }
    //对各组学生确定平均分
    public int average( int setOfGrades[] ){
        int total = 0;
        for ( int i = 0; i < setOfGrades.length; i++ )
             //*********Found**********
            total += ________________;       
        return total /exams;
    }
    //输出格式
    public void buildString(){
        output += "        ";
        for ( int i = 0; i < exams; i++ )
            output += "[" + i + "]   ";
        for ( int i = 0; i < students; i++ ) {
            output += "\ngrades[" + i + "]   ";
            for ( int j = 0; j < exams; j++ )
                output += grades[ i ][ j ] + "   ";
        }
    }    
    public static void main(String[ ]args){
        new Java_2();
    }
}

```

 JTextArea 

 outputArea  

 students 

 setText 

grades [i] [j]

 setOfGrades[i]

### 综合应用

```java
import java.lang.*;
import java.util.*;

public class Java_3{
    
    public static void main(String[ ]args){
        int bound=100;
        int i=0,j=0,counter=0,k=0;
        int temp=0;
        boolean first=true;
        for(i=1;i<bound;i++){
            for(j=1;j<bound;j++){
                //*********Found**********
                temp=___________ +5*j*j;
                k=(int)Math.sqrt(temp);
                //*********Found**********
                if(k<bound && ___________ ){
                    if(first){
                        System.out.println("The first component: ("+i+", "+j+", "+k+")");
                        //*********Found**********
                        first=___________;
                    }
                    //*********Found**********
                    ___________;
                }
            };
        }
        System.out.print("Total number is: "+counter);     
        System.exit(0);     
    }
}

```

i*i

 k*k==temp 

false

count++

## 35

### 基本操作

```java
public class Java_1{
   void equalsMethod1(){
      //*********Found**********
      __________ s1= "how are you";
      //*********Found**********
      _________ s2={'h','o','w',' ','a','r','e',' ','y','o','u'};
   
      //*********Found**********
      System.out.println(s1==s2._____________());
   }
   public static void main(String args[]){
      Java_1 OperAndExp=new Java_1();
      OperAndExp.equalsMethod1();
   }
}

```

String

char[]

toString

### 简单应用

```java
import java.awt.*;
import java.awt.geom.*;
//*********Found**********
import javax._______________.*;

public class Java_2
{
   public static void main(String[] args)
   {
      DrawFrame frame = new DrawFrame();
      frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
//*********Found**********
      frame._______________(true);
   }
}

//*********Found**********
class ___________________ extends JFrame
{
   public DrawFrame()
   {
      setTitle("千里共婵娟");
      setSize(DEFAULT_WIDTH, DEFAULT_HEIGHT);
      DrawPanel panel = new DrawPanel();
//*********Found**********
      Container contentPane = ___________________();
//*********Found**********
      contentPane.______________(panel);
   }
   public static final int DEFAULT_WIDTH = 400;
   public static final int DEFAULT_HEIGHT = 240;
}

//*********Found**********
class DrawPanel ________________________
{
   public void paintComponent(Graphics g)
   {
      super.paintComponent(g);
      Graphics2D g2 = (Graphics2D)g;
      double l = 0;
      double r = 0;
      double w = 400;
      double h = 400;
      Rectangle2D re = new Rectangle2D.Double(l,r,w,h);
      g2.setPaint(Color.BLUE);
      g2.fill(re);
      double leftX = 50;
      double topY = 50;
      double width = 50;
      double height = 50;
      Rectangle2D rect = new Rectangle2D.Double(leftX, topY, width, height);
      Ellipse2D ellipse = new Ellipse2D.Double();
      ellipse.setFrame(rect);
      g2.setPaint(Color.YELLOW);
      g2.fill(ellipse);
   }
}

```

swing

setVisible

DrawFrame 

 getContentPane 

add

 extends JPane 

### 综合应用

```java
import java.io.File;
import java.io.FileReader;
import java.io.FileWriter;
import java.io.IOException;

public class Java_3
{
   public static void main(String args[])
   {
      if(args.length<2)
      {
         System.out.println("ERROR: need parameters.");    
         System.out.println("-usage: java <classname> <file1> <file2>");    
         System.exit(0);      //退出程序
      }
      //*********Found**********
      File f1=new _________________( args[0] );
      //*********Found**********
      File f2=new File( _________________ );
      try
      {
         FileReader fr=new FileReader(f1);
         FileWriter fw=new FileWriter(f2);
         int b;         
         while((b=fr.read()) != -1) 
        //*********Found**********
             fw.write( ________________ );
         //*********Found**********
         fr._____________();       //关闭流文件
         //*********Found**********
         fw._____________();      //关闭流文件
         System.out.println("has done!");
      }
      catch(IOException e)
      {
         e.printStackTrace();
      } 
   }
}

```

File

args[1]

b

close

close

## 34

### 基本操作

```java
//用2至20的偶数去初始化数组 
import javax.swing.*;

public class Java_1{
   public static void main( String args[] ){
      final int ARRAY_SIZE = 10;
      int n[];                    //引用整形数组
      String output = "";
      //*********Found*********
      n = __________________________ int[ ARRAY_SIZE ];  //分配数组
      //给数组赋值
      for ( int i = 0; i < n.length; i++ ) 
         n[ i ] = 2 + 2 * i;
      output += "数组下标\t值\n";
      for ( int i = 0; i < n.length; i++ ) 
         output += i + "\t" + n[ i ] + "\n";
      //*********Found**********
      JTextArea outputArea = __________________________ JTextArea( 11, 10 );
      outputArea.setText( output );
      //*********Found**********
      JOptionPane.__________________________( null, outputArea,
         "用2至20的偶数去初始化数组",
         JOptionPane.INFORMATION_MESSAGE );
      System.exit( 0 );
   }
}

```

new

new

 showMessageDialog 

### 简单应用

```java
import java.util.Random;
public class Java_2{
    //*********Found**********
  public _______________________ void main(String args[]){
    Random random = new Random();
    //*********Found**********
    float x = _______________________.nextFloat();//产生0.0与1.0之间的一个浮点数
    //*********Found**********
    int n = Math._______________________(21*x);  //构造20以内的一个整数
    long f = 1 ;  //保存阶乘的结果
    int k = 1 ;  //循环变量
    do {
    //*********Found**********
       f*= _______________________;
    }while(k<=n);
    System.out.println(n+"!= "+f);
  }
}

```

static

 random 

 Math.round() 

k++

### 综合应用

```java
Java_3.html
<html><applet code="Java_3.class" width=275 height=50></applet></html>
Java_3.java
import java.awt.*;
import java.awt.event.*;
import javax.swing.*;
    //*********Found**********
public class Java_3 extends JApplet implements ___________________{
   JLabel prompt;
   JTextField input;
   public void init(){
      Container c = getContentPane();
      c.setLayout( new FlowLayout() );
      //*********Found**********
      prompt = new __________________( "输入球半径: " );
      input = new JTextField( 10 );
      //*********Found**********
      _________________________________;
      c.add( prompt );
      c.add( input );
   }
   public void actionPerformed( ActionEvent e ){
      double radius =
         Double.parseDouble( e.getActionCommand() );
      showStatus( "体积 " + sphereVolume( radius ) );
   }
   public double sphereVolume( double radius ){
      double volume =
         ( 4.0 / 3.0 ) * Math.PI * Math.pow( radius, 3 );
      return volume;
   }
}

```

 ActionListener 

 JLabel 

 input.addActionListener(this) 

## 33

### 基本操作

```java
import java.io.*;

public class Java_1 {
  public static void main(String[] args) {
    char[] charArray = {'a','b','c','d','e','f','g','h','i'};
    char c  ;
    try{
//*********Found**********
        DataOutputStream out = new DataOutputStream(
               new FileOutputStream("test.dat"));
        for(int i =0; i<charArray.length; i++){
           out.writeChar(charArray[i]);
        }
        out.close();
        DataInputStream in = new DataInputStream(
//*********Found**********
               new FileInputStream("test.dat"));
        while(in.available() != 0){
           c=in.readChar();
           System.out.print(c+" ");
        }
        System.out.println();
//*********Found**********
        in.close();
    }catch(IOException e){}
  }
}

 

```

 DataOutputStream  

test.dat

close

### 简单应用

```java
//*********Found**********
import javax.swing.*;

public class Java_2{
  public static void main(String[] args){
//*********Found**********
    String input=JOptionPane.showInputDialog("你想抽几个数?");
    int k = Integer.parseInt(input);
    input = JOptionPane.showInputDialog("你想在自然数中抽的最大数是几?");
    int n = Integer.parseInt(input);
    int lotteryOdds = 1;
//*********Found**********
    for (int i = 1; i <= k; i++)
       lotteryOdds = lotteryOdds * (n - i + 1)/i;
//*********Found**********
    System.out.println("你中奖的几率是1/" + lotteryOdds + ". Good luck!");
    System.exit(0);
  }
}
```

javax.swing

String

k

 lotteryOdds  

### 综合应用

```java
import java.awt.*;
import javax.swing.*;

//*********Found**********
public class Java_3 extends JApplet{
   JTextArea outputArea;
   public void init(){
      outputArea = new JTextArea();
//*********Found**********
      Container c = getContentPane();
//*********Found**********
      c.add( outputArea);
      //计算0至10的阶乘
      for ( long i = 0; i <= 10; i++ )
         outputArea.append(
            i + "! = " + factorial( i ) + "\n" );
   }  
   //阶乘的递归定义
   public long factorial( long number ){                  
      if ( number <= 1 ) 
         return 1;
      else
         return number * factorial( number - 1 );
   }  
}

 

```

JApplet

 getContentPane 

 outputArea 

## 32

### 基本操作

```java
import javax.swing.*;
import java.text.DecimalFormat;

public class Java_1{
//*********Found**********
   public static void main( String args[] ){
      SimpleTime t = new SimpleTime( 12, 30, 19 );
//*********Found**********
      JOptionPane.showMessageDialog( null, t.buildString(),
         " \"this\" 引用示范",
         JOptionPane.INFORMATION_MESSAGE );
      System.exit( 0 );
   }
}

class SimpleTime {
   private int hour, minute, second;   
   public SimpleTime( int hour, int minute, int second ){
      this.hour = hour;
      this.minute = minute;
      this.second = second;
   }

   public String buildString(){
//*********Found**********
      return "this.toString(): " + toString() +
             "\ntoString(): " + toString() +
             "\nthis (with implicit toString() call): " +
             this;
   }

   public String toString(){
      DecimalFormat twoDigits = new DecimalFormat( "00" );    
      return twoDigits.format( this.hour ) + ":" +
             twoDigits.format( this.minute ) + ":" +
             twoDigits.format( this.second );
   }
}
 

```

void

 JOptionPane 

toString

### 简单应用

```java
import java.awt.*;
import java.awt.event.*;
import java.util.*;
import javax.swing.*;
import javax.swing.Timer;

public class Java_2{
  public static void main(String[] args){
//*********Found**********
    ActionListener listener = new TimePrinter();
    Timer t = new Timer(10000, listener);
    t.start();
    JOptionPane.showMessageDialog(null, "退出程序吗?");
    System.exit(0);
  }
}

//*********Found**********
class TimePrinter implements ActionListener{
//*********Found**********
  public void actionPerformed(ActionEvent event){
    Date now = new Date();
    System.out.println("At the tone, the time is " + now);
    Toolkit.getDefaultToolkit().beep();
  }
}

```

  TimePrinter 

 implements 

 ActionEvent 

### 综合应用

```java
import java.awt.Graphics;   
import javax.swing.*;       

//*********Found**********
public class Java_3 extends JApplet {
   double sum;  //存和的变量
//*********Found**********
   public void init(){
      String firstNumber,   //输入第1个字符串格式的数
             secondNumber;  //输入第2个字符串格式的数
      double number1,       //加数
             number2;       //被加数
      //读入第1个输入的数
      firstNumber =
         JOptionPane.showInputDialog(
            "Enter first floating-point value" );
      //读入第2个输入的数 
      secondNumber =
         JOptionPane.showInputDialog(
            "Enter second floating-point value" );
      //将字符串数据转换成双字长类型
      number1 = Double.parseDouble( firstNumber ); 
      number2 = Double.parseDouble( secondNumber );
      //数据相加
      sum = number1 + number2;
   }
   public void paint( Graphics g )   {
      //用g.drawString给结果
      g.drawRect( 15, 10, 270, 20 );
      g.drawString( "数相加之和为:" + sum, 25, 25 );
   }
}

<html>
//*********Found**********
<applet code="Java_3.class" width=300 height=50>
</applet>
</html>

 

```

JApplet

init

 <applet code="Java_3.class" width=300 height=50> 

## 31

### 基本操作

```java
import javax.swing.JOptionPane;

public class Java_1{
//*********Found**********
   public static void main( String args[] ){
      PackageData d = new PackageData();
      String output;
      output = "实例化后:\n" + d.toString();
      d.x = 77;          //修改包访问的数据
//*********Found**********
      d.s = "祝您成功!";  //修改包访问的数据
      output += "\n修改数据后的访问结果:\n" + d.toString();
//*********Found**********
      JOptionPane.showMessageDialog( null, output,
         "对包的访问示范",
         JOptionPane.INFORMATION_MESSAGE );
      System.exit( 0 );
   }
}

class PackageData {
   int x;     //访问包的实例变量
   String s;  //访问包的实例变量
   //构造方法
   public PackageData(){ 
      x = 0; 
      s = "Hello";
   }               
   public String toString(){
      return "x: " + x + "    s: " + s;
   }
}

```

static

d.s

 showMessageDialog 

### 简单应用

```java
import javax.swing.*;
import java.awt.*;

public class Java_2{
  public static void main(String[] args){
    WelcomFrame frame = new WelcomFrame();
//*********Found**********
    frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
    frame.setVisible(true);
  }
}
//*********Found**********
class WelcomFrame extends JFrame{
  public WelcomFrame(){
    setTitle("Java等级考试");
//*********Found**********
    setSize(DEFAULT_WIDTH, DEFAULT_HEIGHT);
    WelcomPanel panel = new WelcomPanel();
    Container contentPane = getContentPane();
    contentPane.add(panel);
  }
  public static final int DEFAULT_WIDTH = 250;
  public static final int DEFAULT_HEIGHT = 100;
}
//*********Found**********
class WelcomPanel extends JPanel{
  public void paintComponent(Graphics g){
    super.paintComponent(g);
    g.drawString("欢迎参加Java等级考试！",MESSAGE_X, MESSAGE_Y);
  }
  public static final int MESSAGE_X = 60;
  public static final int MESSAGE_Y = 50;
}

```

 EXIT_ON_CLOSE 

 JFrame 

 setSize 
 JPanel 

### 综合应用

```java
import javax.swing.JOptionPane;

public class Java_3 {
   public static void main( String args[] ){
      String firstNumber,   //存储第1个输入数据
             secondNumber,  //存储第2个输入数据
     //*********Found********
             result;        //字符串输出
      int number1,          //用来比较的第1个int型数据 
          number2;          //用来比较的第2个int型数据
      //以字符串格式读输入数据
      firstNumber =
         JOptionPane.showInputDialog( "请输入第1个整数:" );
      secondNumber =
         JOptionPane.showInputDialog( "请输入第2个整数:" );          
      //将字符串转换为int整数
     //*********Found********
      number1 = Integer.parseInt( firstNumber);
     //*********Found********
      number2 = Integer.parseInt( secondNumber );
      //用空字符串初始化结果变量
      result = "";
      if ( number1 == number2 )
         result = number1 + " == " + number2;
      if ( number1 != number2 )
         result = number1 + " != " + number2;
      if ( number1 < number2 )
         result = result + "\n" + number1 + " < " + number2;
      if ( number1 > number2 )
         result = result + "\n" + number1 + " > " + number2;
      if ( number1 <= number2 )
         result = result + "\n" + number1 + " <= " + number2;
      if ( number1 >= number2 )
         result = result + "\n" + number1 + " >= " + number2;
      //显示结果
      JOptionPane.showMessageDialog(
         null, result, "比较结果",
         JOptionPane.INFORMATION_MESSAGE);
      //*********Found********
      System.exit( 0 );
   }
}
 

```

 result 

 firstNumber  

 secondNumber  

 System

## 30

### 基本操作

```java
//Interest.java
//计算复杂利息
import java.text.DecimalFormat;
import javax.swing.JOptionPane;
import javax.swing.JTextArea;

public class Java_1{
   public static void main( String args[] ){
      double amount, principal = 1000.0, rate = .05;
      DecimalFormat precisionTwo = new DecimalFormat( "0.00" );
//*********Found**********
      JTextArea outputTextArea = new JTextArea( 11, 20 );
      outputTextArea.append( "年\t存款总计\n" );
      for ( int year = 1; year <= 10; year++ ) {
         amount = principal * Math.pow( 1.0 + rate, year );
         outputTextArea.append( year + "\t" +
//*********Found**********
            precisionTwo.format( amount ) + "\n" );
      }
//*********Found**********
      JOptionPane.showMessageDialog(
         null, outputTextArea, "复合利息",
         JOptionPane.INFORMATION_MESSAGE );
      System.exit( 0 );
   }
}
 

```

 JTextArea  

 format 

 showMessageDialog 

### 简单应用

```java
import java.awt.*;
import java.awt.event.*;
import javax.swing.*;

public class Java_2{
  public static void main(String[] args){
    RadioButtonFrame frame = new RadioButtonFrame();
    frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
//*********Found**********
    frame.show();
  }
}
class RadioButtonFrame extends JFrame{
  public RadioButtonFrame(){
    setTitle("Radio按钮实例");
    setSize(DEFAULT_WIDTH, DEFAULT_HEIGHT);
    Container contentPane = getContentPane();
    label = new JLabel("热烈庆祝Java程序语言开考三周年");
    label.setForeground(Color.yellow);
    contentPane.setBackground(Color.red);
    label.setFont(new Font("黑体", Font.PLAIN, DEFAULT_SIZE));
    contentPane.add(label, BorderLayout.CENTER);
    buttonPanel = new JPanel();
    group = new ButtonGroup();
    addRadioButton("小", 8);
    addRadioButton("中", 12);
    addRadioButton("大", 18);
    addRadioButton("特大", 30);
    contentPane.add(buttonPanel, BorderLayout.SOUTH);
  }
  public void addRadioButton(String name, final int size){
    boolean selected = size == DEFAULT_SIZE;
//*********Found**********
    JRadioButton button = new JRadioButton(name, selected);
    group.add(button);
    buttonPanel.add(button);
    ActionListener listener = new ActionListener(){
//*********Found**********
      public void actionPerformed(ActionEvent evt){
        label.setFont(new Font("黑体", Font.PLAIN, size));
      }
    };
//*********Found**********
    button.addActionListener(listener);
  }
  public static final int DEFAULT_WIDTH = 340;
  public static final int DEFAULT_HEIGHT = 200;
  private JPanel buttonPanel;
  private ButtonGroup group;
  private JLabel label;
  private static final int DEFAULT_SIZE = 12;
}
 

```



### 综合应用

```java
import java.awt.*;
import javax.swing.*;

//*********Found**********
public class Java_3 extends JApplet{
//*********Found**********
  public void init(){
    Container contentPane = getContentPane();
    JLabel label = new JLabel("Java的诞生是对传统计算模式的挑战！",
         SwingConstants.CENTER);
//*********Found**********
    contentPane.add(label);
  }
}

```

extends

init

label

## 29

### 基本操作

```java
public class Java_1
{
public static void main(String args[])
{
int i,count;
//*Found
________________;
for( i=100 ; i <= 200 ; i++)
//*Found
if ( _________________ ) count++;
//*Found
System.out.println("Count = " + ______________);
}
}
————————————————
版权声明：本文为CSDN博主「张国荣家的弟弟」的原创文章，遵循CC 4.0 BY-SA版权协议，转载请附上原文出处链接及本声明。
原文链接：https://blog.csdn.net/qq_43674360/article/details/108665161
```

count=0

i%3==0

count

### 简单应用

```java
import javax.swing.*;
import java.awt.event.*;

public class Java_2 extends JFrame {
    private JButton b;
    public Java_2(String s){
        setTitle(s);
        b=new JButton("Hello");
        getContentPane().add(b);
     //*********Found********
        b.addActionListener( new HandleButton() );
setSize(150,150);
setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
     //*********Found********
setVisible( true);
    }
    class HandleButton implements ActionListener{
        public void actionPerformed(ActionEvent e){
             //*********Found********
            if ( "Hello".equals( b.getText()) )
                b.setText("你好");
            else
                b.setText("Hello");                          
        }
    }
    public static void main(String args[]){
         //*********Found********
        new Java_2("二级Java");
    }    
}
 


private void addRadioButton(String s, ActionListener listener)
   {
      JRadioButton button = new JRadioButton(s, false)
         {
            protected void fireActionPerformed(ActionEvent event)
            {
               try
               {
                  textField.setText("No exception");
                  super.fireActionPerformed(event);
               }
               catch (Exception exception)
               {
     //*********Found********
                  textField.setText(exception.toString());
               }
            }
         };
      button.addActionListener(listener);
      add(button);
      group.add(button);
   }
   private ButtonGroup group;
   private JTextField textField;
   private double[] a = new double[10];
}
 

```

 new HandleButton() 

true

b.getText()

Java_2("二级Java")

### 综合应用

```java
import java.awt.*;
import java.awt.event.*;
import javax.swing.*;
import java.io.*;

public class Java_3
{
   public static void main(String[] args)
   {
      ExceptTestFrame frame = new ExceptTestFrame();
      frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
      frame.setVisible(true);
   }
}

class ExceptTestFrame extends JFrame
{
   public ExceptTestFrame()
   {
      setTitle("ExceptTest");
      Container contentPane = getContentPane();
      ExceptTestPanel panel = new ExceptTestPanel();
 //*********Found********
      contentPane.add(panel);
      pack();
   }
}

class ExceptTestPanel extends Box
{
   public ExceptTestPanel()
   {
      super(BoxLayout.Y_AXIS);
      group = new ButtonGroup();
      addRadioButton("整数被零除", new
         ActionListener()
         {
     //*********Found********
            public void actionPerformed(ActionEvent event)
            {
               a[1] = 1 / (a.length - a.length);
            }
         });
      textField = new JTextField(30);
      add(textField);
   }

  //*********Found********
   private void addRadioButton(String s, ActionListener listener)
   {
      JRadioButton button = new JRadioButton(s, false)
         {
            protected void fireActionPerformed(ActionEvent event)
            {
               try
               {
                  textField.setText("No exception");
                  super.fireActionPerformed(event);
               }
               catch (Exception exception)
               {
     //*********Found********
                  textField.setText(exception.toString());
               }
            }
         };
      button.addActionListener(listener);
      add(button);
      group.add(button);
   }
   private ButtonGroup group;
   private JTextField textField;
   private double[] a = new double[10];

```

 contentPane  

 actionPerformed 

ActionListener

setText

## 28

### 基本操作

```java
public class Java_1 {
    public static void main(String args[]) {
        int x,n;
        
     //*********Found********
        n=0;
        for( x = 100 ; x <= 200 ; x++)
            if  ( x % 9 == 0 ) {
     //*********Found********
                System.out.print("  " + x);
                n++;
     //*********Found********
                if ( n%5==0) System.out.println( );
            }
    }
}

 

```

n=0

print

n%5==0

### 简单应用

```java
import java.io.*;
import java.util.Vector;

public class Java_2{
   public static void main(String s[]){
      Vector v=new Vector();
      try{
         //*********Found**********
         BufferedReader in = new BufferedReader(new InputStreamReader(System.in));    //键盘输入
         String str = "";
         System.out.println("请输入用户和密码信息，中间用空格隔开，输入quit退出:");
         while (!(str.equals("quit")||str.equals("QUIT"))){
            str = in.readLine();
            //*********Found**********
            if(isValid(str))      //验证输入是否有空格
               v.add(str);
            else{
               if(!(str.equals("quit")||str.equals("QUIT")))
                  System.out.println("The string is NOT valid!");
            }
         }
       
         System.out.println("请输入保存到的文件名:");
         //*********Found**********
         str=in.readLine();

         String curDir = System.getProperty("user.dir");
         File savedfile=new File(curDir+"\\"+str);
            
         //*********Found**********
         BufferedWriter out = new BufferedWriter(new FileWriter(savedfile));
         for(int i=0; i<v.size(); i++){
            String tmp=(String)v.elementAt(i);
            out.write(tmp);
            //*********Found**********
            out.write("\n");      //换行
         }
         out.close();
        
      }
      //*********Found**********
      catch(Exception e){
         System.out.print("ERROR:"+e.getMessage());
      }
   }
   /**
   * 判定输入的字符串是否符合规范
   * @param  s  输入的待校验的字符串
   * @return    校验的结果，正确则返回为真
   */
   public static boolean isValid(String s){
      if(s.indexOf(" ")>0) return true;
      else return false;
   }
}

```

 BufferedReader 

 str 

 in 

 savedfile 

"\n"

 catch 

### 综合应用

```java
//*********Found**********
import javax.swing.*;
import java.awt.event.*;
import java.awt.*;

//*********Found**********
public class Java_3 extends MouseAdapter implements ActionListener
{
   //*********Found**********
   private JPopupMenu pop;
   private JMenu subPop;
   private JMenuItem color;
   private JMenuItem exit;
   private JMenuItem red;
   private JMenuItem blue;
   private JTextArea textArea;
   private JFrame frame;

   public void initGUI()
   {
      pop=new JPopupMenu();
   
      subPop=new JMenu("color");
      red=new JMenuItem("red");
      red.addActionListener(this);
      blue=new JMenuItem("blue");
      blue.addActionListener(this);
      subPop.add(red);
      subPop.add(blue);

      exit=new JMenuItem("exit");
      exit.addActionListener(this);

      pop.add(subPop);
      pop.add(exit);

      //*********Found**********  
      frame=new JFrame("popup frame");
      textArea=new JTextArea("",10,10);

      textArea.addMouseListener(this);
      frame.getContentPane().add(textArea);
      frame.setSize(300,300);
      frame.setVisible(true);

      frame.addWindowListener(new WindowAdapter()
      {
         //*********Found**********  
         public void windowClosing(WindowEvent e)
         {
            System.exit(0);
         }
      });
   }

   public void actionPerformed(ActionEvent event)
   {
      if(event.getSource()==red)
      {
         textArea.setForeground(Color.red);
         textArea.setText("red menu is selected");
      }
      else if(event.getSource()==blue)
      {
         textArea.setForeground(Color.blue);
         textArea.setText("blue menu is selected");
      }
      else if(event.getSource()==exit)
   {
         frame.setVisible(false);
         System.exit(0);
      }
   }

   public void mousePressed(MouseEvent e)
   {
      if(e.getModifiers()==e.BUTTON3_MASK)
      {
         pop.show(e.getComponent(),e.getX(),e.getY());
      }
   }

   public static void main(String args[])
   {
      Java_3 example=new Java_3();
      example.initGUI();
   } 
}

```

swing

ActionListener

JpopupMenu

popup frame

 WindowEvent 

## 27

### 基本操作

```java
public class Java_1
{
   
   public static void main(String[] args)
   {
      long sum;
      //*********Found**********
      sum=0;
      for(int i=1;i<8;i+=2){
          long b=1;
          //*********Found**********
          for(int j=1; j<=i; j++) 
          //*********Found**********  
              b=b*j;
          System.out.println( i + "!= " + b);
          sum+=b;
      }
      System.out.println("sum=" + sum);
      
   }
}

```

sum=0

i

b= b* j

### 简单应用

```java
//*********Found**********
import javax.swing.*;
public class Java_2{
   public static void main( String args[] ){
      int frequency1 = 0, frequency2 = 0,
          frequency3 = 0, frequency4 = 0,
          frequency5 = 0, frequency6 = 0, face; 
      //骰子旋转500次的代码
      for ( int roll = 1; roll <= 500; roll++ ) {
         face = 1 + (int) ( Math.random() * 6 );
//*********Found**********
         switch ( face ) {
            case 1:
               ++frequency1;
               break;
            case 2:
               ++frequency2;
               break;
            case 3:
               ++frequency3;
               break;
            case 4:
               ++frequency4;
               break;
            case 5:
               ++frequency5;
               break;
            case 6:
               ++frequency6;
               break;
         }
      }
//*********Found**********
      JTextArea outputArea = new JTextArea( 7, 10 );
      outputArea.setText(
         "面\t频率" +
         "\n1\t" + frequency1 +
         "\n2\t" + frequency2 +
         "\n3\t" + frequency3 +
         "\n4\t" + frequency4 +
         "\n5\t" + frequency5 +
         "\n6\t" + frequency6 );
//*********Found**********
      JOptionPane.showMessageDialog( null, outputArea,
         "骰子旋转500次",
         JOptionPane.INFORMATION_MESSAGE );
//*********Found**********
      System.exit( 0 );
   }
}

```

swing

face

new

 outputArea  

exit

### 综合应用

```java
import java.awt.Graphics;
import javax.swing.JApplet;

//*********Found**********
public class Java_3 extends JApplet {
//*********Found**********
   public void paint(Graphics g){
      int counter = 1;
      do {
//*********Found**********
         g.drawOval( 110 - counter * 10, 110 - counter * 10,
                     counter * 20, counter * 20 );
//*********Found**********
         counter++;
      } while (counter<=10);
   }
}

 

```

JApplet

 Graphics 

g

 counter ++

## 26

### 基本操作

```java
public class Java_1
{
   //*********Found**********
   public static void main(String []args)
   {
      char ch='d';
   //*********Found**********
      switch(ch)
      { 
         case 'a': System.out.print("a");break;
         case 'b': System.out.print("b");
         case 'c': System.out.print("c");break;
         //*********Found**********
         default: System.out.print("abc");
      }
   } 
}
 

```

String

ch

 default 

### 简单应用

```java
//*********Found**********
import java.io.*;
import java.util.Vector;

public class Java_2
{
   public static void main(String args[])
   {
      Vector v=new Vector();
      try
      {
         //*********Found**********
         BufferedReader in = new BufferedReader(new InputStreamReader(System.in));
         String str = "";
         System.out.println("请输入用户和密码信息，中间用空格隔开，输入quit退出:");
         //*********Found**********
         while (!(str.equals("quit")||str.equals("QUIT")))
         {
            str = in.readLine();
            if(isValid(str))
               v.add(str);
            else 
            {
               if(!(str.equals("quit")||str.equals("QUIT")))
                  System.out.println("The string is NOT valid!");
            }
         }
        
         System.out.println("请输入保存到的文件名:");
         str=in.readLine();

         String curDir = System.getProperty("user.dir");
         File savedfile=new File(curDir+"\\"+   str   );
            
         BufferedWriter out = new BufferedWriter(new FileWriter(savedfile));
         for(int i=0; i<v.size(); i++)
         {
            String tmp=(String)v.elementAt(i);
         //*********Found**********
            out.write(tmp);
            out.write("\n");
         }
         out.close();
        
      }
      catch (Exception e)
      {
         System.out.print("ERROR:"+e.getMessage());
      }
   }

   /**
   * 判定输入的字符串是否符合规范
   * @param  s  输入的待校验的字符串
   * @return    校验的结果，正确则返回为真
   */
   public static boolean isValid(String s)
   {
      if(s.indexOf(" ")>0)
         return true;
      else
         return false;
   }
}

 

```

io

System.in

quit

tmp

### 综合应用

```java
import javax.swing.*;
import java.awt.event.*;
import java.awt.*;

//*********Found**********
public class Java_3 extends MouseAdapter implements ActionListener
{
//*********Found**********
   private JPopupMenu pop;
   private JMenu subPop;
   private JMenuItem color;
   private JMenuItem exit;
   private JMenuItem red;
   private JMenuItem blue;
   private JTextArea textArea;
   private JFrame frame;

   public void initGUI()
   {
      pop=new JPopupMenu();

      subPop=new JMenu("color");
      //*********Found**********
      red=new JMenuItem("red");
      red.addActionListener(this);
      blue=new JMenuItem("blue");
      blue.addActionListener(this);
      subPop.add(red);
      subPop.add(blue);

      exit=new JMenuItem("exit");
      exit.addActionListener(this);

      pop.add(subPop);
      pop.add(exit);

      frame=new JFrame("popup frame");
      textArea=new JTextArea("",10,10);

      textArea.addMouseListener(this);
      //*********Found**********
      frame.getContentPane().add(textArea);
      frame.setSize(300,300);
      frame.setVisible(true);

      frame.addWindowListener(new WindowAdapter()
      {
         public void windowClosing(WindowEvent e)
         {
            System.exit(0);
         }
      });
   }

   public void actionPerformed(ActionEvent event)
   {
      if(event.getSource()==red)
      {
         //*********Found**********
         textArea.setForeground(Color.red);
         textArea.setText("red menu is selected");
      }
      else if(event.getSource()==blue)
      {
         textArea.setForeground(Color.blue);
         textArea.setText("blue menu is selected");
      }
      else if(event.getSource()==exit)
      {
         frame.setVisib


etVisible(false);
         System.exit(0);
      }
   }

   public void mousePressed(MouseEvent e)
   {
      if(e.getModifiers()==e.BUTTON3_MASK)
      {
         pop.show(e.getComponent(),e.getX(),e.getY());
      }
   }

   public static void main(String args[])
   {
      Java_3 example=new Java_3();
      example.initGUI();
   } 
}

```

  MouseAdapter 

 JPopupMenu 

red

 textArea 

red

## 25

### 基本操作

```java
// 阅读下列代码：
public class Java_1
{
   //*********Found**********
   public static void main(String []args)
   {
      String s1=new String("你正在考试");
      String s2=new String("你正在考试");
      System.out.println(s1==s2);
      //*********Found**********
      System.out.println(s1.equals(s2));
   }
}

```

main

String

s1.equals

### 简单应用

```java
import java.io.File;
import java.io.FileReader;
import java.io.FileWriter;
import java.io.IOException;

public class Java_2
{
   public static void main(String args[])
   {
      if(args.length<2)
      {
         System.out.println("ERROR: need parameters.");    
         System.out.println("\n -usage: java <classname> <file1> <file2>");    
         System.exit(0);
      }
      File f1=new File(args[0]);
      //*********Found**********
      File f2=new File(args[1]);
      try
      {
         //*********Found**********
         FileReader fr=new FileReader(f2);
         FileWriter fw=new FileWriter(f1,true);
         int b;
         //*********Found**********
         while(( b=fr.read() ) != -1 )  fw.write(b);
         fr.close();
         fw.close();
      }
      catch(IOException e)
      {
         e.printStackTrace();
      }
      System.out.println("has done!");
      //*********Found**********
      if(f2.delete()) System.out.print("SUCCESS!");
   }
}

```

arg[1]

f2

b

 SUCCESS 

### 综合应用

```java
import javax.swing.*;
import java.awt.event.*;
import java.io.*;
import java.awt.*;

public class Java_3 implements ActionListener
{
   private JFrame frame;
   private JButton button;
   private JButton saveButton;
   private JTextArea textArea;
   private JFileChooser dia;
   private JPanel buttonPanel;

   public void initGUI()
   {
      //*********Found**********
      frame=new JFrame("file chooser");

      button=new JButton("open file");
      button.setActionCommand("open");
      //*********Found**********
      button.addActionListener(this);
      saveButton=new JButton("save file");
      saveButton.setActionCommand("save");
      //*********Found**********
      saveButton.addActionListener(this);

      textArea=new JTextArea("",10,10);
      buttonPanel=new JPanel();
      dia=new JFileChooser();
      frame.addWindowListener(new WindowAdapter()
      {
         public void windowClosing(WindowEvent e)
         {
            System.exit(0);
         }
      });
      buttonPanel.add(button);
      buttonPanel.add(saveButton);
      frame.getContentPane().add(buttonPanel,BorderLayout.NORTH);
      frame.getContentPane().add(textArea,BorderLayout.CENTER);
      frame.setSize(300,300);
      //*********Found**********
      frame.setVisible(true);
   }

   //*********Found**********
   public void actionPerformed(ActionEvent event)
   {
      if(event.getActionCommand().equals("open"))
      {
         dia.showOpenDialog( frame );
         dia.setVisible(true);
         File file=dia.getSelectedFile();
         String fileName=file.getAbsolutePath();
         textArea.append("path of selected file: "+fileName+"\r\n");
      }
      else if(event.getActionCommand().equals("save"))
     

 11:24:58
 {
         dia.showSaveDialog(frame);
         dia.setVisible(true);
         File file=dia.getSelectedFile();
         String fileName=file.getAbsolutePath();
         textArea.append("path of saved file: "+fileName+"\r\n");
      }
   }

   public static void main(String args[])
   {
      Java_3 example=new Java_3();
      example.initGUI();
   }
}
 

```

file choose

this

this

true

event

## 24

### 基本操作

```java
//*********Found**********
import javax.swing.*;

public class Java_1
{
   //*********Found**********
   public static void main(String[] args)
   {
      System.out.println();
      System.out.println("这是一个指定球半径，求球体积的程序。");
      String input=JOptionPane.showInputDialog("请输入球半径。");
      //*********Found**********
      double r=Double.parseDouble(input);
      System.out.println("当球的半径是" + r + "时，该球的体积是    " + (Math.PI*r*r*r*4/3));
      System.exit(0);
   }
}

 

```

javax

static

 input 



### 简单应用

```java
public  class  Java_2
{    
   public static void main(String[] args)
   {
      Thread t = new SimpleThread("Testing_Thread");
       //*********Found**********
      t.start() ;   
   }
} 
 //*********Found**********
class SimpleThread extends Thread
{
   public SimpleThread(String str)
   {
      //*********Found**********
      super(str);
   }
    //*********Found**********
   public void run()
   {  
      System.out.println("Running the " + getName() + ":");
      for (int i = 0; i < 5; i++)
      {
         System.out.println("---" + i + "---" + getName());
         try
         {
            sleep((int)(2 * 100));
         }
         //*********Found**********
         catch(InterruptedException e) { }
      }
   }
}

```

t.start()

Thread

super(str)

run

catch

### 综合应用

```java
import java.awt.event.*;
import java.awt.*;
import java.awt.font.*;
import java.awt.geom.*;
import javax.swing.*;

public class Java_3
{
   public static void main(String[] args)
   {
      FontFrame frame = new FontFrame();
      frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
      frame.setVisible(true);
   }
}

//*********Found**********
class FontFrame extends JFrame
{
   public FontFrame()
   {
      setTitle("北京 2008");
      setSize(DEFAULT_WIDTH, DEFAULT_HEIGHT);
      FontPanel panel = new FontPanel();
      Container contentPane = getContentPane();
      //*********Found**********
      contentPane.add(panel);
   }
   public static final int DEFAULT_WIDTH = 400;
   public static final int DEFAULT_HEIGHT = 250;
}

class FontPanel extends JPanel
{
   public FontPanel()
   {
      JButton yellowButton = new JButton("Yellow");
      JButton blueButton = new JButton("Blue");
      JButton redButton = new JButton("Green");
      add(yellowButton);
      add(blueButton);
      add(redButton);
      ColorAction yellowAction = new ColorAction(Color.YELLOW);
      ColorAction blueAction = new ColorAction(Color.BLUE);
      ColorAction greenAction = new ColorAction(Color.GREEN);
      yellowButton.addActionListener(yellowAction);
      blueButton.addActionListener(blueAction);
      redButton.addActionListener(greenAction);
   }
   public void paintComponent(Graphics g)
   {
      super.paintComponent(g);
      Graphics2D g2 = (Graphics2D)g;
      String message = "同一个世界，同一个梦想！

 11:16:59
Font f = new Font("隶书", Font.BOLD, 27);
      g2.setFont(f);
      FontRenderContext context = g2.getFontRenderContext();
      Rectangle2D bounds = f.getStringBounds(message, context);
      double x = (getWidth() - bounds.getWidth()) / 2;
      double y = (getHeight() - bounds.getHeight()) / 2;
      double ascent = -bounds.getY();
      double baseY = y + ascent;
      g2.setPaint(Color.RED);
      g2.drawString (message, (int)x, (int)(baseY));
   }
   //*********Found**********
   private class ColorAction implements ActionListener
   {
      public ColorAction(Color c)
      {
         BackgroundColor = c;
      }
      //*********Found**********
      public void actionPerformed (ActionEvent event)
      {
         setBackground(BackgroundColor);
      }
      private Color BackgroundColor;
   }
}

```

JFrame

 panel

impelements

actionPerformed

## 23

### 基本操作

```java
public class Java_1
{
   //*********Found**********
   public  static  void main (String args[])
   {
      new SimpleThread("第1").start();
      new SimpleThread("第2").start();
   }
} 

//*********Found**********
class SimpleThread extends Thread
{
   public SimpleThread(String str)
   {
      super(str);
   }
   public void run()
   {
      for (int i = 0; i < 5; i++)
      {
   //*********Found**********
         System.out.println(i + " " + getName());
         try
         {
            sleep((int)(2 * 100));
         }
         catch (InterruptedException e) { }
      }
      System.out.println("运行! " + getName());
   }
}
 

```

String

Thread

 getName 

### 简单应用

```java
import java.text.*;
public class Java_2
{
   public static void main(String[] args)
   {
      Person[] people = new Person[2];
      people[0] = new Worker("老张", 30000);
      people[1] = new Student("小王", "计算机科学");
      for (int i = 0; i < people.length; i++)
      {
         Person p = people[i];
         //*********Found**********
         System.out.println(p.getName() + ", " + p.getDescription());
      }
   }
}

//*********Found**********
abstract class Person
{
   public Person(String n)
   {
     name = n;
   }
//*********Found**********
   public abstract String getDescription();
   public String getName()
   {
     return name;
   }
   private String name;
}

//*********Found**********
class Worker extends Person
{
   public Worker(String n, double s)
   {
      super(n);
      salary = s;
   }
   public String getDescription()
   {
      NumberFormat formatter = NumberFormat.getCurrencyInstance();
      return "工人，年薪是 " + formatter.format(salary) + "。";
   }
   private double salary;
}

//*********Found**********
class Student extends Person
{
   public Student(String n, String m)
   {
      super(n);
      major = m;
   }
   public String getDescription()
   {
      return "学生，专业是 " + major + "。";
   }
   private String major;
}

ActionListener()
         {  
            public void actionPerformed(ActionEvent evt)
            {  
               int r = chooser.showOpenDialog(null);
               if(r == JFileChooser.APPROVE_OPTION)
               {  
          //*********Found**********
                  String name = chooser.getSelectedFile().getPath();
                  label.setIcon(new ImageIcon(name));
               }
            }
         });

```

p.getName

abstract

abstract

extends

### 综合应用

```java
import java.awt.*;
import java.awt.event.*;
import java.io.*;
import javax.swing.*;

public class Java_3
{
   public static void main(String[] args)
   {
      JFrame frame = new ImageViewerFrame();
      frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
      //*********Found**********
      frame.setVisible(true);
   }
}

class ImageViewerFrame extends JFrame
{
   private JLabel label;
   private JLabel labelT;
   private JFileChooser chooser;
   private JComboBox faceCombo;
   private static final int DEFAULT_SIZE = 24;
   public static final int DEFAULT_WIDTH = 570;
   public static final int DEFAULT_HEIGHT = 400;

   public ImageViewerFrame()
   {
      setTitle("ImageViewer");
      setSize(DEFAULT_WIDTH, DEFAULT_HEIGHT);
      label = new JLabel();
      Container contentPane = getContentPane();
      contentPane.add(label,BorderLayout.CENTER);
      chooser = new JFileChooser();
      chooser.setCurrentDirectory(new File("."));
      JMenuBar menuBar = new JMenuBar();
      setJMenuBar(menuBar);
      //*********Found**********
      JMenu menu = new JMenu("File");
      menuBar.add(menu);
      JMenuItem openItem = new JMenuItem("Open");
      //*********Found**********
      menu.add(openItem);
      openItem.addActionListener(new 


labelT = new JLabel("红军不怕远征难");
      labelT.setFont(new Font("隶书", Font.PLAIN, DEFAULT_SIZE));
      contentPane.add(labelT, BorderLayout.NORTH );
      faceCombo = new JComboBox();
      faceCombo.setEditable(true);
      faceCombo.addItem("隶书");
      faceCombo.addItem("华文新魏");
      faceCombo.addItem("华文行楷");
      faceCombo.addItem("华文隶书");
      faceCombo.addActionListener(new
         ActionListener()
         {  


public void actionPerformed(ActionEvent event)
            {
       //*********Found**********
               labelT.setFont(new Font((String)faceCombo.getSelectedItem(),
                  Font.PLAIN, DEFAULT_SIZE));
            }
         });
      JPanel comboPanel = new JPanel();
      comboPanel.add(faceCombo);
      contentPane.add(comboPanel, BorderLayout.SOUTH);
   }
}
 

 

```

true

File

 menu

 chooser 

 faceCombo 

## 22

### 基本操作

```java
public class Java_1 extends TT
{
   //*********Found**********
   public static void main(String args[])
   {
      Java_1 t = new Java_1("小龙");
   }
   public Java_1(String s)
   {
      super(s);
      System.out.println("您好吗？");
   }
   public Java_1()
   {
      this("我是文朋");
   }
}

class TT
{
   public TT()
   {
      System.out.println("多高兴啊!");
   }
   public TT(String s)
   {
   //*********Found**********
      this();
      System.out.println("我是"+s);
   }
}
 

```

main

String

this()

### 简单应用

```java
public class Java_2
{
   public static void main(String[] args)
   {
      System.out.println("观察triple方法参数 double 10.0 的改变：");
      //*********Found**********
      double canshu = 10;
      //*********Found**********
      System.out.println("参数*３前，参数值为 " +canshu);
      triple(canshu);
      System.out.println("在triple方法外，参数值仍为 " + canshu);
      System.out.println("思考：方法能否改变参数值？");
   }
  //*********Found**********
   public static void triple(double x)
   {
      //*********Found**********
      x=3*x;
      //*********Found**********
      System.out.println("在triple方法内，参数 10 变为 " + x);
   }
}

```

double

canshu

triple

x =x * 3

x

### 综合应用

```java
import java.awt.*;
import javax.swing.*;

//*********Found**********
public class Java_3 extends JApplet
{
   //*********Found**********
   public void init ()
   {
      Container contentPane = getContentPane();
      JLabel label = new JLabel("One World  One Dream",SwingConstants.CENTER);
      label.setFont(new Font("Arial", Font.BOLD, DEFAULT_SIZE));
      //*********Found**********
      contentPane.add(label);
   }
   private static final int DEFAULT_SIZE = 24;
}
 

```

JApplet

init

contentPane

## 21

### 基本操作

```java
import javax.swing.JOptionPane;
public class Java_1 {
   public static void main( String args[] ){
      //变量初始化
      int passes = 0,             //考生通过的数目
          failures = 0,           //考生不通过的数目
          student = 1,            //学生计数器
          result;                 //一门考生结果
      String input,               //用户输入的值
             output;              //输出字符串
      //处理10名学生,用计数器控制循环
      while ( student <= 10 ) {
         input = JOptionPane.showInputDialog(
                    "输入结果(1=通过,2=不通过)" );
//*********Found**********
         result = Integer.parseInt( input);
         if ( result == 1 )
            passes = passes + 1;
         else
            failures = failures + 1;
         student = student + 1;
      }
      //结果处理
      output = "通过: " + passes +
               "\n不通过: " + failures;
      if( passes > 8 )
         output = output + "\n提高学费";
//*********Found**********
      JOptionPane.showMessageDialog( null, output,
         "对考试结果的分析示例",
         JOptionPane.INFORMATION_MESSAGE );     
//*********Found**********
      System.exit( 0 );
   }
}

```

input

 showMessageDialog 

exit

### 简单应用

```java
import java.util.*;
public class Java_2
{  
   public static void main(String[] args)
   {
      Student[] java = new Student[3];
      java[0] = new Student("李明", 80);
      java[1] = new Student("赵冬", 75);
      java[2] = new Student("王晓", 98);
      //*********Found**********
      Arrays.sort(java);
      System.out.println("Java 成绩降序排序的结果是：");
      for (int i = 0; i < java.length; i++)
      {
         Student e = java[i];
      //*********Found**********
         System.out.println("name=" + e.getName()
            + ",fenshu=" + e.getFenshu());
      }
   }
}

//*********Found**********
class Student implements Comparable
{
   public Student(String n, double f)
   {
      name = n;
      fenshu = f;
   }
   public String getName()
   {
      return name;
   }
   public double getFenshu()
   {
      return fenshu;
   }
   public int compareTo(Object otherObject)
   {
      Student other = (Student)otherObject;
      if (fenshu < other.fenshu) return 1;
      if (fenshu > other.fenshu) return -1;
      return 0;
   }
   private String name;
   //*********Found**********
   private double fenshu;
}

```

java

getName()

implements

double

### 综合应用

```java
import java.io.*;
public class Java_3
{
   public static void main(String[] args)
   {
      Java_3 exceptionExample = new Java_3();
     //*********Found**********
      try
      {
         FileInputStream fi = new FileInputStream("C:" + "\\" + "abc.txt");
      }
  //*********Found**********
      catch (FileNotFoundException ex)
      {
  //*********Found**********
         System.out.println(ex.getMessage()+
         "请确认文件路径及文件名是否正确！");
      }
   }
}

```

try

catch

ex

## 20

### 基本操作

```java
public class Java_1 {
      public static void main(String[] args) {
        //*********Found********
        int []f=new int[10];
        f[0]=f[1]=1;
        //*********Found********
        for (int i=2;i<10;i++)
            f[i]=f[i-1]+f[i-2];
        //*********Found********
        for (int i=0;i<f.length;i++)
        //*********Found********
            System.out.print(f[i]+"  ");
    }
 

```

new int

int i = 2

length

f[i]

### 简单应用

```java
public class Java_2{
   public static void main(String[] args){
      //*********Found**********
      int [][]aMatrix = new int[4][];
      int i = 0;
      int j = 0;
      int k = 4;

      for(i = 0; i < 4; i++){
         //*********Found**********
         aMatrix[i] = new int[k--];
 
         //*********Found**********
         for (j = 0; j < aMatrix[i].length; j++) {
            aMatrix[i][j] = i+1;
            System.out.print(aMatrix[i][j] + " ");
         }
         //*********Found**********
         System.out.println();
      }
   }
}
}

 

```

[] []

k-

aMatrix [i]

println()

### 综合应用

```java
import java.awt.*;
import java.awt.event.*;
import javax.swing.*;

public class Java_3 extends JFrame {
   public Java_3(){
      super( "打印无符号整数位" );
      Container c = getContentPane();
      c.setLayout( new FlowLayout() );
      c.add( new JLabel( "请输入整数: " ) );
      final JTextField output = new JTextField( 33 );
      JTextField input = new JTextField( 10 );
      input.addActionListener(
         new ActionListener() {
            //*********Found********
            public void actionPerformed( ActionEvent e ){
               int val = Integer.parseInt(
                  e.getActionCommand() );
               //*********Found********
               output.setText( getBits( val ) );
            }
         }
      );
      c.add( input );
      c.add( new JLabel( "该数的二进制位表示是" ) );      
      output.setEditable( false );
     //*********Found********
      c.add( output);
      setSize( 720, 70 );
      setVisible(true);
   }

   private String getBits( int value ){
      int displayMask = 1 << 31;
      StringBuffer buf = new StringBuffer( 35 );
      for ( int c = 1; c <= 32; c++ ) {
         buf.append(
            ( value & displayMask ) == 0 ? '0' : '1' );
         value <<= 1;
         if ( c % 8 == 0 )
            buf.append( ' ' );
      }
      return buf.toString();
   }

   public static void main( String args[] ){
      Java_3 app = new Java_3();
      app.addWindowListener(
         new WindowAdapter() {
     //*********Found********
            public void windowClosing( WindowEvent e ){
               System.exit( 0 );
            }
         }
      );
   }
}

 

```

actionPerformed

output  

 output  

windowEvent

## 19

### 基本操作

```java
public class Java_1 {

    public static void main(String[] args) {
        int []a = {5,9,2,8,7};
        int max = 0;
        int k = 0,t ;
        for(int i=0;i<5;i++){
          //*********Found********
            if (a[i]%2==0 && max < a[i]){
                max = a[i];
          //*********Found********
                k=i;
            }
        }
        t = a[0];
        a[0] = a[k];
        a[k] = t;
        //*********Found********
        for(int i=0;i<a.length;i++)
            System.out.print(a[i] + "  ");
    }
}

```

%2==0

k=i

length 

### 简单应用

```java
import java.awt.*;
import java.awt.event.*;
import java.util.Vector;

import javax.swing.*;
import javax.swing.event.*;
import javax.swing.table.*;

//*********Found********
public class Java_2 implements ActionListener{
JTable table = null;
DefaultTableModel defaultModel = null;

        //*********Found********
        public Java_2(){
JFrame f = new JFrame();
String[] name = {"字段 1","字段 2","字段 3","字段 4","字段 5"};
String[][] data = new String[5][5];
                int value =1;
for(int i=0; i<data.length; i++){
for(int j=0; j<data.length ; j++)
data[i][j] = String.valueOf(value++);
}
defaultModel = new DefaultTableModel(data,name);
table=new JTable(defaultModel);
table.setPreferredScrollableViewportSize(new Dimension(400, 80));
JScrollPane s = new JScrollPane(table);

JPanel panel = new JPanel();
JButton b = new JButton("增加行");
panel.add(b);

//*********Found********
       b.addActionListener(this);
b = new JButton("删除行");
panel.add(b);
b.addActionListener(this);

//*********Found********
                Container contentPane = f.getContentPane();
contentPane.add(panel, BorderLayout.NORTH);
contentPane.add(s, BorderLayout.CENTER);

//*********Found********
f.setTitle("增删表格行");
f.pack();
f.setVisible(true);

f.addWindowListener(new WindowAdapter() {
public void windowClosing(WindowEvent e) {
System.exit(0);
}
});
//*********Found********
table.addMouseListener(new MouseAdapter() {
public void mouseClicked(MouseEvent e) {
if(table.isCellSelected(table.getSelectedRow(), table.getSelectedColumn())){
int selRow=table.getSelectedRow();
int selCol=table.getSelectedColumn();
JOptionPane.showMessageDialog(null, 
"位于 ("+selRow+","+selCol+")的元素： "+table.getValueAt(selRow,selCol), 
"PLAIN_MESSAGE", JOptionPane.PLAIN_MESSAGE);
}
}
  });
}
public void actionPerformed(ActionEvent e){
if(e.getActionCommand().equals("增加行"))    
defaultModel.addRow(new Vector());
if(e.getActionCommand().equals("删除行")
int rowcount = defaultModel.getRowCount()-1; //getRowCount返回行数，rowcount<0代表已经没有任何行了。
if(rowcount >= 0){
defaultModel.removeRow(rowcount);
defaultModel.setRowCount(rowcount);
}
}
table.revalidate();
}

public static void main(String[] args) {
new Java_2();
}
}

```

implements

Java_2

addActionListener

 getContentPane 

 setTitle 

 addMouseListener 

### 综合应用

```java
import java.io.*;
import java.lang.Thread;

class MyThread extends Thread{
   public int x = 0;
//*********Found********
   public void run(){
    System.out.println(++x);
  }
}
//*********Found********
class RThread implements Runnable{
   private int x = 0;
   public void run(){
        System.out.println(++x);
  }
}

public class Java_3 {
  public static void main(String[] args) throws Exception{
    for(int i=0;i<5;i++){
       Thread t = new MyThread();
//*********Found********
       t.start();
    }
    Thread.sleep(1000);
    System.out.println();
//*********Found********
    RThread r = new RThread();
//*********Found********
    for(int i=0;i<5;i++){
       Thread t = new Thread(r);
       t.start();
    }
  }
}

 

```

run

 Runnable 

start

 RThread 

5

## 18

### 基本操作

```java
public class Java_1 {
    //*********Found********
    public static void main(String args[]) {
        int arr[][] = {{1, 2, 3, 4, 5}, {6, 7, 8, 9, 10}, {11, 12, 13, 14, 15}, {16, 17, 18, 19, 20}, {21, 22, 23, 24, 25}};
        //*********Found********
        int i, j, sum=0;
        for (i = 0; i < 5; i++) 
            for (j = 0; j < 5; j++) 
                //*********Found********
                if (i+j==4) 
                    sum += arr[i][j];
        System.out.println(sum);
    }
}

```

sum=0

i+j

### 简单应用

```java
import java.io.*;

public class Java_2 {
    public static void main(String args[]) {
        String ShowMes[] = {"在那山的那边海的那边有一群蓝精灵", "它们活泼又聪明它们调皮又灵敏", "它们自由自在生活在那绿色的大森林", "它们善良勇敢相互都欢喜！"};
        try {
            //*********Found********
            FileWriter out = new FileWriter(new File("test.txt"));
            BufferedWriter outBW = new BufferedWriter(out);
            for (int i = 0; i < ShowMes.length; i++) {
                outBW.write(ShowMes[i]);
                outBW.newLine();
            }
            //*********Found********
            outBW.close();
        } catch (Exception e) {
            e.printStackTrace();
        }
        try {
            //*********Found********
            FileReader in = new FileReader(new File("test.txt"));
            BufferedReader inBR = new BufferedReader(in);
            String stext = null;
            int j = 1;
            while ((stext = inBR.readLine()) != null) {
                System.out.println("第" + j + "行内容：" + stext);
                //*********Found********
                j++;
            }
            inBR.close();
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}

```

"test.txt"

close

 FileReader  

j++

### 综合应用

```java
import java.awt.*;
import java.awt.event.*;
import java.io.*;
import javax.imageio.*;
import javax.swing.*;

public class Java_3 extends JFrame {
    private JLabel label;
    private JFileChooser fileChooser;
    private ImagePanel panel;
    public Java_3() {
        setTitle("图片浏览器");
        setSize(500, 400);
        fileChooser = new JFileChooser();
        fileChooser.setCurrentDirectory(new File("."));//设置默认路径为当前目录
        JMenuBar menuBar = new JMenuBar();
        setJMenuBar(menuBar);
        JMenu menu = new JMenu("文件");
        menuBar.add(menu);
        JMenuItem openItem = new JMenuItem("打开图片");
        menu.add(openItem);
        panel = new ImagePanel();
        add(panel);
        //*********Found********
        openItem.addActionListener(new ActionListener(){
            public void actionPerformed(ActionEvent event){
                int result = fileChooser.showOpenDialog(null);
                if(result==JFileChooser.APPROVE_OPTION){
                    String name = fileChooser.getSelectedFile().getPath();
                    //*********Found********
                    panel.setImage(name);
                    panel.repaint();
                }
            }
        });
        JMenuItem exitItem = new JMenuItem("退出图片");
        menu.add(exitItem);
        exitItem.addActionListener(new ActionListener(){
            public void actionPerformed(ActionEvent event){
                System.exit(0);
        });        
    }
    

    public static void main(String[] args) {
        //*********Found********
        Java_3 frame = new Java_3 ();
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        //*********Found********
        frame.setVisible(true);
    }
}

//*********Found********
class ImagePanel extends JPanel {
    private Image image;
    private int showWidth;
    private int showHeight;
    public void setImage(String fileName) {
        try {
            image = ImageIO.read(new File(fileName));
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
public void paintComponent(Graphics g) {
        super.paintComponent(g);
        if (image == null)
            return;
        int imageWidth = image.getWidth(this);
        int imageHeight = image.getHeight(this);
        int width = getWidth();
        int height = getHeight();
        if(imageWidth>width){
            this.showWidth = width;
        }else{
            this.showWidth = imageWidth;
        }
        if(imageHeight>height){
            this.showHeight = height;
        }else{
            this.showHeight = imageHeight;
        }
        g.drawImage(image, 0, 0, showWidth, showHeight, null, null);
    }
}

```

 addActionListener 

 name  

new

setVisible

  JPanel  

## 17

### 基本操作

```java
public class Java_1{
 
    public static void main(String[] args){

        //*********Found********
        int[] ages = {35,43,28,39,62,57,48,29,54,46}; 
        int sum = 0, avg = 0; 
        int tt = 0,fot = 0,fit = 0,st = 0; 

        for (int i=0; i<ages.length; i++){
            if (ages[i] <=40 )
                tt++;
            else if (ages[i] >40 && ages[i]<=50)
                fot++;
            else if (ages[i] >50 && ages[i]<=60)
                //*********Found********
                fit++;
            else 
                st++;
        }
   
        //*********Found********
        for (int i=0; i<ages.length; i++)
            //*********Found********
            sum += ages[i];
        avg = sum/ages.length;

        System.out.println("<=40: "+tt+"     41-50: " +fot+"     51-60: " 
                            + fit +"     >=61: " + st);
    }
}

```

int[]

 fit++

int

arg[i]

### 简单应用

```java
//*********Found********
import  java.awt.*;
import java.io.*;
import java.awt.event.* ;
import javax.swing.*;

//*********Found********
public class Java_2 implements ActionListener{ 
   
    JTextArea ta;
    JFrame f ;
    JLabel label;
    JButton bt;

    public static void main(String args[ ]){
        Java_2 t = new Java_2();
        t.go();
    }

    void go(){
        f = new JFrame("Save data");
        label = new JLabel("请输入需要保存的文本：");
        ta = new JTextArea(3,20);
        bt = new JButton("保存");
        //*********Found********
        f.add(label,BorderLayout.NORTH);
        f.add(ta,BorderLayout.CENTER);
        f.add(bt,BorderLayout.SOUTH);
        //*********Found********
        bt.addActionListener(this);
        f.setSize(400,400);
        f.pack( );
        f.setVisible(true) ;
        f.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
    }

    public void actionPerformed(ActionEvent event){
        try{
            FileWriter  out = new FileWriter("out.txt");
            String str = ta.getText();
            //*********Found********
            out.write(str);  
            out.close();
        } catch( Exception e){
        }
    }    
}
 

```

java.awt.*

implements ActionListener

BorderLayout.NORTH

addActionListener

out.write

### 综合应用

```java
//*********Found********
public class Java_3 extends Thread{
    static RegistrationAgent agent;
    static boolean timetoquit=false;

    public static void main(String[] args){
        agent = new RegistrationAgent();
        Thread[] t= new Thread[3];
        for (int i=0; i<3; i++){
            t[i] = new Java_3();
            //*********Found********
           t[i].start();
        }
    }

    public void run( ){   
        //*********Found********
        while (!timetoquit){
            boolean r = agent.reg();  
            if (!r) 
                timetoquit = true;
            try{
                Thread.sleep(2);
            }catch(Exception e){}
        }
    }
}

class RegistrationAgent {
    private int quota = 0;
    public boolean reg(){
        synchronized(this){
            if( quota < 10){
                //*********Found********
                quota++;
                System.out.print(Thread.currentThread().getName());
                System.out.println( " Registered one student, and total " + quota 
                                   +" students registered.");
                return true;
            }
            else
                //*********Found********
                return false;
        }
    } 
}

 

```

extends Thread

 t[i].start() 

! timetoquit 

 quota++ 

 return false 

## 16

### 基本操作

```java
public class Java_1 {

    public static void main(String args[]) {
        int a[][] = {{2, 3, 4}, {4, 6, 5}};
        int b[][] = {{1, 5, 2, 8}, {5, 9, 10, -3}, {2, 7, -5, -18}};
        int c[][] = new int[2][4];
        for (int i = 0; i < 2; i++) {
            for (int j = 0; j < 4; j++) {
                //*********Found********
                c[i][j] = 0;
                //*********Found********
                for (int k = 0; k < 3; k++) 
                    //*********Found********
                    c[i][j]+=a[i][k]*b[k][j];
                System.out.print(c[i][j] + "  ");
            }
            System.out.println();
        }
    }
}
 

```

=0

=0

<3

+=

### 简单应用

```java
public class Java_2{

    public static void main(String args[]) {
        SubClass subC = new SubClass();
        subC.doSomething();
    }
}
class SuperClass {

    int x;

    SuperClass() {
        //*********Found********
        x =3;
        System.out.println("in SuperClass : x=" + x);
    }

    void doSomething() {
        //*********Found********
        System.out.println("in SuperClass.doSomething()");
    }
}

class SubClass extends SuperClass {

    int x;

    SubClass() {
        super();
        //*********Found********
        x =5;
        System.out.println("in SubClass  :x=" + x);
    }

    void doSomething() {
        super.doSomething();
        //*********Found********
        System.out.println("in SubClass.doSomething()");
        System.out.println("super.x=" + super.x + "  sub.x=" + x);
    }
}

```

3

in SuperClass.doSomething()

5

in SubClass.doSomething()

### 综合应用

```java
import javax.swing.*;
//*********Found********
import java.awt.event.*;
import java.io.*;
import java.awt.*;

//*********Found********
public class Java_3 implements ActionListener{
    JFrame f;
    JTextArea ta;
    //*********Found********
    JFileChooser fc;
    Container c;
    File myFile;

    public static void main(String args[]){
        Java_3 demo = new Java_3();
        demo.go();
    }
    void go(){
        f = new JFrame("File Chooser Demo");
        //*********Found********
        JButton b = new JButton("Open File");
        ta = new JTextArea("Where is your file path?",10,30);
        //*********Found********
        b.addActionListener(this);
        c = f.getContentPane();
        f.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        //*********Found********
        f.getContentPane().add("South", b);
        f.getContentPane().add("Center",ta);
        f.setSize(300,300);
        f.setVisible(true);
    }

    public void actionPerformed(ActionEvent e){
        fc = new JFileChooser();
        int selected = fc.showOpenDialog(c); 
        if (selected==JFileChooser.APPROVE_OPTION){
            myFile = fc.getSelectedFile();
            ta.setText("You have selected file: "+ myFile.getName());
        }
    }
}

 

```

event

ActionListener

fc

Open File

this

b

## 15

### 基本操作

```java
public class Java_1 {
    public static void main(String[] args) {
        int a,x = 2008;
        //*********Found**********
        System.out.print(  x +" -> ");
        while( x != 0 ){
            //*********Found**********
            a = x%10;
            System.out.print(a);
            //*********Found**********
            x = x/10;
        }
    }
}

```

 +" -> " 

 x%10 

 x/10 

### 简单应用

```java
//*********Found**********
public class Java_2 extends Thread{
    private String sThreadName; 
    public static void main(String argv[]){
        Java_2 first = new Java_2("first");
        //*********Found**********
        first.start();
        Java_2 second = new Java_2("second");
        //*********Found**********
        second.start();
    }
    
    //*********Found**********
    public Java_2 (String s){
        sThreadName = s;
    }
    
    public String getThreadName(){
        return sThreadName;
    }

    public void run(){
        for(int i = 0; i < 4; i ++){
            //*********Found**********
            System.out.println(getThreadName()+i);
            try{
                 Thread.sleep(100);
            } catch(InterruptedException e){
            System.out.println(e.getMessage());
            }
        }
    }
}
 

```

extends Thread

start()

start()

 Java_2  

 getThreadName()

### 综合应用

```java
import javax.swing.*;
import java.awt.event.*;
import java.io.*;
import java.awt.*;

//*********Found**********
public class Java_3 implements ActionListener{
    JFrame f;
    JPanel p;
    JColorChooser cc;
    Container c;
    Color myColor;
    JMenuBar mb;
    JMenu m1;
    JMenuItem mi1;
    public static void main(String args[]){
        Java_3 demo=new Java_3();
        demo.go();
    }
    void go(){
        JFrame f=new JFrame("File Chooser Demo");
        mb=new JMenuBar();
        f.setJMenuBar(mb);
        //*********Found**********
        m1=new JMenu("Edit");
        mb.add(m1);
        mi1=new JMenuItem("Choose Color");
        m1.add(mi1);
        //*********Found**********
        mi1.addActionListener(this);
        c=f.getContentPane();
        f.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        p=new JPanel();
        myColor=Color.red;
        p.setBackground(myColor);
        c.add("Center",p);
        f.setSize(300,300);
        f.setVisible(true);
    }

    public void actionPerformed(ActionEvent e){
        cc=new JColorChooser();
        //*********Found**********
        myColor=cc.showDialog(c,"Choose window background color",Color.white); 
        p.setBackground(myColor);
    }
}

```

ActionListener

Edit

this

 Choose window background color 

## 14

### 基本操作

```java
public class Java_1 {
    public static void main(String[] args) {
        //*********Found**********
        for (int i=1;i<=5;i++){
            for(int k=1;k<=5-i;k++)
                //*********Found**********
                System.out.print(" ");
            //*********Found**********
            for(int j=1;j<=2*i-1;j++)
                System.out.print("*");
            //*********Found**********
            System.out.println();
        }
    }

```

i<=5

 System.out.print(" ") 

System.out.println()

### 简单应用

```java
import java.io.*;
 
public class Java_2 {
    public static void main(String[] args) {
        ObjectOutputStream oos = null;
        ObjectInputStream ois = null;
        try { 
            File f = new File("Person.dat");
            //*********Found**********
            oos = new ObjectOutputStream(new FileOutputStream(f));
            oos.writeObject(new Person("小王"));
            oos.close();
            ois = new ObjectInputStream(new FileInputStream(f));
            //*********Found**********
            Person d = (Person) ois.readObject();
            System.out.println(d);
            ois.close();
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
//*********Found**********
class Person implements Serializable{
    String name = null;
    public Person(String s) {
        name = s;
    }
    //*********Found**********
    public String toString() {
        return name;
    }
}

```

 FileOutputStream 

 readObject 

 Serializable 

 toString 

### 综合应用

```java
import java.awt.*;
import java.awt.event.*;
import javax.swing.*;

public class Java_3 {
    public static void main(String[ ] args) {
        JFrame frame = new JFrame("Demo");
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);

        //*********Found**********
        frame.getContentPane().add(new Change());

        frame.pack();
        //*********Found**********
        frame.setVisible(true);
    }
}

class Change extends JPanel{

    int count = 200;
    JLabel l1;
    JButton b1, b2;

    public Change() {
        setPreferredSize(new Dimension(280, 60));
        l1 = new JLabel("200");
        b1 = new JButton("增大");
        b2 = new JButton("减小");
        add(l1);
        add(b1);
        add(b2);
        b1.addActionListener(new BListener1());
        //*********Found**********
        b2.addActionListener(new BListener2());
    }

    private class BListener1 implements ActionListener {

        public void actionPerformed(ActionEvent e) {
            count++;
            l1.setText("" + count);
        }
    }
    private class BListener2 implements ActionListener {

        public void actionPerformed(ActionEvent e) {
            //*********Found**********
            count--;
            l1.setText("" + count);
        }
    }
}

 

```

add

true

 BListener2

--

## 13

### 基本操作

```java
class MethodOverloading {
void receive(int i) {
    System.out.println("Receive one int data");
    System.out.println("i=" + i);
}

//*********Found**********
void receive(int x, int y) {
    System.out.println("Receive two int data");
    System.out.println("x=" + x + "  y =" + y);
}
//*********Found**********
void receive(double d) {
    System.out.println("Receive one double data");
    System.out.println("d=" + d);
}

//*********Found**********
void receive(String s) {
    System.out.println("Receive a string");
    System.out.println("s="+s);
}
}

public class Java_1 {
public static void main(String args[]) {
    MethodOverloading mo = new MethodOverloading();
    mo.receive(1);
    mo.receive(2, 3);
    mo.receive(12.56);
    mo.receive("very interesting, is not it?");
}
}
```

int

int

d

s

### 简单应用

```java
public class Java_2 {
public static void main(String args[]) {
int [][]a = {{2, 3, 4}, {4, 6, 5}};
int [][]b = {{1, 5, 2, 8}, {5, 9, 10, -3}, {2, 7, -5, -18}};
//Found
int [][]c = new int[2][4];
for (int i = 0; i < 2; i++) {
//Found*
for (int j = 0; j < b[i].length; j++) {
//Found*
c[i][j]=0;
for (int k = 0; k < 3; k++)
//Found*
c[i][j] += a[i][k]*b[k][j];
System.out.print(c[i][j] + " ");
}
System.out.println();
}
}
}

```

 new int[2] [4]

4

c[i] [j] =0

a[i] [j] * b[i] [j]

### 综合应用

```java
//Found*
import javax.swing.;
import java.awt.event.;
import java.io.;
import java.awt.;

//Found*
public class Java_3 implements ActionListener {
JFrame f;
JPanel p;
JColorChooser cc;
Container c;
Color myColor;
JMenuBar mb;
JMenu m1;
JMenuItem mi1;

public static void main(String args[]) {
    Java_3 demo = new Java_3();
    demo.go();
}

void go() {
    JFrame f = new JFrame("File Chooser Demo");
    mb = new JMenuBar();
    f.setJMenuBar(mb);
    m1 = new JMenu("Edit");
    mb.add(m1);
    mi1 = new JMenuItem("Choose Color");
    m1.add(mi1);
    mi1.addActionListener(this);
    //*********Found**********
    c = f.getContentPane();
    f.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
    p = new JPanel();
    myColor = Color.red;
    p.setBackground(myColor);
    c.add("Center", p);
    f.setSize(300, 300);
    //*********Found**********
    f.setVisible(true);
}

public void actionPerformed(ActionEvent e) {
    //*********Found**********
    cc = new JColorChooser();
    myColor = cc.showDialog(c, "Choose window background color", Color.white);
    p.setBackground(myColor);
}
```

swing

ActionListener

f

true

 JColorChooser  

## 12

### 基本操作

```java
//*********Found**********
public class Java_1{
    public static void main(String[] args){
        int []a = {1,2,3,4,5,6,7,8};
        int []b = {0,1,2,3,4,5,6,7};
        int []c = new int[8];
        int s=0;
        
        //*********Found**********
        for(int i=0;i<a.length;i++)
            c[i]=a[i]+b[i];
        for(int j=c.length-1;j>=0;j--)
            //*********Found**********
            s=s+c[j];
        //*********Found**********
        System.out.println("s="+s);
    }
}

```

class

length

c[j]

out

### 简单应用

```java
public class Java_2 {
    public static void main(String[ ] args) {
        //*********Found**********
        Point[] pt = new Point[2];
        pt[0] = new Point();
        pt[1] = new Point(2, 3);
        //*********Found**********
        for (int i=0; i < pt.length; i++) {
            System.out.print( pt[i] );
        }
    }
}

class Point {

    private int x;
    private int y;

    public Point() {
        this(0, 0);
    }

    //*********Found**********
    public Point (int a, int b) {
        x = a;
        y = b;
    }

    int getX( ) {
        return x;
    }

    int getY( ) {
        //*********Found**********
        return y;
    }

    void setX(int a) {
        x = a;
    }

    void setY(int b) {
        y = b;
    }

    public String toString ( ) {
        return "  ( " + x + "," + y + " ) ";
    }
}

```

Point[]
length

Point

y

### 综合应用

```java
import java.io.*;
import java.awt.event.* ;
import javax.swing.*;

//*********Found**********
public class Java_3 implements ActionListener{
  public static void main(String args[]){
    Java_3 t = new Java_3();
    JFrame f = new JFrame("Test");
    JButton b = new JButton("复制文件");
    b.setSize(100,40);
    //*********Found**********
    b.addActionListener (t);   //注册监听器
    f.setSize(400,400);
    f.getContentPane().add(b);
    f.pack();
    f.setVisible(true) ;
    f.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
  }

  public void actionPerformed(ActionEvent event){
    try{
      //*********Found**********
      FileInputStream in=new FileInputStream("a.txt");
      //*********Found**********
      FileOutputStream out=new FileOutputStream("b.txt"); 
      int c;
      while ((c = in.read()) != -1)
        out.write(c);
      in.close();
      out.close();
    } catch( Exception e){
    }
  }    
}

```

JFrame

b

new FileInputStream  

new FileOutputStream  

## 11

### 基本操作

```java
public class Java_1{
  public static void main(String[] args){
    //*********Found**********
    int[]  scores = {90,80,75,67,53}; 
    int best = 0; 
    char grade; 

    // 找出这组成绩中的最高分
    //*********Found**********
    for (int i=0;i<=4; i++){
      //*********Found**********
      if (scores[i]>best)
        best = scores[i];
    }
 
    //求各分数的等级并显示
    for (int i=0; i<scores.length; i++){
      if (scores[i] >= best - 10)
        grade = 'A';
      //*********Found**********
      else if (scores[i] >= best - 20)
        grade = 'B';
      else if (scores[i] >= best - 30)
        grade = 'C';
      else if (scores[i] >= best - 40)
        grade = 'D';
      else
        grade = 'F';
      System.out.println("Student " + i + " score is " + scores[i] +
        " and grade is " + grade);
    }
  }
}

```

int[]

i<=4

scores[i] > best

else if



### 简单应用

```java
public class Java_2 {
    public static void main(String[ ] args) {
        Point pt;
        //*********Found**********
        pt = new Point(2, 3);
        System.out.println(pt);
    }
}

class Point {

    //*********Found**********
    private int x;
    private int y;

    //*********Found**********
    public Point (int a, int b) {
        x = a;
        y = b;
    }

    int getX( ) {
        return x;
    }

    int getY( ) {
        return y;
    }

    void setX(int a) {
        x = a;
    }

    void setY(int b) {
        y = b;
    }

    //*********Found**********
    public String toString ( ) {
        return "( " + x + "," + y + " ) ";
    }
}

```

new

int x

Point

toString

### 综合应用

```java
import java.awt.*;
import java.awt.event.*;    
//*********Found**********
import javax.swing.*;
   
//*********Found**********
public class Java_3 extends JPanel{     
   
  private int counter = 0;    
   
  private JButton closeAllButton;    
   
  public Java_3() {    
    JButton newButton = new JButton("New");    
    //*********Found**********
    add(newButton);
    newButton.addActionListener(new ActionListener(){
      public void actionPerformed(ActionEvent evt){
        CloseFrame f = new CloseFrame();    
        counter++;    
        f.setTitle("窗体 " + counter);    
        f.setSize(200, 150);    
        f.setLocation(30 * counter, 30 * counter);    
        //*********Found**********
        f.setVisible(true);    
        closeAllButton.addActionListener(f); 
      }  
    });
        
    closeAllButton = new JButton("Close all");    
    add(closeAllButton);    
  }      
   
  public static void main(String[ ] args) {    
    JFrame frame = new JFrame();    
    frame.setTitle("多窗体测试");    
    frame.setSize(300, 200);    
    frame.addWindowListener(new WindowAdapter() {    
      public void windowClosing(WindowEvent e) {    
        System.exit(0);    
      }    
    });    
   
    Container contentPane = frame.getContentPane();    
    contentPane.add(new Java_3());   
  
    frame.setVisible(true) ;    
  } 
} 
   
//*********Found**********
class CloseFrame extends JFrame implements ActionListener {    
  public void actionPerformed(ActionEvent evt) {     
    setVisible(false);    
  }
}

```

javax

 extends 

 newButton  

f

ActionListener

## 10

### 基本操作

```java
import java.io.*;
public class Java_1 {
    public static void main(String[ ] args) throws IOException {
        InputStreamReader ir;
        BufferedReader in;
        int max, x;
        String data;

        max = 0;
        ir = new InputStreamReader(System.in);
        in = new BufferedReader(ir);
        System.out.println("请输入5个正整数：");
        //*********Found**********
        for (int i = 1; i<=5; i++) {
            data = in.readLine();
            //*********Found**********
            x = Integer.parseInt(data);
            if ( max < x )
                //*********Found**********
                max=x;
        }
        System.out.println("输入的最大值是 "+ max);
    }
}

```

i<=5

parseInt

max=x

### 简单应用

```java
import java.io.File;

public class Java_2
{
   public static void main(String s[])
   {
      //Getting the Current Working Directory
      String curDir = System.getProperty("user.dir");
      System.out.println("当前的工作目录是:"+curDir);

      //*********Found**********
      File ff=new File(curDir);  //以路径文件名来建立文件对象
      String[] files=ff.list();
      for(int i=0; i<files.length; i++)
      {
         String ss=curDir+"\\"+files[i];
         traverse(0,ss);
      }
   }

   /**
   * 递归地遍历目录树
   * @param  level 目录的层次
   * @param  s     当前目录路径名
   */
   public static void traverse(int level,String s)
   {
      File f=new File(s);
      for(int i=0; i<level; i++) System.out.print("   ");
      if(f.isFile()) 
      {
         System.out.println(f.getName());
      }
      else if(f.isDirectory())
      {
         //*********Found**********
         System.out.println("<"+f.getName()+">");  //输出路径名
         String[] files=f.list();
         level++;
         //*********Found**********
         for(int i=0; i<files.length;i++)  //使用for循环来控制递归调用，变量i初值为0，循环条件为i小于字符串数组files的长度，每执行一轮循环，变量i的值加1
         {
            String ss=s+"\\"+files[i];
            //*********Found**********
            traverse(level,ss);     //traverse方法包含两个参数int型的变量level和String型的变量s，递归调用时，需要将参数带入
         }
      }
      else
      {
         System.out.println("ERROR!");
      }
   }
}
  

```

 curDir 

 getName ()

i++
 level 

### 综合应用

```java
import java.awt.*;
import java.awt.event.*;
//*********Found**********
import javax.swing.*;

public class Java_3 {

    public static void main(String[ ] args) {
        JFrame frame = new JFrame("Demo");
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);

        //*********Found**********
        frame.getContentPane().add(new Change());

        frame.pack();
        frame.setVisible(true);
    }
}

class Change extends JPanel {

    int count = 200;
    JLabel l1;
    JButton b1, b2;

    public Change( ) {
        setPreferredSize(new Dimension(280, 60));
        l1 = new JLabel("200");
        b1 = new JButton("增大");
        b2 = new JButton("减小");
        add(l1);
        //*********Found**********
        add(b1);
        //*********Found**********
        add(b2);
        b1.addActionListener( new BListener( ) );
        b2.addActionListener( new BListener( ) );
    }

    //*********Found**********
    private class BListener implements ActionListener {

        //*********Found**********
        public void  actionPerformed(ActionEvent e) {
            if (e.getSource( ) == b1) {
                count++;
            } else {
                count--;
            }
            l1.setText("" + count);
        }
    }
}
}

```

swing

 getContentPane 

(b1)

(b2)

 BListener 

 actionPerformed 

## 9

### 基本操作

```java
//*********Found**********
import java.io.*;

public class Java_1 {
    public static void main(String[ ] args) throws IOException {
        InputStreamReader ir;
        BufferedReader in;
        int sum, x;
        String data;
        //*********Found**********
       sum=0;
        ir = new InputStreamReader(System.in);
        in = new BufferedReader(ir);
        System.out.println("请输入5个整数：");
        //*********Found**********
        for (int i = 1; i<=5; i++) {
            data = in.readLine();
            x = Integer.parseInt(data);
            //*********Found**********
            if (x%2==0) 
                sum += x;
        }
        System.out.println("偶数之和为"+ sum );
    }
}
  

```

io

sum=0

i<=5

 x%2==0 

### 简单应用

```java
public class Java_2{
   public static void main(String args[]){
      int i=0;
      String greetings[] ={ "Hello World!","Hello!","HELLO WORLD!!"};
      while (i<4){
         try{
            //*********Found********
            System.out.println(greetings[i]);
         }
     //*********Found********
         catch(ArrayIndexOutOfBoundsException e){
     //*********Found********
            System.out.println("Catch " + e.getMessage());
            System.out.println("Ending the print.");
         }
         finally{
            System.out.println("---------------------");
         }  
     //*********Found********
         i++;
      }
   }
}
 

```

 greetings 

catch

e

i++

### 综合应用

```java
import javax.swing.*;
import java.awt.*;
import java.awt.event.*;

//*********Found**********
public class Java_3 extends WindowAdapter implements ActionListener
{
   private JFrame frame;
   private JTextField name;
   private JPasswordField pass;
   private JLabel nameLabel;
   private JLabel passLabel;
   private JPanel textPanel;
   private JPanel labelPanel;
   private JButton button;
   private JTextArea textArea;

   public void initGUI()
   {
      frame=new JFrame("Frame with Dialog");
      frame.addWindowListener(this);
      button=new JButton("JDialog");
  //*********Found**********
      button.addActionListener(this);
      textArea=new JTextArea("",3,10);

      frame.getContentPane().add(textArea,BorderLayout.CENTER);
      frame.getContentPane().add(button,BorderLayout.NORTH);

      frame.setSize(400,300);
      frame.setVisible(true);

   }

   public void actionPerformed(ActionEvent e)
   {
      final JDialog dia=new JDialog(frame,"login information");
      JButton ok=new JButton("ok");
      ok.addActionListener(new ActionListener()
      {
         public void actionPerformed(ActionEvent e)
         {
            textArea.setText("");
            textArea.append("name:"+name.getText()+"\r\n");
            textArea.append("passWord:"+new String(pass.getPassword())+"\r\n");
            //*********Found**********   
            dia.setVisible(false);    //

 
  }
      });

      name=new JTextField("",10);
      pass=new JPasswordField("",10);
      pass.setEchoChar('*');
      textPanel=new JPanel();
      textPanel.setLayout(new GridLayout(2,1,10,10));
      textPanel.add(name);
      textPanel.add(pass);

      nameLabel=new JLabel("name");
      passLabel=new JLabel("passWord");
      labelPanel=new JPanel();
      labelPanel.setLayout(new GridLayout(2,1,20,20));
      labelPanel.add(nameLabel);
      labelPanel.add(passLabel);

 
dia.getContentPane().add(labelPanel,BorderLayout.WEST);
      dia.getContentPane().add(textPanel,BorderLayout.CENTER);
      dia.getContentPane().add(ok,BorderLayout.SOUTH);
      dia.setSize(200,130);
      dia.setVisible(true);
   }

   public void windowClosing(WindowEvent event)
   {
      frame.setVisible(false);
      System.exit(0);
   }

   public static void main(String args[])
   {
      Java_3 example=new Java_3();
   //*********Found**********
      example.initGUI();
   }
}

```

extends

addActionListener

false

 initGUI()

## 8

### 基本操作

```java
//*********Found**********
import java.io.*;

public class Java_1{
   //*********Found**********
   public static void main(String[] args) throws Exception{
      InputStreamReader ir;
      BufferedReader in;
      ir=new InputStreamReader(System.in);
      in=new BufferedReader(ir);
      System.out.println("输入年份是:");
      //*********Found**********
      String s=in.readLine();
      //*********Found**********
      int year=Integer.parseInt(s);
      if(year%4==0&&year%100!=0||year%400==0){
         System.out.println(""+year+"年是闰年.");
      }
      else{
         System.out.println(""+year+"年不是闰年.");
      }
   }
}

```

io

 throws 

in

s

### 简单应用

```java
import java.io.*;

public class Java_2{
   public static void main(String args[]) { 
      int a[][] = new int[5][5];
      int i,j,k=1;
      for(i=0;i<5;i++)
         //*********Found**********
         for( j=0; j<5 ;j++ )
            //*********Found**********
            if((i+j)< 4)
               a[i][j]=0;
            else{
               //*********Found**********
               a[i][j]=k++;
            }
      for(i=0;i<5;i++){ 
         for(j=0;j<5;j++)
            //*********Found**********
            if(a[i][j]< 10)
               System.out.print(a[i][j]+ "   ");
            else
               System.out.print(a[i][j]+ "  ");
         System.out.println();
      }
   }
}

 

```

j<5

4

 a[i] [j] =k++

10

### 综合应用

```java
import javax.swing.*;
import java.awt.event.*;
import java.io.*;
import java.awt.*;

//*********Found**********
public class Java_3 implements ActionListener{
    JFrame f;
    JTextArea ta;
    JFileChooser fc;
    Container c;
    File myFile;


public static void main(String args[]){
        Java_3 demo=new Java_3();
        demo.go();
    }
    void go(){
        JFrame f=new JFrame("File Chooser Demo");
        JButton b=new JButton("Open file");
        ta=new JTextArea("Where is your file path?",10,30);
        //*********Found**********
        b.addActionListener(this);
        c=f.getContentPane();
        f.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        f.getContentPane().add("South",b);
        f.getContentPane().add("Center",ta);
        f.setSize(300,300);
        f.setVisible(true);
    }
public static void main(String args[]){
        Java_3 demo=new Java_3();
        demo.go();
    }
    void go(){
        JFrame f=new JFrame("File Chooser Demo");
        JButton b=new JButton("Open file");
        ta=new JTextArea("Where is your file path?",10,30);
        //*********Found**********
        b.addActionListener(this);
        c=f.getContentPane();
        f.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        f.getContentPane().add("South",b);
        f.getContentPane().add("Center",ta);
        f.setSize(300,300);
        f.setVisible(true);
    }

public void actionPerformed(ActionEvent e){
        fc=new JFileChooser();
        //*********Found**********
        int selected=fc.showOpenDialog(c); 
        if (selected==JFileChooser.APPROVE_OPTION){
            myFile=fc.getSelectedFile();
            //*********Found**********
            ta.setText("You have selected file: "+myFile.getName());
        }
    }
}

```

ActionListener

this

showOpenDialog 

 getName 

## 7

### 基本操作

```java
import java.io.*;
public class Java_1{
   public static void main(String[] args) {
      int[] anArray;   //声明一个整数型数组
      //*********Found**********
      anArray = new int[10];   //创建一个整数数组对象s
      //*********Found**********
      for (int i = 0; i < anArray.length;i++) {  //对数组中每个元素赋值并显示
         anArray[i] = i;
         //*********Found**********
         System.out.print(anArray[i]+ " ");
      }
      System.out.println();
   }
}

```

int

i++

 anArray [i]

### 简单应用

```java
import java.io.*;
public class Java_2{
   public static void main (String[] args){
      //*********Found**********
      byte buf[] = new byte[5];
      int len= 0 ,c1 = 0,c2=0;
      //*********Found**********
      try{
         //*********Found**********
         FileInputStream in = new FileInputStream("test.txt");
         while((len =in.read(buf,0,5))>0){
            for(int i = 0; i < len;i++)
               if(buf[i]>= '0' && buf[i] <= '9'){
                  c1 ++;
               }
               else 
                  if((buf[i]>= 'a' && buf[i] <= 'z') || buf[i]>= 'A' && buf[i] <= 'Z') 
                     c2++;
            if(len <5) break;
         }
         //*********Found**********
         in.close(); 
      }catch(Exception e ){}
      System.out.println("数字数是 " + c1 + "，字母数是 " + c2);
   }
}
}

```

byte

try

new  FileInputStream  

close

### 综合应用

```java
import java.awt.*;
import java.awt.event.*;
import javax.swing.*;

public class Java_3{
   public static void main(String[] args){
      MulticastFrame frame = new MulticastFrame();
      frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
      frame.show();
   }
}

class MulticastFrame extends JFrame{
   public MulticastFrame(){
      setTitle("MulticastTest");
      setSize(WIDTH, HEIGHT);
      MulticastPanel panel = new MulticastPanel();
      Container contentPane = getContentPane();
      //*********Found**********
      contentPane.add(panel);
   }
   public static final int WIDTH = 300;
   public static final int HEIGHT = 200;  
}

class MulticastPanel extends JPanel{
   public MulticastPanel(){
      JButton newButton = new JButton("New");
      add(newButton);
      ActionListener newListener = new ActionListener(){
         public void actionPerformed(ActionEvent event){
            makeNewFrame();
         }
      };
      newButton.addActionListener(newListener);
      closeAllButton = new JButton("Close all");
      add(closeAllButton);
   }
   private void makeNewFrame(){
      final BlankFrame frame = new BlankFrame();
      frame.show();
      ActionListener closeAllListener = new ActionListener(){
         public void actionPerformed(ActionEvent event){
            //*********Found**********
            frame.dispose();     //使窗口隐藏或消除
         }
      };
      //*********Found**********
      closeAllButton.addActionListener(closeAllListener);
   }
   private JButton closeAllButton;
}

class BlankFrame extends JFrame{
   public BlankFrame(){
      //*********Found**********
      counter ++ ;
      setTitle("Frame " + counter);
      setSize(WIDTH, HEIGHT);
      setLocation(SPACING * counter, SPACING * counter);     
   }
   public static final int WIDTH = 200;
   public static final int HEIGHT = 150;  
   public static final int SPACING = 30;
   private static int counter =0;

```

 panel  

 dispose 

 closeAllListener 

 counter 

## 6

### 基本操作

```java
public class Java_1{
   //*********Found**********
   public static void main(String args[]){
      String string="现在学习如何访问一个字符串";
      System.out.println("字符串 \""+string+"\"");
      //*********Found**********
      System.out.println("字符串长度："+string.length());
      //*********Found**********
      System.out.println("其中第7个字符是："+string.charAt(6));
      char sub[] = new char[20];
      System.out.print("从字节数组的第7到12获取字符是：");
      string.getChars(6,12,sub,0);
      System.out.println(sub);
   }
}

```

main

string.length()

charAt

### 简单应用

```java
public class Java_2{
   public static void main(String args[]) { 
      //*********Found**********
      int a[][] = new int[5][5];
      int i,j,k = 1;
      for(i=0;i<5;i++)
         for(j=0;j<5;j++)
            if((i+j)<5){
               a[i][j] = k;
               //*********Found**********
               k++;
               if (k > 9) k = 1;
            }else
               //*********Found**********
               a[i][j]=0;
      for(i=0;i<5;i++){ 
         for(j=0;j<5;j++)
            System.out.print(a[i][j]+ "   ");
         //*********Found**********
         System.out.println();
      }
   }
}

```

new

k++

a[i] [j] = 0

### 综合应用

```java
import java.io.*;
public class Java_3{
   public static int data[]={32,18,41,23,2,56,36,67,59,20};
   public static void main(String args[]){
      int i;
      //*********Found**********
      int index=data.length;
      System.out.println("排序前:");
      for(i=0;i<index;i++)
         System.out.print(" "+data[i]+" ");
      System.out.println();
      //*********Found**********
      BubbleSort(index);
      System.out.println("排序后:");
      for(i=0;i<index;i++)
         System.out.print(" "+data[i]+" ");
      System.out.println();
   }
   // 冒泡法排序
   public static void BubbleSort(int index){
      int i,j;
      int temp;
      for(j=1;j<index;j++){
         for(i=index-1;i>=j;i--){
   if(data[i]<data[i-1]){  //比较相邻的两个数
               temp=data[i];
               data[i]=data[i-1];
               //*********Found**********
               data[i-1]= temp;
            }
         }
      }
   }
}

```

 length 

 index 

temp

## 5

### 基本操作

```java
//*********Found**********
public class Java_1{
   public static void main(String args[]) {
      byte b = 10;   // 二进制表示00001010 
      //*********Found**********
      byte c = 0X000f;
      b = (byte)(b ^ c);
      //*********Found**********
      System.out.println("b的结果是：" +b);
   }
}

```

class

 0X000f 

+b

### 简单应用

```java
public class Java_2 { 
   public static void main (String args[]) { 
      try { 
         Sleep a = new Sleep (); 
         Thread t = new Thread (a); 
         //*********Found**********
         t.start();
         t.join(); 
         int j= a.i; 
         System.out.println("j="+j+",a.i="+a.i);
      } catch (Exception e) {} 
   } 
} 

//*********Found**********
class Sleep implements Runnable{ 
   int i; 
   public void run () { 
      try { 
         //*********Found**********
         Thread.sleep(50); 
         i= 10; 
      } 
      //*********Found**********
      catch (InterruptedException e) {} 
   } 
}

```

start

Runnable

sleep

catch

### 综合应用

```java
//*********Found**********
import javax.swing.JFrame ;
import java.awt.*;
public class Java_3{
   static final int WIDTH=300;
   static final int HEIGHT=200;
   public static void main(String[] args){
      //*********Found**********
      JFrame jf=new JFrame() ;
      jf.setSize(WIDTH,HEIGHT);
      jf.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
      //*********Found**********
      jf.setTitle ("股票分析系统");
      Toolkit kit=Toolkit.getDefaultToolkit();
      Dimension screenSize=kit.getScreenSize();
      int width=screenSize.width;
      int height=screenSize.height;
      int x=(width-WIDTH)/2;
      int y=(height-HEIGHT)/2;
      jf.setLocation (x,y);
      //*********Found**********
      jf.setVisible(true);
   }
}
 

```

 swing

new JFrame

setTittle

jf

## 4

### 基本操作

```java
//*********Found**********
import javax.swing.JOptionPane;

public class Java_1{
   public static void main( String args[] ){
      String s1, s2, s3, s4, output;
      s1 = new String( "hello" );
      s2 = new String( "good bye" );
      s3 = new String( "Happy Birthday" );
      s4 = new String( "happy birthday" );
      output = "s1 = " + s1 + "\ns2 = " + s2 +
               "\ns3 = " + s3 + "\ns4 = " + s4 + "\n\n";
      //测试字符串相等
      if ( s1.equals( "hello" ) )
         //*********Found**********
         output = output + "s1 equals \"hello\"\n";
      else
         output = output + "s1 does not equal \"hello\"\n"; 
      //用==测试相等
      if ( s1 == "hello" )
         output += "s1 equals \"hello\"\n";
      else
         output += "s1 does not equal \"hello\"\n";
      //忽略字符格式测试相等
      if ( s3.equalsIgnoreCase( s4 ) )
         output += "s3 equals s4\n";
      else
         output += "s3 does not equal s4\n";
      //内容比较
      output +=
         "\ns1.compareTo( s2 ) is " + s1.compareTo( s2 ) +
         "\ns2.compareTo( s1 ) is " + s2.compareTo( s1 ) +
         "\ns1.compareTo( s1 ) is " + s1.compareTo( s1 ) +
         "\ns3.compareTo( s4 ) is " + s3.compareTo( s4 ) +
         "\ns4.compareTo( s3 ) is " + s4.compareTo( s3 ) +
         "\n\n";
      //测试包含字符格式的域匹配
      if ( s3.regionMatches( 0, s4, 0, 5 ) )
         output += "First 5 characters of s3 and s4 match\n";
      else
         output +=
            "First 5 characters of s3 and s4 do not match\n";
      //忽略字符格式的域匹配
      if ( s3.regionMatches( true, 0, s4, 0, 5 ) )
         output += "First 5 characters of s3 and s4 match";
      else
         output +=
            "First 5 characters of s3 and s4 do not match";
      //*********Found**********
      JOptionPane.showMessageDialog( null, output,
         "字符串构造方法示例",
         JOptionPane.INFORMATION_MESSAGE );
    System.exit( 0 );
  }  

```

swing

 s1.equals (“hello”\n) 

showMessageDialog

### 简单应用

```java
//*********Found**********
public class Java_2 implements Runnable{ 
   private int x=0; 
   private int y=0; 
 
   public static void main(String[]args){
      Java_2 r = new Java_2();
      //*********Found********** 
      Thread t = new Thread( r );
      t.start(); 
   }
   public void run() { 
      //*********Found**********
      int  k = 0;
      for(;;){
         x++; 
         //*********Found**********
         y++; 
         k++;
         if (k>5) break;
         System.out.println("x=" + x + ",y ="+ y); 
      }
   }
}

```

 implements Runnable 

r

k

y++

### 综合应用

```java
import java.awt.*;
import javax.swing.*;
public class Java_3{
   public static void main(String[] args){
      BeijingFrame frame = new BeijingFrame();
      frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
      frame.show();
   }
}
//*********Found*********
class  BeijingFrame   extends JFrame{
   public BeijingFrame(){
      setTitle("Welcome to Beijing");
      Container contentPane = getContentPane();
      BeijingPanel panel = new BeijingPanel();
      contentPane.add(panel);
      pack();
   }
}
class BeijingPanel extends JPanel{
   public BeijingPanel(){
      //*********Found*********
      setLayout(new BorderLayout());
      ImageIcon icon = new ImageIcon("tiantan.jpg");
      //*********Found*********
      jLC = new JLabel( icon );
      add(jLC, BorderLayout.CENTER);
      lpanel = new JPanel();
      jLS = new JLabel("The Temple of Heaven");
      lpanel.add(jLS);
      add(lpanel, BorderLayout.SOUTH);
   }
   private JLabel jLC;
   private JLabel jLS;
   private JPanel panel;
   private JPanel lpanel;
}

```

 BeijingFrame 

 BorderLayout（）

 icon 

## 3

### 基本操作

```java
public void paint(Graphics g) 
 {
      g.drawString( "欢迎你参加Java考试!", 25, 25 ); 
 }
    上面列的代码显示了在paint()方法内使用drawString()方法。这个范例代码在含paint()方法的部件中显示字符"欢迎你参加Java考试!"，x和y坐标指明文本框左下角位置。
    Applet程序如下：
import java.applet.*;
import java.awt.Graphics;

//*********Found********
public class Java_1 extends Applet {  
   public void paint( Graphics g )
   {
//*********Found********
      g.drawString("欢迎你来参加Java 语言考试!",25,25);
   }
}

```

Applet

 drawString 



### 简单应用

```java
public class Java_2
{
    public static void main(String[] args) {
        int[][] aMatrix = {{1,1,1,1,1},{2,2,2,2,2},{3,3,3,3,3},{4,4,4,4,4}};
int i = 0; //循环变量
int j = 0; //循环变量
        //print matrix
        for (i = 0; i < aMatrix.length; i++) {
   //*********Found********
      for ( j = 0; j<aMatrix[i].length ; j++) {
   //*********Found********
       System.out.print(aMatrix[i][j] + " ");
      }
   System.out.println();
        }
    }
}

```

j< aMatrix[i].length 

aMatrix[i] [j]

### 综合应用

```java
public class Java_3{
   public static void main(String[] args) {
      String text = "Beijing, the Capital City, is the political,"
                  + "cultural and diplomatic centre of China. It has"
                  + "become a modern international cosmopolitan city"
                  + "with more than 11 million people. The Capital"
                  + "International Airport, 23.5 km from the city centre,"
                  + "is China's largest and most advanced airport.";
      int vowels  = 0 ;
      //*********Found*********
      int textLength = text.length();
      for(int i = 0; i < textLength; i++) {
         //*********Found*********
         char ch = Character.toLowerCase(text.charAt(i));
         if(ch == 'a' || ch == 'e' || ch == 'i' || ch == 'o' || ch == 'u') {
            //*********Found*********
            vowels++;
         }
      }
      System.out.println("The text contained vowels: " + vowels + "\n" );
   }
}

```

 textLength  

charAt(i)

 vowels ++

## 2

### 基本操作

```java
//*********Found********
import java.applet.*;
import java.awt.Graphics;

//*********Found********
public class Java_1 extends Applet{  
   public void paint( Graphics g )
   {
//*********Found********
      g.drawString( "欢迎你来参加Java 语言考试!", 25, 25 );
   }
}
```

applet.*

Applet

 drawString 

### 简单应用

```java
import java.awt.*;
import java.applet.*;

//*********Found********
public class Java_2 extends Applet
{
    TextArea outputArea;

    public void init()
    {
        setLayout(new BorderLayout());
        outputArea = new TextArea();
     //*********Found********
        add( outputArea );

      // 计算0至10的阶乘
        for ( long i = 0; i <= 10; i++ )
            //*********Found********
            outputArea.append(i + "! = " +factorial(i)+ "\n" );
    }
   
   // 用递归定义阶乘方法
    public long factorial( long number )
    {                  
        if ( number <= 1 )  // 基本情况
            return 1;
        else
            //*********Found********
            return number * factorial(number- 1 );
    }  
}
 
```

Applet

 add 

 factorial (i)

 number -1

### 综合应用



```java
import java.awt.*;
import java.awt.font.*;
import java.awt.geom.*;
import javax.swing.*;
public class Java_3
{
   public static void main(String[] args)
   {
      FontFrame frame = new FontFrame();
      frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
      frame.setVisible(true);
   }
}
     //*********Found********
class FontFrame extends JFrame
{
   public FontFrame()
   {
      setTitle("沁园春.雪");
      setSize(DEFAULT_WIDTH, DEFAULT_HEIGHT);
      FontPanel panel = new FontPanel();
      Container contentPane = getContentPane();
      contentPane.add(panel);
   }
   public static final int DEFAULT_WIDTH = 300;
   public static final int DEFAULT_HEIGHT = 200;
}
     //*********Found********
class FontPanel extends JPanel
{
   public void paintComponent(Graphics g)
   {
      super.paintComponent(g);
      Graphics2D g2 = (Graphics2D)g;
      String message = "数风流人物，还看今朝！";
      Font f = new Font("隶书", Font.BOLD, 24);
      g2.setFont(f);
      FontRenderContext context = g2.getFontRenderContext();
      Rectangle2D bounds = f.getStringBounds(message, context);
      double x = (getWidth() - bounds.getWidth()) / 2;
      double y = (getHeight() - bounds.getHeight()) / 2;
      double ascent = -bounds.getY();
      double baseY = y + ascent;
      g2.setPaint(Color.RED);
     //*********Found********
      g2.drawString(message, (int)x, (int)(baseY));
   }
}
```

 extends  

 JFrame 

 drawString 

## 1

### 基本操作

```java
import javax.swing.JOptionPane;  //导入JOptionPane类

public class Java_1 {
   public static void main( String args[] )
   {
//*********Found********
      JOptionPane.showMessageDialog(
         null, "欢迎\n你\n参加\nJava\n考试!" );
      System.exit( 0 );  // 结束程序
   }
}
/* JOptionPane类的常用静态方法如下：
   showInputDialog()
   showConfirmDialog()
   showMessageDialog()
   showOptionDialog()
*/
```

 JOptionPane.showMessageDialog 

### 简单应用

```java

import java.util.Random;

public class Java_2
{
   public static void main(String args[]){
      Random random = new Random();
      float x = random.nextFloat();//产生0.0与1.0之间的一个符点数
      int n = Math.round(20*x);  //构造20以内的一个整数
      long f = 1 ;  //保存阶乘的结果
      int k = 1 ;  //循环变量
   //*********Found********
      do{f*=k;
         k++;
   //*********Found********
      }while(k<=n);
      System.out.println(n+"!= "+f);
   }
}
```



### 综合应用

```java
import java.text.DecimalFormat;
import javax.swing.*;
import java.awt.*;
import java.awt.event.*;

     //*********Found********
public class Java_3 extends JFrame implements ActionListener {
   private JTextField input1, input2, output;
   private int number1, number2;
   private double result;

   // 初始化
   public Java_3()
   {
     //*********Found********
      super( "示范异常" );

      Container c = getContentPane();
      c.setLayout( new GridLayout( 3, 2 ) );

      c.add( new JLabel( "输入分子",
                         SwingConstants.RIGHT ) );
      input1 = new JTextField( 10 );
      c.add( input1 );

      c.add(
         new JLabel( "输入分母和回车",
                     SwingConstants.RIGHT ) );
      input2 = new JTextField( 10 );
      c.add( input2 );
      input2.addActionListener( this );

      c.add( new JLabel( "计算结果", SwingConstants.RIGHT ) );
      output = new JTextField();
   

 
      c.add( output );

      setSize( 425, 100 );
      show();
   }

   //处理 GUI 事件
   public void actionPerformed( ActionEvent e )
   {
      DecimalFormat precision3 = new DecimalFormat( "0.000" );

      output.setText( "" ); // 空的JTextField输出

     //*********Found********
      try{         
         number1 = Integer.parseInt( input1.getText() );
         number2 = Integer.parseInt( input2.getText() );


result = quotient( number1, number2 );
     //*********Found********
         output.setText(precision3.format(result));
      }
      catch ( NumberFormatException nfe ) {
         JOptionPane.showMessageDialog( this,
            "你必须输入两个整数",
            "非法数字格式",
            JOptionPane.ERROR_MESSAGE );
      }
      catch ( Exception dbze ) {
     //*********Found********
         JOptionPane.showMessageDialog( this, 
            "除法异常",
            "除数为零",
            JOptionPane.ERROR_MESSAGE );
      }
   }


// 定义求商的方法，如遇除数为零时，能抛出异常。
     public double quotient( int numerator, int denominator )
      throws Exception
   {
      if ( denominator == 0 )
         throw new Exception();

      return ( double ) numerator / denominator;
   }

   public static void main( String args[] )
   {
      Java_3 app = new Java_3();


app.addWindowListener(
         new WindowAdapter() {
            public void windowClosing( WindowEvent e )
            {
               e.getWindow().dispose();
               System.exit( 0 );
            }
         }
      );
   }
}
/* JOptionPane类的常用静态方法如下：
   showInputDialog()
   showConfirmDialog()
   showMessageDialog()
   showOptionDialog()
*/
```





