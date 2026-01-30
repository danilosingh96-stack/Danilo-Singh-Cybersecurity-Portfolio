# **Project: Python Algorithm for File Updates**

### **Project Description**
In this project, I developed a Python algorithm to automate the management of an "allow list" containing IP addresses authorized to access restricted research data. The algorithm cross-references a main access file against a "remove list" of revoked IPs, ensuring the organization's security posture remains up-to-date without manual intervention.

---

### **Technical Execution**

#### **1. Opening and Reading the Access File**
To begin the update process, I utilized the `with` statement and `open()` function. This ensures that the system resources are managed efficiently and the file is closed automatically after reading.

* **Code Implementation**:
```python
import_file = "allow_list.txt"
with open(import_file, "r") as file:
    ip_addresses = file.read()

