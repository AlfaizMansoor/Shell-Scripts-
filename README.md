# Shell-Scripts
This is a folder contains Shell Scripting folders/files of 90-DaysOfDevops.
Each folder contains shell scripts of intermediate to pro level, it also  contains cheatsheet and log_analyzer `.txt`, `.md` and as well as `.log` files.

We'll discuss each folder below what they stores.
There are total six folders -

1.  day-16
2.  day-17
3.  day-18
4.  day-19
5.  day-20
6.  day-21

## day-16 

learn the fundamentals every script needs.

-    Understand shebang (#!/bin/bash) and why it matters
-    Work with variables, echo, and read
-    Write basic if-else conditions

### day-16 folder includes some sub-files
- hello.sh
- variables.sh
- greet.sh
- check_number.sh
- file_check.sh
- server_check.sh
Including one `.md` file
- day-16-shell-scripting.md

### What i learned -
- Shebang: #!/bin/bash tells the system which interpreter to use
- Variables: NAME="Alfaiz" (no spaces around =)
- Read: read -p "Enter name: " NAME
- If syntax: if [ condition ]; then ... elif ... else ... fi
- File check: if [ -f filename ]; then

## day-17
Level up your scripting — use loops, handle arguments, and deal with errors.

-    Write for and while loops
-    Use command-line arguments ($1, $2, $#, $@)
-    Install packages via script
-    Add basic error handling

### day-17 folder includes some sub-files
- for_loop.sh
- count.sh
- countdown.sh
- greet.sh
- args_demo.sh
- install_packages.sh
- safe_script.sh
Including one `.md` file
- day-17-scripting.md

### What i learned -
- For loop: for item in list; do ... done
- While loop: while [ condition ]; do ... done
- Arguments: $1 first arg, $# count, $@ all args
- Check root: if [ "$EUID" -ne 0 ]; then echo "Run as root"; exit 1; fi
- Check package: dpkg -s <pkg> &> /dev/null && echo "installed"

## day-18
Write cleaner, reusable scripts — learn functions, strict mode, and real-world patterns.

-    Write and call functions
-    Use set -euo pipefail for safer scripts
-    Work with return values and local variables
-    Build an intermediate script

### day-18 folder includes some sub-files
- function.sh
- disk_check.sh
- strict_demo.sh
- local_demo.sh
- system_info.sh
Including one `.md` file
- day-18-scripting.md
  
### What i learned
- Function syntax: function_name() { ... }
- Local vars: local MY_VAR="value"
- Strict mode: set -euo pipefail as first line after shebang
- Pass args to functions: greet "Alfaiz" → access as $1 inside
- $? gives the exit code of last command

## day-19
Apply everything from Days 16–18 in real-world mini projects.

-    Write a log rotation script
-    Write a server backup script
-    Schedule them with crontab

### day-19 folder includes some sub-files
- log_rotate.sh
- backup.sh
- mainetnance.sh
- Logs all output to /var/log/maintenance.log with timestamps
Including one `.md` file
- day-19-project.md

### What i learned -

-    Compress old files: find /path -name "*.log" -mtime +7 -exec gzip {} \;
-    Timestamp: date +%Y-%m-%d
-    Tar: tar -czf backup.tar.gz /source/dir
-    Cron edit: crontab -e
-    Log with timestamp: echo "$(date): message" >> logfile

## day-20
You are a system administrator responsible for managing a network of servers. Every day, a log file is generated on each server containing important system events and error messages. Your job is to analyze these log files, identify specific events, and generate a summary report.

Write a Bash script (log_analyzer.sh) that automates the process of analyzing log files and generating a daily summary report.

-    A Bash script: log_analyzer.sh
-    A generated summary report: log_report_<date>.txt
-    A markdown file: day-20-solution.md documenting your approach

### day-20 folder includes some sub-files
- log_analyzer.sh
Including some `.txt` files
- log_report_<date>.txt

### What i learned -
- Count errors: grep -c "ERROR" logfile.log
- Print with line numbers: grep -n "CRITICAL" logfile.log
- Top occurrences: grep "ERROR" logfile.log | awk '{$1=$2=$3=""; print}' | sort | uniq -c | sort -rn | head -5
- Associative arrays: declare -A error_map
- Date for filename: date +%Y-%m-%d
- Move files: mv logfile.log archive/

  ## day-21
  I've spent the last several days learning Shell scripting — from basics to real-world projects. Now it's time to consolidate everything into a personal cheat sheet that you can use as a quick-reference guide for the rest of your DevOps journey.

The best way to revise is to teach it back. Writing a cheat sheet forces you to organize your understanding and identify gaps.
### Create <shell_scripting_cheatsheet.md> is to revise that what i learned in last six days, it stores all commands i used in last ssix days.
#### Example:
Topic         |           	Key Syntax 	     |         Example

Variable 	    |            VAR="value"       |   	NAME="DevOps"

Argument 	    |             $1, $2           |	./script.sh arg1

If            |        	if [ condition ]; then |	if [ -f file ]; then
