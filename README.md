# MyVagrantEnv

Just a vagrantfile to deploy an environment based on Debian 10 (Buster).

This vagrantfile also install docker and ansible with latest version.

## How to use it

You can use this vagrantfile with my Dockerfile that create a container with nginx that you can find here : https://github.com/Thomson33/MyDockerStarter

0. Install Vagrant :-)
1. Clone this repo
2. (Optional) Clone the Dockerfile repo
3. With you favorite CMD, go to this repo (for me : `cd /Users/Antoine/Desktop/MyVagrantEnv`)
4. Init Vagrant : `vagrant init`
5. Start the VM : `vagrant up`
6. Have fun !

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