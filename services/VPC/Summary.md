### About NAT instances

* When creating NAT instance, disable source/destination check on the instance.
* NAT instances must be in a public subnet
* There must be a route out of the private subnet to NAT instance in order for this to work.
* The amount of traffic that NAT instances can support depends on the instance size. If you are bottlenecking, increase the instance size.
* You can create high availability using Autoscaling groups, multiple subnets in different AZs, and a script to automate failover.
* Always behind the security group.


### About NAT Gateways

* Preferred by enterprise
* Scale automatically up to 10GBps
* No need to patch
* Not associated with security groups
* Automatically assigned a public ip address
* Remember to update your route tables.
* No need to disable source/destination checks
* More secure than a NAT instance


### About Network ACLs

* Your VPC comes a default network ACL, and by default it allows all outbound and inbound traffic.
* You can create custom network ACLs. By default, each custom netork ACL denies all inbound and outbound traffic until you add rules.
* Each subnet in you VPC must be associated with a network ACL. If you don't explicitly associate a subnet with a network ACL, subnet is automatically associated with the default network ACL.
* You can associate a network ACL with multiple subnets, however, a subnet can be associated with only one network ACL at a time and previous is removed.
* Network ACLs contain a numbered list of rules that is evaluated in order, starting with the lowest numbered rule.
* ACLs have seperate inbound and outbound rules and each rule can either allow or deny traffic.
* ACLs are stateless.
* You can block IPs via ACLs.

### About Application Load Balancers (ALB)

* You will need at least 2 public subnets in order to deploy an application load balancer

### About VPC Flow Logs

* You cannot enable flow logs for VPCs that are peered with your VPC unless the peer VPC in your account
* You cannot tag a flow log
* After you've created a flow log, you cannot change its configuration, i.e. you can't associate a different IAM role with the flow log

* Not all IP traffic is monitored;
    * Traffic generated by instances when they contact the Amazon DNS server. If you use your own DNS server, then all traffic to that DNS is logged.
    * Traffic generated by a Windows instance for Amazon Windows licence activation
    * Traffic to and from 169.254.169.254 for instance metadata
    * DHCP traffic
    * Traffic to the reserved IP address for the default VPC router.