
Born to be root is a project of 42schools that aims to introduce how virtuali-
zation and server administration works. 

# Virtual machine creation

[Hypervisor](https://aws.amazon.com/what-is/hypervisor/)
To set up a virtual machine the first tthing you need is a hypervisor. 
Hypervisor is a software that you can use to run multiple virtual machine .
Every virtual machine has its own operating system and applications. The role
of the hypervisor is to allocate the underlying physical computing resources
sush as cpu and memory to individual virtual machines as demanded.

The fundamentals of virtual machines and other virtualization technologies have 
enable cloud computing services as they allow you to scale the computer services
on limited hardware infrastructure.

The use of hypervisor offers some benefits:

1. Hard independence
A hypervisor abstracts the host's hardware from the operating software 
environment. IT administrators can configure, deploy, and manage software 
applications without being constrained to a specific hardware setup. 
For example, you can run macOS on a virtual machine instead of iMac computers. 

2. Efficiency
Hypervisors make setting up a server operating system more efficient. 
Manually installing the operating system and related software components is a 
time-consuming process. Instead, you can configure the hypervisor to 
immediately create your virtual environment.

3. Scalability
Organizations use hypervisors to maximize resource usage on physical 
computers. Instead of using separate machines for different workloads, 
hypervisors create multiple virtual computers to run several workloads on a 
single machine. This translates to faster scalability and reduced hardware 
expenditure for organizations.

4. Portability
IT teams can allocate memory, networking, processing, and storage resources 
across multiple servers as needed. They have the ability to shift workloads 
between machines or platforms easily. When an application requires more 
processing power, the hypervisor provides seamless access to additional physical
resources.

[Guide](https://42-cursus.gitbook.io/guide/1-rank-01/born2beroot)
[Other guide](https://github.com/chlimous/42-born2beroot_guide)

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

## The benefits of virtual machines

- It allow to test operating systems and creating the environment to security tests.
- Vms simplifies data backup thanks to a snapshot of the vm and its data, which
allows to restore the vm to its previous state;
- Increases the security of data by partitioning them and isolating the services
on different servers (each VM is isolated from the others, including the host system),
limiting the risk of propagation in the case of malware intrusion.

## Difference between aptitude and apt

Aptitude is an enhanced version of apt.
APT is a lower-level package manager and aptitude is a high-level package manager.
`APTITUDE` offers better functionality compared to `apt`.
apt is command-line only and focuse on being simple and consistent interface.
Aptitude can be command-line or GUI, has more detailed package management options
and an interactive mode where you can browse available packages.

## What is APPArmor

It is a linux kernel security mode that allows the system to restrict program's
capabilities with per-program profiles. Theses profiles can allow capabilities 
like network access, raw socket access and permission to read, write, or execute
files on matching paths. The `APPArmor` supplement the traditional discretionary
access control (DAC) model by providing mandatory access control (MAC).

SElinux is considered difficult to administrator set up and maintain.

## What is a LVM?
It is a system for managing disk storage that provides a layer of abstraction
between physical storage devices and the file systems used by the operating system.
It can combine to physical storages to act as one.

The way of the abstraction the LVM does is:
- First it combines every physical storage into one big pool;
- This big pool is called logical volumes and will act like virtual partitions.
- This block devices are divided into smaller chunks called `extents(4MB)`.
- The LVM maps which physical extents belong to which logical volume
- All this mapping is invisible to the OS and its applications.

## Passwords
- rootpass = `This;shall;Pass42`
- userpass = `The;secret;Pass42`
- encrypt pass= `It;is;a;Secret42`

## Commands

### Check services

- Check if it is not GUI: `ls /usr/bin/*session`
- Check ssh status: `sudo service ssh status`
- Check ssh restart: `sudo service ssh restart`
- Connect via ssh: `<user>@localhost -p 4241`
- Check ufw status: `sudo service ufw status`
- Check APPArmor is active:  `sudo systemctl status apparmor`

### Creating and manage users/groups
- Creating user: `sudo adduser <username>`
- Delete user: `sudo userdel <username>`
- Delete user from groups: `sudo delgroup <username>`
- Creating group: `sudo addgroup <group_name>`
- Delete group: `sudo groupdel <group_name>`
- Check the group: `getent group <group_name>`
- Add user to group: `sudo adduser <user> <group_name>`
- Rules of user: `sudo chage -l <username>`

### Rules
- Enable ufw: `sudo ufw enable`
- Check ufw rules: `sudo ufw status numbered`
- Allow ufw rules port: `sudo ufw allow 4242`
- Delete ufw rules port: `sudo ufw delete <numbe>`

### Other stuffs
- Show partitions: `lsblk`
- Configure crontab: `sudo crontab -u root -e`
- Sha signature: `shasum machinename.vdi`
- Check packages in debian: `dpkg -s <name_package>`
- Check the encryption:  `sudo cryptsetup luksDump <sda_something>`

## Files paths

- ssh: `vim /etc/ssh/ssh_config`
- ssh: `vim /etc/ssh/sshd_config`
- sudo: `touch /etc/sudoers.d/sudo_config`
- sudo: `vim /etc/sudoers.d/sudo_config`
- Editing password: `vim /etc/login.defs`
- Editing password: `vim /etc/pam.d/common-password`
- Checking/changing hostname: `vim /etc/hostname`
- Checking/changing hostname: `vim /etc/hosts`

## ssh
The ssh stands for secure Shell and it is a protocol designed as a secure
alternative to operating network services. The services are based on client-server
architecture connecting the ssh-client with the ssh-server.
The `ssh` operates as a layered protocol comprising three componets: the
transport layer provides server authenticaton, confidentiality and integrity;
the user authentication protocol validates the user to the server; and the 
connection protocol multiplexes the encrypted tunnel into multiple logical 
communication channels.

## Sudo Rules:
- `passwd_tries=3`: 
Allows a total of 3 tries entering the sudo password.

- `badpass_message="message"`:
Message shown when the password failed.

- `logfile="/var/log/sudo/sudo_config`:
The path where will the sudo logs will be stored.

- `log_input, log_output`:
What will be logged.

- `iolog_dir="/var/log/sudo"`
What will be logged.

- `requiretty`:
TTY (TeleTYpewriter) become required.
the command prints the name of the terminal connected to standar input.

- `secure_path="/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/snap/bin"`:
These are the path that are excluded of sudo.

## Password policy

- Installing: `sudo apt install libpam-pwquality`
- `minlen=10`:
Minimum characters of the password.

- `ucredit=-1`:
The password must have at least 1 capital letter. The minus means it is the 
Minimum if it was + it means maximum of characters.

- `dcredit=-1`:
The passworld at least have to contain a digit.

- `lcredit=-1`:
The password at least have to contain a lowercase letter.

- `maxrepeat=3`:
The password can not have the same characters repited 3 continously times.

- `reject_username`:
The password can not contain the username inside itself.

- `difok=7`:
The password it have to contain at least seven different characters from the 
last password used.

- `enforce_for_root`:
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

### LVM(Logical Volume Manager) use:

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
it will search for crontab files and check if there is some command to be used.

## Signature

The code `shasum` will print the sha checksums
SHA-256 checksum is a sequence of numbers and letters that you can use to check
that your copy of a downloaded update file is identical to the original.
