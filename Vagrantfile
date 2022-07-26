Vagrant.configure("2") do |config|

  config.vm.define "default",primary: true do |master|
    config.vm.network "private_network", ip: "192.168.21.100"
    config.vm.network "forwarded_port", id: "ssh", host: 2222, guest: 22
    config.vm.network "forwarded_port", id: "nginx", host: 80, guest: 80
    config.vm.boot_timeout = 1440
  end

  config.vm.provider "docker" do |d, override|
    d.build_dir = "."
    d.remains_running = true
    d.has_ssh = true
  end
end
