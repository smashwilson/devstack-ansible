# Devstack Ansible playbook

This is an Ansible playbook that will install a single-host
[devstack](http://devstack.org/) *(Icehouse release)* on a freshly provisioned
Ubuntu 14.04 server. You'll need at least 4GB of RAM on the target box.

It's useful for development of services that hit the OpenStack API. It also
contains a workaround for
[this devstack issue](https://bugs.launchpad.net/devstack/+bug/1316328).

## Installing

To use this, you'll need [Ansible](http://docs.ansible.com/intro_installation.html)
installed on your client machine. Generally this is some variant on
`brew install ansible`, `apt-get install ansible`, or `pip install ansible`.

Then, copy `customize.yml` and change whatever things you feel need changing:

```bash
cp customize.yml.example customize.yml
${EDITOR} customize.yml
```

And run the playbook:

```bash
ansible-playbook -i "${SERVER_IP}," site.yml
```
