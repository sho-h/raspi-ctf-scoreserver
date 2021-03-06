# raspi-ctf-scoreserver

CTF Score Server deploy files for Raspberry Pi

## install

1. setup Raspberry Pi
2. disable GUI/disable auto login
3. change pi user password
4. add ssh config(like below)

  ```
  Host raspberrypi
  HostName 192.0.2.100
  User pi
  Port 9022
  ```

5. execute below commands

  ```
  $ bundle install

  (Debian/Ubuntu)
  $ sudo apt-get install ansible
  (Mac)
  $ brew install ansible
  ```

## setup

```
$ vi production # edit hostname(default: raspberrypi)
$ ansible-playbook -i production site.yml
```

## test

```
$ TARGET_HOST=raspberrypi rspec
($ TARGET_HOST=raspberrypi bundle exec rspec)
```

## access

- [ctf-scoreserver](https://github.com/yoggy/ctf-scoreserver): \<IP\>:4567
- [ctfd](https://github.com/isislab/CTFd.git): \<IP\>:4000
