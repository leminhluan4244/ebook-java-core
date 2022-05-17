# Local inner class

## Định nghĩa
Một lớp được tạo ra bên trong một phương thức được gọi là local inner class trong java. Nếu bạn muốn gọi các phương thức của lớp được khai báo bên trong một phương thức, bạn phải tạo ra thể hiện của lớp này bên trong phương thức chứa nó.

## Ví dụ về local inner class trong java

![image-1](./image/vi-du-local-inner-class-trong-java.png)

File: LocalInner1.java
```java
public class LocalInner1 {
    private int data = 30;// biến instance
 
    void display() {
        class Local {
            void msg() {
                System.out.println(data);
            }
        }
        Local l = new Local();
        l.msg();
    }
 
    public static void main(String args[]) {
        LocalInner1 obj = new LocalInner1();
        obj.display();
    }
}
```
```
30
```

#### Lớp nội được tạo ra bởi trình biên dịch
Trong trường hợp này, trình biên dịch sẽ tạo ra một lớp có tên LocalInner1$1Local.class có tham chiếu của lớp bên ngoài (LocalInner1) .

```java
import java.io.PrintStream;
 
class LocalInner1$Local {
    final LocalInner1 this$0;
 
    LocalInner1$Local() {
        super();
        this$0 = Simple.this;
    }
 
    void msg() {
        System.out.println(LocalInner1.access$000(LocalInner1.this));
    }
}
```

#### Nguyên tắc
- Biến local không thể là private, public hoặc protected.
- Local Inner class không thể được gọi từ một phương thức bên ngoài.
- Local Inner class không thể truy cập biến local non-final từ JDK 1.7 trở vể trước. Kể từ JDK 1.8, có thể truy cập vào các biến local non-final trong lớp local inner class.


## Ví dụ về local inner class với biến local
```java
class LocalInner2 {
    private int data = 30; // biến instance
 
    void display() {
        int value = 50; // biến local phải là final từ jdk 1.7 trở về trước
        class Local {
            void msg() {
                System.out.println(value);
            }
        }
        Local l = new Local();
        l.msg();
    }
 
    public static void main(String args[]) {
        LocalInner2 obj = new LocalInner2();
        obj.display();
    }
}
```
```
50
```