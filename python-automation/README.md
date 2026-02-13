Project: Python Algorithm for File Updates

Project Description
In this project, I developed a Python algorithm to automate the management of an "allow list" containing IP addresses authorized to access restricted research data. The algorithm cross-references a main access file against a "remove list" of revoked IPs, ensuring the organization's security posture remains up-to-date without manual intervention.

Technical Execution
<u>1. Opening and Reading the Access File</u>
To begin the update process, I first identified the file containing the authorized IP addresses. I utilized the with statement and the open() function to access the file. This approach is a security best practice because it uses a context manager, which ensures that the file is automatically closed after the code finishes executing, preventing potential memory leaks or file corruption. I opened the file in "r" (read) mode to extract the data into a string variable.

Code Implementation:

Python
 Assign the file name to a variable
import_file = "allow_list.txt"

 Use with + open() to open the file for reading
with open(import_file, "r") as file:
    # Use the .read() method to read the file into a string
    ip_addresses = file.read()
<u>2. Converting Strings to Searchable Lists</u>
Because the file is initially read as a single, continuous string, it is not possible to remove individual IP addresses directly. To make the data searchable and easy to manipulate, I utilized the .split() method. This function converts the string into a list format where each IP address becomes an individual element. This transformation is essential for the next stage of the algorithm, which requires iterating through the data.

Code Implementation:

Python
 Use the .split() method to convert the string into a list
ip_addresses = ip_addresses.split()
<u>3. Iterating and Removing Unauthorized IPs</u>
The core of the algorithm involves a for loop that iterates through a separate list called remove_list, which contains the IP addresses that should no longer have access. For every IP address in that list, the algorithm performs a membership check. If the revoked IP exists within the main ip_addresses list, the algorithm calls the .remove() method to delete it. This ensures that only authorized users remain on the allow list.

Code Implementation:

Python
 Iterate through the elements in the remove_list
for element in remove_list:
    # Check if the element is in the ip_addresses list
    if element in ip_addresses:
        # Remove the unauthorized IP from the list
        ip_addresses.remove(element)
<u>4. Finalizing and Writing to the File</u>
After the unauthorized addresses were removed, the list needed to be saved back to the original file. Since the .write() method requires a string, I used the .join() method to convert the list back into string format. I utilized "\n" as a separator to ensure each IP address appears on its own line, preserving the original file structure. Finally, I opened the file in write mode ("w") and saved the updated, secured list.

Code Implementation:

Python
 Convert the list back into a string with newlines
ip_addresses = "\n".join(ip_addresses)

 Open the file in write mode and update its contents
with open(import_file, "w") as file:
    file.write(ip_addresses)
Summary of Python Competencies
Beyond this algorithm, I have completed several automated scripts that demonstrate my proficiency in using Python for cybersecurity:

Regular Expressions (Regex): I have used the re module to extract specific patterns from log files, such as identifying device IDs with specific prefixes and flagging suspicious IP patterns.

Functional Programming: I define reusable functions to automate repetitive security tasks, such as creating a script that calculates failed login ratios to trigger alerts.

String Manipulation: I utilize indexing and slicing to standardize employee IDs and methods like .index() to parse URLs for malicious indicators.

Conditional Logic: I implement multi-layered algorithms using if, elif, and else statements to verify security credentials before granting access to resources.

Key Takeaways
Automation Efficiency: This algorithm reduces the administrative burden of manually updating security files, decreasing the likelihood of human error.

Resource Management: Utilizing the with statement ensures that file I/O operations are handled safely and system resources are protected.

Principle of Least Privilege: By automating the removal of revoked IP addresses, the system ensures that access is strictly limited to authorized users at all times.
