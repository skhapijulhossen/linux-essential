# Craete Instace by Clincking on Launch Instance
- Instance ID
- i-03baf9d154dfb2a97 (aiattendanceserver)

-    Open an SSH client.

-    Locate your private key file. The key used to launch this instance is aiattendance.pem

-    Run this command, if necessary, to ensure your key is not publicly viewable.

- chmod 400 aiattendance.pem

- Connect to your instance using its Public DNS:

-     ec2-44-197-116-189.compute-1.amazonaws.com

- Example:
- ssh -i "aiattendance.pem" ubuntu@ec2-44-197-116-189.compute-1.amazonaws.com
