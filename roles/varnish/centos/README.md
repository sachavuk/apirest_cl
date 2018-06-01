Requirements

None.

Role Variables: 

Available variables are listed below, along with default values (see defaults/main.yml):

varnish_version: version of varnish you want, default value '3.0.7' the lastest

varnish_vcl_file: name of template file what you want to use, default value 'default.vcl' 

varnish_config_path: path where you want to put your vcl config, default value '/etc/varnish'

varnish_nfiles: set number of open files, default value '131072'

varnish_memlock: set number locked shared memory, default value '82000' (82 MB) 

varnish_nprocs: set maximum thread for varnish, default unlimited

varnish_listen_address: set varnish listen address , default value 0.0.0.0

varnish_listen_port: set varnish listen port, default value '6081'

varnish_admin_listen_address: set ip adresse for varnishadm , default value '127.0.0.1'

varnish_admin_listen_port: set port for varnishadm, default value '6082'

varnish_min_threads: the minimum number of worker threads to start, default value '50'

varnish_max_threads: the Maximum number of worker threads to start, default value '1000'

varnish_thead_timeout: idle timeout for worker threads, default value '120'

varnish_storage_file: cache file location, default value 'var/lib/varnish'

varnish_storage_size: size of your cache value possible G or M , default value '1G'

varnish_ttl: set ttl used when the backend doesn't specify one, default value '120' 

varnish_storage_type: file or malloc, default it's file

varnish_nuke_limit: Optional set maximum number of objects we attempt to nuke in orderto make space for a object body

Dependencies

None.

Example Playbook

- hosts: webservers
  roles:
    - { role: varnish }
