# Strudel Web Infrastructure

## Components
Strudel Web for [CVL](https://desktop.cvl.org.au) infrastructure consists of these components:   
* [HAProxy](./HAPROXY.md)   
* [Strudel Web Server](./STRUDELWEB.md)   
* [pysshauthz](https://github.com/Characterisation-Virtual-Laboratory/ansible-pysshauthz) or [ssh-authz - old](https://github.com/monash-merc/ssh-authz)
* LDAP Server. The installation and configuration of a directory service server such as [LDAP](https://www.tldp.org/HOWTO/LDAP-HOWTO/whatisldap.html) is not covered by this document.

## Example of deployment
Current [CVL](https://desktop.cvl.org.au) consists of:
* 2 HAProxy servers   
* 2 Strudel Web Server   
* 1 ssh-authz   
* 1 LDAP server   

The HAProxy servers are the front-end to the Strudel Web service, effectively load-balancing between the two Strudel Web servers.
The HAProxy servers themselves are load-balanced via DNS round-robin. All the components for Strudel Web are running on NECTAR.
