![Slide](https://projects.100xdevs.com/tracks/g0AcDSPl74nk45ZZjRdU/aws-1)

# AWS (Amazon Web Services)(provides pay as you go model)
AWS is Amazon’s cloud service.
(we call it cloud because we dont own the machine someone else does )
It let’s you 
- Rent servers
- Manage domains
- Upload objects (mp4 files, jpgs, mp3s …)
- Autoscale servers
- Create k8s clusters
…
 
The offering we will be focussing on today is Renting servers


# EC2(Elastic compute cloud)
**Amazon EC2 (Elastic Compute Cloud)** is a cloud service by AWS that provides **virtual servers (instances)** to run applications on the internet.

👉 Simple definition:
**EC2 = Rent a computer (server) in the cloud.**

---

### Why is it called EC2?

* **E** → Elastic (you can scale up/down anytime)
* **C2** → Compute Cloud

### Why “Elastic”?

“Elastic” means you can:

- Increase CPU/RAM anytime

- Add more servers during high traffic

- Remove servers when traffic decreases

So you only pay for what you use 💰

It’s called **Elastic Compute Cloud** because it provides **scalable computing power in the cloud**.


### Steps for creating a ec server
- give name of VM
- Select OS
- select the OS version
- Select the Instance type
- Create a new Keypair , set it
- Add a new sec group
- Add storage
- launch instance


#### Ports
Port 22 → SSH (remote server login)

Port 80 → HTTP (non-secure web)

Port 443 → HTTPS (secure web) 

MySQL → 3306

PostgreSQL → 5432



# REVERSE PROXY

## 🔁 What is a Reverse Proxy?

A **reverse proxy** is a server that sits **in front of backend servers** and handles client requests on their behalf.

👉 Client → Reverse Proxy → Backend Server
👉 Client never talks directly to backend.

---

## 📦 Simple Definition

> A reverse proxy receives requests from users and forwards them to the appropriate backend server, then sends the response back to the user.

---

## 🧠 Why Use Reverse Proxy?

### 1️⃣ Security

Hides internal servers from the internet.

### 2️⃣ Load Balancing

Distributes traffic across multiple servers.

### 3️⃣ SSL Termination

Handles HTTPS encryption centrally.

### 4️⃣ Caching

Stores responses to improve speed.

---

## 🔄 How It Works

![Image](https://cf-assets.www.cloudflare.com/slt3lc6tev37/3msJRtqxDysQslvrKvEf8x/f7f54c9a2cad3e4586f58e8e0e305389/reverse_proxy_flow.png)

![Image](https://www.digitalocean.com/api/static-content/v1/images?src=https%3A%2F%2Fjournaldev.nyc3.cdn.digitaloceanspaces.com%2F2019%2F03%2Fnginx-reverse-proxy.png\&width=1920)

![Image](https://miro.medium.com/0%2AkDWOAKI2SxARjmQ-.png)

![Image](https://cdn.prod.website-files.com/5efc3ccdb72aaa7480ec8179/673c413af7c9e8a1b4d94706_61ee500a7545cc25448246d8_Proxy%2520Servers%2520vs.%2520VPNs%25202.png)

Flow:

1. User sends request
2. Reverse proxy receives it
3. Forwards to backend
4. Backend sends response
5. Reverse proxy returns it to user

---

## 🔥 Real Example

Popular reverse proxy tools:

* **Nginx**
* **Apache HTTP Server**
* **AWS Application Load Balancer**

Example:
When you deploy a MERN app:

* Nginx acts as reverse proxy
* Node.js runs on port 3000
* Nginx listens on port 80/443
* Nginx forwards traffic to Node

---

## 🎯 Interview One-Line Answer

> A reverse proxy is a server that sits in front of backend servers, forwards client requests to them, and returns the response while improving security, scalability, and performance.

---


# NGINX
NGINX is a opem source software for web serving , reverse proxying , caching , load balancing , media streaming , and mor . It started out as a web server designed for max. performance and stability . In addition to its HTTP server  capabilities , NGINX can also function as a proxy server for email(IMAP , POP#  and SMTP) and a reverse proxy and load balancer for HTTP , TCP  and UDP servers.



### Assignments
- get a gcp acc and do this there
- Replace nginx with traffic/ HAproxy/ Apache
- Try deploying a react app
- Get a domain (namecheap)
- Try ASGs
- Try to do cert management yourself
- Create a CI/CD pipeline to auto deploy to your server from GH
- forever on pm2 (process management)