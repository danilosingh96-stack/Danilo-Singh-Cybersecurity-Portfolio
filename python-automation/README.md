# **Project: Python Algorithm for File Updates**

### **Project Description**
In this project, I developed a Python algorithm to automate the management of an **"allow list"** containing IP addresses authorized to access restricted research data. The algorithm cross-references a main access file against a **"remove list"** of revoked IPs, ensuring the organization's security posture remains up-to-date without manual intervention.

---

### **Technical Execution**

#### **1. Opening and Reading the Access File**
To begin the update process, I utilized the `with` statement and `open()` function. This ensures that the system resources are managed efficiently and the file is closed automatically after reading.

* **Code Implementation**:
```python
import_file = "allow_list.txt"
with open(import_file, "r") as file:
    ip_addresses = file.read()
2. Converting Strings to Searchable Lists
Since the file is read as a single string, I used the .split() method to convert the data into a list format. This allows the algorithm to iterate through individual IP addresses for comparison.

Code Implementation:

Python
ip_addresses = ip_addresses.split()
3. Iterating and Removing Unauthorized IPs
I implemented a for loop to iterate through the remove_list. For every IP identified as no longer authorized, the algorithm checks if it exists in the ip_addresses list and utilizes the .remove() method to delete it.

Logic:

Python
for element in remove_list:
    if element in ip_addresses:
        ip_addresses.remove(element)
4. Finalizing and Writing to the File
To save the changes, I converted the list back into a newline-separated string using the .join() method. I then opened the file in write mode ("w") to overwrite the old data with the secured, updated list.

Code Implementation:

Python
ip_addresses = "\n".join(ip_addresses)
with open(import_file, "w") as file:
    file.write(ip_addresses)
Summary of Python Competencies
Beyond this algorithm, I have completed several automated security scripts covering:

Regular Expressions (Regex): Extracting device IDs and flagging suspicious IP patterns from log files.

Functional Programming: Defining reusable functions to calculate login ratios and automate alert triggers.

String Manipulation: Standardizing employee IDs and parsing URLs for malicious indicators.

Conditional Logic: Developing algorithms that verify both user approval and assigned device IDs.

Key Takeaways
Automation Efficiency: Reduced manual error by programmatically updating security records.

Resource Management: Used Python context managers (with) to handle file I/O operations safely.

Principle of Least Privilege: Used code to enforce access control by strictly maintaining allow lists.
