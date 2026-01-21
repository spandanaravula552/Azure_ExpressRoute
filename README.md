What is ER: Expressroute circuit is a private connection, it is used to establish the private connection between the on-prem network and Microsoft network via the Internet service provider.
<img width="1215" height="581" alt="image" src="https://github.com/user-attachments/assets/1897a0a1-d0a5-49f3-a38d-c8c981e934ff" />
The expressroute circuit does not go over the public internet. It is fast, reliable and less latency.capacity to withstand and recover quickly from failures(resiliency)
network flow is: on-prem network->internet service provider(called as partner edge)we have two connections(tunnels) those are primary and seconday connections for redundancy purpose, if one is failed, we have secondary connection->Microsoft edge network where we have two types of peerings, one is microsoft peering to connect onto  Microsoft 365, Azure public services and another one is private peering to connect on to Azure VNETs.
Creation of ER:
portal->search for ER-> select internet service provider, bandwidth, sku, billing model(metered, unlimited)->create.
once ER gets created, you can find "service key" in the overview page of ER, every ER has unique service key, need to give it with the service provider to create connection to our ER ckt, service provide maps the service key with the microsoft, to map that they provide VLAN id, MS ASN number, peer ASN number, then we can see the ckt is provisioned in azure.
ER ckt has two peerings - Private and Microsoft
Private Peering: before creating the private peering for ER ckt in portal, we should have two subnets, one is for primary link and second subnet is for secondary link, VLAN ID, ASN number.
then we create VNG, vpn type as ER, then link the VNET to ER ckt.
