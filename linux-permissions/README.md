Project: Linux File Permissions & Least Privilege
Project Description
In this project, I worked as a security analyst to examine and manage file permissions within a research team’s Linux environment. I utilized Linux commands to identify incorrect authorizations and applied the principle of least privilege to secure files and directories. This ensures that only appropriate users have access to sensitive data.

Technical Audit
I began by auditing the directory details to identify security gaps:

Command: ls -la /home/researcher2/projects

Finding: project_k.txt had permissions set to -rw-rw-rw-, meaning anyone could modify the file, violating security best practices.

Remediation Steps
1. Securing Publicly Writable Files
Action: Removed write permissions from "others" for project_k.txt.

Command: chmod o-w project_k.txt

Result: Permissions updated to -rw-rw-r--.

2. Hardening Hidden Archive Files
Action: Secured the hidden file .project_x.txt by making it read-only for both user and group.

Command: chmod u-w,g-w .project_x.txt

Result: Permissions updated to -r--r-----.

3. Restricting Directory Access
Action: Restricted the drafts directory so only the owner (researcher2) can access it.

Command: chmod g-x drafts

Result: Permissions updated to drwx------.

Summary
Through this project, I demonstrated the ability to manage Linux permissions effectively and enforce the principle of least privilege to protect sensitive organizational data.
