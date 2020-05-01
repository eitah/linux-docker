# linux host with docker for playing


## pre install

```
brew cask install virtualbox
brew cask install vagrant
vagrant plugin install vagrant-vbguest
```

## start

```
vagrant up
```

## login

```
$ vagrant ssh
Last login: Fri May  1 16:44:36 2020 from 10.0.2.2
vagrant@ubuntu-xenial:~$ docker ps
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS              PORTS               NAMES
```

## stop

```
vagrant halt
```

