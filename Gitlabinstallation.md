### GITLAB INSTALLATION IN SERVER
-----------------------------------------

* This is the best document for installation of GITLAB-CE 
  
  ![REFER]https://computingforgeeks.com/how-to-install-gitlab-ce-on-ubuntu-linux/

  ![refer]https://chat.openai.com/share/e8781988-44ae-4859-99b1-f23625d9efc6
  
  * Git installation steps
   ```
  sudo apt update
  sudo apt upgrade -y
  sudo apt install -y ca-certificates curl openssh-server tzdata
  sudo apt update
  sudo apt install curl debian-archive-keyring lsb-release ca-certificates apt-transport-https software-properties-common -y
  curl -sS https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.deb.sh | sudo bash
  cat /etc/apt/sources.list.d/gitlab_gitlab-ce.list
  sudo apt update
  sudo apt install gitlab-ce
  sudo vim /etc/gitlab/gitlab.rb
  sudo gitlab-ctl reconfigure
  sudo gitlab-ctl status
  cat /etc/gitlab/initial_root_password

   ```
  * Gitlab version downgrade commands
    ```
    sudo gitlab-ctl stop puma
    sudo gitlab-ctl stop sidekiq
    sudo dpkg -r gitlab-ce
    sudo apt-cache madison gitlab-ce
    sudo apt install gitlab-ce=16.0.1-ce.0
    sudo gitlab-ctl reconfigure

    ```

  * Gitlab version upgrade
    ```
    apt-get update
    apt-get install gitlab-ce=16.2.4-ce.0
    gitlab-ctl reconfigure
    gitlab-ctl restart
    ```

  * Gitlab server backup restore path command
    ```
    sudo /var/opt/gitlab/backups
    sudo gitlab-rake gitlab:backup:restore BACKUP=
    ```
  
  * Gitlab to edit nano configure file & see the version 
    ```
    sudo nano /etc/gitlab/gitlab.rb
    sudo gitlab-rake gitlab:env:info
    ```

  
  * Gitlab when see the 500 error 
   ```
   sudo gitlab-ctl tail
   sudo gitlab rm /var/opt/gitlab/redis/dump.rdb
   ```