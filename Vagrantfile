Vagrant.configure("2") do |config|
  config.vm.box = "bento/rockylinux-9"
  config.vm.synced_folder ".", "/vagrant", mount_options: ["dmode=755", "fmode=644"]

  machines = {
    "control" => "192.168.56.10",
    "app1"    => "192.168.56.11",
    "app2"    => "192.168.56.12",
  }

  machines.each do |name, ip|
    config.vm.define name do |node|
      node.vm.hostname = name
      node.vm.network "private_network", ip: ip
      node.vm.provider "virtualbox" do |vb|
        vb.memory = (name == "control") ? 2048 : 1536
        vb.cpus = 1
      end
    end
  end
end