Installing Jenkins LTS as servlet in Tomcat 9   
=========

Runnig Jenkins LTS with a series of plugins as servlet in Tomcat 9   

Requirements
------------

Sensitive variables defined in playbook bellow should have been added in a vault file

Role Variables
--------------

Installation variables can be found in defaults folder, while customization / plugins variables are defined in vars folder.                  

Dependencies
------------

Jenkins LTS on a RHEL79 OS with Tomcat 9.0.45    
   
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
