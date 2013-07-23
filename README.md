## mysql server Ansible role

This role installs mysql-server and manages users and databases.

**[7/23/2013] Right now, the role only facilitates adding users and databses**

### Usage

Add the role to a playbook:
	
	---
	- hosts: db_servers
	  sudo: yes
	  roles:
	 	- mysql_server

By adding the role, the tasks in `tasks/main.yml` run automatically when the playbook is called. 

**This has only been tested on Ubuntu 12.10**

### Tasks

#### add_user
	
	tasks:
    - include: roles/mysql_server/tasks/add_user.yml user=testuser password=testpass

#### add_db
  
    tasks:
      - include: roles/mysql_server/tasks/add_db.yml name=testdb

### Todo

* Add ability to define granular permissions for MySQL users
* Add more configuration options to my.cnf that can be set as vars