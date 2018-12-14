# vxlan_OS10

  
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
#      vlti_vlan_state: absent
      member_interface:
        - interface: ethernet 1/1/19 vlan-tag 200 # or "vlan xxx"
          state: absent
#          vlan: 400
#          vlan_state: absent
    - vn_id: 102
      vxlan_tag: 101102
#      vxlan_tag_state: absent
      vlti_vlan: 3102
      member_interface:
        - vlan: 400
          vlan_state: absent
