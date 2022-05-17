# Set trong Java
- Set là một interface kế thừa Collection interface trong java.
- Set trong java là một Collection không thể chứa các phần tử trùng lặp.
- Set được triển khai bởi HashSet, LinkedHashSet, Treeset hoặc EnumSet.
    - HashSet lưu trữ các phần tử của nó trong bảng băm, là cách thực hiện tốt nhất, tuy nhiên nó không đảm bảo về thứ tự các phần tử được chèn vào.
    - TreeSet lưu trữ các phần tử của nó trong một cây, sắp xếp các phần tử của nó dựa trên các giá trị của chúng, về cơ bản là chậm hơn HashSet.
    - LinkedHashSet được triển khai dưới dạng bảng băm với có cấu trúc dữ liệu danh sách liên kết, sắp xếp các phần tử của nó dựa trên thứ tự chúng được chèn vào tập hợp (thứ tự chèn).
    - EnumSet là một cài đặt chuyên biệt để sử dụng với các kiểu enum.

> Khai báo interface Set trong java
```java
public interface Set<E> extends Collection<E>
```
## Khai báo Set trong Java
Vì Set là một (giao diện) interface, bạn cần khởi tạo một triển khai cụ thể của giao diện để sử dụng nó. Về cơ bản bạn có thể chọn các collection sau:
- HashSet
- LinkedHashSet
- TreeSet
- EnumSet

```java
Set setA = new EnumSet();
Set setB = new HashSet();
Set setC = new LinkedHashSet();
Set setD = new TreeSet();
```

## Các phương thức của interface Set trong java

- **boolean add(Object element)**: Chèn các phần tử vào set.
- **boolean addAll(Collection c)**: Chèn tất cả các phần tử của c vào set.
- **void clear()**: Xóa tất cả các phần tử khỏi set.
- **boolean contains(Object element)**: Trả về true nếu tập hợp này chứa phần tử đã chỉ định.
- **boolean containsAll(Collection c)**: Trả về true nếu set chứa tất cả các phần tử của collection c đã chỉ định.
- **boolean equals(Object o)**: So sánh các đối tượng được chỉ định với set.
- **boolean isEmpty()**: Trả về true nếu set không chứa phần tử.
- **int hashCode()**: Trả về giá trị mã băm
- **Iterator iterator()**: Trả về một trình vòng lặp iterator để duyệt qua các phần tử của set.
- **boolean remove(Object o)**: Xóa phần tử đã chỉ định khỏi set.
- **boolean removeAll(Collection c)**: Xóa khỏi set tất cả các phần tử của nó được chứa trong collection c đã chỉ định.
- **boolean retainAll(Collection c)**: Chỉ giữ lại các phần tử trong set được chứa trong collection c đã chỉ định.
- **int size()**: Trả về số lượng các phần tử của set.
- **Object[] toArray()**: Trả về một mảng chứa tất cả các phần tử trong set.
- **T[] toArray(T[] a)**: Trả về một mảng chứa tất cả các phần tử trong set, kiểu run-time của mảng trả về là kiểu đã chỉ định.

> Ví dụ 1: Hãy xem ví dụ đơn giản về Set trong java sau, để cho bạn cảm nhận về cách Set hoạt động:

```java
package vn.viettuts.set;
 
import java.util.HashSet;
import java.util.Set;
 
public class SetExam {
    public static void main(String[] args) {
        Set<String> setA = new HashSet<String>();
        setA.add("Java");
        setA.add("Python");
        setA.add("Java");
        setA.add("PHP");
        System.out.println("Số phần tử của setA: " + setA.size());
        System.out.println("Các phần tử của setA: " + setA);
        System.out.println("setA có chứa Java không? " + setA.contains("Java"));
        System.out.println("setA có chứa C++ không? " + setA.contains("C++"));
    }
}
```
```
Số phần tử của setA: 3
Các phần tử của setA: [Java, PHP, Python]
setA có chứa Java không? true
setA có chứa C++ không? false
```