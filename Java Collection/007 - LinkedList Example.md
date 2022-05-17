# Các ví dụ về sử dụng LinkedList trong java

### Khởi tạo một LinkedList

Để khai báo một LinkedList, chúng ta cần phải import gói thư viện java.util.LinkedList của Java. Cú pháp import như sau:

```java
// import gói thư viện java.util.LinkedList
import java.util.LinkedList;
 
public class KhoiTaoLinkedList {
    public static void main(String[] args) {
        // khai báo 1 LinkedList có tên là listString
        // có kiểu là String
        LinkedList<String> listString = new LinkedList<String>();
    }
}
```
Ngoài ra, nếu chúng ta đã biết trước số lượng phần tử thì chúng ta có thể khai báo kèm với số lượng phần tử của nó. Ví dụ dưới đây sẽ khai báo một LinkedList có kiểu String và có 20 phần tử:

```java
// import gói thư viện java.util.LinkedList
import java.util.LinkedList;
 
public class KhoiTaoLinkedList {
    public static void main(String[] args) {
        // khai báo 1 LinkedList có tên là listString
        // có kiểu là String
        LinkedList<String> listString = new LinkedList<String>(20);
    }
}
```

### Hiển thị các phần tử có trong LinkedList
Để hiển thị các phần tử có trong LinkedList, chúng ta có các cách như sau:

#### Hiển thị theo tên của LinkedList.

```java
package vn.viettuts.linkedlist;
 
import java.util.LinkedList;
 
public class DuyetLinkedList1 {
    public static void main(String[] args) {
        // khai báo 1 LinkedList có tên là list
        // có kiểu là String
        LinkedList<String> list = new LinkedList<String>();
        // thêm các phần tử vào list
        list.add("Java");
        list.add("C++");
        list.add("PHP");
        list.add("Java");
        // hiển thị các phần tử của list
        System.out.println("Các phần tử có trong list là: ");
        System.out.println(list);
    }
}
```
```
Các phần tử có trong list là: 
[Java, C++, PHP, Java]
```
#### Duyệt các phần tử của LinkedList - sử dụng vòng lặp for
```java
package vn.viettuts.linkedlist;
 
import java.util.LinkedList;
 
public class DuyetLinkedList2 {
    public static void main(String[] args) {
        // khai báo 1 LinkedList có tên là list
        // có kiểu là String
        LinkedList<String> list = new LinkedList<String>();
        // thêm các phần tử vào list
        list.add("Java");
        list.add("C++");
        list.add("PHP");
        list.add("Java");
        // sử dụng vòng lặp for - hiển thị các phần tử của list
        System.out.println("Các phần tử có trong list là: ");
        for (int i = 0; i < list.size(); i++) {
            System.out.println(list.get(i));
        }
    }
}
```
```
Các phần tử có trong list là: 
Java, 
C++, 
PHP, 
Java
```

#### Duyệt các phần tử của LinkedList - sử dụng vòng lặp for cải tiến

```java
package vn.viettuts.linkedlist;
 
import java.util.LinkedList;
 
public class DuyetLinkedList3 {
    public static void main(String[] args) {
        // khai báo 1 LinkedList có tên là list
        // có kiểu là String
        LinkedList<String> list = new LinkedList<String>();
        // thêm các phần tử vào list
        list.add("Java");
        list.add("C++");
        list.add("PHP");
        list.add("Java");
        // sử dụng vòng lặp for cải tiến - hiển thị các phần tử của list
        System.out.println("Các phần tử có trong list là: ");
        for (String str : list) {
            System.out.println(str);
        }
    }
}
```
```
Các phần tử có trong list là: 
Java, 
C++, 
PHP, 
Java
```

#### Duyệt các phần tử của LinkedList - sử dụng Iterator.

Để sử dụng được Iterator chúng ta cần phải import gói thư viện java.util.Iterator của Java.

```java
package vn.viettuts.linkedlist;
 
import java.util.LinkedList;
import java.util.Iterator;
 
public class DuyetLinkedList4 {
    public static void main(String[] args) {
        // khai báo 1 LinkedList có tên là list
        // có kiểu là String
        LinkedList<String> list = new LinkedList<String>();
        // thêm các phần tử vào list
        list.add("Java");
        list.add("C++");
        list.add("PHP");
        list.add("Java");
        // sử dụng Iterator - hiển thị các phần tử của list
        Iterator<String> iterator = list.iterator();
        System.out.println("Các phần tử có trong list là: ");
        while (iterator.hasNext()) {
            System.out.println((String) iterator.next());
        }
    }
}
```
```
Các phần tử có trong list là: 
Java, 
C++, 
PHP, 
Java
```
#### Duyệt các phần tử của LinkedList - sử dụng ListIterator.

Vì LinkedList là một lớp triển khai của List Interface nên nó cũng có thể sử dụng ListIterator để duyệt qua các phần tử của nó. Để sử dụng được ListIterator chúng ta cần phải import gói thư viện java.util.ListIterator của Java.

```java
package vn.viettuts.linkedlist;
 
import java.util.LinkedList;
import java.util.ListIterator;
 
public class DuyetLinkedList5 {
    public static void main(String[] args) {
        // khai báo 1 LinkedList có tên là list
        // có kiểu là String
        LinkedList<String> list = new LinkedList<String>();
        // thêm các phần tử vào list
        list.add("Java");
        list.add("C++");
        list.add("PHP");
        list.add("Java");
        // sử dụng ListIterator - hiển thị các phần tử của list
        ListIterator<String> iterator = list.listIterator();
        System.out.println("Các phần tử có trong list là: ");
        while (iterator.hasNext()) {
            System.out.println((String) iterator.next());
        }
    }
}
```
```
Các phần tử có trong list là: 
Java, 
C++, 
PHP, 
Java
```

### Các phương thức addAll(), removeAll(), retainAll() của lớp LinkedList

Ví dụ sau minh họa cách sử dụng các phương thức addAll(), removeAll(), retainAll() của lớp LinkedList trong Java

```java
package vn.viettuts.linkedlist;
 
import java.util.LinkedList;
 
public class PhuongThucLinkedList1 {
    public static void main(String[] args) {
        // khai báo 1 LinkedList có tên là list
        // có kiểu là String
        LinkedList<String> list = new LinkedList<String>();
        // Add objects to list
        list.add("Java");
        list.add("C++");
        list.add("PHP");
        list.add("Java");
 
        System.out.println("ví dụ sử dụng phương thức addAll()");
        System.out.println("-----------------------------------");
        // thêm các phần tử của list vào listA
        LinkedList<String> listA = new LinkedList<String>();
        listA.addAll(list);
        System.out.print("listA:");
        showList(listA);
 
        System.out.println("\nví dụ sử dụng phương thức retainAll()");
        System.out.println("-----------------------------------");
        // khởi tạo listB
        LinkedList<String> listB = new LinkedList<String>();
        listB.add("Java");
        // xóa những phần tử không thuộc listB khỏi listA
        listA.retainAll(listB);
        System.out.print("listA:");
        showList(listA);
 
        System.out.println("\nví dụ sử dụng phương thức removeAll()");
        System.out.println("-----------------------------------");
        // xóa những phần tử thuộc listB  khỏi list
        list.removeAll(listB);
        System.out.print("list:");
        showList(list);
    }
 
    public static void showList(LinkedList<String> list) {
        // Show list through for-each
        for (String obj : list) {
            System.out.print("\t" + obj + ", ");
        }
        System.out.println();
    }
}
```
```
ví dụ sử dụng phương thức addAll()
-----------------------------------
listA:	Java, 	C++, 	PHP, 	Java, 

ví dụ sử dụng phương thức retainAll()
-----------------------------------
listA:	Java, 	Java, 

ví dụ sử dụng phương thức removeAll()
-----------------------------------
list:	C++, 	PHP, 
```

### Truy cập phần tử của LinkedList
Java cung cấp cho chúng ta phương thức get() để truy cập đến 1 phần tử bất kỳ trong LinkedList thông qua chỉ số của phần tử đó. Chỉ số của LinkedList trong Java bắt đầu từ 0.

```java
package vn.viettuts.linkedlist;
 
import java.util.LinkedList;
 
public class TruyCapLinkedList1 {
    public static void main(String[] args) {
        // khai báo 1 LinkedList có tên là list
        // có kiểu là String
        LinkedList<String> list = new LinkedList<String>();
        // thêm các phần tử vào list
        list.add("Java");
        list.add("C++");
        list.add("PHP");
        list.add("Java");
         
        // truy cập phần tử có chỉ số 3 của list
        System.out.println(list.get(3));
    }
}
```
```
Java
```

### Cập nhật giá trị của phần tử Linkedlist

Để cập nhật giá trị của phần tử trong LinkedList, Java cung cấp cho chúng ta phương thức set(index, element), trong đó index là chỉ số của phần tử cần cập nhật và element là phần tử mới để thay thế.

```java
package vn.viettuts.linkedlist;
 
import java.util.LinkedList;
 
public class CapNhatLinkedList1 {
    public static void main(String[] args) {
        // khai báo 1 LinkedList có tên là list
        // có kiểu là String
        LinkedList<String> list = new LinkedList<String>();
        // thêm các phần tử vào list
        list.add("Java");
        list.add("C++");
        list.add("PHP");
        list.add("Java");
 
        System.out.println("list trước khi cập nhật: ");
        System.out.println(list);
        // cập nhật giá trị cho phần tử có chỉ số là 3 (Java)
        list.set(3, "Python");
        System.out.println("list trước khi cập nhật: ");
        System.out.println(list);
    }
}
```
```
list trước khi cập nhật: 
[Java, C++, PHP, Java]
list trước khi cập nhật: 
[Java, C++, PHP, Python]
```

### Xóa phần tử LinkedList

Để xóa phần tử trong LinkedList, Java cung cấp cho chúng ta 2 phương thức có sẵn đó là phương thức clear() và phương thức remove().

```java
// Phương thức clear()
// Phương thức clear() sẽ xóa tất cả các phần tử có trong LinkedList. Sau đây là ví dụ minh họa phương thức này.

package vn.viettuts.linkedlist;
 
import java.util.LinkedList;
 
public class XoaLinkedList1 {
    public static void main(String[] args) {
        // khai báo 1 LinkedList có tên là list
        // có kiểu là String
        LinkedList<String> list = new LinkedList<String>();
        // thêm các phần tử vào list
        list.add("Java");
        list.add("C++");
        list.add("PHP");
        list.add("Python");
 
        System.out.println("Số phần tử của list ban đầu : " + list);
        System.out.println("Các phần tử của list ban đầu: " + list.size());
        // clear list
        list.clear();
        System.out.println("\nSố phần tử của list sau khi clear: " + list);
        System.out.println("Các phần tử của list sau khi clear: " + list.size());
    }
}
```
```
Số phần tử của list ban đầu : [Java, C++, PHP, Python]
Các phần tử của list ban đầu: 4

Số phần tử của list sau khi clear: []
Các phần tử của list sau khi clear: 0
```
### Phương thức remove()
Phương thức remove() sẽ xóa phần tử ra khỏi LinkedList theo 2 cách đó là xóa dựa vào chỉ số của phần tử và xóa trực tiếp phần tử đó (không cần biết đến chỉ số của nó). Ví dụ dưới đây sẽ minh họa 2 cách xóa này:

```java
package vn.viettuts.linkedlist;
 
import java.util.LinkedList;
 
public class XoaLinkedList1 {
    public static void main(String[] args) {
        // khai báo 1 LinkedList có tên là list
        // có kiểu là String
        LinkedList<String> list = new LinkedList<String>();
        // thêm các phần tử vào list
        list.add("Java");
        list.add("C++");
        list.add("PHP");
        list.add("Python");
 
        System.out.println("Số phần tử của list ban đầu : " + list);
        System.out.println("Các phần tử của list ban đầu: " + list.size());
        // remove phần tử có chỉ số index = 1 khỏi list
        list.remove(1);
        System.out.println("\nSố phần tử của list sau khi remove phan tu co index = 1: "
                + list);
        System.out.println("Các phần tử của list sau khi remove phan tu co index = 1: "
                + list.size());
        // remove phần tử có chỉ số index = 1 khỏi list
        list.remove("PHP");
        System.out.println("\nSố phần tử của list sau khi remove phan tu \"PHP\": "
                + list);
        System.out.println("Các phần tử của list sau khi remove phan tu \"PHP\": "
                + list.size());
    }
}
```
```
Số phần tử của list ban đầu : [Java, C++, PHP, Python]
Các phần tử của list ban đầu: 4

Số phần tử của list sau khi remove phan tu co index = 1: [Java, PHP, Python]
Các phần tử của list sau khi remove phan tu co index = 1: 3

Số phần tử của list sau khi remove phan tu "PHP": [Java, Python]
Các phần tử của list sau khi remove phan tu "PHP": 2
```

### Tìm kiếm một phần tử LinkedList

Để tìm kiếm một phần tử trong LinkedList thì chúng ta có 3 phương pháp tìm kiếm như sau:

#### Tìm kiếm trực tiếp phần tử.

Để tìm kiếm trực tiếp phần tử, chúng ta sẽ sử dụng phương thức contains() . Kết quả trả về là true nếu tìm thấy, ngược lại trả về false.

```java
package vn.viettuts.linkedlist;
 
import java.util.LinkedList;
 
public class TimKiemLinkedList1 {
    public static void main(String[] args) {
        // khai báo 1 LinkedList có tên là list
        // có kiểu là String
        LinkedList<String> list = new LinkedList<String>();
        // thêm các phần tử vào list
        list.add("Java");
        list.add("C++");
        list.add("PHP");
        list.add("Python");
         
        // kiểm tra xem PHP có tồn tại trong list hay không?
        System.out.println(list.contains("PHP"));
        // kiểm tra xem ANDROID có tồn tại trong list hay không?
        System.out.println(list.contains("ANDROID"));
    }
}
```
```
true
false
```

#### Tìm kiếm vị trí xuất hiện đầu tiên của 1 phần tử trong LinkedList.

Để tìm kiếm vị trí xuất hiện đầu tiên của 1 phần tử trong LinkedList, chúng ta sẽ sừ dụng phương thức indexOf(). Kết quả của phương thức này sẽ trả về chỉ số xuất hiện đầu tiên của phần tử đó trong LinkedList, ngược lại nếu không tìm thấy trả về -1.

```java
package vn.viettuts.linkedlist;
 
import java.util.LinkedList;
 
public class TimKiemLinkedList2 {
    public static void main(String[] args) {
        // khai báo 1 LinkedList có tên là list
        // có kiểu là String
        LinkedList<String> list = new LinkedList<String>();
        // thêm các phần tử vào list
        list.add("Java");
        list.add("C++");
        list.add("PHP");
        list.add("Python");
         
        // kiểm tra xem Java có tồn tại trong list hay không?
        System.out.println(list.indexOf("Java"));
        // kiểm tra xem ANDROID có tồn tại trong list hay không?
        System.out.println(list.indexOf("ANDROID"));
    }
}
```
```java
0
-1
```

#### Tìm kiếm vị trí xuất hiện cuối cùng của 1 phần tử trong List.

Để tìm kiếm vị trí xuất hiện cuối cùng của 1 phần tử trong LinkedList, chúng ta sẽ sừ dụng phương thức lastIndexOf(). Kết quả của phương thức này sẽ trả về chỉ số xuất hiện cuối cùng của phần tử đó trong LinkedList, ngược lại nếu không tìm thấy trả về -1.

```java
package vn.viettuts.linkedlist;
 
import java.util.LinkedList;
 
public class TimKiemLinkedList3 {
    public static void main(String[] args) {
        // khai báo 1 LinkedList có tên là list
        // có kiểu là String
        LinkedList<String> list = new LinkedList<String>();
        // thêm các phần tử vào list
        list.add("Java");
        list.add("C++");
        list.add("PHP");
        list.add("Java");
         
        // kiểm tra xem Java có tồn tại trong list hay không?
        System.out.println(list.lastIndexOf("Java"));
        // kiểm tra xem ANDROID có tồn tại trong list hay không?
        System.out.println(list.lastIndexOf("ANDROID"));
    }
}
```
```
3
-1
```
### Chuyển LinkedList sang mảng (Array) trong Java

Phương thức toArray() trong Java được dùng để chuyển đổi một LinkedList sang mảng tương ứng. Sau đây là ví dụ minh họa phương thức này:

```java
package vn.viettuts.linkedlist;
 
import java.util.LinkedList;
 
public class ConvertToArray {
    public static void main(String[] args) {
        // khai báo 1 LinkedList có tên là list
        // có kiểu là String
        LinkedList<String> list = new LinkedList<String>();
        // thêm các phần tử vào list
        list.add("Java");
        list.add("C++");
        list.add("PHP");
        list.add("Java");
 
        // sử dụng phương thức toArray() chuyển list thành mảng
        // kết quả của phương thức này sẽ trả về mảng arr
        Object[] arr = list.toArray();
 
        // hiển thị các phần tử có trong mảng arr
        for (int i = 0; i < arr.length; i++) {
            System.out.println("Phần tử tại vị trí " + i + " "
                    + "trong arr là " + arr[i]);
        }
    }
}
```
```
Phần tử tại vị trí 0 trong arr là Java
Phần tử tại vị trí 1 trong arr là C++
Phần tử tại vị trí 2 trong arr là PHP
Phần tử tại vị trí 3 trong arr là Java
```
### Tạo LinkedList có kiểu generic là String
File: LinkedListExample1.java

```java
import java.util.LinkedList;
import java.util.Iterator;
 
public class LinkedListExample1 {
    public static void main(String args[]) {
        // Creating linkedlist
        LinkedList<String> list = new LinkedList<String>();
        // Add objects to linkedlist
        list.add("Java");
        list.add("C++");
        list.add("PHP");
        list.add("Java");
        // Show list through Iterator
        Iterator<String> itr = list.iterator();
        while (itr.hasNext()) {
            System.out.print(itr.next() + ", ");
        }
        // Show list through for-each
        System.out.println();
        for (String obj : list) {
            System.out.print(obj + ", ");
        }
        // Show list through index
        System.out.println();
        int size = list.size();
        for (int i = 0; i < size; i++) {
            System.out.print(list.get(i) + ", ");
        }
    }
}
```
### Tạo LinkedList có kiểu generic là đối tượng do người dùng định nghĩa

File: LinkedListExample2.java

```java
import java.util.LinkedList;
 
class Student {
    private String name;
    private int age;
    public Student(String name, int age) {
        super();
        this.name = name;
        this.age = age;
    }
    public String getName() {
        return name;
    }
    public void setName(String name) {
        this.name = name;
    }
    public int getAge() {
        return age;
    }
    public void setAge(int age) {
        this.age = age;
    }
    @Override
    public String toString() {
        return "Student@[name=" + name + ", age=" + age + "]";
    }
}
 
public class LinkedListExample2 {
    public static void main(String[] args) {
        // Create listStudent
        LinkedList<Student> listStudent = new LinkedList<Student>();
        // Create students
        Student student1 = new Student("Bac", 17);
        Student student2 = new Student("Nam", 20);
        Student student3 = new Student("Trung", 19);
        // Add objects to listStudent
        listStudent.add(student1);
        listStudent.add(student2);
        listStudent.add(student3);
        // Show listStudent
        for (Student student : listStudent) {
            System.out.println(student.toString());
        }
    }
}
```
```
Student@[name=Bac, age=17]
Student@[name=Nam, age=20]
Student@[name=Trung, age=19]
```

