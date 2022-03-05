# Hello-World-by-Java

Let’s enjoy our first java “Hello World!” program. But wait, we are not going to write only simple “Hello World!” program. We will explore the execution beauty of this program with the JMV **(Java Virtual Machine)**. 

#### Code snapshot : 01
```java
public class HelloWorld {
  public static void main(String[] args) {
    System.out.println("Hello World!");
  }
}
```

#### Code snapshot : 02
```java
public class Main {
    static {
        System.out.println("Hello world! :: static block");
    }
    
    {
        System.out.println("Hello world! :: non-static block");
    }
    
    public Main() {
        System.out.println("Hello world! :: constructor");
    }
    
    public static void main(String[] args) {
        System.out.println("Hello world! :: main method");
        Main obj = new Main();
    }
    
}
```
Consider above two code snapshot, “Code snapshot : 02” is litle bit compicated than “Code snapshot : 01”. Can you guess the output of the “Code snapshot : 02”? Well, Hope after completing this article we will be able to guess it easily. 

There are several components to run our simple “Hello World!” program. As we know the java is platform independent and the slogan of java is ***WORA (Write Once Run Anywhere)***, that is possible for the JVM ***(Java Virtual Machine)*** but the JVM is not platform independent. Different types of operating systems contain diffrent types of JVM. 
However, can JVM understand the java program? The answer is : No.  JVM can’t understant the java program but it can understand the Bytecode. 

#### Now the question is, what is the Bytecode in java?
Basically the Bytecode is the JVM readable code that is created after compiing the java source code. 
If we execute the javac command like ```javac HelloWorld.java``` then the java compiler generates a dot(.) class file like “HelloWorld.class” this is nothing but Bytecode. If we execute the ```javap -verbose HelloWorld.class``` command then we can see the following:

#### HelloWorld Bytecode
```java
Classfile /home/mamun/java/HelloWorld.class
  Last modified Mar 5, 2022; size 426 bytes
  MD5 checksum 90469fd7405d19947ba6e767de8a8b5f
  Compiled from "HelloWorld.java"
public class HelloWorld
  minor version: 0
  major version: 52
  flags: ACC_PUBLIC, ACC_SUPER
Constant pool:
   #1 = Methodref          #6.#15         // java/lang/Object."<init>":()V
   #2 = Fieldref           #16.#17        // java/lang/System.out:Ljava/io/PrintStream;
   #3 = String             #18            // Hello World!
   #4 = Methodref          #19.#20        // java/io/PrintStream.println:(Ljava/lang/String;)V
   #5 = Class              #21            // HelloWorld
   #6 = Class              #22            // java/lang/Object
   #7 = Utf8               <init>
   #8 = Utf8               ()V
   #9 = Utf8               Code
  #10 = Utf8               LineNumberTable
  #11 = Utf8               main
  #12 = Utf8               ([Ljava/lang/String;)V
  #13 = Utf8               SourceFile
  #14 = Utf8               HelloWorld.java
  #15 = NameAndType        #7:#8          // "<init>":()V
  #16 = Class              #23            // java/lang/System
  #17 = NameAndType        #24:#25        // out:Ljava/io/PrintStream;
  #18 = Utf8               Hello World!
  #19 = Class              #26            // java/io/PrintStream
  #20 = NameAndType        #27:#28        // println:(Ljava/lang/String;)V
  #21 = Utf8               HelloWorld
  #22 = Utf8               java/lang/Object
  #23 = Utf8               java/lang/System
  #24 = Utf8               out
  #25 = Utf8               Ljava/io/PrintStream;
  #26 = Utf8               java/io/PrintStream
  #27 = Utf8               println
  #28 = Utf8               (Ljava/lang/String;)V
{
  public HelloWorld();
    descriptor: ()V
    flags: ACC_PUBLIC
    Code:
      stack=1, locals=1, args_size=1
         0: aload_0
         1: invokespecial #1                  // Method java/lang/Object."<init>":()V
         4: return
      LineNumberTable:
        line 1: 0

  public static void main(java.lang.String[]);
    descriptor: ([Ljava/lang/String;)V
    flags: ACC_PUBLIC, ACC_STATIC
    Code:
      stack=2, locals=1, args_size=1
         0: getstatic     #2                  // Field java/lang/System.out:Ljava/io/PrintStream;
         3: ldc           #3                  // String Hello World!
         5: invokevirtual #4                  // Method java/io/PrintStream.println:(Ljava/lang/String;)V
         8: return
      LineNumberTable:
        line 3: 0
        line 4: 8
}
SourceFile: "HelloWorld.java"
```


The java compiler is part of JDK (Java Development Kit). JRE (Java Runtime Environment) is also part of JDK. On the other hand the JVM is part of JRE. AS a result, the complete picture of the JDK, JRE and JVM looks like:

- JDK = JRE + Development Tools
- JRE = JVM + Library Classes


