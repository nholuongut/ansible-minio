<p><img src="https://avatars0.githubusercontent.com/u/695951?s=200&v=4" alt="minio logo" title="minio" align="right" height="60" /></p>

# Ansible Role: Minio

![](https://i.imgur.com/waxVImv.png)
### [View all Roadmaps](https://github.com/nholuongut/all-roadmaps) &nbsp;&middot;&nbsp; [Best Practices](https://github.com/nholuongut/all-roadmaps/blob/main/public/best-practices/) &nbsp;&middot;&nbsp; [Questions](https://www.linkedin.com/in/nholuong/)
<br/>

Install and configure the [Minio](https://minio.io/) S3 compatible object storage server
on RHEL/CentOS and Debian/Ubuntu.

## Requirements

None.

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

```yaml
minio_server_bin: /usr/local/bin/minio
minio_client_bin: /usr/local/bin/mc
```

Installation path of the Minio server and client binaries.

```yaml
minio_user: minio
minio_group: minio
```

Name and group of the user running the minio server.
**NB**: This role automatically creates the minio user and/or group if these does not exist in the system.

```yaml
minio_server_envfile: /etc/default/minio
```

Path to the file containing the minio server configuration ENV variables.

```yaml
minio_server_addr: ":9091"
```

The Minio server listen address.

```yaml
minio_server_datadirs: [ ]
```

Directories of the folder containing the minio server data
**NB**: This variable must always be set by the role, otherwise the minio service will not start.

```yaml
minio_server_make_datadirs: true
```

Create directories from `minio_server_datadirs` 

```yaml
minio_server_cluster_nodes: [ ]
```

Set a list of nodes to create a [distributed cluster](https://docs.minio.io/docs/distributed-minio-quickstart-guide).

In this mode, ansible will create your server datadirs, but use this list for the server startup. Note you will need a number of disks to satisfy Minio's distributed storage requirements.

Example:

```yaml
minio_server_datadirs:
  - '/minio-data'
  - ...
minio_server_cluster_nodes:
  - 'https://server1/minio-data'
  - 'https://server2/minio-data'
  - 'https://server3/minio-data'
  - ...
```

```yaml
minio_server_opts: ""
```

Additional CLI options that must be appended to the minio server start command.

```yaml
minio_access_key: ""
minio_secret_key: ""
```

Minio access and secret keys.

```yaml
minio_install_server: true
minio_install_client: true
```

Switches to disable minio server and/or minio client installation.

## Dependencies

None.

## Example Playbook

```yaml
- name: "Install Minio"
  hosts: all
  roles:
    - nholuong.minio
  vars:
    minio_server_datadirs: [ "/minio-test" ]
```

# 🚀 I'm are always open to your feedback.  Please contact as bellow information:
### [Contact ]
* [Name: nho Luong]
* [Skype](luongutnho_skype)
* [Github](https://github.com/nholuongut/)
* [Linkedin](https://www.linkedin.com/in/nholuong/)
* [Email Address](luongutnho@hotmail.com)

![](https://i.imgur.com/waxVImv.png)
![](Donate.png)
[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/nholuong)

# License
* Nho Luong (c). All Rights Reserved.🌟
