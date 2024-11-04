# Directing Traffic with Elastic Load Balancing
> **Elastic Load Balancing** is the AWS service that automatically distributes incoming application traffic across multiple resources, such as [04A-Amazon Elastic Compute Cloud(EC2)](04A-Amazon%20Elastic%20Compute%20Cloud(EC2).md) instances.

- A load balancer acts as a single point of contact for all incoming web traffic to your Auto Scaling group.
- As you add or remove Amazon EC2 instances in response to the amount of incoming traffic, these requests route to the load balancer first.
- ELB and EC2 work together to help ensure that applications running in [04D-EC2 Auto Scaling](04D-EC2%20Auto%20Scaling.md) can provide high performance and availability.
- For example, if you have multiple Amazon EC2 instances, Elastic Load Balancing distributes the workload across the multiple instances so that no single instance has to carry the bulk of it.

	![elastic_load_balancing_example](../img/elastic_load_balancing_example.png)
	- Suppose that a few customers have come to the coffee shop and are ready to place their orders. 
	- If only a few registers are open, this matches the demand of customers who need service. The coffee shop is less likely to have open registers with no customers. In this example, you can think of the registers as Amazon EC2 instances.

	![elb_example_two](../img/elb_example_two.png)
	- Throughout the day, as the number of customers increases, the coffee shop opens more registers to accommodate them. 
	- Additionally, a coffee shop employee directs customers to the most appropriate register so that the number of requests can evenly distribute across the open registers. You can think of this coffee shop employee as a load balancer.
