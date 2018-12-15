vxlan role
==============
This is a very basic role to configure vxlan

Installation
------------ 

Role variables
--------------


Example playbook
----------------


**Sample hosts file**

   

**Sample host_vars/**

	vxlan:
	  nve: loopback1
	  asn: 64625
	  evpn: auto-evi
	  neighbor:
		- ip: 1.2.3.9
		  remote_asn: 6669
		- ip: 1.2.3.4
		  remote_asn: 6666
	  virtual_network:
		- vn_id: 101
		  vxlan_tag: 101101
		  vlti_vlan: 3101
		  vlti_vlan_state: absent # absent is used to remove
		  member_interface:
			- interface: ethernet 1/1/19 vlan-tag 200 # or "vlan xxx"
			  state: absent # absent is used to remove
			  vlan: 400 # or interface above
			  vlan_state:
		- vn_id: 102
		  vxlan_tag: 101102
		  vxlan_tag_state: absent # absent is used to remove
		  vlti_vlan: 3102
		  member_interface:
			- vlan: 400
			  vlan_state: absent # absent is used to remove    
	
**Simple playbook to setup system - leaf.yaml**


**Run**

