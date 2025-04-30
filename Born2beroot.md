
Born to be root is a project of 42schools that aims to introduce how virtuali-
zation and server administration works. 

# Virtual machine creation

[https://aws.amazon.com/what-is/hypervisor/](link)
To set up a virtual machine the first tthing you need is a hypervisor. 
Hypervisor is a software that you can use to run multiple virtual machine .
Every virtual machine has its own operating system and applications. The role
of the hypervisor is to allocate the underlying physical computing resources
sush as cpu and memory to individual virtual machines as demanded.

The fundamentals of virtual machines and other virtualization technologies have 
enable cloud computing services as they allow you to scale the computer services
on limited hardware infrastructure.

The use of hypervisor offers some benefits:

- Hard independence
A hypervisor abstracts the host's hardware from the operating software 
environment. IT administrators can configure, deploy, and manage software 
applications without being constrained to a specific hardware setup. 
For example, you can run macOS on a virtual machine instead of iMac computers. 

- Efficiency
Hypervisors make setting up a server operating system more efficient. 
Manually installing the operating system and related software components is a 
time-consuming process. Instead, you can configure the hypervisor to 
immediately create your virtual environment.

- Scalability
Organizations use hypervisors to maximize resource usage on physical 
computers. Instead of using separate machines for different workloads, 
hypervisors create multiple virtual computers to run several workloads on a 
single machine. This translates to faster scalability and reduced hardware 
expenditure for organizations.

- Portability
IT teams can allocate memory, networking, processing, and storage resources 
across multiple servers as needed. They have the ability to shift workloads 
between machines or platforms easily. When an application requires more 
processing power, the hypervisor provides seamless access to additional physical
resources.

[https://42-cursus.gitbook.io/guide/1-rank-01/born2beroot](born2beroot-guide)
[https://github.com/chlimous/42-born2beroot_guide](Another-guide)

## Types of Hipervisors

- Type 1:
The type 1 hypervisor sits on top of the metal server and has direct access to 
the hardware resources. Because of this, the type 1 hypervisor is also known as
a bare-metal hypervisor. The host machine does not have an operating system 
installed in a bare-metal hypervisor setup. Instead, the hypervisor software 
acts as a lightweight operating system.

Pros and cons
Due to its architecture, the type 1 hypervisor is very efficient. It can 
directly manage and allocate resources for multiple virtual machines without 
going through the host operating system. These types of hypervisors are also 
more secure, as the absence of a host operating system reduces the risks of 
instability. 

- Type 2:
The type 2 hypervisor is a hypervisor program installed on a host operating 
system. It is also known as a hosted or embedded hypervisor. Like other 
software applications, hosted hypervisors do not have complete control of the 
computer resources. Instead, the system administrator allocates the resources 
for the hosted hypervisor, which it distributes to the virtual machines.

Pros and cons
The presence of the host operating system introduces latency to the virtualized
environment. When the virtual machine requests computing resources, the 
hypervisor cannot directly access the underlying hardware but relays the request
to the host operating system. Also, the hypervisor and its hosted virtual 
machines are dependent on the stability of the host operating system. 

comparison
Despite their differences, both types of hypervisors are helpful in different 
applications. For example, enterprise cloud data centers use type 1 or 
bare-metal hypervisors because of their efficiency, scalability, and 
flexibility when allocating resources to virtual machines. Also, a type 1 
hypervisor is generally more secure and stable because it does not run on top 
of another operating system. 

Conversely, administrators use type 2 hypervisors because they are more user-
friendly. Type 2 hypervisors are easier to install, configure, and use than 
bare-metal hypervisors. It is similar to installing and using other desktop 
applications.


pass = `This;shall;Pass42`
userpass = `The;secret;pass42`
encrypt pass= `It;is;a;Secret42`

- What is the difference between hypervisors and containers?
A container is a software package that stores all the necessary files and 
configurations to run an application on any operating system. Developers use 
containers to reduce software development complexities and improve efficiency 
when deploying the applications. A containerized application can run on a 
public, hybrid, or on-premises cloud with consistent performance because it is 
independent of the underlying operating system. 

Both hypervisors and containers provide virtualization but at a different 
software layer. A hypervisor abstracts the hardware from the software 
environment. In contrast, a container runs in an environment where a container 
engine abstracts the operating system.

- What are the security considerations for hypervisors?
Software programs on a virtual machine do not interfere with applications on 
other guest operating systems, which provides a degree of security. However, 
the virtualized environment relies on the hypervisor for a robust security 
posture. Any issues affecting the hypervisor will impact all virtual machines 
running on top of it. So, it’s essential to use a hypervisor with built-in 
safeguard measures to secure the workload’s integrity.

## Commands

- Creating user: `sudo adduser <login>`
- Creating group: `sudo addgroup <group_name>`
- Check the group: `getent group <group_name>`
- Add user to group: `sudo adduser <user> <group_name>`
- Check ssh status: `sudo service ssh status`
- Check ssh restart: `sudo service ssh restart`
- Connect via ssh: `<user>@localhost -p 4241`
- Enable ufw: `sudo ufw enable`
- Check ufw status: `sudo service ufw status`
- Allow ufw port: `sudo ufw allow 4242`
- Check ufw rules: `sudo ufw status`
- Configure crontab: `sudo crontab -u root -e`
- Sha signature: `shasum machinename.vdi`

## Address

- ssh: `nano /etc/ssh/ssh_config`
- ssh: `nano /etc/ssh/sshd_config`
- sudo: `touch /etc/sudoers.d/sudo_config`
- sudo: `nano /etc/sudoers.d/sudo_config`
- Editing password: `nano /etc/login.defs`
- Editing password: `nano /etc/pam.d/common-password`

## Sudo Rules:
- passwd_tries=3: 
Allows a total of 3 tries entering the sudo password.

- badpass_message="message":
Message shown when the password failed.

- logfile="/var/log/sudo/sudo_config:
The path where will the sudo logs will be stored.

- log_input, log_output:
What will be logged.

- iolog_dir="/var/log/sudo"
What will be logged.

- requiretty:
TTY (TeleTYpewriter) become required.
the command prints the name of the terminal connected to standar input.

- secure_path="/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/snap/bin"
These are the path that are excluded of sudo.

## Password policy

- Installing: `sudo apt install libpam-pwquality`
- minlen=10:
Minimum characters of the password.

- ucredit=-1:
The password must have at least 1 capital letter. The minus means it is the 
Minimum if it was + it means maximum of characters.

- dcredit=-1:
The passworld at least have to contain a digit.

- lcredit=-1:
The password at least have to contain a lowercase letter.

- maxrepeat=3:
The password can not have the same characters repited 3 continously times.

- reject_username:
The password can not contain the username inside itself.

- difok=7:
The password it have to contain at least seven different characters from the 
last password used.

- enforce_for_root:
This policy is implemented to the root user too.

## Script
### Architecture:

`uname -a`
Print the informaton of the architecture.

### Physical Cores (CPU):

`grep "physical id" /proc/cpuinfo | wc -l` 
The cpu info are shown in the file located in /proc/cpuinfo, like type, brand,
model, performance, etc

### Virtual Cores (vCPU):

`grep processor /proc/cpuinfo | wc -l`
A virtual core is a logical processor that is created through software 
virtualization. It emulates the behavior of a physical CPU core, allowing 
multiple operating systems or applications to run concurrently on a single 
physical machine. Virtual cores are often used to improve performance, resource
utilization, and flexibility. By dividing a physical CPU into multiple virtual 
cores, virtualization software can create the illusion of having multiple 
independent processors.

### Memory usage:

`free -m | grep Mem | awk '{printf("%s/%sMB (%.2f%%)", $3, $2, ($3/$2)*100)}'`
To check the memory usage of the machine.

### Disk Usage:

`df -h --total | grep total | awk '{printf("%.f/%.fGb (%s)", $3, $2, $5)}'`
`df` command is used to get a complete summary of the use of disk space.

### CPU load:

`top -bn1 | grep Cpu | awk '{printf("%.1f%%", $2 + $4)}'`

### Last boot:

`who -b | awk '$1 == "system" {print $3 " " $4}'`
The who command with `who -b` flag will display the time of the last system boot on 
the screen.

### LVM use:

`lsblk | grep lvm | wc -l | awk '{if ($1){printf("yes"); exit;} else print "no"}'`
The `lsblk` command will show the information about all the blocks of memory devices

### Connections TCP:

`ss -ta | grep ESTAB | wc -l`
The `ss` command is used now to intead of the obsolete netstat. It will show how 
many connections are shown.

### User log:

`users | wc -w`
The command users will show the names of the users and the `wc -w` will count 
words.

### Network:

`ip link | grep "link/ether" | awk '{print $2}'`
The `ip link` will show or modify the network interfaces
The `grep "link/ether"` will search line where the word appear.
the `awk '{print$2}'` is a scripting language used for manipulating data and 
generating reports.
Aho, Weinberg and Kernighan are the names of the developer.

### Sudo:

`journalctl _COMM=sudo | grep COMMAND | wc -l`
The command `journalctl` is a tool that is responsable to collect and manage the
system logs.
The `_COMM=sudo` is a filter applied to search for sudo only.
The `grep COMMAND` will search the line where the word command appear.
the command `wc -l` will count the words by line.

## Crontab
cron - daemon to execute scheduled commands (Vixie Cron)

## Signature

The code `shasum` will print the sha checksums
SHA-256 checksum is a sequence of numbers and letters that you can use to check
that your copy of a downloaded update file is identical to the original.
