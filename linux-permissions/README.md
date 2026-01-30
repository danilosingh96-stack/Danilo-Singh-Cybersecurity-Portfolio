# **Project: Linux File Permissions & Least Privilege**

### **Project Description**
In this project, I performed the role of a **Security Analyst** to examine and manage file permissions within a research team’s Linux environment. I utilized Linux commands to identify incorrect authorizations and applied the **Principle of Least Privilege** to secure sensitive files and directories. This proactive approach ensured that only authorized users had access to critical information.

---

### **Technical Audit**
I initiated the process by auditing the directory details to identify existing security gaps:

* **Command Executed**: 
    `ls -la /home/researcher2/projects`
* **Audit Finding**: 
    The file `project_k.txt` was identified with permissions set to `-rw-rw-rw-`. This configuration allowed everyone on the system to modify the file, which directly violated security best practices and the principle of least privilege.

---

### **Remediation Steps**

#### **1. Securing Publicly Writable Files**
To mitigate the risk of unauthorized modifications to `project_k.txt`, I restricted access to only the necessary owners.
* **Action**: Removed write permissions from “others”.
* **Command**: 
    `chmod o-w project_k.txt`
* **Resulting Permissions**: 
    `-rw-rw-r--`

#### **2. Hardening Hidden Archive Files**
Hidden files often contain sensitive configuration data and must be protected accordingly.
* **Action**: Secured `.project_x.txt` by converting it to a read-only format for both the user and the group.
* **Command**: 
    `chmod u-w,g-w .project_x.txt`
* **Resulting Permissions**: 
    `-r--r-----`

#### **3. Restricting Directory Access**
Access to project directories should be limited to the specific owner to prevent lateral movement or unauthorized viewing of drafts.
* **Action**: Restricted the `drafts` directory so that only the owner (`researcher2`) has access.
* **Command**: 
    `chmod g-x drafts`
* **Resulting Permissions**: 
    `drwx------`

---

### **Summary**
Through the execution of this project, I demonstrated a high level of proficiency in managing
