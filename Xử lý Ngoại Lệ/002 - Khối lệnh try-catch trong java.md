# Khối lệnh try trong java
Khối lệnh try trong java được sử dụng để chứa một đoạn code có thế xảy ra một ngoại lệ. Nó phải được khai báo trong phương thức.
Sau một khối lệnh try bạn phải khai báo khối lệnh catch hoặc finally hoặc cả hai.

- Cú pháp của khối lệnh try-catch trong java
```java
try {  
    // code có thể ném ra ngoại lệ
} catch(Exception_class_Name ref) {
    // code xử lý ngoại lệ
}
```
- Cú pháp của khối lệnh try-finally trong java
```java
try {  
    // code có thể ném ra ngoại lệ
} finally {
    // code trong khối này luôn được thực thi
}  
```
## Khối lệnh catch trong java
Khối catch trong java được sử dụng để xử lý các Exception. Nó phải được sử dụng sau khối try.
Bạn có thể sử dụng nhiều khối catch với một khối try duy nhất.

> Vấn đề không có ngoại lệ xử lý. Trong ví dụ này, phần còn lại của code không được thực thi (dòng chữ "rest of the code..." không được in ra màn hình). Tất cả các lệnh không được thực thi sau khi xảy ra ngoại lệ.

```java
public class TestTryCatch1 {
    public static void main(String args[]) {
        int data = 50 / 0;  // ném ra ngoại lê ở đây
        System.out.println("rest of the code...");
    }
}
```
```
Exception in thread "main" java.lang.ArithmeticException: / by zero
 at vn.tpv.exception1.TestTryCatch1.main(TestTryCatch1.java:5)
```
> Giải quyết bằng xử lý ngoại lệ. Trong ví dụ này, phần còn lại của code được thực thi nghĩa là dòng chữ "rest of the code..." được in ra màn hình.

```java
public class TestTryCatch2 {
    public static void main(String args[]) {
        try {
            int data = 50 / 0;
        } catch (ArithmeticException e) {
            System.out.println(e);
        }
        System.out.println("rest of the code...");
    }
}
```
```
java.lang.ArithmeticException: / by zero
rest of the code...
```

## Đa khối lệnh catch trong java
Nếu bạn phải thực hiện các tác vụ khác nhau mà ở đó có thể xảy ra các ngoại lệ khác nhau, hãy sử dụng đa khối lệnh catch trong java.
- Quy tắc 1: Vào một thời điểm chỉ xảy ra một ngoại lệ và tại một thời điểm chỉ có một khối catch được thực thi.
- Quy tắc 2: Tất cả các khối catch phải được sắp xếp từ cụ thể nhất đến chung nhất, tức là phải khai báo khối lệnh catch để xử lý lỗi ArithmeticException trước khi khai báo catch để xử lý lỗi Exception.

> Hãy xem ví dụ sau về việc sử dụng nhiều khối lệnh catch trong java
```java
public class TestMultipleCatchBlock {
    public static void main(String args[]) {
        try {
            int a[] = new int[5];
            a[5] = 30 / 0;
        } catch (ArithmeticException e) {
            System.out.println("task1 is completed");
        } catch (ArrayIndexOutOfBoundsException e) {
            System.out.println("task 2 completed");
        } catch (Exception e) {
            System.out.println("common task completed");
        }
 
        System.out.println("rest of the code...");
    }
}
```
```
task1 is completed
rest of the code...
```
> Hãy xem ví dụ sau về cách áp dụng các quy tắc. Chương trình này bị lỗi tại compile-time là vì khi có ngoại lệ xảy ra thì các khối lệnh catch (ArithmeticException e) và catch (ArrayIndexOutOfBoundsException e) không bao giờ được thực thi, do khối catch (Exception e) đã bắt tất cả các ngoại lệ rồi.
```java
public class TestMultipleCatchBlock1 {
    public static void main(String args[]) {
        try {
            int a[] = new int[5];
            a[5] = 30 / 0;
        } catch (Exception e) {
            System.out.println("common task completed");
        } catch (ArithmeticException e) {
            System.out.println("task1 is completed");
        } catch (ArrayIndexOutOfBoundsException e) {
            System.out.println("task2 is completed");
        }
        System.out.println("rest of the code...");
    }
}
```
```
Compile-time error
```
## Khối lệnh try lồng nhau trong java
Khối try trong một khối try được gọi là khối try lồng nhau trong java.

> Tại sao phải sử dụng khối try lồng nhau ? : Đôi khi một tình huống có thể phát sinh khi một phần của một khối lệnh có thể xảy ra một lỗi và toàn bộ khối lệnh chính nó có thể xảy ra một lỗi khác. Trong những trường hợp như vậy, trình xử lý ngoại lệ phải được lồng nhau. Hãy xem ví dụ đơn giản sau về khối lệnh try lồng nhau.
```java
public class TestException {
    public static void main(String args[]) {
        try {
            try {
                System.out.println("Thuc hien phep chia");
                int b = 39 / 0;
            } catch (ArithmeticException e) {
                System.out.println(e);
            }
 
            try {
                int a[] = new int[5];
                a[5] = 4;
            } catch (ArrayIndexOutOfBoundsException e) {
                System.out.println(e);
            }
 
            System.out.println("khoi lenh khac");
        } catch (Exception e) {
            System.out.println("xy ly ngoai le");
        }
 
        System.out.println("tiep tuc chuong trinh..");
    }
}
```

## Khối lệnh finally trong java
- Khối lệnh finally trong java được sử dụng để thực thi các lệnh quan trọng như đóng kết nối, đóng cá stream,...
- Khối lệnh finally trong java luôn được thực thi cho dù có ngoại lệ xảy ra hay không hoặc gặp lệnh return trong khối try.
- Khối lệnh finally trong java được khai báo sau khối lệnh try hoặc sau khối lệnh catch.
- Khối finally có thể được sử dụng để chèn lệnh "cleanup" vào chương trình như việc đóng file, đóng các kết nối,...
- Đối với mỗi khối try, có thể có không hoặc nhiều khối catch, nhưng chỉ có một khối finally.
- Khối finally sẽ không được thực thi nếu chương trình bị thoát (bằng cách gọi System.exit() hoặc xảy ra một lỗi không thể tránh khiến chương trình bị chết).

![image-4](/image/flow-cua-khoi-lenh-finally-trong-java.png)

> Dưới đây là các trường hợp khác nhau về việc sử dụng khối finally trong java.

> 1. Sử dụng khối lệnh finally nơi ngoại lệ không xảy ra.
```java
public class TestFinallyBlock {
    public static void main(String args[]) {
        try {
            int data = 25 / 5;
            System.out.println(data);
        } catch (NullPointerException e) {
            System.out.println(e);
        } finally {
            System.out.println("finally block is always executed");
        }
        System.out.println("rest of the code...");
    }
}
```
```
5
finally block is always executed
rest of the code...
```
> 2. Sử dụng khối lệnh finally nơi ngoại lệ xảy ra nhưng không xử lý.
```java
public class TestFinallyBlock1 {
    public static void main(String args[]) {
        try {
            int data = 25 / 0;
            System.out.println(data);
        } catch (NullPointerException e) {
            System.out.println(e);
        } finally {
            System.out.println("finally block is always executed");
        }
        System.out.println("rest of the code...");
    }
}
```
```
finally block is always executed
Exception in thread "main" java.lang.ArithmeticException: / by zero
```
> 3. Sử dụng khối lệnh finally nơi ngoại lệ xảy ra và được xử lý.
```java
public class TestFinallyBlock2 {
    public static void main(String args[]) {
        try {
            int data = 25 / 0;
            System.out.println(data);
        } catch (ArithmeticException e) {
            System.out.println(e);
        } finally {
            System.out.println("finally block is always executed");
        }
        System.out.println("rest of the code...");
    }
}
```
```
java.lang.ArithmeticException: / by zero
finally block is always executed
rest of the code...
```

> 4. Sử dụng khối lệnh finally trong trường hợp trong khối try có lệnh return.
```java
public class TestFinallyBlock3 {
    public static void main(String args[]) {
        try {
            int data = 25;
            if (data % 2 != 0) {
             System.out.println(data + " is odd number");
             return;
            }
        } catch (ArithmeticException e) {
            System.out.println(e);
        } finally {
            System.out.println("finally block is always executed");
        }
        System.out.println("rest of the code...");
    }
}
```

```
25 is odd number
finally block is always executed
```
