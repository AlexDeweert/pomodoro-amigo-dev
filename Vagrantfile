#PomodoroAmigo development environment
#Virtual machine configuration
#Ruby for Vagrant

$postgres_script = <<-SCRIPT
sudo apt update
sudo apt -y install postgresql postgresql-contrib
SCRIPT

Vagrant.configure("2") do |config|
  config.vm.define "api" do |api|
    api.vm.box = "ubuntu/focal64"
    api.vm.network "forwarded_port", guest: 5000, host: 5000
    api.vm.network "private_network", ip: "10.0.0.10"
  end
  config.vm.define "postgres" do |postgres|
    postgres.vm.provision "shell", inline: $postgres_script
    postgres.vm.box = "ubuntu/focal64"
    postgres.vm.network "forwarded_port", guest: 5432, host: 5431
    postgres.vm.network "private_network", ip: "10.0.0.80"
  end
end
