[Slide](https://petal-estimate-4e9.notion.site/VMs-and-Deploying-a-MERN-app-1867dfd10735809b8c3ad17e07e23ff2)
## Local Network , routing (mild hosting)

-> If you have multiple laptops on the sme wifi router , you an access one machine from another by using their private IP address . This is a mild version of deploying your app on your loal network (for whats called intranet)


### Port scanning:-
The process of checking which network ports on a computer/server are open and listening for connections.

### 🔎 Port Scanning — Simple Definition

**Port scanning** is:

> The process of checking which network ports on a computer/server are open and listening for connections.

---

### 🧠 First understand: What is a Port?

A **port** is like a door on a computer.

Each service uses a specific port:

* Web (HTTP) → **Port 80**
* Secure Web (HTTPS) → **Port 443**
* SSH → **Port 22**
* Database (MySQL) → **Port 3306**

If the port is **open**, that service is running.
If it's **closed**, nothing is listening there.

---

### 🔍 What Port Scanning Does

A port scanner sends small requests to many ports and checks:

* Is the port open?
* Is it closed?
* Is it filtered (blocked by firewall)?

---

### 🎯 Why Port Scanning is Used

#### ✅ Legitimate Uses (Security Testing)

* Cybersecurity audits
* Finding vulnerable services
* Checking exposed ports
* Network troubleshooting

#### ❌ Malicious Uses

* Hackers use it to find weak entry points
* Look for open services to attack

---

### 🛠️ Common Tool

One popular tool is:

* Nmap

Example command:

```
nmap 192.168.1.1
```

It scans the target machine’s ports.

---

### 📊 Types of Port Scans

* **TCP Connect Scan**
* **SYN Scan (Half-open scan)**
* **UDP Scan**
* **Stealth Scan**

---

### 🧠 In One Line (Interview Answer)

> Port scanning is the technique of identifying open ports and services running on a target system to assess security or detect vulnerabilities.

---






## Virtual machine(VM)
- VMs run on a physical server (called the host) but are abstracted through a layer of virtualization software called a Hypervisor(eg. VMware , KVM). This hypervisor divides the host machine's resources (CPU , memory , storage ) into separate virtual machines.

- Each VM acts like a completely independent machine, even though they share the underlying hardware. You can run different operating systems and applications in different VMs on the same physical server.

- VMs are highly flexible and easy to scale. You can quickly spin up, modify, or delete VMs, and you can consolidate multiple workloads on a single server.

- The virtualization layer introduces a slight overhead in terms of performance because the hypervisor needs to manage resources and ensure each VM operates independently. However, with modern hypervisors and powerful hardware, this overhead is minimal.



![Image](https://petal-estimate-4e9.notion.site/What-is-a-VM-1867dfd1073580d68977c35dc558b592)



# Bare metal servers

n a bare-metal setup, an operating system (OS) runs directly on the physical hardware without a hypervisor in between. There’s no virtualization layer.

 Since there's no hypervisor, bare-metal systems tend to offer better performance, as the OS can directly access all the server’s resources without sharing them with other instances. This is especially important for high-performance applications like large databases, gaming servers, or mining crypto

With bare-metal, you’re typically limited to the resources (CPU, memory, storage) of the actual physical server. You can't dynamically allocate resources like you can in a VM.


# SSH protocol, password based auth

The **SSH protocol** (Secure Shell) is a cryptographic network protocol that allows secure communication between two systems, typically for remote administration. It’s most commonly used to log into remote servers and execute commands, but it also facilitates secure file transfers and other operations.

### Key Features of SSH:

1. **Encryption**: SSH encrypts the data that’s sent between the client and the server, so even if someone intercepts the connection, they can’t read the data. This makes it much more secure than older protocols like Telnet or FTP, which transmit data in plaintext.
2. **Authentication**: SSH can use two methods of authentication:
    - **Password-based**: You enter a password to authenticate yourself to the remote system.
    - **Public Key-based**: A more secure method, where the client uses a private key to authenticate, and the server checks it against the corresponding public key. This eliminates the need for passwords and provides an extra layer of security.
3. **Integrity**: SSH ensures the integrity of data, meaning that data cannot be tampered with while it’s in transit. If someone tries to alter the data being sent, the connection will be immediately disrupted.

## Password based

While setting up a server, select password based authentication

**Example from `digitalocean`** 

![Screenshot 2025-01-25 at 7.12.34 PM.png](attachment:40f19f5b-2ebe-4646-b478-a78d6ff768cb:Screenshot_2025-01-25_at_7.12.34_PM.png)

![Screenshot 2025-01-25 at 7.12.55 PM.png](attachment:8197216a-0af1-4205-8392-cd3e42e7608b:Screenshot_2025-01-25_at_7.12.55_PM.png)

```solidity
ssh ubuntu@SERVER_IP
or
ssh root@SERVER_IP
```