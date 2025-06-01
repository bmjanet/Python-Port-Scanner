# Python-Port-Scanner

Welcome to the Python Port Scanner project! This repository contains a python program that the user can interact with via a GUI that scans the port(s) of the given IP address(es). This Python script is an asynchronous, multi-target port scanner with basic service detection. It scans one or more IP addresses or subnets for open ports using multithreading for speed. The scanner can identify common services by port number and banner, and supports custom port lists, ranges, and multiple hosts or subnets. Results can be exported to JSON or CSV for further analysis or use in a GUI. The script is designed for both command-line and GUI integration, making it suitable for quick scans or as a backend for graphical network tools.

While I don't believe this program can compete with tools such as nmap, it is great for learning how sockets interact with each other and how to use multi-threading to speed up multiple processes going on simultaneously!

### Features
* Can take in 1 or more IP address targets and/or subnets (xx.xx.xx.xx/XX)
* Can take on single, multiple, and ranges of ports, or a combination of all of these for scanning purposes!
* Prints all results onto a user-friendly GUI designed using tkinter.

### Usage
1. Clone the repository:
```
https://github.com/bmjanet/Python-Port-Scanner.git
```
2. Navigate to the project directory:
```
    cd Python-Port-Scanner
```
3. Download any necessary packages:
```
This project uses:
* tkinter
* socket
* threading
* ipaddress
* csv
* json
* argparse
* subprocess
```
> [!NOTE]
> These are usually very easy to install, or already come with your version of Python!

4. RUN THE PROGRAM‼️:
```
python port_scanner_gui.py
```

## Code Overview
The main components of this program are:
- port_scanner_gui, run_scan(): This function uses multithreaded processing in order for the backend of the program to run while still keeping the GUI responsive to the user.
- using ThreadPoolExecutor(): the program defaults to 200 threads as a default. However, this number can be changed in the program! I don't recommend going over 500 though... that might overload the target server, and sound alarms to what you are doing!!
- Scanning/Parsing ports/target IPs: The program parses through the given list of IP targets from the user, and the ports, and then scans each port given on each IP address in a nested for-loop. To counteract this O(n^2) run time, we use multi-threading to conduct multiple scans at once.

### How to run
1. Make sure you have Python installed. I used 3.11, but any version that supports the packages above should do!
2. Run the program using the command above, you mayyyyyy have to run it as python3.

### How to test
1. Open a terminal and identify your IP address using `ifconfig` (in Linux, at least). It should be something like 127.0.0.1
2. Next, use `python3 -m http.server <PORT#>` to open a port on your IP
3. Run the GUI and enter your IP and the port you specified as shown. You should have a successful scan with the port you opened‼️

   ![image](https://github.com/user-attachments/assets/52255f6e-6138-486f-94e0-812f4c35c4bd)


Thank you for reading!
