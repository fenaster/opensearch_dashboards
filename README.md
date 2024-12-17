Opensearch Role
=========

Ansible role to install opensearch via Helm on top of Kubernetes

Requirements
------------

A kubernetes cluster, internet access (unless self hosting files), root access, linux box.

Role Variables and Associated Defaults
--------------

```yaml
osd_helm_dir: /root/helm
osd_helm_url: https://get.helm.sh/helm-v3.16.4-darwin-amd64.tar.gz
osd_ulb_dir: /usr/local/bin
osd_opensearch_dir: /root/opensearch
osd_password: 'Ch4ng3M3!!'
osd_opensearch_version: stable
osd_opensearch_repo: https://opensearch-project.github.io/helm-charts/
osd_opensearch_name: testing
osd_customvalues: customvalues.yaml
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
    - name: Call opensearch role
      ansible.builtin.include_role:
        name: opensearch
        apply:
          become: true
```

License
-------

BSD

Author Information
------------------

Fen UwU
