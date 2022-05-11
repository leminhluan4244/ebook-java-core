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

## Từ khóa throws trong java
- Từ khóa throws trong java được sử dụng để khai báo một ngoại lệ. Nó thể hiện thông tin cho lập trình viên rằng có thể xảy ra một ngoại lệ, vì vậy nó là tốt hơn cho các lập trình viên để cung cấp các mã xử lý ngoại lệ để duy trì luồng bình thường của chương trình.

- Exception Handling chủ yếu được sử dụng để xử lý ngoại lệ checked. Nếu xảy ra bất kỳ ngoại lệ unchecked như NullPointerException, đó là lỗi của lập trình viên mà anh ta không thực hiện kiểm tra trước khi code được sử dụng.

- Cú pháp của throws trong java
```java
return_type method_name() throws exception_class_name {  
    / /method code
}
```

- Chỉ nên khai báo ngoại lệ checked bởi vì: 
    - Ngoại lệ **unchecked**: nằm trong sự kiểm soát của bạn.
    - **error**: nằm ngoài sự kiểm soát của bạn, ví dụ bạn sẽ không thể làm được bất kì điều gì khi các lỗi VirtualMachineError hoặc StackOverflowError xảy ra.

- Lợi ích của từ khóa throws trong java: Ngoại lệ checked có thể được ném ra ngoài và được xử lý ở một hàm khác. Cung cấp thông tin cho caller của phương thức về các ngoại lệ.

- Quy tắc: Nếu bạn đang gọi một phương thức khai báo throws một ngoại lệ, bạn phải bắt hoặc throws ngoại lệ đó. Có hai trường hợp:
    - TH1: Bạn đã bắt ngoại lệ, tức là xử lý ngoại lệ bằng cách sử dụng try/catch.
    - TH2: Bạn khai báo ném ngoại lệ, tức là sử dụng từ khóa throws với phương thức.


> Ví dụ về từ khóa throws trong java: Duới đây là ví dụ về mệnh đề throws trong java mô tả rằng ngoại lệ checked có thể được truyền ra bằng từ khóa throws.

```java
import java.io.IOException;
 
public class TestThrows1 {
    void m() throws IOException {
        throw new IOException("Loi thiet bi");// checked exception
    }
 
    void n() throws IOException {
        m();
    }
 
    void p() {
        try {
            n();
        } catch (Exception e) {
            System.out.println("ngoai le duoc xu ly");
        }
    }
 
    public static void main(String args[]) {
        TestThrows1 obj = new TestThrows1();
        obj.p();
        System.out.println("luong binh thuong...");
    }
}
```
```
ngoai le duoc xu ly
luong binh thuong...
```

> Ví dụ: TH1: xử lý ngoại lệ với try/catch: Trong trường hợp bạn xử lý ngoại lệ, code sẽ được thực thi tốt cho dù ngoại lệ có xuất hiện trong chương trình hay không.

```java
import java.io.IOException;
 
class M {
    void method() throws IOException {
        throw new IOException("Loi thiet bi");
    }
}
 
public class TestThrows2 {
    public static void main(String args[]) {
        try {
            M m = new M();
            m.method();
        } catch (Exception e) {
            System.out.println("Ngoai le duoc xu ly");
        }
 
        System.out.println("Luong binh thuong...");
    }
}
```
```
Ngoai le duoc xu ly
Luong binh thuong...
```

> Ví dụ: TH2: Khai báo throws ngoại lệ. 
> A) Trong trường hợp bạn khai báo throws ngoại lệ, nếu ngoại lệ không xảy ra, code sẽ được thực hiện tốt.
> B) Trong trường hợp bạn khai báo throws ngoại lệ, nếu ngoại lệ xảy ra, một ngoại lệ sẽ được ném ra tại runtime vì throws nên không xử lý ngoại đó.
```java
import java.io.IOException;
 
class M {
    void method() throws IOException {
        System.out.println("Thiet bi dang hoat dong tot");
    }
}
 
public class TestThrows2 {
    public static void main(String args[]) throws IOException {
        M m = new M();
        m.method();
        System.out.println("Luong binh thuong...");
    }
}
```
```
Thiet bi dang hoat dong tot
Luong binh thuong...
```
> Ngoại lệ xảy ra

```java
import java.io.IOException;
 
class M {
    void method() throws IOException {
        throw new IOException("Thiet bi");
    }
}
 
public class TestThrows2 {
    public static void main(String args[]) throws IOException {
        M m = new M();
        m.method();
        System.out.println("Luong binh thuong...");
    }
}
```
```
Exception in thread "main" java.io.IOException: Thiet bi
```

## Sự khác nhau giữa throw và throws trong java
Có một vài sự khác nhau giữa từ khóa throw và throws trong java được mô tả trong bảng dưới đây.

| throw                                                                 | throws                                                                                            |
| --------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------- |
| Từ khóa throw trong java được sử dụng để ném ra một ngoại lệ rõ ràng. | Từ khóa throws trong java được sử dụng để khai báo một ngoại lệ.                                  |
| Ngoại lệ checked không được truyền ra nếu chỉ sử dụng từ khóa throw.  | Ngoại lệ checked được truyền ra ngay cả khi chỉ sử dụng từ khóa throws.                           |
| Sau throw là một instance.                                            | Sau throws là một hoặc nhiều class.                                                               |
| Sau throw là một instance.                                            | Sau throws là một hoặc nhiều class.                                                               |
| Throw được sử dụng trong phương thức.                                 | Throws được khai báo ngay sau dấu đóng ngoặc đơn của phương thức.                                 |
| Bạn không thể throw nhiều exceptions.                                 | Bạn có thể khai báo nhiều exceptions, Ví dụ: public void method()throws IOException,SQLException. |

> Ví dụ về throw trong java
```java
void m() {
    int n;
    if (n < 0) {
        throw new ArithmeticException("sorry");
    }
}
```

> Ví dụ về throws trong java
```java
void m()throws ArithmeticException {  
    //method code  
}
```

> Ví dụ về throw và throws trong java
```java
void m() throws ArithmeticException {  
    throw new ArithmeticException("sorry");  
}
```