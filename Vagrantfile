# vi: set ft=ruby :

# In the future, this might do something more interesting
# like contain code to sync git from the local dir into
# the system and do builds/installs there.  But for
# now at least this exists as a starting point, and
# once `ostree admin unlock` exists in the next version,
# things will be a bit simpler.

Vagrant.configure(2) do |config|
    config.vm.box = "centos/atomic-host"
    config.vm.hostname = "centosah-dev"
    config.vm.synced_folder ".", "/srv/vagrant", disabled: true

    config.vm.provision "ansible" do |ansible|
      ansible.playbook = "tests/new-image-smoketest/main.yaml"
      ansible.skip_tags = "jenkins"
    end
end
