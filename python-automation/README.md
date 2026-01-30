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

#### **2. Converting Strings to Searchable Lists**
Since the file is initially read as a single string, it is difficult to isolate and remove individual IP addresses. To make the data searchable and easy to manipulate, I used the `.split()` method to convert the string into a list format. This allows the algorithm to iterate through each IP address as a separate element.

**Code Implementation:**
```python
# Use the .split() method to convert the string into a list
ip_addresses = ip_addresses.split()

#### **3. Iterating and Removing Unauthorized IPs**
To update the list, I implemented a `for` loop that iterates through the `remove_list`. For every IP address identified as no longer authorized, the algorithm performs a membership check to see if that IP exists within the `ip_addresses` list. If a match is found, the `.remove()` method is called to delete the unauthorized IP from the list.



**Code Implementation:**
```python
# Iterate through the IPs that should be removed
for element in remove_list:
    # Check if the IP is in the allow list
    if element in ip_addresses:
        # Remove the unauthorized IP
        ip_addresses.remove(element)

#### **4. Finalizing and Writing to the File**
In the final step of the algorithm, the updated list of IP addresses must be written back to the original file. Since the `.write()` function requires a string argument, I used the `.join()` method to convert the list back into a single string. To maintain the original file format, I used `"\n"` as a separator so that each IP address appears on a new line. I then opened the file in write mode (`"w"`) to overwrite the old contents with the corrected allow list.



**Code Implementation:**
```python
# Convert the list back into a string with newlines
ip_addresses = "\n".join(ip_addresses)

# Open the file in write mode and update its contents
with open(import_file, "w") as file:
    file.write(ip_addresses)

---

### **Summary of Python Competencies**
Beyond the file update algorithm, I have completed a series of automated scripts that apply Python to common security tasks. These activities demonstrate proficiency in the following areas:

#### **Regular Expressions (Regex)**
I utilized the `re` module to identify specific patterns within log files. This included developing expressions to extract device IDs and flag IP addresses that matched known malicious patterns.

#### **Functional Programming**
I developed reusable, user-defined functions to streamline security audits. One script involved creating a function that calculates the ratio of failed login attempts to successful ones, allowing for automated threshold alerts.

#### **String Manipulation**
I processed string-based security data by using indexing and slicing to standardize employee IDs. I also utilized string methods such as `.strip()` and `.lower()` to ensure data consistency when parsing URLs and system logs.

#### **Conditional Logic**
I implemented multi-layered algorithms using `if`, `elif`, and `else` statements. These scripts automate the verification process by checking multiple security criteria, such as confirming if a user is approved before validating their assigned device ID.

---

### **Key Takeaways**

#### **Reduced Manual Error**
By using Python to handle file updates and data parsing, the risk of human error associated with manual entry is minimized. The algorithm ensures that the allow list is modified precisely according to the removal criteria.

#### **Efficient Resource Management**
The use of the `with` statement for file operations ensures that system resources are handled correctly. This practice prevents files from remaining open unnecessarily, which is essential for maintaining system stability during automated tasks.

#### **Enforcement of Least Privilege**
These automation tools support the **Principle of Least Privilege** by providing a reliable method to revoke access. Automating the removal of unauthorized IP addresses ensures that access permissions remain accurate and current.
