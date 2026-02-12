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




