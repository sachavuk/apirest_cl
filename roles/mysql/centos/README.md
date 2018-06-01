Requirements

None.

Role Variables: 

Available variables are listed below, along with default values (see defaults/main.yml):
    
        update_mysql_conf: if you want to disable update mysql conf , add value to variable false
	mysql_datadir: set mysql path where store db, default value '/var/lib/mysql' 
	mysql_port: Set mysql port, default value '3306'
	mysql_bind_address: set mysql listen address, default value '127.0.0.1'
        mysql_tmp_dir: if you want to change tmp dir for mysql
	mysql_character_set_server: set character for server , default value 'utf8'
	mysql_collation_server: set collation server , default value 'utf8_general_ci' 

For mysql > 5.5
        mysql_enable_slow_query: set if slow query is enable, default value '0'
	mysql_slow_query_file: set path for slow query
	mysql_slow_query_time: set time for slow query 

For mysql < 5.5
	mysql_slow_query_file: set path for slow query
	mysql_slow_query_time: set time for slow query 


Default MySQL connection configuration.

	mysql_key_buffer_size: "256M"
	mysql_max_allowed_packet: "1M"
	mysql_table_open_cache: "256"
	[...]
	See default/main.yml for other options 



The rest of the settings in `defaults/main.yml` control MySQL's memory usage. The default values are tuned for a server where MySQL can consume ~512 MB RAM, so you should consider adjusting them to suit your particular server better.


First installation of mysql, the role will create a default password for user root you must run your playbook with arg --ask-vault. This password is stored in vars/password.yml , If a mysql is already installed this step will be ignored. 
 
Dependencies

None.

Example Playbook

- hosts: dbservers
  roles:
    - { role: mysql }
