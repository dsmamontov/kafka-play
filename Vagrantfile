Vagrant.configure("2") do |config|

  config.vm.define "kafka1" do |kafka1|
    kafka1.vm.box = "centos/8"
    kafka1.vm.hostname = "kafka1"
    kafka1.vm.network "private_network", ip: "10.0.4.15"
    kafka1.vm.network 'forwarded_port', guest: 9092, host: 9092
    kafka1.vm.network 'forwarded_port', guest: 2181, host: 2181

    kafka1.vm.provision "shell", inline: <<-SHELL
    	echo "ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQD1j1A0g7ebdghBy2UX+baArSx9jzYGTS5HwqyKEniRZ49wc/P20v5HLboCW+pzf3W8GYN3wAN2yTgxczydBO30bXAFhmAwsv/WI43kPRHLlgswSTV7KZcChqc//IsLi74LDY2kxpxcfQZG4uD3ZijsATbyZYO1atBcG5o2Ufobu0FQpSAh9F7eR0mtXzMa2XA2Mt8OlWkzmM3Oz/ORdAPqt9AMLIDk5jiCsBF8qEkLvDHtgU2MwWE6JywbdEYwQ+c6cB17LnJHaoNjOnQ/6z/YLV0TBnXeDO+SwW5dm36IPC9bulBqy4q/mo9cV3Ml3qOT41HsA2fRG8FxXpMum5aD OpenSSH-rsa-import-101417" >> /home/vagrant/.ssh/authorized_keys
      sudo yum update -y && sudo yum install -y vim docker
      sudo systemctl restart docker && sudo systemctl enable docker
  	SHELL
  end
end
