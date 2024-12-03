Role Name
=========

A brief description of the role goes here.

Requirements
------------

* Ansible 2.9+ installed on the control machine.
* Docker must be installed and running on the target machine.

Role Variables
--------------

The role provides the following customizable variables. These should be defined in the playbook or inventory:
| Variable       | Default Value  | Description    |
|----------------|----------------|----------------|
| reg_token      | null           | gitlab registration token |
| domain         | gitlab.foo.uz  | gitlab domain name |
| ip_address     | null           | ip address of gitlab if use local ip |
| volume_enable  | false          | it should be `true` or `false` |
| volume_name    | runner-volume  | name of volume which uset for docker volume create |
| image_name     | gitlab/gitlab-runner | name of image for gitlab runner |
| image_tag      | latest         | tag name of gitlab runner |
| container_name | runner-1       | name of container |
| runner_name    | runner-1       | name of runner   |
| runner_tags    | TEST           | tag name    |
| extra_volumes  | []             | volume list     |
| etc_hosts      | []             | extra host list for container |
| extra_hosts    | []             | extra host for runner config, it will be set in to config.toaml file |
| base_dir       | /etc/gitlab-runner | workdir for gitlab runner |
| timezone       | "Asia/Tashkent" | timzenoe |
| executor       | docker          | runner executor, `docker`, `docker-machine`, `shell`, `kubernetes` |
|  docker_image  | alpine:latest   | image for executor |
| concurrency    | 10              | number of concurrency |

Dependencies
------------

geerlingguy.docker 

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: karen.docker-runner }

License
-------

This role is licensed under the MIT License.

Author Information
------------------

Abbos Pulatov from AnyOps teams
