https://projects.100xdevs.com/tracks/hor-ver-scaling/Horizontal-and-vertical-scaling--Indexes-in-DBs-1

htop:- htop is a command-line utility used to monitor system resources and manage running processes in real time.(using it we can visualise which CPU core is doing which job)


- Javascript is a single threaded language 
- if a lot of processes are running then the cpu cores do context switching between processes

- a single nodejs process can capture or take 100% of 1 cpu 

- since js is a single threaded lang. i can run my code on one of my cores at a time  , cann't run (same code) on multiple cores .

- thread is something that runs on cpu cores.
##### Vertical Scaling:-  vertical scaling means increasing the size or capacity of the machine to support more loads.

- Vertical scaling is of no use for js projects as the nodejs project can run on a single core of the machine so there is no use of adding mre machines.

- Golang , python , java , rust are multithreaded languages .
 they can run on multiple cores.

- spawn :- spawn usually means creatin new process or thread


### Implementing vertical scaling in Node js project:
You can start multiple node projects then? If there are 8 cores, then just start 8 projects?
node index.js
node index.js
node index.js
node index.js
node index.js
node index.js
node index.js
node index.js

This, ofcourse has a lot of problems
Just ugly to do this, keep track of the processes that are up and down
Processes will have port conflicts, you’ll have to run each process on a saparate port


- cluster.isprimary = true only for parent node.
- cluster.isprimary tells ki this is my parent node .
- here we used os module just to know that how much cpu cores are present in my pc

This is where the cluster module comes into the picture
```
import express from "express";
import cluster from "cluster";
import os from "os";

const totalCPUs = os.cpus().length;

const port = 3000;

if (cluster.isPrimary) {
  console.log(`Number of CPUs is ${totalCPUs}`);
  console.log(`Primary ${process.pid} is running`);

  // Fork workers.
  for (let i = 0; i < totalCPUs; i++) {
    cluster.fork();
  }

  cluster.on("exit", (worker, code, signal) => {
    console.log(`worker ${worker.process.pid} died`);
    console.log("Let's fork another worker!");
    cluster.fork();
  });
} else {
  const app = express();
  console.log(`Worker ${process.pid} started`);

  app.get("/", (req, res) => {
    res.send("Hello World!");
  });

  app.get("/api/:n", function (req, res) {
    let n = parseInt(req.params.n);
    let count = 0;

    if (n > 5000000000) n = 5000000000;

    for (let i = 0; i <= n; i++) {
      count += i;
    }

    res.send(`Final count is ${count} ${process.pid}`);
  });

  app.listen(port, () => {
    console.log(`App listening on port ${port}`);
  });
}

```

Notice different pids in different devices


###### Horizontal scaling:-





# Capacity Estimation

Capacity estimation is a very common topic in **System Design Interviews**.

Interviewers may ask questions like:

* How would you scale your server?
* How do you handle traffic spikes?
* How can you support a certain SLA(service level agreement) under heavy load?
* How many servers are required for X million users?
* What happens during peak traffic?

---

## Why Capacity Estimation Matters

Capacity planning helps you:

* Prevent downtime
* Meet SLA (Service Level Agreement)
* Handle peak traffic smoothly
* Optimize infrastructure cost
* Avoid over-provisioning

---

## Step 1: Estimate Traffic

Start by estimating:

### 1. Number of Users

* Total registered users
* Daily active users (DAU)
* Peak concurrent users

### 2. Requests Per Second (RPS)

Example:

* 1 million daily active users
* Each user makes 20 requests/day

Total requests per day:

```
1,000,000 × 20 = 20,000,000 requests/day
```

Convert to requests per second:

```
20,000,000 / (24 × 60 × 60)
≈ 231 RPS
```

Now assume peak traffic is 5× average:

```
231 × 5 ≈ 1155 RPS
```

Design for **peak RPS**, not average.

---

## Step 2: Estimate Machine Capacity

Assume:

* One server handles 500 RPS safely.

If peak load = 1155 RPS

Servers needed:

```
1155 / 500 ≈ 3 servers
```

Add redundancy (e.g., 1 extra for safety):

```
Total = 4 servers
```

---

## Step 3: Handle Traffic Spikes

Strategies:

* Load Balancers
* Auto-scaling groups
* Queue-based buffering
* Rate limiting
* Caching (Redis, CDN)
* Horizontal scaling

---

## Step 4: Support SLA (Service Level Agreement)

Example SLA:

* 99.9% uptime
* Response time < 200 ms

To meet SLA:

* Use redundancy
* Multi-region deployment
* Health checks
* Monitoring + alerting
* Failover mechanisms

---

## Step 5: Storage & Bandwidth Estimation

### Storage

If:

* 1 user uploads 2 MB/day
* 1M users

```
2 MB × 1,000,000 = 2 TB/day
```

Plan:

* Daily growth
* Monthly growth
* 1-year growth

---

### Bandwidth

If average response = 100 KB
At 1000 RPS:

```
100 KB × 1000 = 100 MB/sec
```

Ensure:

* Network capacity
* CDN usage
* Compression

---

## Step 6: Monitoring & Scaling

Key metrics:

* CPU utilization
* Memory usage
* Disk I/O
* Network throughput
* RPS
* Error rate
* Latency (p95, p99)

Auto-scale when:

```
CPU > 70%
or
RPS > threshold
```

---

## General Interview Framework

When asked capacity questions:

1. Clarify assumptions
2. Estimate users
3. Estimate RPS
4. Calculate machine capacity
5. Add redundancy
6. Plan for spikes
7. Consider scaling strategy

---

## Important Concepts to Mention in Interviews

* Horizontal vs Vertical scaling
* Load balancing
* Auto-scaling
* Caching
* CDN
* Database sharding
* Replication
* Queue systems
* Circuit breakers
* Backpressure

---

## Final Thought

Capacity estimation is not about exact numbers.

It’s about:

* Structured thinking
* Reasonable assumptions
* Order-of-magnitude calculations
* Clear communication

---


- scale up:- if cpu utilization is above a certain threshold
- scale up:- if cpu utilization is below  a certain threshold