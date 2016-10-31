# Ansible Role: install PostgreSQL
##scope
The scope of this Role is solely to install the PostgreSQL Server Package on your Server. It does enable you to choose the available Versions distributed by the PostgreSQL Project.

##distributions

currently these Distributions are supported

 - CentOS 6
 - CentOS 7
 - Debian 6
 - Debian 7
 - Debian 8
 - Ubuntu 12.04
 - Ubuntu 14.04
 - Ubuntu 16.04

Extending is fairly easy and pull-requests are welcome.

##PostgreSQL Versions
Look here: [https://yum.postgresql.org/repopackages.php](https://yum.postgresql.org/repopackages.php)
and here: [http://wiki.postgresql.org/wiki/Apt](http://wiki.postgresql.org/wiki/Apt)

##tested distributions
I have tested on these distributions / Versions

 - CentOS 7
 - Debian 8
 - Ubuntu 16.04

##version variables

- pgversionmajor
- pgversionminor

You might want to set these Variables in group_vars, as this helps moving from one version to another Version. 
"{{ pgversionmajor }}.{{ pgversionminor }}" would resolve to "9.6" as per defaults/main.yml

##example playbook

	---
	- name: install bitbucket-server
	  hosts: postgres-server
	  become: true
	  become_user: root
	  roles:
	    - { role: "install_postgresql-server",
	        pgversionmajor: "9", 
	        pgversionminor: "5"  
	      }

## License
MIT / BSD

## Author Information
This role was created in 2016 by Wolfgang Wangerin at [Hawesko GmbH](http://www.hawesko.de)
