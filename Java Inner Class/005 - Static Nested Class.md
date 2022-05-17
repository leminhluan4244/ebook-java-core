# Static nested class trong java

## Định nghĩa
Một lớp static được tạo bên trong một lớp được gọi là lớp static lồng hay static nested class trong java. Nó không thể truy cập các thành viên và phương thức non-static. Nó có thể được truy cập bởi tên lớp bên ngoài.

- Nó có thể truy cập các thành viên dữ liệu tĩnh của lớp ngoài bao gồm cả private.
- Static nested class không thể truy cập thành viên dữ liệu hoặc phương thức non-static (instance).

## Ví dụ về static nested class trong java
```java
class TestOuter1 {
    static int data = 30;
 
    static class Inner {
        void msg() {
            System.out.println("data is " + data);
        }
    }
 
    public static void main(String args[]) {
        TestOuter1.Inner obj = new TestOuter1.Inner();
        obj.msg();
    }
}
```
```
data is 30
```
Trong ví dụ này, bạn cần tạo ra thể hiện lớp static lồng nhau bởi vì nó có phương thức instance msg(). Nhưng bạn không cần phải tạo ra đối tượng lớp ngoài (Outer class) vì lớp lồng bên trong là static, các phương thức hoặc các lớp có thể được truy cập mà không cần tạo đối tượng.

#### Lớp nội bộ được trình biên dịch tạo ra

```java
import java.io.PrintStream;
 
static class TestOuter1$Inner {
    TestOuter1$Inner() {
    }
 
    void msg() {
        System.out.println((new StringBuilder()).append("data is ")
                .append(TestOuter1.data).toString());
    }
}
```

## Ví dụ static nested class với phương thức static
Nếu bạn có thành viên static bên trong lớp static lồng nhau, bạn không cần tạo ra thể hiện của lớp tĩnh lồng nhau.

```java
class TestOuter2 {
    static int data = 30;
 
    static class Inner {
        static void msg() {
            System.out.println("data is " + data);
        }
    }
 
    public static void main(String args[]) {
        TestOuter2.Inner.msg();// khong can tao ra the hien cua
                               // static nested class
    }
}
```