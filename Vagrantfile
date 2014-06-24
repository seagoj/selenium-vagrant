Vagrant.configure("2") do |config|
    config.vm.box = "precise64docker"
    config.vm.box_url = "https://oss-binaries.phusionpassenger.com/vagrant/boxes/latest/ubuntu-14.04-amd64-vbox.box"
    config.ssh.forward_agent = true
    config.vm.provision "docker" do |d|
        d.run "seagoj/selenium-chrome",
            args: "--privileged -p 9222:9222 -p 4444:4444",
            cmd: "/usr/local/bin/start-selenium-server.sh"
    end
    config.vm.network :forwarded_port, guest:4444, host:4444
    config.vm.network :forwarded_port, guest:9222, host:9222
end
