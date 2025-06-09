

```java
import java.io.*;
import javax.servlet.*;
import javax.servlet.http.*;

public class HelloServlet extends HttpServlet 
{
    private string message;

    public void init() throws ServletException{
        message = "Hello World";
    }

    public void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException 
    {

        // Set response content type
        response.setContentType("text/html");

        // Get writer to send response
        PrintWriter out = response.getWriter();

        // Send HTML content
        out.println("<html><body>");
        out.println("<h2>Hello from doGet() Servlet!</h2>");
        out.println("</body></html>");
    }

    public void destroy(){};
}


```