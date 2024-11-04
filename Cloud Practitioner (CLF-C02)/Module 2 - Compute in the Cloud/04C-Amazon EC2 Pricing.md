# Amazon EC2 Pricing
- You only pay for what you use.
## On-Demand Instances
- You only pay for the duration that your instance runs for.
- Ideal for short-term, irregular workloads that cannot be interrupted. No upfront costs or minimum contracts apply. The instances run continuously until you stop them, and you pay for only the compute time you use.  
  - Sample use cases for On-Demand Instances include developing and testing applications and running applications that have unpredictable usage patterns. On-Demand Instances are not recommended for workloads that last a year or longer because these workloads can experience greater cost savings using Reserved Instances.

## Reserved Instances
- There are suited for steady-state workloads or ones with predictable usage.
- Billing discount applied to the use of On-Demand Instances in your account.
- Standard Reserved Instances: Is a good fit if you know the EC2 instance type and size you need for your steady-state applications and in which AWS Region you plan to run them. Require you to state the instance type and size, the platform description(OS) and Tenancy.
- Convertible Reserved Instances: If you need to run your EC2 instances in different [08B-Availability Zones](../Module%203%20-%20Infrastructure%20and%20Realiability/08B-Availability%20Zones.md) or different instance types, then Convertible Reserved Instances might be right for you.

## Instance Saving Plans
- Reduce your EC2 instance costs when you make an hourly spend commitment to an instance family and Region for a 1-year or 3-year term.
- The EC2 Instance Savings Plans are a good option if you need flexibility in your Amazon EC2 usage over the duration of the commitment term.

## Spot Instances
- Ideal for workloads with flexible start and end times, or that can withstand interruptions. Spot Instances use unused Amazon EC2 computing capacity and offer you cost savings at up to 90% off of On-Demand prices.
- After you have launched a Spot Instance, if capacity is no longer available or demand for Spot Instances increases, your instance may be interrupted.

## Dedicated Host
- Are physical hosts dedicated for your use for EC2. These are usually for meeting certain compliance requirements and nobody else will share tenancy of that host.
- Physical servers with Amazon EC2 instance capacity that is fully dedicated to your use. 
- You can use your existing per-socket, per-core, or per-VM software licenses to help maintain license compliance. You can purchase On-Demand Dedicated Hosts and Dedicated Hosts Reservations. Of all the Amazon EC2 options that were covered, Dedicated Hosts are the most expensive.