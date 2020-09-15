# Vagrant 

### For Seminar Course
---
![Vargtant](vagrant.png)

---

> ## Vargrant Box

---

### [Vargant Box Link ! ](https://app.vagrantup.com/boxes/search)

---

## Vargrant Commands

- Initialized Vagrant Box

```
vagrant init ubuntu/trusty64 || Image Name


```

- Up Running Image

```
vagrant up
```

---

- Connect To Vagrant Vm

  - check box status

  ```
  vagrant status
  vagrant global-status
  ```

  - shutdown and destory image

  ```
  vagrant halt
  vagrant destroy
  ```

  - start or reload box

  ```
  vagrant reload
  ```

  - Login Vagrant box in ssh then exit for logout

  ```
  vagrant ssh
  ```

- Folder Synchorization
  - in Vagrantfile
    ```
    config.vm.synced_folder "../. /vagrant"
    ```
- Networking
  - Port Forwording
    > less secure
    ```
     config.vm.network "forwarded_port", guest: 80, host: 8080
    ```
    > secure
    ```
    config.vm.network "forwarded_port", guest: 80, host: 8080, host_ip: "127.0.0.1"
    ```
    > example port forwording
    ***
    ```
    vagrant ssh
    sudo apt-get update
    sudo apt-get upgrade
    sudo apt-get install -y nginx
    curl localhost
    ```
    ***
  - Private networks
    > uncomment then go ip in the browser
  ```
   config.vm.network "private_network", ip: "192.168.33.10"
  ```
  - Public networks
- Providers
  - VirtualBox
  - Hyper-V
- Provisioners
  ```
  config.vm.provision "shell",path:"./nginx-shell.sh"
  ```
- Multi-Machine VagrantFile
