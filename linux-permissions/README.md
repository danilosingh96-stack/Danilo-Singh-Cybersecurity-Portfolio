# Project: Linux File Permissions & Least Privilege 

## **Project Description**
[cite_start]In this project, I worked as a security analyst to examine and manage file permissions within a research team’s Linux environment[cite: 3]. [cite_start]I utilized Linux commands to identify incorrect authorizations and applied the **principle of least privilege** to secure files and directories[cite: 4]. [cite_start]This ensures that only appropriate users have access to sensitive data[cite: 5].

## **Technical Audit**
I began by auditing the directory details to identify security gaps:
* [cite_start]**Command**: `ls -la /home/researcher2/projects` [cite: 8]
* [cite_start]**Finding**: `project_k.txt` had permissions set to `-rw-rw-rw-`, meaning anyone could modify the file, violating security best practices[cite: 11, 23].

## **Remediation Steps**

### **1. Securing Publicly Writable Files**
* [cite_start]**Action**: Removed write permissions from "others" for `project_k.txt`[cite: 25, 27].
* [cite_start]**Command**: `chmod o-w project_k.txt` [cite: 27]
* [cite_start]**Result**: Permissions updated to `-rw-rw-r--`[cite: 30].

### **2. Hardening Hidden Archive Files**
* [cite_start]**Action**: Secured the hidden file `.project_x.txt` by making it read-only for both user and group[cite: 33, 36].
* [cite_start]**Command**: `chmod u-w,g-w .project_x.txt` [cite: 35]

### **3. Restricting Directory Access**
* [cite_start]**Action**: Restricted the `drafts` directory so only the owner (`researcher2`) can access it[cite: 41, 44].
* [cite_start]**Command**: `chmod g-x drafts` [cite: 43]
* [cite_start]**Result**: Permissions updated to `drwx------`[cite: 46].

## **Summary**
[cite_start]Through this project, I demonstrated the ability to manage Linux permissions effectively and enforce the **principle of least privilege** to protect sensitive organizational data[cite: 50].
