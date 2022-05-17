# Java inner class - lớp lồng nhau trong java
## Định nghĩa và cú pháp

- Java inner class hoặc lớp lồng nhau trong java là một lớp được khai báo trong lớp hoặc interface khác.
- Chúng ta sử dụng inner class để nhóm các lớp và các interface một cách logic lại với nhau ở một nơi để giúp cho code dễ đọc và dẽ bảo trì hơn.
- Thêm vào đó, nó có thể truy cập tất cả các thành viên của lớp bên ngoài (outer class) bao gồm các thành viên dữ liệu private và phương thức.

- Cú pháp của inner class trong java
```java
class Java_Outer_class{  
    //code  
    class Java_Inner_class{  
        //code  
    }  
}
```

## Các ưu điểm của inner class trong java
- Inner class biển diễn cho một kiểu đặc biệt của mối quan hệ đó là **nó có thể truy cập tất cả các thành viên (các thành viên dữ liệu và các phương thức) của lớp ngoài** bao gồm cả private.
- Inner class được sử dụng để giúp code dễ đọc hơn và dễ bảo trì bởi vì nó nhóm các lớp và các interface một cách logic vào trong một nơi.
- Code được tối ưu hóa: tiết kiệm code hơn.

## Các kiểu của lớp lồng nhau trong java
Có hai kiểu của các lớp lồng nhau. Lớp lồng nhau non-static và lớp lồng nhau static. Lớp lồng nhau non-static còn được gọi là inner class.
- Lớp lồng nhau non-static (inner class)
    - Member inner class: Một lớp được tạo ra bên trong một lớp và bên ngoài phương thức.
    - Annomynous inner class: Một lớp được tạo ra để implements interface hoặc extends class. Tên của nó được quyết định bởi trình biên dịch java.
    - Local inner class: Một lớp được tạo ra bên trong một phương thức.
- Lớp lồng nhau Static: Một lớp static được tạo ra bên trong một lớp.