# Out-Of-Memory Investigation .py


The following python script can be used to calculate the estimated RSS (RAM) value of each service moments before the OOM incident. The system logs the RSS values of all processes at the time OOM is invoked, the file will calculate how much RAM your service was theorietically trying to use and how much it actualy has 


The script looks in /var/log/messages and takes the values recorded by the system just before the incident occurs. 






Current usage is as follows:

```
curl -s https://raw.githubusercontent.com/LukeShirnia/out-of-memory-investigation.py/master/oom.py | python
```

The script currently works on the following OS:

..* RedHat 5,6,7

..* CentOS 5,6,7

Testing for Debian and Ubuntu to commence shortly 



###Example Output

```
----------------------------------------

      _____ _____ _____
     |     |     |     |
     |  |  |  |  | | | |
     |_____|_____|_|_|_|

     Out Of Memory Analyser

----------------------------------------
**************************************************
         !!!!OOM ISSUE!!!!
This device HAS run out of memory recently
**************************************************


Sytem RAM: 987 MB

--------------------
Dates OOM occured:    Mar, 7, 15:13:50
Estimated RAM at OOM: 1783 MB
Services Killed:      mysqld
--------------------

--------------------
Dates OOM occured:    Mar, 8, 12:13:50
Estimated RAM at OOM: 1783 MB
Services Killed:      mysqld
--------------------
```
