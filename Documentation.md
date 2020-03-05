Benchmarks:
===========
1. Network Latency (netperf)
2. Block I/O (fio)
3. Network Bandwidth (nuttcp)
4. Memory Bandwith (stream)

Automated Installation Process:
===============================
User will execute the master.sh script on a functioning Arch Linux distribution (running in CloudLab). The script will do the following:
1. Automate the installation of Docker and its dependencies onto the system (if neccesary)
2. Will install the netperf, fio, nuttcp, and stream programs along with their dependencies (if neccesary)
3. Execute the netperf, fio, nuttcp, and stream benchmark programs, displaying the data of each process to a file and the terminal
4. Repeat the process of executing, displaying, and writing the benchmark program twenty times for sufficient data gathering
