
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


pass = 'This;shall;Pass42'
userpass = 'The;secret;pass42'
encrypt pass= 'It;is;a;Secret42'

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
