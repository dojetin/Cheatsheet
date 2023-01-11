## Process Management

top - displays processor activity in real time.
htop / bashtop / ...
ps returns the snapshot of current processes.
ps -e returns every process running on the system
ps -u returns list of processes running on user account.
ps -u | grep - fetches all processes of "Application"
pstree display running processes as a tree
kill - kills the process having PID as that entered.
kill -9 - performs a violent kill
killall - kills all instances of processname


## Ports
ufw allow puerto          Abre puerto

## TRYHACKME
gobuster -u http://fakebank.com -w wordlist.txt dir       -- Find hidden website pages
