# armtemplates
This ARM Template deploys the following architecture to Azure:

1) Creates a Virtual Network with 2 Subnets, one for the Web Server and the other for the database Server
2) For the Web Server
-	Creates multiple Ubuntu Virtual Machines for Web cum Application Server (it takes # of VMs, the VM Sizes, etc as user input parameters) with an OS Disk size of 512 GB
-	Adds the above Virtual Machines to an Availability Set (this is to ensure High availability in the Web Tier)
-	Adds a Load balancer to the above VMs and assigns a Public IP Address to the Load Balancer
-	Add Security Rules that ensures only port # 80 for HTTP and port 22 for SSH is opened, from the internet
-	Adds a custom script Virtual Machine Extension that downloads a bash script from a predefined location in Azure Blob Store, runs the script on each of the Virtual machines (e.g. install web server, deploy a web application)
-	Adds a Standard SSD Disk for the OS Disk of the VMS(you can change the code to use HDD instead, if required)
3) For the Database server
-	Creates a single Ubuntu VM that could be used as the db tier with an OS Disk of 1024 GB
-	Adds this VM to an Availability Set
-	Adds security rules to ensure only port 22 is open from the internet (this is just for demo. In production, you would not do it..)
-	Adds a Public IP Address for the VM (this is just for demo. In production, you will not add this for the database server) you can exclude this for Production
-	Adds a premium SSD Disk for the VM OS Disk

