## List trong java
List là một interface trong java. Nó chứa các phương thức để chèn và xóa các phần tử dựa trên chỉ số index.

> Khai báo interface List trong java
```java
public interface List<E> extends Collection<E>
```

Các phương thức của interface List trong java
- **void add(int index,Object element)** : Nó được sử dụng để chèn các phần tử vào list tại chỉ số index.
- **boolean addAll(int index,Collection c)** : Nó được sử dụng để chèn tất cả các yếu tố của c vào danh sách tại chỉ số index.
- **object get(int index)** : Nó được sử dụng để trả về đối tượng được lưu trữ tại chỉ số index trong list.
- **object set(int index,Object element)** : Nó được sử dụng để gán phần tử cho vị trí được chỉ định index trong list.
- **object remove(int index)** : Nó được sử dụng để xóa các phần tử tại vị trí có chỉ số index và trả về phần tử đã xóa.
- **ListIterator listIterator()** : Nó được sử dụng để trả về một Iterator mà bắt đầu từ phần tử đầu tiên của list.
- **ListIterator listIterator(int index)** : Nó được sử dụng để trả về một Iterator mà phần tử bắt đầu từ chỉ số index chỉ định.


> Ví dụ 1: Hãy xem ví dụ đơn giản về List trong java sau:
```java
import java.util.ArrayList;
import java.util.List;
 
public class ListExample {
    public static void main(String args[]) {
        List<String> list = new ArrayList<String>();
        list.add("Java");
        list.add("C++");
        list.add("PHP");
        list.add(1, "Python");
        System.out.println("Phan tu co index = 2 la: " + list.get(2));
        // show list
        for (String s : list) {
            System.out.println(s);
        }
    }
}
```
```
Phan tu co index = 2 la: C++
Java
Python
C++
PHP
```

> Ví dụ 2: Sử dụng Arrays.asList():
```java
import java.util.Arrays;
import java.util.List;
 
public class ListExample1 {
    public static void main(String args[]) {
        // create new array
        String[] arr = { "Java", "C++", "PHP", "Python" };
        // convert array to List
        List<String> list = Arrays.asList(arr);
        // show list
        for (String s : list) {
            System.out.println(s);
        }
    }
}
```
```
Java
C++
PHP
Python
```
