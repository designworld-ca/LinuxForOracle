* Shutdown or reboot System
shutdown ubuntu
or
poweroff debian
or
systemctl reboot -i

* Update packages

sudo apt-get update


* Set Oracle environment
. oraenv
<enter database instance name>

* List all running oracle instances
ps -ef | grep pmon 

* See all processes
ps -aux
or
top

* For a just started database to register with listener

ALTER SYSTEM REGISTER; 

* To edit files
nano
CTRL X to quit
or vim

* Typical path to executables
/u01/app/oracle/product/12.1.0.2/db_1/

* Show current file path

ECHO $PWD

* Go up the file tree
cd ..

*To see list of Oracle patches that have been applied :

$ORACLE_HOME/OPatch/opatch lsinventory

* Chmod to change file permissions
chmod -R ugo+rw /DATA/SHARE
-R – this modifies the permission of the parent folder and the child objects within

ugo+rw – this gives User, Group, and Other read and write access.
chmod -R ugo+rw /u02/app/oracle/diag/rdbms/xxxxx/xxxxx

* Check for updates on RHEL using Yum

rpm -qa --last kernel-uek

rpm -qa --last | grep "Wed 22 Aug 2018 09"

rpm -qa --last kernel-uek

rpm -qa --last | grep "Wed 22 Aug 2018 08"

* OS patching with yum
yum update

* Linux version 
cat /etc/*release

* Kernel version 
uname -r

