# Exception tùy chỉnh
Nếu bạn tạo ngoại lệ riêng của mình được biết đến như ngoại lệ tùy chỉnh (exception tùy chỉnh) hoặc ngoại lệ do người dùng định nghĩa. Các ngoại lệ tùy chỉnh trong Java được sử dụng để tùy chỉnh ngoại lệ theo nhu cầu của người dùng.

Sử dụng ngoại lệ tùy chỉnh, bạn có thể có ngoại lệ và message của riêng bạn.

> Ví dụ:
```java
class InvalidAgeException extends Exception {
    InvalidAgeException(String s) {
        super(s);
    }
}
```

```java
class TestCustomException1 {
 
    static void validate(int age) throws InvalidAgeException {
        if (age < 18)
            throw new InvalidAgeException("not valid");
        else
            System.out.println("welcome to vote");
    }
 
    public static void main(String args[]) {
        try {
            validate(13);
        } catch (Exception m) {
            System.out.println("Exception occured: " + m);
        }
 
        System.out.println("rest of the code...");
    }
}
```
```
Output:Exception occured: InvalidAgeException:not valid
       rest of the code...
```