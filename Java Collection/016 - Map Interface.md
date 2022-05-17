# Map trong Java
- Map là một interface kế thừa Collection interface trong java.
- Map được sử dụng để lưu trữ và truy xuất dữ liệu theo cặp key và value
- Mỗi cặp key và value được gọi là mục nhập (entry)
- Map trong java chỉ chứa các giá trị key duy nhất.
- Map rất hữu ích nếu bạn phải tìm kiếm, cập nhật hoặc xóa các phần tử trên dựa vào các key.
- Map được triển khai bởi HashMap, LinkedHashMap, TreeMap.

## Map.Entry Interface
Entry là một interface con của Map. Vì vậy, chúng ta được truy cập nó bằng tên Map.Entry. Nó cung cấp các phương pháp để truy xuất các key và value.
- **Object getKey()**: Lấy key của Map.
- **Object getValue()**: Lấy value của Map.

> Ví dụ 1: sử dụng Generic

```java
package vn.viettuts.collection;
 
import java.util.HashMap;
import java.util.Map;
import java.util.Set;
 
public class MapExample1 {
    public static void main(String args[]) {
        // init map
        Map<Integer, String> map = new HashMap<Integer, String>();
        map.put(100, "A");
        map.put(101, "B");
        map.put(102, "C");
        // show map
        Set<Integer> set = map.keySet();
        for (Integer key : set) {
            System.out.println(key + " " + map.get(key));
        }
    }
}
```
```
100 A
101 B
102 C
```

> Ví dụ 2: KHÔNG sử dụng Generic

```java
package vn.viettuts.collection;
 
import java.util.HashMap;
import java.util.Map;
import java.util.Set;
 
public class MapExample2 {
    public static void main(String[] args) {
        // init map
        Map map = new HashMap();
        // add elements to map
        map.put(1, "Java");
        map.put(3, "C++");
        map.put(2, "PHP");
        map.put(4, "Python");
        // show Map
        Set set = map.keySet();
        for (Object key : set) {
            System.out.println(key + " " + map.get(key));
        }
    }
}
```
```
1 Java
2 PHP
3 C++
4 Python
```

> Ví dụ 3: sử dụng Map.Entry interface để truy cập các phần tử của Map

```java
package vn.viettuts.collection;
 
import java.util.HashMap;
import java.util.Map;
 
public class MapExample3 {
    public static void main(String args[]) {
        // init map
        Map<Integer, String> map = new HashMap<Integer, String>();
        // add elements to map
        map.put(1, "Java");
        map.put(3, "C++");
        map.put(2, "PHP");
        map.put(4, "Python");
        // show map
        for (Map.Entry<Integer, String> entry : map.entrySet()) {
            System.out.println(entry.getKey() + " " + entry.getValue());
        }
    }
}
```
```
1 Java
2 PHP
3 C++
4 Python
```