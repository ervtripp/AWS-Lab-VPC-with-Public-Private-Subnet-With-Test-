<h1>AWS Lab: VPC With Public and Private Subnets</h1>


<h2>Description</h2>
In this lab, I'll design a segmented AWS network using resources such as VPC's, EC2, IGW and subnets to create a segmented network. One private, and one public. This could simulate a company with an application facing public internet, with backend processes that are private. These two segments are still able to communicate to one another.
<br />


<h2>Utilities Used</h2>

- <b>AWS Console</b> 



<h2>Environments Used </h2>

- <b>Windows 11</b>

<h2>Lab walk-through:</h2>

<p align="center">
Connected PCs to the switch and the switch to the router using copper straight-through cables. Establish physical network connectivity and simulate a real-world LAN deployment : <br/>
<img src="https://res.cloudinary.com/dsz8pn2ym/image/upload/v1771182342/Screenshot_2026-02-14_092441_ateiiz.png"/>
<br />
<br />
Assigned IP addresses and subnet masks to both PCs and configure the router interface as the default gateway :  <br/>
<img src="https://res.cloudinary.com/dsz8pn2ym/image/upload/v1771182339/Screenshot_2026-02-14_110935_exty1v.png"/>
<img src="https://res.cloudinary.com/dsz8pn2ym/image/upload/v1771182340/Screenshot_2026-02-14_093338_ublajj.png"/>  
<br />
<br />
Configure the router interface with IP address, subnet mask and no shutdown. The purpose is enable Layer 3 routing functionality and acitvate the interface as well as verify connectivity: <br/>
<img src="https://res.cloudinary.com/dsz8pn2ym/image/upload/v1771182339/Screenshot_2026-02-14_104957_mvsjz1.png"/>
<br />
<br />

<br />
<br />

</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
