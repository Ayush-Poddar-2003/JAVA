**What is a Servlet?**  
Programs that run on a web server (e.g., Tomcat).  
A Java class that handles HTTP requests and responses.  
Used to create dynamic web content.

![alt text](image.png)
![alt text](image-1.png)

---
### LIFECYCLE
Loading and Instantiation – Container loads the servlet class
![alt text](image-2.png)
1. Initialization (init()) – Called once when servlet is first loaded.
2. Request Handling (service()) – Called each time a request is made.
3. Destruction (destroy()) – Called once before servlet is removed.

![alt text](image-3.png)

---
### ARCHITECTURE
![alt text](image-4.png)