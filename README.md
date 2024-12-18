Opensearch Dashboards Role
=========

Ansible role to install Opensearch and Opensearch Dashboards via Helm on top of Kubernetes

Requirements
------------

A kubernetes cluster, internet access (unless self hosting files), root access, linux box.

Role Variables and Associated Defaults
--------------

```yaml
osd_helm_dir: /root/helm
osd_helm_url: https://get.helm.sh/helm-v3.16.4-linux-amd64.tar.gz
osd_ulb_dir: /usr/local/sbin
osd_opensearch_dir: /root/opensearch
osd_password: 'Ch4ng3M3!!'
osd_helm_opensearch_version: opensearch
osd_helm_opensearch_repo: https://opensearch-project.github.io/helm-charts
osd_opensearch_name: testing
osd_opensearch_dashboards_name: testing-dash
osd_opensearch_namespace: default
osd_customvalues: customvalues.yaml
osd_dashboards: true
```

Dependencies
------------

My k3s role will prep a box with k3s kubernetes.

Example Playbook
----------------

```yaml
- name: Install Opensearch
  hosts: all
  tasks:
    - name: Call Opensearch Dashboards role
      ansible.builtin.include_role:
        name: opensearch_dashboards
        apply:
          become: true
      vars:
        osd_password: 'CU5T0MP455W0RD'
```

License
-------

BSD

Author Information
------------------

Fen UwU
