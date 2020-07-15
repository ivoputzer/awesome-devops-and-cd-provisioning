Vagrant.configure("2") do |config|
    config.vm.box = "ubuntu/bionic64"
    config.vm.network "private_network", ip: "192.168.50.4"
    config.vm.network "forwarded_port", guest: 80, host: 80
    config.vm.provision "ansible" do |ansible|
      ansible.compatibility_mode = "2.0"
      ansible.playbook = "provisioning.yml"
      ansible.verbose = "v"
      ansible.extra_vars = {
        ansible_become_user: "root",
        ansible_python_interpreter: "/usr/bin/python3",
        ansible_become: true
      }
    end
end
