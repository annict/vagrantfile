VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box_url = "https://cloud-images.ubuntu.com/vagrant/trusty/current/trusty-server-cloudimg-amd64-vagrant-disk1.box"
  config.ssh.insert_key = false

  config.vm.define "app" do |web|
    web.vm.box = "annict-app"
    web.vm.network "private_network", ip: "192.168.33.11"
  end

  config.vm.define "marie" do |web|
    web.vm.box = "annict-marie"
    web.vm.network "private_network", ip: "192.168.33.20"
  end

  # rootでSSH接続するためにVagrantが生成したauthorized_keysをrootでも使う
  config.vm.provision "shell", inline: "sudo cp -f /home/vagrant/.ssh/authorized_keys /root/.ssh"
end
