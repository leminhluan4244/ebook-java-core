Một phương thức truyền thông tin phổ biến hơn, đáng tin cậy hơn là phương thức POST. Phương thức này gói thông tin theo cách chính xác giống như phương thức GET, nhưng thay vì gửi nó như một chuỗi văn bản sau một ? (dấu chấm hỏi) trong URL thì phương thức này gửi nó như một thông điệp riêng biệt. Thông báo này đi kèm với chương trình backend dưới dạng đầu vào tiêu chuẩn mà bạn có thể phân tích và sử dụng cho quá trình xử lý của bạn. Servlet xử lý kiểu yêu cầu này sử dụng phương thức doPost().

### Ví dụ phương thức POST sử dụng Form
Tạo servlet HelloForm để xử lý yêu cầu từ máy khách.
File: HelloForm.java trong package vn.viettuts

```java
package vn.viettuts;
 
import java.io.IOException;
import java.io.PrintWriter;
 
import javax.servlet.ServletException;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;
 
public class HelloForm extends HttpServlet {
     
    /**
     * Xử lý phương thức POST
     */
    public void doPost(HttpServletRequest request, HttpServletResponse response)
            throws ServletException, IOException {
             
        // Set response content type
        response.setContentType("text/html");
 
        PrintWriter out = response.getWriter();
        String title = "Vi du phuong thuc POST su dung Form";
        String docType =
           "<!doctype html public \"-//w3c//dtd html 4.0 " + 
           "transitional//en\">\n";
            
        out.println(docType +
           "<html>\n" +
              "<head><meta charset=\"UTF-8\">\n" +
              "<title>" + title + "</title></head>\n" +
              "<body bgcolor = \"#f0f0f0\">\n" +
                 "<h1 align = \"center\">" + title + "</h1>\n" +
                 "<ul>\n" +
                    "  <li><b>First Name</b>: "
                    + request.getParameter("first_name") + "\n" +
                    "  <li><b>Last Name</b>: "
                    + request.getParameter("last_name") + "\n" +
                 "</ul>\n" +
              "</body>" + 
           "</html>"
        );
     }
}
```


Cấu hình servlet trong file web.xml

```xml
<servlet>
  <servlet-name>HelloForm</servlet-name>
  <servlet-class>vn.viettuts.HelloForm</servlet-class>
</servlet>
 
<servlet-mapping>
  <servlet-name>HelloForm</servlet-name>
  <url-pattern>/HelloForm</url-pattern>
</servlet-mapping>
```

Tạo trang index.html

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
</head>
<body>
  <form action="HelloForm" method="POST">
    First Name: <input type="text" name="first_name"> <br />
    Last Name: <input type="text" name="last_name" /> 
    <input type="submit" value="Submit" />
  </form>
</body>
</html>
```

Demo

![image-1](./image/vi-du-phuong-thuc-post-su-dung-form-1.png)

Click Submit

![image-2](./image/vi-du-phuong-thuc-post-su-dung-form-2.png)

Như bạn thấy không giống như phương thức GET, phương thức POST không để lộ thông tin lên URL.