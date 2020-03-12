# OS queries
## show Linux version
cat /etc/*release
## Kernel version 
uname -r
# Oracle Instances
## List all running oracle instances (includes the call to grep)
ps -ef | grep pmon 
## List only Oracle processes
ps -ef | grep -i smon | grep -v grep
## List all system processes with ora_smon in the name  
## does not cover instances that are shut down  
ps -ef --sort=cmd | grep ora_smon
## Show the instance names
ps -ef | grep ora_smon | grep -v grep | sed 's/.*smon_//' | sort
## Show all instances that can be easily accessed
cat /etc/oratab
# Find 
## Alert log
find $ORACLE_BASE -type f -name alert_$ORACLE_SID.log
## Find all file types excluding a directory
find . -type f -name "*.sh" -not -path "./app/oracle/*"
## find all files in a folder with a specific date/time
find . -type f -ls |grep 'Jan 30 08:2'

## See all processes
ps -aux
## See all processes in real time
top



# Listing
ls -ltr 
## List last modified date and time
ls -ltr --full-time *.sh

## Show current file path
ECHO $PWD

# OS commands
## Shutdown or reboot System
### ubuntu
shutdown 
### debian
poweroff 

systemctl reboot -i

## Update OS packages

sudo apt-get update

## To edit files
nano
CTRL X to quit
or vim

## Go up the file tree
cd ..

# Chmod to change file permissions
chmod -R ugo+rw /DATA/SHARE
-R – this modifies the permission of the parent folder and the child objects within

ugo+rw – this gives User, Group, and Other read and write access.
chmod -R ugo+rw /u02/app/oracle/diag/rdbms/xxxxx/xxxxx

## Check for updates on RHEL using Yum

rpm -qa --last kernel-uek

rpm -qa --last | grep "Wed 22 Aug 2018 09"

rpm -qa --last kernel-uek

rpm -qa --last | grep "Wed 22 Aug 2018 08"

## OS patching with yum
yum update

# Oracle commands
## Set Oracle environment
. oraenv
<enter database instance name>

## Register a database with the listener

ALTER SYSTEM REGISTER; 

# Typical path to executables
/u01/app/oracle/product/12.1.0.2/db_1/

# To see list of Oracle patches that have been applied :

$ORACLE_HOME/OPatch/opatch lsinventory


## Syntax for a typical cronjob
### clean up file every Friday
### **************************************************************************
11 * * 5 /u01/FridayJob.sh > /u01/logs/FridayJobs.log 2>&1



