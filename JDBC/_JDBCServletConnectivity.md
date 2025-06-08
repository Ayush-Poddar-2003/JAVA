# JDBC

```JAVA
import java.io.*;
import javax.servlet.*;
import javax.servlet.http.*;
import java.sql.*;

public class RegisterServlet extends HttpServlet {
    protected void doPost(HttpServletRequest request, HttpServletResponse response)
            throws ServletException, IOException {

        response.setContentType("text/html");
        PrintWriter out = response.getWriter();

        String name = request.getParameter("name");
        String email = request.getParameter("email");

        try {
            Class.forName("com.mysql.cj.jdbc.Driver");

            Connection con = DriverManager.getConnection(
                "jdbc:mysql://localhost:3306/mydb", "root", "yourPassword"
            );

            PreparedStatement ps = con.prepareStatement(
                "INSERT INTO users(name, email) VALUES(?, ?)"
            );
            ps.setString(1, name);
            ps.setString(2, email);

            int status = ps.executeUpdate();

            if (status > 0) {
                out.println("<h3>Record saved successfully!</h3>");
            } else {
                out.println("<h3>Error saving record!</h3>");
            }

            con.close();
        } catch (Exception e) {
            e.printStackTrace();
            out.println("<h3>Database error: " + e.getMessage() + "</h3>");
        }
    }
}
```