VAGRANTFILE_API_VERSION = '2'

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box_url = 'https://cloud-images.ubuntu.com/vagrant/trusty/current/trusty-server-cloudimg-amd64-vagrant-disk1.box'

  config.vm.define 'web' do |web|
    web.vm.box = 'annict-web'
    web.vm.network 'private_network', ip: '192.168.33.10'
  end

  config.vm.define 'db' do |db|
    db.vm.box = 'annict-db'
    db.vm.network 'private_network', ip: '192.168.33.11'
  end

  # rootでSSH接続するためにVagrantが生成したauthorized_keysをrootでも使う
  config.vm.provision 'shell', inline: 'sudo cp -f /home/vagrant/.ssh/authorized_keys /root/.ssh'
end
