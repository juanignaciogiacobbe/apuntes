
> [!IMPORTANT] Directing Traffic with Elastic Load Balancing
> Automatically distributes incoming application traffic across multiple resources, such as [Amazon Elastic Compute Cloud(EC2)](AWS/Cloud%20Practitioner%20(CLF-C02)/02-Compute%20in%20the%20Cloud/04-Amazon%20Elastic%20Compute%20Cloud(EC2).md).
> - A load balancer acts as a single point of contact for all incoming web traffic to your Auto Scaling group.
> - As you add or remove Amazon EC2 instances in response to the amount of incoming traffic, these requests route to the load balancer first.


![elastic_load_balancing_example](../img/elastic_load_balancing_example.png)

- Suppose that a few customers have come to the coffee shop and are ready to place their orders. 
- If only a few registers are open, this matches the demand of customers who need service. The coffee shop is less likely to have open registers with no customers. In this example, you can think of the registers as Amazon EC2 instances.


![elb_example_two](../img/elb_example_two.png)

- Throughout the day, as the number of customers increases, the coffee shop opens more registers to accommodate them. 
- Additionally, a coffee shop employee directs customers to the most appropriate register so that the number of requests can evenly distribute across the open registers. You can think of this coffee shop employee as a load balancer.
