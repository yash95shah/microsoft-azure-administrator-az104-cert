VPN Gateway is used in a hub and spoke topology.

SKU is one of the configurations and it defines how much throughput in Gbps you can get. Other configs include Active-Active Mode and GW private IPs. (and also configure BGP)

This is also where you configure point to site.

public IP associated of course as the communication happens through 

three different types of connections VPN-to-VPN, site to site (ipsec) and expressroute

There has to be a way to authenticate the connection - shared key or key vault certificate

IKE protocol v1 or v2 may be used. Private IP support is there if enabled on the VNET gateways themselves.

We can also assocaite the NAT gateways for ingress and egress.

There can only be one type of gw that exist in a VNET -if it is VPN-VPN or Expressroute.



VM NIC has IP configs, DNS config NSG
