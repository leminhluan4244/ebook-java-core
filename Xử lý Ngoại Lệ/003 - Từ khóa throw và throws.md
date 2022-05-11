# Từ khóa throw trong java

## Từ khóa throw trong java
- Từ khoá throw trong java được sử dụng để ném ra một ngoại lệ cụ thể.
- Chúng ta có thể ném một trong hai ngoại lệ checked hoặc unchecked trong java bằng từ khóa throw. 
- Từ khóa throw chủ yếu được sử dụng để ném ngoại lệ tùy chỉnh (ngoại lệ do người dùng tự định nghĩa). Chúng ta sẽ học ngoại lệ tùy chỉnh trong bài sau.
- Cú pháp từ khóa throw:
```java
throw exception;
```
> Ví dụ về throw IOException.
```java
throw new IOException("File không tồn tại");
```

> Ví dụ 1: throw ra ngoại lệ nhưng không xử lý. Trong ví dụ này, chúng ta tạo ra phương thức validate() với tham số truyền vào là giá trị integer. Nếu tuổi dưới 18, chúng ta ném ra ngoại lệ ArithmeticException nếu không in ra một thông báo "welcome".
```java
public class TestThrow1 {
    static void validate(int age) {
        if (age < 18)
            throw new ArithmeticException("not valid");
        else
            System.out.println("welcome");
    }
 
    public static void main(String args[]) {
        validate(13);
        System.out.println("rest of the code...");
    }
}
```
```
Exception in thread "main" java.lang.ArithmeticException: not valid
```
>Ví dụ 2: throw ra ngoại lệ nhưng có xử lý
```java
public class TestThrow2 {
    static void validate(int age) {
        try {
            if (age < 18)
                throw new ArithmeticException("not valid");
            else
                System.out.println("welcome");
        } catch (ArithmeticException ex) {
            System.out.println(ex.getMessage());
        }
    }
 
    public static void main(String args[]) {
        validate(13);
        System.out.println("rest of the code...");
    }
}
```
```
not valid
rest of the code...
```