### how to use
  * flash a sd-card with raspbian/jessie
  * plugin the sd-card in your raspberry
  * bring your raspberry up and in a cable based lan
  * execute `nmap -sn 192.168.1.1/24` (replace CIDR Block with your own)
  * edit hosts.dist file and save it as hosts
    * you must for first run all founded IP's placed in the part like "setup"
  * login to your raspberrys an expand filesystem
    * default-user: `pi`
    * default-password: `raspberry`
    * `sudo raspi-config`
  * execute `ansible-playbook deploy-setup.yml -i hosts --ask-pass`
  * enter the raspians default passwort `raspberry`
  * move all hosts from part "setup" to part "raspberrys"

### tasks
- [x] create how to use
- [x] create playbook and role for inventory part "setup"
- [ ] create playbook and role for inventory part "raspberrys"
- [ ] create playbook and role for inventory part "nginx"
- [ ] create playbook and role for inventory part "database"
