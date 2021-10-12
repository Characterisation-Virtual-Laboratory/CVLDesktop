# CVL Desktop
This has to be defined 

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
* 1 pysshauthz   
* 1 LDAP server   

The HAProxy servers are the front-end to the Strudel Web service, effectively load-balancing between the two Strudel Web servers.
The HAProxy servers themselves are load-balanced via DNS round-robin. All the components for Strudel Web are running on NECTAR.

# development environment

The following sentences have nothing to do with Strudel Web Infrastructure yet. This is work in progress

## miniCVL
For easier development a miniCVL is defined as a Virtual Machine with a mate desktop which is accessible via VNC capable of running singularity containers with GPU support.
This mini CVL is intended to be a development environment for the CVL Desktop menu and therefore has to be able to support [CVL-Software](https://github.com/Characterisation-Virtual-Laboratory/CharacterisationVL-Software). 

## microCVL
Is a future iteration of miniCVL. Where we exchange the requirement of a VM to be a singularity container.

