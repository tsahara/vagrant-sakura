# Vagrantfileの例(CentOS最新安定板を利用する場合)

```bash
Vagrant.configure("2") do |config|
  config.vm.box = "dummy"
  config.ssh.username = "root"

  config.vm.provider :sakura do |sakura, override|
    sakura.os_type = "centos"
    
    sakura.public_key_path        = File.expand_path("~/.ssh/id_rsa.pub")
    override.ssh.private_key_path = File.expand_path("~/.ssh/id_rsa")
  end
end
```