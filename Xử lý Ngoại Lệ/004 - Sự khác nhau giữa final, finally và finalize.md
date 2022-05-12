# Sự khác nhau giữa final, finally và finalize

## Final
- Final được sử dụng để áp dụng các hạn chế về class, phương thức và biến. Lớp final không thể được kế thừa, phương thức final không thể được ghi đè và giá trị biến final không thể thay đổi.
- Final là một từ khóa.

## Finally
- Finally được sử dụng để thực thi code quan trọng, nó luôn được thực thi cho dù ngoại lệ được xử lý hay không.
- Finally là một khối (block).

## Finalize
- Finalize được sử dụng để thực hiện quá trình xử lý xóa ngay trước khi đối tượng thu gom rác.
- Finalize là một phương thức.

> Ví dụ về final trong java
```java
class FinalExample{  
class FinalExample {
    public static void main(String[] args) {
        final int x = 100;
        x = 200;// Compile Time Error
    }
} 
```

> Ví dụ về finally trong java
```java
class FinallyExample {
    public static void main(String[] args) {
        try {
            int x = 300;
        } catch (Exception e) {
            System.out.println(e);
        } finally {
            System.out.println("finally block is executed");
        }
    }
}
```

> Ví dụ về finalize trong java
```java
class FinalizeExample {
    public void finalize() {
        System.out.println("finalize called");
    }
 
    public static void main(String[] args) {
        FinalizeExample f1 = new FinalizeExample();
        FinalizeExample f2 = new FinalizeExample();
        f1 = null;
        f2 = null;
        System.gc();
    }
}
```