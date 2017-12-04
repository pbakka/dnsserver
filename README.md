# dnsserver


Create local DN Server Primary and secondary with a forwarder.

Select two different machines one as primary and other as slave.

Add Client host ip address and name under the clients section of the inventory file

**Fill in the inventory file with IP address** 

## [master]
192.168.2.7 host_name="ns.tipsoft.local"  
[slave]  
192.168.2.8 host_name="ns-slave.tipsoft.local"  
## [all:vars]  
ansible_become=True  
ansible_become_user=root  
ansible_become_pass=XXXXXX  
domain_name=tipsoft.local  
gateway_address=192.168.2.1  
allowed_ips=192.168.2.0/24  
forwarders="8.8.8.8"  
## [clients]  
192.168.2.10 host_name="rhel1.tipsoft.local"  
[clients:vars]  
add_client=true  
 
#To Run:

*ansible-playbook -i inventory setup-dns-server.yml*  



 # dnsserver
