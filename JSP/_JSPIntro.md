### What is JSP?

* JSP is a **server-side technology** used to create dynamic, platform-independent web content.
* It allows you to embed **Java code in HTML pages**.

###  JSP Life Cycle
1. Translation (.jsp → .java)
2. Compilation
3. Initialization (jspInit())
4. Request Handling (_jspService())
5. Destruction (jspDestroy())

---

## 📑 Anatomy of a JSP Page

A basic JSP page includes:

```jsp
<%@ page language="java" contentType="text/html" %>
<html>
<head><title>Hello JSP</title></head>
<body>
<%
    String name = "Ayush";
%>
<h2>Hello <%= name %></h2>
</body>
</html>
```

### ✅ Key Parts:

| Element              | Description                                     |
| -------------------- | ----------------------------------------------- |
| `<%@ page %>`        | Page directive – defines settings like language |
| `<% code %>`         | Scriptlet – raw Java code                       |
| `<%= expression %>`  | Outputs a value directly to the page            |
| `<%! declaration %>` | Declares methods or variables globally          |

---

## 📐 JSP Application Design with MVC (Model-View-Controller)

### ✅ MVC in JSP:

| Component      | Role                                 | Technology Used        |
| -------------- | ------------------------------------ | ---------------------- |
| **Model**      | Business logic, database operations  | JavaBeans, POJOs, JDBC |
| **View**       | Presentation layer (UI)              | JSP                    |
| **Controller** | Handles requests, updates model/view | Servlet                |

### ✅ Example Flow:

1. User submits form to a **Servlet** (Controller)
2. Servlet processes input, interacts with **JavaBean** (Model)
3. Servlet forwards to a **JSP** (View) to display result

---

## ⚙️ JSP Application Development

### ✅ Generating Dynamic Content

* JSP generates HTML pages dynamically based on user input or server-side logic.

Example:

```jsp
<%
    String user = request.getParameter("username");
%>
<h3>Welcome <%= user %>!</h3>
```

---

## ✍️ Using JSP Scripting Elements

### ✅ Types of Scripting Elements:

| Element     | Syntax               | Use                               |
| ----------- | -------------------- | --------------------------------- |
| Scriptlet   | `<% code %>`         | Java logic like loops, conditions |
| Expression  | `<%= expression %>`  | Outputs result directly           |
| Declaration | `<%! declaration %>` | Declares methods or fields        |

---

## 📦 Implicit JSP Objects

JSP provides **9 built-in objects**:

| Object        | Type                  | Description                          |
| ------------- | --------------------- | ------------------------------------ |
| `request`     | `HttpServletRequest`  | Client request data                  |
| `response`    | `HttpServletResponse` | Sends response to client             |
| `session`     | `HttpSession`         | Stores user session data             |
| `application` | `ServletContext`      | Shared data for all users            |
| `out`         | `JspWriter`           | Writes output to response            |
| `config`      | `ServletConfig`       | Servlet configuration info           |
| `pageContext` | `PageContext`         | Access all other objects             |
| `page`        | `Object`              | Current JSP page                     |
| `exception`   | `Throwable`           | Error handling (only in error pages) |

---

## 🔄 Conditional Processing in JSP

### ✅ Using If/Else:

```jsp
<%
    int marks = 75;
    if (marks >= 50) {
%>
    <p>Passed</p>
<%
    } else {
%>
    <p>Failed</p>
<%
    }
%>
```

---

## 🔗 Sharing Session Data

### ✅ Use `session` object to share data between pages:

```jsp
<%
    session.setAttribute("username", "Ayush");
%>
```

### ✅ Retrieve in another page:

```jsp
<%
    String name = (String)session.getAttribute("username");
%>
<p>Welcome <%= name %></p>
```

---

## 📝 Summary

| Topic              | Summary                                           |
| ------------------ | ------------------------------------------------- |
| JSP Basics         | Java code in HTML to build dynamic web pages      |
| JSP Anatomy        | Includes directives, scriptlets, expressions      |
| MVC with JSP       | JSP (View) + Servlet (Controller) + Beans (Model) |
| Scripting Elements | Scriptlet, Declaration, Expression                |
| Implicit Objects   | request, response, session, application, etc.     |
| Conditional Logic  | Use `<% if %>` blocks for flow control            |
| Session Management | Use `session.setAttribute()` and `getAttribute()` |

---

Would you like this in **markdown**, with **examples**, or a **project structure** showing Servlet + JSP + JDBC?
