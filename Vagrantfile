# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure('2') do |config|
  config.vm.box = "ubuntu/precise64"

  config.vm.provision "shell", inline: <<-SCRIPT
    apt-add-repository ppa:brightbox/ruby-ng -y
    apt-get update -y
    apt-get -y install ruby2.1 ruby2.1-dev ruby-switch
    ruby-switch --set ruby2.1
    gem install bundler --no-rdoc --no-ri
  SCRIPT

  config.vm.provision "shell",
    path: 'https://gist.githubusercontent.com/mikz/411dbbc2aad5f147f87b/raw/ffb23a9c46d3210ba4b6b1067effd674b99cacdc/travis.rb',
    args: '/vagrant'
end
