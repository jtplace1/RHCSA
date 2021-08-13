Manage Containers

# Manage Containers

        
- Find and retrieve container images from a remote registry
- Inspect container images
- Perform container management using commands such as podman and skopeo
- Perform basic container management such as running, starting, stopping, and listing running containers
- Run a service inside a container
- Configure a container to start automatically as a systemd service
- Attach persistent storage to a container

| **Podman enabling auto start container**                     |                                                              |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| podman run -d --name web -p 8888:8080 -v /home/containerdata:/var/www/html:Z -e HTTPD_MPM=event [registry.redhat.io/rhel8/httpd-24:1-112.1599745027](http://registry.redhat.io/rhel8/httpd-24:1-112.1599745027) | Creating a container                                         |
| Cd /etc/systemd/system                                       | Changing the directory to the right location                 |
| Sudo podman generate systemd —name \<container\> --files     |                                                              |
| Login as the user and then -> ~/.config/systemd/user         | Location where the service must be                           |
| Systemctl —user daemon-reload **(with ae)**                  |                                                              |
| Systemctl —user enable container-web.service                 |                                                              |
| setsebool -P container_manage_cgroup on                      |                                                              |
|                                                              |                                                              |
| Loginctl enable-linger \<username\>                          | Enable this so that the container can start automatically as the system boots |
|                                                              |                                                              |
