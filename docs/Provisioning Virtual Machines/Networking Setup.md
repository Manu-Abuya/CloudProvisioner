## Networking Setup

1. Create a VPC (Virtual Private Cloud):

- In the AWS Management Console, navigate to the VPC service.
- Click on "Create VPC" and provide a name for your VPC.
- Specify the desired IPv4 CIDR block for your VPC (e.g., 10.0.0.0/16).
  
2. Configure subnets:

- In the VPC dashboard, select "Subnets" from the sidebar.
- Click on "Create subnet" and provide a name for your subnet.
- Choose the VPC you created in the previous step.
- Specify an IPv4 CIDR block for the subnet (e.g., 10.0.0.0/24).
- Repeat this step to create additional subnets as needed.

3. Set up an internet gateway:

- In the VPC dashboard, select "Internet Gateways" from the sidebar.
- Click on "Create internet gateway" and provide a name for the gateway.
- Select the newly created internet gateway and click on "Actions".
- Choose "Attach to VPC" and select the VPC you created earlier.

4. Configure route tables:

- In the VPC dashboard, select "Route Tables" from the sidebar.
- Click on "Create route table" and provide a name for the route table.
- Select the VPC you created earlier and click on "Create".
- Associate the route table with the desired subnets.
- Edit the route table's routes to ensure traffic is routed appropriately:
  - For public subnets, add a route with the destination 0.0.0.0/0 and the internet gateway as the target.
  - For private subnets, add routes based on your specific requirements (e.g., routes to other VPCs, VPN connections).

5. Set up public and private subnets:

- Assign the appropriate subnets as public or private based on their intended use:
  - Public subnets: These are associated with the route table that has a route to the internet gateway. Typically used for resources that require direct internet access.
  - Private subnets: These are associated with a route table that does not have a route to the internet gateway. Typically used for resources that should not be directly accessible from the internet.

6. Associate security groups with subnets:

- In the VPC dashboard, select "Security Groups" from the sidebar.
- Create or select an existing security group for your resources.
- Associate the security group with the desired subnets to control inbound and outbound traffic.
