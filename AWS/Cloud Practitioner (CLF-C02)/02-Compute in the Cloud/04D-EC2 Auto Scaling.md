# Scalability
- **Scalability** involves beginning with only the resources you need and designing your architecture to automatically respond to changing demand by scaling out or in. 
- You pay for only the resources you use. 
- You don’t have to worry about a lack of computing capacity to meet your customers’ needs.

## Amazon EC2 Auto Scaling
> Enables you to automatically add or remove Amazon EC2 instances in response to changing application demand.
> By automatically scaling your instances in and out as needed, you can maintain a greater sense of application availability.


![scaling_ec2](../img/scaling_ec2.png)

- Dynamic scaling responds to changing demand. 
- Predictive scaling automatically schedules the right number of Amazon EC2 instances based on predicted demand.
- To scale faster, you can use dynamic scaling and predictive scaling together.

## Amazon EC2 Auto Scaling Example

![auto_scaling_group](../img/auto_scaling_group.png)

- Because Amazon EC2 Auto Scaling uses Amazon EC2 instances, you pay for only the instances you use, when you use them. You now have a cost-effective architecture that provides the best customer experience while reducing expenses.