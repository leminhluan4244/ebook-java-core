# Truyền Exception cho caller
Một ngoại lệ đầu tiên được ném ra từ phía trên của call stack (stack chứa các phương thức gọi đến nhau) và nếu nó không được catch, nó sẽ giảm xuống ngăn xếp đến phương thức trước, nếu không được catch ở đó, ngoại lệ lại giảm xuống phương thức trước, và cứ như vậy cho đến khi chúng được catch hoặc cho đến khi chúng chạm đến đáy của stack.Điều này được gọi là truyền ngoại lệ (truyền exception trong java).

- Theo mặc định, Các ngoại lệ unchecked được chuyển tiếp trong chuỗi gọi (được truyền).
- Theo mặc định, Các ngoại lệ checked không được chuyển tiếp trong các hàm.

> Ví dụ 1: Ví dụ về tryền exception trong java. Trong ví dụ về ngoại lệ trên xảy ra trong phương thức m() nơi nó không được xử lý, do đó nó được truyền đến phương thức n() nhưng nó không được xử lý, một lần nữa nó được truyền đến phương thức p() trong đó ngoại lệ được xử lý.
> Ngoại lệ có thể được xử lý trong bất kỳ phương thức nào trong call stack hoặc trong phương thức main(), phương thức p(), phương thức n() hoặc m().

```java
class TestExceptionPropagation1 {
    void m() {
        int data = 50 / 0;
    }
 
    void n() {
        m();
    }
 
    void p() {
        try {
            n();
        } catch (Exception e) {
            System.out.println("exception handled");
        }
    }
 
    public static void main(String args[]) {
        TestExceptionPropagation1 obj = new TestExceptionPropagation1();
        obj.p();
        System.out.println("normal flow...");
    }
}
```
```
Output:exception handled
       normal flow...
```

> Ví dụ 2: Chương trình dưới đây mô tả ngoại lệ đã checked không được truyền
```java
class TestExceptionPropagation2 {
    void m() {
        throw new java.io.IOException("device error");// checked exception
    }
 
    void n() {
        m();
    }
 
    void p() {
        try {
            n();
        } catch (Exception e) {
            System.out.println("exception handeled");
        }
    }
 
    public static void main(String args[]) {
        TestExceptionPropagation2 obj = new TestExceptionPropagation2();
        obj.p();
        System.out.println("normal flow");
    }
}
```
```
Output:Compile Time Error
```