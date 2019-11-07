freehck.k8s_init
=========

Initialize kubernetes cluster with `kubeadm`

Description
-----------

This role initializes kubernetes address. It suggests that all the binaries (`kubeadm` and `kubelet`) are already installed.

Role Variables
--------------

`k8s_base_node_ip`: ip address of this kubernetes node

`k8s_base_ver`: version of kubernetes binaries you want to install

Example
-------

    - hosts: all
      become: true
      vars:
        # k8s_base is an implicit dependency
        k8s_base_node_ip: "10.118.19.10"
        k8s_base_ver: "1.16.2-00"
        # this role configurations
        k8s_init_cidr: "192.168.0.0/16"
        k8s_init_node_ip: "10.118.19.10"
        k8s_init_node_name: "{{ inventory_hostname }}"
      roles:
        - role: freehck.k8s_base
        - role: freehck.k8s_init


Install
-------

This role can be installed from [Ansible Galaxy](https://galaxy.ansible.com/):

`ansible-galaxy install freehck.k8s_init`

License
-------

MIT

Author Information
------------------

Dmitrii Kashin, <freehck@freehck.ru>
