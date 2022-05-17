
## So sánh ArrayList vs LinkedList
- ArrayList và LinkedList đều là lớp triển khai của List Interface. 
- Cả hai lớp này đều là lớp không đồng bộ (non-synchronized).

Có vài sự khác nhau giữa ArrayList và LinkedList:
- Cách lưu trữ các phần tử
    - ArrayList nội bộ sử dụng mảng động để lưu trữ các phần tử.
    - LinkedList nội bộ sử dụng danh sách liên kết doubly để lưu trữ các phần tử.
- Thao tác
    - Thao tác ArrayList là chậm bởi vì nó sử dụng nội bộ mảng. Nếu bất kỳ phần tử nào được xoá khỏi mảng, tất cả các bit được chuyển trong bộ nhớ.
    - Thao tác với LinkedList là nhanh hơn so với ArrayList bởi vì nó sử dụng danh sách liên kết doubly do đó không cần chuyển đổi bit nào trong bộ nhớ.
- Hoạt động
    -  Lớp ArrayList trong java chỉ có thể hoạt động như một list vì nó chỉ implements giao tiếp List.
    - Lớp LinkedList trong java có thể hoạt động như một list và queue(hàng đợi) vì nó implements các giao tiếp List và Deque.
- Sử dụng:
    - ArrayList là tốt hơn trong việc lưu trữ và truy cập dữ liệu.
    - LinkedList là tốt hơn trong việc thao tác dữ liệu (cập nhật và xóa phần tử)

> Ví dụ cách sử dụng

```java
import java.util.ArrayList;
import java.util.LinkedList;
import java.util.List;
 
public class ArraylistAndLinkedListExample {
    public static void main(String args[]) {
 
        // create arrayList
        List<String> arrayList = new ArrayList<String>();
        // add object in arraylist
        arrayList.add("Java");
        arrayList.add("C++");
        arrayList.add("PHP");
        arrayList.add("Python");
 
        // create linkedlist
        List<String> linkedList = new LinkedList<String>();
        // aadd object in linkedlist
        linkedList.add("Hiberante");
        linkedList.add("Struts2");
        linkedList.add("Spring");
        linkedList.add("Mybatis");
 
        System.out.println("arraylist: " + arrayList);
        System.out.println("linkedlist: " + linkedList);
    }
}
```
```
arraylist: [Java, C++, PHP, Python]
linkedlist: [Hiberante, Struts2, Spring, Mybatis]
```