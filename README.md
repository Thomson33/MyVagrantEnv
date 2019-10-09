# MyVagrantEnv

Just a vagrantfile to deploy an environment based on Debian 10 (Buster).

This vagrantfile also install docker and ansible with latest version.

## How to use it

You can use this vagrantfile with my Dockerfile that create a container with nginx that you can find here : https://github.com/Thomson33/MyDockerStarter

0. Install Vagrant :-) [https://www.vagrantup.com/downloads.html]
1. Clone this repo
2. With you favorite CMD, go to this repo (in my case : `cd /Users/Antoine/Desktop/MyVagrantEnv`)
3. (Optional) Clone the Dockerfile in this repo (in my case : `cd /Users/Antoine/Desktop/MyVagrantEnv && curl https://raw.githubusercontent.com/Thomson33/MyDockerStarter/master/Dockerfile > Dockerfile`)
4. Start the VM : `vagrant up`
5. Have fun !
6. (Optional) Start the docker's nginx container : 

    6.1. SSH the VM : `vagrant ssh`

    6.2. Go to the synced folder : `cd /vagrant`

    6.3. Build the container : `sudo docker build -t my-container .`
    
    6.4. Start the contianer : `sudo docker run -d -p 8080:80 -p 2222:22 my-container`

## Some tips

> **How to SSH to my Vagrant Box** ?

Just use : `vagrant ssh`

> **How to delete my Vagrant Box** ?

Just use : `vagrant destroy`

## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request
