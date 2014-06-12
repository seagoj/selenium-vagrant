Vagrant.configure("2") do |config|
    config.vm.box = "precise64"
    config.vm.box_url = "http://files.vagrantup.com/precise64.box"
    config.ssh.forward_agent = true
    config.vm.provision "docker" do |d|
        d.build_image "/vagrant/docker-selenium-chrome"
        d.run "seagoj/docker-selenium-chrome",
            args: "--privileged -p 9222:9222 -p 4444:4444",
            image: "seagoj/docker-selenium-chrome"
    end
    config.vm.network :forwarded_port, guest:4444, host:4444
    config.vm.network :forwarded_port, guest:9222, host:9222
end
