# ERP-NEXT Installation Method
## Step 1: Install git
```bash
sudo apt install git -y
```
## Step 2: Install Python3.10
Frappe Bench and erpnext requires python3,10. Heres how to install it in Ubuntu 22
### Install Python3.10 - PPA Method
The first and easiest solution for Ubuntu users would be to import the [“deadsnakes”](https://launchpad.net/~deadsnakes) team Launchpad PPA. This will always contain the latest updates for Python and all extra packages that may be required.

First, install the prerequisite for adding custom PPAs.
```bash
sudo  apt  install software-properties-common -y
```
Second, add the **deadsnakes/ppa**  to your APT package source list with the following command.

```bash
sudo add-apt-repository ppa:deadsnakes/ppa -y
```

Once the repository has been imported, run an  **APT update**  to fresh your package manager to reflect the new imported PPA.
```bash
sudo apt update
```

You can now install Python 3.10 by executing the following code:

```bash
sudo apt install python3.10 -y
```

To verify the installation and Python 3.10 build version, perform the following.

```bash
python3.10 --version
```
**outcome**

```bash
Python 3.10.6
```
### Install Virtual Enviorment
```bash
sudo apt install python3.10-venv -y
```

## Step 3: Install PIP
```bash
sudo apt install python-pip -y
```
## Step 4: Install Redis Server
```bash
sudo apt install redis-server -y
```
## Step 5: Install MariaDB
**NOTE**
skip this cmd if you already used it above
```bash
sudo apt-get install software-properties-common
```
If you are on Ubuntu version older than 20.04, run this before installing MariaDB:
```bash
apt-key adv --recv-keys --keyserver hkp://keyserver.ubuntu.com:80 0xF1656F24C74CD1D8
add-apt-repository 'deb [arch=amd64,i386,ppc64el] http://ftp.ubuntu-tw.org/mirror/mariadb/repo/10.3/ubuntu xenial main'
```
### Start here
If you are on version Ubuntu 20.04, then MariaDB is available in default repo and you can directly run the below commands to install it:
```bash
apt-get update
apt-get install mariadb-server-10.6 -y
```
During this installation you'll be prompted to set the MySQL root password. If you are not prompted, you'll have to initialize the MySQL server setup yourself. You can do that by running the command:
```bash
sudo mysql_secure_installation
```

> Remember: only run it if you're not prompted the password during setup.

It would then ask for machines's password

> [sudo] password for [YOUR_MACHINE_NAME]:

Enter your machine's passowrd and proceed to then next step.
Answer the Questions as following:

> Switch to unix_socket authentication [Y/n] n  
Change the root password? [Y/n] y  
password: pass123 
re-enter new password: pass123  
Remove anonymous users? [Y/n] y  
Disallow root login remotely? [Y/n] y  
Remove test database and access to it? [Y/n] y  
Reload privilege tables now? [Y/n] y

And MariaDB Server is configured. Now for the client.

It is really important that you remember this password, since it'll be useful later on. You'll also need the MySQL database development files.

```bash
sudo apt-get install mariadb-client-10.6
```
Now, edit the MariaDB configuration file.

```bash
sudo nano /etc/mysql/my.cnf
```

And add this configuration

```hljs
[mysqld]
character-set-client-handshake = FALSE
character-set-server = utf8mb4
collation-server = utf8mb4_unicode_ci

[mysql]
default-character-set = utf8mb4
```

Now, just restart the mysql service and you are good to go.

```bash
service mysql restart
```


## Step 6: Install Node

I recommend installing node using  [nvm](https://github.com/creationix/nvm)

```bash
curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.11/install.sh | bash
```
**Note**
If you don't have "curl" you can install it, using 
```bash
sudo apt install curl
```
After nvm is installed, you may have to close your terminal and open another one. Now run the following command to install node.

Now find out the available version of Node.js to install. Use  `ls-remote`  option to list versions.

```
nvm ls-remote 
```

You will see a long list of available versions.

Output:

       ...
       ...
       v16.12.0
       v16.13.0   (LTS: Gallium)
       v16.13.1   (LTS: Gallium)
       v16.13.2   (LTS: Gallium)
       v16.14.0   (Latest LTS: Gallium)
        v17.0.0
        v17.0.1
        v17.1.0
        v17.2.0
        v17.3.0
        v17.3.1
        v17.4.0
        v17.5.0

Now install the node.js version you need to use for running the node.js application. Below command will install node.js  **16.14.0**  the LTS release on your system.

```
nvm install v16.17.1 
```

You can have also installed the latest version of Node.js.

```
nvm install v18.10.0
```

Repeat the above command with the different-2 node.js versions to install multiple versions of node.js on your system.

Verify the installation, by running:

```bash
node -v
# output
v14.17.2
```
Finally, install  `yarn`  using  `npm`

```bash
npm install -g yarn
```

## Step 7: Install wkhtmltopdf

```bash
sudo apt-get install xvfb libfontconfig wkhtmltopdf -y
```


## Step 8: Install Bench CLI [🔗](https://frappeframework.com/docs/v14/user/en/installation#install-bench-cli)

Install bench via pip3
```bash
sudo apt install python3-pip -y
```
```bash
sudo -H pip3 install frappe-bench
```
Confirm the bench installation by checking version

```bash
bench --version

# output
5.2.1
```
Actual CMD
```bash
bench init frappe-bench --frappe-branch version-14
```
break down, if you need to make a custom one
-   Create a new bench:
    ```bash
    $ bench init [bench-name]
    ```
-   Add a site under current bench:
    ```bash
    $ bench new-site [site-name]
    ```
    After the frappe-bench folder is created, change your directory to it and run this command

```bash
bench start
```

Congratulations, you have installed bench on to your system.

## Step 9:
Install git
```bash

```

## Step 10:
Install git
```bash

```

## Step 11:
Install git
```bash

```
