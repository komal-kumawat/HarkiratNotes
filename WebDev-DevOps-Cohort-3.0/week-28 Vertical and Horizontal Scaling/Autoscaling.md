#### slide
https://petal-estimate-4e9.notion.site/Autoscaling-groups-1a27dfd1073580adaaccc785189f156f

### Auto Scaling groups
# Context

As your app grows, you need to `autoscale` your app if traffic incrases/decreases. 

This would require

1. Increasing/Decreasing compute 
2. Putting your compute behind a load balancer


# ASGs in AWS

An **Auto Scaling Group** (ASG) in AWS (Amazon Web Services) is a service that automatically adjusts the number of EC2 (Elastic Compute Cloud) instances in a specified group to meet the demand for your application. It helps ensure that you have the right amount of compute capacity at any given time by automatically scaling up (adding more instances) or scaling down (removing instances) based on demand. This helps optimize costs and ensures that your application is always running efficiently.

### Features

1. **Automatic Scaling:**
    - Based on predefined metrics like CPU utilization, memory usage, or custom metrics, ASGs scale your EC2 instances up or down to maintain optimal performance and availability.
2. **Health Checks:**
    - ASGs perform regular health checks on the EC2 instances in the group. If an instance becomes unhealthy, it is automatically replaced with a new one.
3. **Scaling Policies:**
    - You can configure scaling policies to define how the scaling should happen. This could be based on a schedule, like increasing the number of instances during peak traffic hours, or dynamically adjusting based on real-time metrics.
4. **Launch Configurations/Launch Templates:**
    - These specify the configuration of instances launched within the group, such as the AMI (Amazon Machine Image), instance type, security group, key pair, and other parameters.
5. **Desired, Minimum, and Maximum Instance Counts:**
    - You define the minimum and maximum number of instances the group can scale between. The **desired capacity** is the target number of instances you want the ASG to maintain at any time.
6. **Elastic Load Balancer Integration:**
    - ASGs can be integrated with Elastic Load Balancing (ELB), so new instances launched by the Auto Scaling Group are automatically registered with the load balancer, ensuring traffic is distributed across healthy instances.

**Why use Auto Scaling Groups?**

- **Cost Efficiency:** ASGs help reduce costs by ensuring you're only running as many instances as needed to handle the load.
- **High Availability:** Automatically replacing unhealthy instances keeps your application running smoothly.
- **Flexibility:** ASGs support both manual and dynamic scaling policies to cater to a wide range of use cases.