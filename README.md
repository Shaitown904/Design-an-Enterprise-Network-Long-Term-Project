# Design-an-Enterprise-Network-Long-Term-Project
Introduction

In this document, I will be discussing the approach I will take to build the Across the states Corporate Network. My goal for this approach is to Provide Across the States bank with a secure, stable, and reliable network infrastructure. To achieve this, I will also discuss the best practices for designing the network when it comes to Route and Switch and their configurations, security, fault tolerance, IPv4 and IPv6 configurations, and WAN. Additionally, I will also go over the cost of the Network Appliances and Labor used for building this network using my approach. 
 
![Untitled](https://github.com/user-attachments/assets/77bba614-378f-49ff-ae60-f6afc97f500a)


# Recommendations  


# Route and Switch
When Selecting Routers and Switches for the Across the States Corporate office and branch location, I had to do research and find the best enterprise level appliances but at an affordable cost. The two routing devices I picked for Across the states corporate office are, a cisco Firepower 2130 for the networks firewall, and a Cisco Catalyst 3900 for the layer 3 switch. 

The manufacturer and model number of the firewall are manufacturer: Cisco Systems and model: FPR2130-NGFW-K9. Hardware specs include, dimensions: 1.73 x 16.90 x 19.76 in. (4.4 x 42.9 x 50.2 cm), rack units: 1RU, I/O slots: 1 NM slot, Integrated I/O: 12 x 10M/100M/1GBASE-T Ethernet interfaces (RJ-45), 4 x 1 Gigabit (SFP) Ethernet interfaces, Network Modules: (FPR-NM-8X10G) 8 x 10 Gigabit Ethernet Enhanced Small Form-Factor Pluggable (SFP+) network module, Max Interfaces: Up to 24, Serial port: 1 x RJ-45 console, USB: 1 x USB 2.0 Type-A (500mA), Storage: 1x 200 GB 1x spare slot, and Power supply: AC input voltage- 100 to 240V AC. The sellers are router-switch.com, according to them the MSRP of the firewall is $39,176.


For the L3 switch, the model number and manufacturer are, model: C9300-24T-A and the manufacturer is Cisco Systems. Hardware specs include Dimensions: 1.73 x 17.5 x 17.5 Inches, Weight: 16.33 Pounds, Total 10/100/1000 or Multigigabit copper ports: 24, Default AC power supply: 350W AC, Switching capacity: 208 Gbps on 24-port Gigabit Ethernet model, MAC Address total: 32,000, IPv4 route total: 32,000 (24,000 direct routes and 8000 indirect routes), IPv4 routing entries: 32,000, IPv6 routing entries: 16,000, VLAN IDs: 4000, and Flash: 16GB.   MSRP for the Cisco Switch Catalyst 9300 is $5,449.00. 

For the switching devices, I used switches from the Cisco Catalyst 2960-L. This series has both 24 port L2 switches and 48 port L2 switches. The Model I selected for the 48-port switch was, Catalyst 2960L 48 GigE with POE, model number WS-C2960L-48PS-LL.  The Manufacturer is Cisco Systems, and the list price for the switch is $6,243. Hardware Specs include Dimensions: 1.73 x 11.5 x 17.5 in. (4.4 x 29.2 x 44.5 cm), Net Weight (10.25 lb (4.65 kg), IOS: LAN Lite, Forwarding Bandwidth: 52 Gbps, Switching bandwidth: 104 Gbps, 10/100/1000 Ethernet Ports: 48 PoE+ Ports, and Available PoE Power: 370W

The model for the 24-port switch is Catalyst 2960L 24 port, model number WS-C2960L-24PQ-LL. The manufacture is the same as the 48-port one, and the list price of the Switch is $4,700. Hardware specs include, Dimensions: 1.73 x 10.45 x 17.5 in. (4.4 x 26.5 x 44.5 cm), Net Weight: 7.39 lb (3.35 kg), IOS: LAN Lite, Forwarding bandwidth: 64 Gbps, Switching bandwidth: 128 Gbps, 10/100/1000 Ethernet Ports: 24 PoE+ Ports, and Available PoE Power: 195W.


# WAN
When Choosing which WAN Connections to use for the Across the state’s corporate office, I had to choose between two Internet service providers. Those being Cox and Century link, I ended up using both. The reason why I chose to use both is to have one ISP provide fiber connections to the corporate office and the second one provides broadband connections. This is to ensure the best practices when picking a WAN for the corporate office. 

Due to the size of the Network, it is best that we use two different ISPs in case one goes down the other one will still be able to provide internet. With that being said, I decided to use Cox for fiber Connections due to Cox having better speeds. I chose CenturyLink for the Broadband Connections this will be the secondary ISP for the Corporate office. For the Branch location using one ISP is enough for the size of the network. For the Branch location I decided to use Cox fiber. 

Across the States bank should also use Virtual Private Networks (VPN). This will allow employees that work outside the corporate office to still send data to the corporate office through an encrypted tunnel. The VPN I recommend is Cisco AnyConnect. Cisco AnyConnect is a cloud-based VPN that works with SSL and IKEv2 encryption protocols. Some of these features include Unified Endpoint Compliance, Highly Secure Network Access, Web security, and Mobile Device Support. With these features in mind, the company could benefit from these features because it gives our IT admins the proper tools to implement a secure VPN while giving our other employees a secure way to remotely connect to our company’s network. 



# IPv4

When adding IP addresses, subnets, and vlans to the across the states network, I had to ensure that I am using the best practices when assigning Ipv4 addresses for the network. To achieve this, it is best to categorize the devices into departments and separate them to their own vlan. I separated each device based on the networks needs such as data, Management, VoIP/Video, DMZ, Guest wireless. There’s also a similar setup for data and Guest Wireless for the branch location.   


The IP address Class I decided to use for Across the states bank were Class A IP Addresses. The reason why I chose Class A was due to the fact that Across the states bank’s corporate office network is a relatively large network, covering 240 devices within the corporate office and 60 devices within the branch location, I also had to make sure they were private addresses. Therefore, I needed an IP and subnets that could cover all 260 devices in the network while still separating each department for the corporate office and allow for most hosts if we wanted to expand the network. For this I assigned the corporate office 10.1 for location purposes. I then assigned each department to a vlan, in the order of vlan10(data), vlan20 (Management), vlan30(VoIP/Video), vlan40(DMZ), vlan99(Guest Wireless). For vlan10, I gave it the subnet mask 255.255.255.0/24 because it would grant the use of 254 total hosts but only 118 devices will be using those addresses. This gives us more room for expansion if we wish to add more devices to the network. Therefore, the IP address of this would be 10.1.10.0/24 and the host range would be 10.1.10.2-254. For Vlan20 I also gave it the subnet mask of 255.255.255.0/24 with an IP Address of 10.1.20.0/24 and host range of 10.1.20.2-254 for the same reason as vlan10. For vlan30 I gave is a subnet mask of 255.255.255.0/24 with an IP Address of 10.1.30.1/24 and host range of 10.1.20.2-254 for the same reason as Vlan10 and 20.
 
For Vlan40 I gave it a subnet mask of 255.255.255.0/24 with an IP Address of 10.1.40.0/24 and a host range of 10.1.40.2-254 for the reasons stated before. For Vlan99, I used the Subnet 255.255.252.0/22 With an IP address of 172.16.99.0/22 because Vlan99 is where guests can connect there IoT devices to the internet. It is a good Idea to keep these separate from your wired networks because if someone on your guest network turns out to be an attacker, they are separated from the company’s LAN. Therefore, I air gapped vlan99 out of the Lan. 

For the branch location I only created 2 vlans. Vlan10(data), Vlan15(Guest wireless). The IP setup was similar to the corporate offices Wireless vlans, the only differences were that I assigned a different IP address to this location, that being 10.2. For the Data vlan for the branch location I used subnet mask 255.255.255.0/24 with an IP address of 10.2.10.0/24 and a host range of 10.2.10.2-254(For similar reasons why I used /24 subnets for the corporate office). For the Guest Wireless I also air Gapped this network for the same reasons I did for the corporate office. The Subnet mask I used was, 255.255.252.0/22 With the IP address 172.16.15.0/22.  

# IPv6

I also recommend implementing IPv6 into our company’s network. The reason being is IPv4 exhaustion (term that refers to IPv4 addresses eventually running out). An advantage that Ipv6 has over Ipv4 is that it utilizes 128-bit IP address. This means that IPv6 can cover a more significant number of devices. For example, IPv4 can cover up to 4.29 billion devices which is less than the population of devices today. IPv6 in comparison, can cover 1028 time more than IPv4 according to Cisco. To future proof the Network without the use of NAT technology, IPv6 would be our most logical solution. If we were to purchase an IPv6 block the block would be 2001:AD2:5493: :/64. We could also use these addresses with our current vlan set up similar to IPv4. For example, Vlan10 for IPv4 is 10.1.10.0/24, if we were to address this with IPv6 it would be 1001:AD2:5493:0010::/64. 

# Wireless Network/Policy
For our company’s network, I have created a security policy that everyone should follow to ensure the safety of our network. The purpose of this policy is to mitigate any threats to our network through wireless connections. That is why I suggest we separate the wireless network from our wired one. This will be done by creating two different subnets, 10.1.0.0/24 for our wired network and 172.16.99.0/23 for our wireless network. It is beneficial to keep these two networks separate because if an untrustworthy device was able to access the wireless network, the attacker wouldn’t be able to access the wired one. Thus, adding an extra layer of security. 

Which brings me to my second suggestion, Encryption security for the wireless network. In my research, I found that the best The best practice for wireless security is to implement the latest Wi-Fi Security technologies, this being WPA3. WPA3 replaces WPA2 and uses a pre-shared key for users to access the network. In practice, if someone wanted to use the wireless network, the client needs find the network’s SSID, and must have the correct password to access the network. WPA3 uses the Device Providing Protocol or (DPP) to encrypt any networks that may have sensitive data.  DPP is more secure than AES encryption that WPA2 uses thanks to its robust features. These features include Simultaneous Authentication of Equal protocol where a network device generates a new Pre-shared Key to the wireless device every time it authenticates the device. The encryption type for DPP GCMP-256 encryption, this is uses 256 bit thus providing better performance for wireless devices, compared to AES-CCMP which uses 128 bits.

To further Secure our network, I suggest we add further measures on our guest Wi-Fi. I suggest we implement a captive portal. A captive portal is used to authorize clients on to the network that agree to the set of terms presented as soon as they log on to the network. By agreeing to these terms, they are allowed to use the internet. By using this policy, we have the ability to ensure our networks security. 


See the Across the States Wireless Network Policy Attached to this Document. 

# Fault Tolerance 
When designing this network, one of the most important things I had to consider was Fault tolerance. Fault tolerance is when a component or part of a system or network fails but is still able to function without interruptions or the loss of data. To achieve this goal for our network, it is a good idea to buy our network appliances in pairs, in case one fails. If one fails, then the 2nd one will take over continuing to provide services that the previous one oversaw. 



Some examples are the Layer two and three switches, and the firewalls. As you can see on the diagram, each device comes in pairs or has more than one for this reason. To prevent the loss of data, I have invested in server backups. How this will be done is by using the same concept we used to make our network appliances fault tolerant by buying them in pairs. By running a main server and an identical backup server, we are ensuring that data will not be lost if our main server were to have issues. Another way to ensure fault tolerance is investing in UPS’s. These will temporarily provide power to Network Appliances and servers in the event of an outage. Using these will buy the Network Admin enough time to run the proper backups and shut down procedures to ensure that no data has been lost.  


# Network Diagram 

See Network Diagram PDF Attached to this Document


# Switch configurations  
Core Switch

Building configuration...

Current configuration : 2025 bytes
!
version 16.3.2
no service timestamps log datetime msec
no service timestamps debug datetime msec
no service password-encryption
!
hostname CORP-CORE-01
!
!
!
!
!
!
!
no ip cef
ip routing
!
no ipv6 cef
!
!
!
!
!
!
!
!
!
!
!
!
no ip domain-lookup
!
!
spanning-tree mode pvst
!
!
!
!
!
!
interface GigabitEthernet1/0/1
!
interface GigabitEthernet1/0/2
 switchport trunk allowed vlan 2,4,6,96
 switchport mode trunk
!
interface GigabitEthernet1/0/3
 switchport trunk allowed vlan 2,4,6,96
 switchport mode trunk
!
interface GigabitEthernet1/0/4
 switchport trunk allowed vlan 2,4,6,96
 switchport mode trunk
!
interface GigabitEthernet1/0/5
 switchport trunk allowed vlan 2,4,6,96
 switchport mode trunk
!
interface GigabitEthernet1/0/6
 switchport trunk allowed vlan 2,4,6,96
 switchport mode trunk
!
interface GigabitEthernet1/0/7
!
interface GigabitEthernet1/0/8
!
interface GigabitEthernet1/0/9
!
interface GigabitEthernet1/0/10
!
interface GigabitEthernet1/0/11
!
interface GigabitEthernet1/0/12
!
interface GigabitEthernet1/0/13
!
interface GigabitEthernet1/0/14
!
interface GigabitEthernet1/0/15
!
interface GigabitEthernet1/0/16
!
interface GigabitEthernet1/0/17
!
interface GigabitEthernet1/0/18
!
interface GigabitEthernet1/0/19
!
interface GigabitEthernet1/0/20
!
interface GigabitEthernet1/0/21
!
interface GigabitEthernet1/0/22
!
interface GigabitEthernet1/0/23
!
interface GigabitEthernet1/0/24
!
interface GigabitEthernet1/1/1
!
interface GigabitEthernet1/1/2
!
interface GigabitEthernet1/1/3
!
interface GigabitEthernet1/1/4
!
interface Vlan1
 no ip address
 shutdown
!
interface Vlan2
 mac-address 000c.cf21.0701
 ip address 10.0.2.1 255.255.255.0
!
interface Vlan4
 mac-address 000c.cf21.0702
 ip address 10.0.4.1 255.255.255.0
!
interface Vlan6
 mac-address 000c.cf21.0703
 ip address 10.0.6.1 255.255.255.0
!
interface Vlan96
 mac-address 000c.cf21.0704
 ip address 10.0.96.1 255.255.255.0
!
ip classless
!
ip flow-export version 9
!
!
!
!
!
!
!
!
line con 0
!
line aux 0
!
line vty 0 4
 login
!
!
!
!
end
 
Access Switch Configuration

Building configuration...

Current configuration : 2430 bytes
!
version 15.0
no service timestamps log datetime msec
no service timestamps debug datetime msec
no service password-encryption
!
hostname CORP-SW-03
!
!
!
!
!
!
spanning-tree mode pvst
spanning-tree extend system-id
!
interface FastEthernet0/1
 switchport access vlan 2
 switchport mode access
!
interface FastEthernet0/2
 switchport access vlan 2
 switchport mode access
!
interface FastEthernet0/3
 switchport access vlan 2
 switchport mode access
!
interface FastEthernet0/4
 switchport access vlan 2
 switchport mode access
!
interface FastEthernet0/5
 switchport access vlan 2
 switchport mode access
!
interface FastEthernet0/6
 switchport access vlan 2
 switchport mode access
!
interface FastEthernet0/7
 switchport access vlan 2
 switchport mode access
!
interface FastEthernet0/8
 switchport access vlan 2
 switchport mode access
!
interface FastEthernet0/9
 switchport access vlan 2
 switchport mode access
!
interface FastEthernet0/10
 switchport access vlan 2
 switchport mode access
!
interface FastEthernet0/11
 switchport access vlan 2
 switchport mode access
!
interface FastEthernet0/12
 switchport access vlan 2
 switchport mode access
!
interface FastEthernet0/13
 switchport access vlan 2
 switchport mode access
!
interface FastEthernet0/14
 switchport access vlan 2
 switchport mode access
!
interface FastEthernet0/15
 switchport access vlan 2
 switchport mode access
!
interface FastEthernet0/16
 switchport access vlan 2
 switchport mode access
!
interface FastEthernet0/17
 switchport access vlan 2
 switchport mode access
!
interface FastEthernet0/18
 switchport access vlan 2
 switchport mode access
!
interface FastEthernet0/19
 switchport access vlan 2
 switchport mode access
!
interface FastEthernet0/20
 switchport access vlan 2
 switchport mode access
!
interface FastEthernet0/21
 switchport access vlan 2
 switchport mode access
!
interface FastEthernet0/22
 switchport access vlan 2
 switchport mode access
!
interface FastEthernet0/23
 switchport access vlan 2
 switchport mode access
!
interface FastEthernet0/24
 switchport access vlan 2
 switchport mode access
!
interface GigabitEthernet0/1
 switchport trunk allowed vlan 2,4,6,96
 switchport mode trunk
!
interface GigabitEthernet0/2
!
interface Vlan1
 no ip address
 shutdown
!
interface Vlan6
 ip address 10.0.6.3 255.255.255.0
!
ip default-gateway 10.0.6.1
!
!
!
!
line con 0
!
line vty 0 4
 login
line vty 5 15
 login
!
!
!
!
end



# Cost Analysis 

Networking Device Cost

Cisco Firepower 2130 NGFW-Cost $39,176.00
We need 6 of them 
$39,176.00 * 6 = $235,056

 Routers L3
Cisco Switch Catalyst 9300
We need 4 of them
$5,592.00 * 4 = $22,368

Router L2
Cisco Catalyst 2960L 48 ports
We need 9 of them
$5,243.00 * 9 = $471,187


Cisco Catalyst 2960L 24 ports
We need 2 of them
$4,700 * 2 = $9,400

Total cost of Networking devices 
$ 738,011
Cisco Firepower 2130 NGFW-Cost $39,176.00
We need 6 of them 
$39,176.00 * 6 = $235,056

 Routers L3
Cisco Switch Catalyst 9300
We need 4 of them
$5,592.00 * 4 = $22,368

Router L2
Cisco Catalyst 2960L 48 ports
We need 9 of them
$5,243.00 * 9 = $471,187


Cisco Catalyst 2960L 24 ports
We need 2 of them
$4,700 * 2 = $9,400

Total cost of Networking devices 
$ 738,011
Cisco Firepower 2130 NGFW-Cost $39,176.00
We need 6 of them 
$39,176.00 * 6 = $235,056

 Routers L3
Cisco Switch Catalyst 9300
We need 4 of them
$5,592.00 * 4 = $22,368

Router L2
Cisco Catalyst 2960L 48 ports
We need 9 of them
$5,243.00 * 9 = $471,187


Cisco Catalyst 2960L 24 ports
We need 2 of them
$4,700 * 2 = $9,400

Total cost of Networking devices 
$738,011
*Branch Location Included

Labor Costs 
9 Network Engineers
$50 per hour
40 hours each
Total labor for network engineers
50*9*40= $18,000
*Three will be assigned to the branch location

6 Network Administrators
$50 per hour
40 hours each
Total labor for network administrators
50*6*40= $12,000
*Three will be assigned to the branch location

Total cost of labor
$30,000
*Branch location included


The total cost of equipment is based on the network devices I researched. The equipment listed above is subject to change if Across the States bank sees better options. This could raise the cost of equipment or lower it. To build a secure stable network, I believe it should be built from the ground up. The installation of these devices is based on a schedule of 8 hours a day 5 days a week at the hourly pay of $50.



# Work Breakdown Structure


See Work Breakdown structure attached to this document




# Project Risk Analysis

When planning this project, it is imperative that we prepare for any potential threats, setbacks, or service issues when it comes to following through with this project. We need to make sure that our schedule is still going to be met and identify any challenges that we may face.   When it comes to project management, a risk analysis is needed to determine any impacts to the company caused by production delays. For Across the States, we will be run the risk analysis by using these steps: identifying the risk, examining the impact of risk, and analyzing risk probability.

 To start, we anticipate that the project will be finished according to the times listed on the work breakdown structure. A risk factor to package completion would be delays such as purchasing delays due to an event where the product doesn’t arrive on time, Funding delays, and Vendor delays such as the vendor not having the products available. 


Now that we have identified the risks of this project, we must identify the impacts of any these risks were to happen. This would include, having to adjust our production schedule based on the situation if a vendor delay or purchasing delay were to happen. Having to substitute Cheaper products than the one I listed in the Cost Analysis to adjust to funding delays. Unfortunately, the consequences of such events would cause a delay on the deployment of this network.

The Probability of Purchasing delays and vendor delays depends on the vendor and inventory. If the vendor doesn’t have the product available, this will cause setbacks to the schedule. To lower the probability of this risk we must be proactive and contact the vendors according to the schedule.  The probability of Funding delays depends on our team getting the proper funding according to the budget. As long as the budget stays reasonable, the probability of this happing is relatively low.


 
# LAN/WAN Risk analysis

Unfortunately, with the growing number of cyber threats, it is also crucial that we use a risk analysis while our network is in operation. This analysis will help us determine and prepare for any threat to the network. We can also use the steps I listed before: identifying the risk, examining the impact of risk, and analyzing risk probability.

Our risks include targets of attackers such as, Credit card numbers, Bank account information, social security numbers etc.… Other Attacks such as social engineering attacks should also be a risk factor of concern and prepared for. 

The impact of these risks is that we could potentially lose valuable information such as customer or employee information, or hundreds to thousands of dollars to Phishing Schemes (Social engineering). We could also lose customer trust and our reputation. 

We have the ability to lower such the risk of such attacks by following industry level best practices when installing the LAN/WAN. This includes separating wireless networks form our wired one, AES encryption to only allow authorized users on the network, and properly configuring firewalls with ACLs to ensure that only authorized incoming traffic is entering the network. It is also important that we must also train our employees on social engineering, and the proper use of our wireless networks. (Refer to Wireless security policy for details) These will all mitigate security threats.   


 






# Cyber Security Organizations

To ensure that this network is following the best security practices, I recommend that we partner with one of the three Cybersecurity Organizations. These organizations are, CompTIA ISAO, Center for internet security (CIS), and Information System Security Association (ISSA). All three of these organizations provide businesses with threat prevention, response, and employee training. Although these organizations provide similar services, I had to select the best one to fit our business’s needs. Therefore, I recommend partnering with CompTIA ISAO. My reasoning for this decision was shaped by there solution services such as Threat intelligence and analysis, Cyber risk ratings for our network, and Cybersecurity best practice sharing. Another reason I chose CompTIA ISAO is that they have established business partners such as Dell.


				Conclusion
In closing, these recommendations are based off the research I made throughout the creation of this proposal. Across the States Bank is allowed to change, suggest, or alter this proposal anyway they see fit for the company’s needs.  
