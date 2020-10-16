# ansible-mysql-server
Deploy docker container with MySQL-server based on official mysql container (https://hub.docker.com/)

## Role variables
| Variable | Default value | Description |
| :---:        |     :---:      |         :---: |  
service_name                    |       mysql-docker            |   Service name in OS
uninstall_service               |       false                   |
host_dir                        |       /var/docker/mysql       |   Mapping directory on host
container_dir                   |       /var/lib/mysql          |   Mapping directory on container
docker_image                    |       mysql                   |   Docker image (https://hub.docker.com/)

### How to use
    - installation: just start the role
    - uninstallation: add --extra-vars "uninstall_service=true" (WARNING: It doesn't delete directory /var/docker/tftpboot on host!!)

#### MYSQL_DATABASE, MYSQL_USER, MYSQL_PASSWORD, MYSQL_ROOT_PASSWORD
These variables are used in ./templates/systemd/mysql.service.j2 service template. It's better to store these variables in encrypted file (for example in encrypted <your project ansible directory>/group_vars/all.yml . For more information see - https://docs.ansible.com/ansible/latest/cli/ansible-vault.html