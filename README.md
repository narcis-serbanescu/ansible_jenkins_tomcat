Use of Ansible in installing Tomcat and Jenkins LTS            
=========

The purpose of the above Ansible role:
- Install Tomcat 9 
- Install and customize Jenkins LTS as servlet in Tomcat 9       
- Add a series of Jenkins plugins     

Requirements
------------

Sensitive variables defined in playbook bellow should have been added in a vault file

Role Variables
--------------

Installation variables can be found in defaults folder, while customization / plugins variables are defined in vars folder.                  

Dependencies
------------

Basic installation of RHEL79 OS, that will host Tomcat and Jenkins installations.   
Any existing JDK package will be removed by the role.     

   
Example Playbook
----------------

Example of how to use the role:     
```
---
- name: Run Jenkins as servlet in Tomcat    
  hosts: target_host     
  become: true    
  vars:    
    tomcat_ver: 9.0.45     
    ui_manager_user: manager                    # User who can access the UI manager          
    ui_manager_pass: Zaq!2wsxCde34rfv           # UI manager user password     
    ui_admin_username: admin                    # User access bpth manager and admin UI         
    ui_admin_pass: Zaq!2wsxCde34rfv             # UI admin password      
    jenkins_user: jenadm                        # Additional admin user     
    jenkins_pass: Zaq!2wsxCde34rfv              # Additional admin user password      
    jenkins_fullname: Jenkins Admin     
    jenkins_email: jenadm@rhel79     

  roles:        
    - tomcat_jenkins            
...
```
License
-------

BSD

Author Information
------------------

narcis.serbanescu@gmail.com      
