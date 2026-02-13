## 📜 What is Certificate Management?

### 📌 Definition

> **Certificate Management** is the process of creating, issuing, storing, renewing, and revoking digital certificates to secure communication between systems.

It is mainly used in **SSL/TLS security** (HTTPS websites).

---

# 🔐 First Understand: What is a Digital Certificate?

A **digital certificate** is like an **online ID card** for a website or server.

It contains:

* Public key
* Website/domain name
* Certificate Authority (CA) signature
* Expiry date

Example:
When you open:

```
https://google.com
```

The lock icon 🔒 appears because the website has a valid SSL certificate.

---

# 🌐 How It Works (Simple Flow)

![Image](https://cf-assets.www.cloudflare.com/slt3lc6tev37/5aYOr5erfyNBq20X5djTco/3c859532c91f25d961b2884bf521c1eb/tls-ssl-handshake.png)

![Image](https://www.researchgate.net/publication/298065605/figure/fig1/AS%3A357056767905792%401462140375566/TLS-handshake-protocol.png)

![Image](https://assets.bytebytego.com/diagrams/0220-how-does-https-work.png)

![Image](https://media2.dev.to/dynamic/image/width%3D800%2Cheight%3D%2Cfit%3Dscale-down%2Cgravity%3Dauto%2Cformat%3Dauto/https%3A%2F%2Fdev-to-uploads.s3.amazonaws.com%2Fuploads%2Farticles%2Fmcdespm57e62g90p9nlg.png)

Steps:

1️⃣ Browser requests website
2️⃣ Server sends SSL certificate
3️⃣ Browser verifies certificate
4️⃣ Secure encrypted connection starts

---

# 🛠️ What Does Certificate Management Include?

## 1️⃣ Certificate Issuance

Getting certificate from a CA like:

* **Let's Encrypt**
* **DigiCert**

---

## 2️⃣ Installation

Install certificate on:

* Web server (Nginx, Apache)
* Load balancer
* Cloud service

---

## 3️⃣ Renewal

Certificates expire (usually 90 days or 1 year).
Must renew before expiry.

---

## 4️⃣ Revocation

If certificate is compromised → revoke it.

---

## 5️⃣ Monitoring

Track expiry dates to avoid downtime.

---

# ☁️ In AWS

AWS provides certificate management through:

**AWS Certificate Manager**

It:

* Issues free SSL certificates
* Auto-renews them
* Works with Load Balancer & CloudFront

---

# 🚨 Why Certificate Management Is Important?

✔ Prevents website hacking
✔ Ensures encrypted communication
✔ Avoids “Not Secure” browser warning
✔ Required for production apps

---

# 🎯 Interview Definition

> Certificate management is the process of issuing, storing, renewing, and revoking digital SSL/TLS certificates to maintain secure encrypted communication.

---

