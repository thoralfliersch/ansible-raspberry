### how to use
  * flash a sd-card with raspbian/jessie
    * `sudo diskutil list`
    * `sudo diskutil unmountDisk /dev/disk1` replace /dev/disk1 with your volume
    * `sudo dd bs=1m if=Downloads/raspbian-jessie-lite.img | pv | sudo dd of=/dev/disk1` replace /dev/disk1 with your volume
  * plugin the sd-card in your raspberry
  * bring your raspberry up and in a cable based lan
  * execute `nmap -sn 192.168.1.1/24` (replace CIDR Block with your own)
  * edit hosts.dist file and save it as hosts
    * you must for first run all founded IP's placed in the part like "setup"
  * login to your raspberrys and expand filesystem
    * default-user: `pi`
    * default-password: `raspberry`
    * `sudo raspi-config`
    * reboot your raspberrys
  * execute `ansible-playbook deploy-setup.yml -i hosts --ask-pass`
  * enter the raspians default passwort `raspberry`
  * move all hosts from part "setup" to part "raspberrys"

### tasks
- [x] create how to use
- [x] create playbook and role for inventory part "setup"
  - [x] update apt cache
  - [x] upgrade system
  - [x] delete unused packages
  - [x] delete unused directorys in pi's homefolder
  - [x] add ssh key(s)
  - [x] autoremove and autoclean system
  - [x] install common packages
  - [x] set hostname
  - [x] set Timezone `(/etc/timezone)`
  - [x] set Keyboardlayout `(/etc/default/keyboard)`
  - [x] restart
- [ ] create playbook and role for inventory part "raspberrys"
- [x] create playbook and role for inventory part "nginx"
- [x] create playbook and role for inventory part "database"
- [ ] create playbook and role for update/upgrade all raspberrys
- [ ] create Makefile
- [ ] create playbook and role for inventory part "monitor"
  - this is my own project to monitor all my raspberrys
