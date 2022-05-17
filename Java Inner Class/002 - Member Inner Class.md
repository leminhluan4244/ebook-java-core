# Member inner class trong java

## Định nghĩa và cú pháp
Một lớp non-static được tạo ra bên trong một lớp nhưng ngoài một phương thức được gọi là thành viên bên trong lớp hay member inner class trong java.
```java
class Outer {
    // code
    class Inner {
        // code
    }
}
```

## Ví dụ về member inner class trong java
Trong ví dụ này, chúng ta tạo phương thức msg() trong thành viên lớp bên trong (lớp Inner) đó là truy cập vào thành viên dữ liệu private của lớp bên ngoài.
```java
class TestMemberOuter1 {
    private int data = 30;
 
    class Inner {
        void msg() {
            System.out.println("data is " + data);
        }
    }
 
    public static void main(String args[]) {
        TestMemberOuter1 obj = new TestMemberOuter1();
        TestMemberOuter1.Inner in = obj.new Inner();
        in.msg();
    }
}
```
```
data is 30
```

## Hoạt động nội bộ của member inner class trong java
Trình biên dịch java tạo ra hai file .class trong trường hợp của inner class. Tên của file của lớp bên trong là "Outer$Inner". Nếu bạn muốn tạo ra thể hiện của lớp bên trong, bạn phải tạo ra thể hiện của lớp bên ngoài. Trong trường hợp này, thể hiện của lớp bên trong được tạo ra bên trong thể hiện của lớp bên ngoài.

## Code nội bộ được tạo ra bởi trình biên dịch
Trình biên dịch java tạo ra một file .class tên là Outer$Inner trong trường hợp này. Các member inner class có tham chiếu của lớp bên ngoài Outer đó là lý do tại sao nó có thể truy cập tất cả các thành viên dữ liệu của lớp Outer bao gồm cả private.

```java
import java.io.PrintStream;
 
class Outer$Inner {
    final Outer this$0;
 
    Outer$Inner() {
        super();
        this$0 = Outer.this;
    }
 
    void msg() {
        System.out.println((new StringBuilder()).append("data is ")
            .append(Outer.access$000(Outer.this)).toString());
    }
}
```