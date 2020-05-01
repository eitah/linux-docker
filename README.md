# linux host with docker for playing


## pre install

```bash
brew cask install virtualbox
brew cask install vagrant
vagrant plugin install vagrant-vbguest
```

If you encounter errors when trying to install
vagrant and virtualbox using brew, google the error text
and you should find answers to common issues. Here are a
few of the ones that I hit.

If you get an error about a missing `/dev/vboxnetctl` it
relates to an issue with virtual box running on high sierra
or later mac operating system. I had to go into the security
preferences as described in the below stack overflow and restart.
https://stackoverflow.com/questions/18149546/vagrant-up-failed-dev-vboxnetctl-no-such-file-or-directory

## start

cd into the project repo first.

```bash
vagrant up
```

## login

```bash
$ vagrant ssh
Last login: Fri May  1 16:44:36 2020 from 10.0.2.2
vagrant@ubuntu-xenial:~$ docker ps
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS              PORTS               NAMES
```

## stop

```bash
vagrant halt
```
