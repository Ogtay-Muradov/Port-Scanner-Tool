Port Scanner Tool
Overview
The Port Scanner Tool is a Python-based utility designed to scan network ports on a specified domain or IP address. It helps identify which ports are open and listening, providing valuable insights into network security and server configurations. The tool supports concurrent scanning using multiple threads, which allows for faster detection of open ports.

Key Features
Multi-threaded Scanning: The tool uses concurrent threads to scan multiple ports simultaneously, improving scanning efficiency and speed. Users can specify the number of threads based on their system's capacity.
Port Range Specification: Users can define a specific range of ports to scan, making it flexible for different needs, whether it's a few ports or a large range.
Error Handling and Logging: Detailed logging of the scanning process and errors encountered helps in troubleshooting and understanding scan results.
How It Works
User Input: The tool prompts the user to enter:

Target: The domain name or IP address of the server to scan.
Start Port Number: The beginning of the port range to scan.
End Port Number: The end of the port range to scan.
Number of Threads: Optional parameter to specify how many threads to use for scanning (default is 500).
Validation:

The input values are validated to ensure that port numbers are within the acceptable range (1 to 65535) and that the start port is less than or equal to the end port.
The number of threads is capped to prevent overloading the system (default max is 1000).
Scanning Process:

The tool initiates a scan using multiple threads (if specified). Each thread attempts to connect to a port and checks if it is open.
Results for each port are printed to the console, and open ports are logged for review.
Logging:

All activities, including port scanning results and any errors encountered, are recorded in a log file (port_scanner.log). This file helps track the scan's progress and diagnose issues.
Usage Example
python
Copy code
Enter the target (domain name or IP address): www.coursera.org
Enter the start port number: 1
Enter the end port number: 1000
Enter the number of threads (default 500): 450
Scanning Process: The tool will scan ports from 1 to 1000 on www.coursera.org using 450 threads.
Output: The tool will display open ports in the console and log the details in port_scanner.log.
Considerations
System Resources: High thread counts may affect system performance. It is essential to choose a number that matches your system’s capabilities.
Network Constraints: Be aware of network policies and firewalls that may restrict scanning activities or the number of simultaneous connections.
Ethical Use: Ensure that scanning is performed on systems you own or have permission to scan. Unauthorized scanning can be considered illegal and unethical.
Enhancements
The tool can be further enhanced with additional features such as:

Port Type Detection: Identifying the type of service running on open ports.
Custom Timeouts: Allowing adjustable timeouts for connections.
User Interface: Adding a graphical user interface (GUI) for easier use.
