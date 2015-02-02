Learning Locker Vagrant
=======================

Vagrant with an ansible-provisioned Learning Locker instance. It's a nice easy way to get a local version of Learning Locker running.

Setup
-----

1. Install Vagrant, Virtualbox, Git, and Ansible.

  Requires Vagrant 1.5+.

  See http://vagrant-up.com/downloads and https://www.virtualbox.org/wiki/Downloads for binary installers.

  If you're on Mac OS X, you probably want to install Homebrew (http://brew.sh/) because it makes installing Ansible easy, and because it is awesome anyway.

  ```
  ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
  ```

  Then you can install Ansible easily.

  ```
  brew update
  brew install ansible
  ```

  If you are on a debian-based Linux, you can install Ansible thusly:

  ```
  apt-get install python-software-properties -y
  add-apt-repository ppa:rquillo/ansible
  apt-get update
  apt-get install ansible -y
  ```

2. Clone this repo if you haven't already.

  ````
  git clone https://github.com/rael9/learninglocker-vagrant.git learninglocker-vagrant
  cd learninglocker-vagrant
  ````

3. Edit the vars.project.yml.

  Edit the vars.project.yml file to change the URL that you would like to use, if you want.

  You can also change the mongo user/pass if you want.

  By default, it uses a local private network using the 2.3.4.5 IP address. You should add this, and the URL configured, to your hosts file:

  ````
  # MacOS/Linux: /etc/hosts
  # Windows: C:\Windows\System32\drivers\etc\hosts
  2.3.4.5       local.learninglocker.org
  ````

  If you want to change the local IP address you can add this, editing the IP:

  ```
  vansible_ip: '2.3.4.5'
  ```

4. Bring up the virtual machine.

  ````
  vagrant up
  ````

  Vagrant will automatically install all the required packages, and then install Learning Locker.

5. Visit http://local.learninglocker.org/register (or whatever URL you configured).

  This will allow you to configure the first user.
