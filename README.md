# ansible-playbook

## How to use

1. Provision from host environment
1. Provision in guest environment

### Provision from host environment

Add below settings to `Vagrantfile` and run vagrant provisioning.

```ruby
config.vm.provision "km45", type: "ansible_local" do |ansible|
  ansible.playbook = "km45-playbooks/host/site.yml"
  ansible.compatibility_mode = "2.0"
  # ansible.verbose = "vvv"
end
```

### Provision in guest environment

Vagrant provisioning can not complete some tasks,
so run them in guest environment.

[CAUSION] Run them in guest environment, not in ssh connection.

```console
$ cd ${PATH_TO_km45-playbooks}/guest
$ ansible-playbook site.yml
```
