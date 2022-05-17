## ListIterator trong java
ListIterator là một interface được sử dụng để duyệt các phần tử của List trong java.

> Khai báo interface ListIterator trong java
```java
public interface ListIterator<E> extends Iterator<E>
```
Các phương thức của interface ListIterator trong java
- **boolean hasNext()** : Phương pháp này trả về true nếu list interator có tồn tại phần tử kế tiếp phần tử hiện tại.
- **Object next()** : Phương thức này trả về phần tử kế tiếp trong danh sách và vị trí con trỏ tăng lên 1.
- **boolean hasPrevious()** : Phương pháp này trả về true nếu list interator có tồn tại phần tử kế sau phần tử hiện tại.
- **Object previous()** : Phương thức này trả về phần tử kế sau trong danh sách và vị trí con trỏ giảm đi 1.

> Ví dụ về ListIterator trong java: Hãy xem ví dụ đơn giả về việc duyệt các phần tử của List trong java bằng cách sử dụng ListIterator:

```java
import java.util.ArrayList;
import java.util.List;
import java.util.ListIterator;
 
public class ListExample {
    public static void main(String args[]) {
        List<String> list = new ArrayList<String>();
        list.add("Java");
        list.add("C++");
        list.add("PHP");
        list.add(1, "Python");
        System.out.println("Phan tu co index = 2 la: " + list.get(2));
 
        ListIterator<String> itr = list.listIterator();
        System.out.println("Duyet cac phan tu tu dau den cuoi:");
        while (itr.hasNext()) {
            System.out.println("\t" + itr.next());
        }
        System.out.println("Duyet cac phan tu tu cuoi ve dau:");
        while (itr.hasPrevious()) {
            System.out.println("\t" + itr.previous());
        }
    }
}
```
```
Phan tu co index = 2 la: C++
Duyet cac phan tu tu dau den cuoi:
 Java
 Python
 C++
 PHP
Duyet cac phan tu tu cuoi ve dau:
 PHP
 C++
 Python
 Java
```