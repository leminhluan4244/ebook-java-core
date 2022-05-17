# Nested Interface trong java

## Định nghĩa
Một interface được khai báo trong một interface hoặc lớp khác được gọi là interface lồng nhau hay nested interface trong java. Các interface lồng nhau được sử dụng để nhóm các interface liên quan để chúng có thể dễ dàng được bảo trì. Interface lồng nhau phải được bao bọc bên ngoài bởi interface hoặc lớp. Nó không thể truy cập trực tiếp.

Những điểm cần nhớ đối với các interface lồng nhau
- Interface lồng nhau (Nested interface) phải public nếu nó được khai báo bên trong interface nhưng nó có thể có bất kỳ access modifier nào nếu khai báo trong lớp.
- Interface lồng nhau (Nested interface) được khai báo static một cách hiển nhiên.
- Khai báo nested interface bên trong interface
```java
interface interface_name {
    // code
    interface nested_interface_name {
        // code
    }
}
```
- Khai báo nested interface bên trong class
```java
class class_name {
    // code
    interface nested_interface_name {
        // code
    }
}
```

## Ví dụ về nested interface được khai báo bên trong interface
Trong ví dụ này, chúng ta sẽ học cách khai báo interface lồng nhau và cách chúng ta có thể truy cập nó.

```java
interface Showable {
    void show();
 
    interface Message {
        void msg();
    }
}
 
class TestNestedInterface1 implements Showable.Message {
    public void msg() {
        System.out.println("Hello nested interface");
    }
 
    public static void main(String args[]) {
        Showable.Message message = new TestNestedInterface1(); // upcasting
        message.msg();
    }
}
```
```
hello nested interface
```

Như bạn thấy trong ví dụ trên, chúng ta truy cập interface Message bằng interface Showable bên ngoài của nó vì nó không thể được truy cập trực tiếp. Trong khuôn khổ collection, hệ thống sun microsystem đã cung cấp một nested interface là Entry. Entry là subinterface của Map, nghĩa là được truy cập bởi Map.Entry.

#### Code nội bộ được tạo ra bởi trình biên dịch java cho interface lồng nhau Message
Trình biên dịch java tạo ra interface public và static như thể hiện dưới đây:

```java
public static interface Showable$Message {
    public abstract void msg();
}
```

## Ví dụ về nested interface được khai báo bên trong lớp
```java
class A {
    interface Message {
        void msg();
    }
}
 
public class TestNestedInterface2 implements A.Message {
    public void msg() {
        System.out.println("Hello nested interface");
    }
 
    public static void main(String args[]) {
        A.Message message = new TestNestedInterface2();// upcasting
        message.msg();
    }
}
```
```
hello nested interface
```

## Chúng ta có thể định nghĩa một lớp bên trong interface?
Có, Nếu chúng ta xác định một lớp bên trong interface, trình biên dịch java tạo ra một lớp static lồng nhau. Hãy xem chúng ta có thể định nghĩa một lớp trong giao diện như thế nào:
```java
interface M {
    class A {
    }
}
```