Vagrant.configure(2) do |config|

  config.vm.box = "ubuntu/xenial64"

  if !ENV['NO_USE_SFC_MIRROR']
    config.vm.box_url = "http://www.sfc.wide.ad.jp/~aky/cloudimg/xenial-server-cloudimg-amd64-vagrant.box"
  else
    config.vm.box_url = "https://cloud-images.ubuntu.com/xenial/current/xenial-server-cloudimg-amd64-vagrant.box"
  end

  config.vm.box_download_checksum = "d0fdac0be25cfa1c85a8087d546ec807addbaae41080df9cf7f05a0101b24d3e"
  config.vm.box_download_checksum_type = "sha256"

  config.vm.network "forwarded_port", guest: 80, host: 10080

  config.vm.provider "virtualbox" do |vm|
    vm.memory = 2048
    vm.cpus = 2
  end

  config.vm.provision "shell", inline: <<-SHELL
    echo "linking python to python3..."
    ln -sf /usr/bin/python{3,}
  SHELL

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "playbook.yml"
    ansible.vault_password_file = "vault_password"

    ansible.verbose = "v"
    ansible.compatibility_mode = "2.0"
  end
end
