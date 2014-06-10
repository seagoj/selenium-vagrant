Vagrant.configure("2") do |config|
    config.vm.box = "precise64"
    config.vm.box_url = "http://files.vagrantup.com/precise64.box"
    config.ssh.forward_agent = true
    config.vm.provision :shell, :path => "setup.sh"
    config.vm.network :forwarded_port, guest:4444, host:4444
    config.vm.network :forwarded_port, guest: 9222,host: 9222
end
