![slide](https://projects.100xdevs.com/tracks/hor-ver-scaling/Horizontal-and-vertical-scaling--Indexes-in-DBs-1)

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


