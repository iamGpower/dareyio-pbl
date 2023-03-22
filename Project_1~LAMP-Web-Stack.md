# Lamp Stack Implementation

> update list of packages in package manager

```bash
sudo apt update
```

![dareyio_pbl_screen grabs](./attachments/Pasted_image_20230317092840.png)

## Install Apache Web server using the package manager

---

```shell
sudo apt install apache2
```

![dareyio_pbl_screen grabs](./attachments/Pasted_image_20230317093249.png)

> verify Apache is running as a service

```shell
sudo systemctl status apache2
```

![dareyio_pbl_screen grabs](./attachments/Pasted_image_20230317093640.png)

> instance firewall configured to allow `tcp traffic` on `port 80`

- this firewall configuration allow incoming traffic from the internet to our web server listening on `port 80`

![dareyio_pbl_screen grabs](./attachments/Pasted_image_20230317094252.png)

> using the `curl` command to test connection to our web server

```shell
curl http://localhost:80
```

![dareyio_pbl_screen grabs](./attachments/Pasted_image_20230317094928.png)

> using the browser to test connection to our web server

![dareyio_pbl_screen grabs](./attachments/Pasted_image_20230317095314.png)

## Install MYSQL Database Server

---

```shell
sudo apt install mysql-server
```

![dareyio_pbl_screen grabs](./attachments/Pasted_image_20230317100511.png)

> connection to MYSQL server as `root`

![dareyio_pbl_screen grabs](./attachments/Pasted_image_20230317100804.png)

> create a root password for mysql using `ALTER USER 'root'@'localhost' IDENTIFITED WITH mysql_native_password BY '<my password>'` and `exit`

![dareyio_pbl_screen grabs](./attachments/Pasted_image_20230317152957.png)

> improving MYSQL security

![dareyio_pbl_screen grabs](./attachments/Pasted_image_20230317101804.png)

> Testing MYSQL with root password

![dareyio_pbl_screen grabs](./attachments/Pasted_image_20230317153334.png)

## Install PHP

---

> installing PHP and some required libraries / dependencies to enable interaction between Apache web server and MySQL

```shell
sudo apt install php libapache2-mod-php php-mysql
```

![dareyio_pbl_screen grabs](./attachments/Pasted_image_20230317102413.png)

> confirm PHP successful installation

![dareyio_pbl_screen grabs](./attachments/Pasted_image_20230317102552.png)

## Create a virtual host for our website using Apache

---

> create a directory for `projectlamp` using the command

```shell
sudo mkdir /var/www/projectlamp
```

![dareyio_pbl_screen grabs](./attachments/Pasted_image_20230317121952.png)

> also change ownership `(user and group)` from root of the directory to our current user `iamgp`

![dareyio_pbl_screen grabs](./attachments/Pasted_image_20230317122344.png)

> create a new config file with the following configurations for Apache's `sites-available` directory using vi text editor

 ``` shell
sudo vi /etc/apache2/site-available/projectlamp.conf
 ```

![dareyio_pbl_screen grabs](./attachments/Pasted_image_20230317124309.png)

![dareyio_pbl_screen grabs](./attachments/Pasted_image_20230317124119.png)

> enabling the new virtual host using

``` shell
sudo a2ensite projectlamp
```

![dareyio_pbl_screen grabs](./attachments/Pasted_image_20230317124640.png)

> to disable the default website that comes with Apache, use

``` shell
sudo a2dissite 000-default
```

![dareyio_pbl_screen grabs](./attachments/Pasted_image_20230317125134.png)

> testing your configuration is also important to avoid syntax error, using

 ``` shell
 sudo apache2ctl configtest
 ```

![dareyio_pbl_screen grabs](./attachments/Pasted_image_20230317125343.png)

> finally, reload Apache to make changes take effect using 

``` shell
sudo systemctl reload apache2
```

> testing setup page with a dummy `index.html` page at the document root `/var/www/projectlamp/`

![dareyio_pbl_screen grabs](./attachments/Pasted_image_20230317134349.png)

![dareyio_pbl_screen grabs](./attachments/Pasted_image_20230317134519.png)

## Enable PHP on the website
---

> a change in the priority of file extensions for Apache using `sudo vi /etc/apache2/mods-enabled/dir.conf` to make the web server serve PHP scripts as priority

![dareyio_pbl_screen grabs](./attachments/Pasted_image_20230317135803.png)

![dareyio_pbl_screen grabs](./attachments/Pasted_image_20230317135736.png)

> finally, reload Apache to make changes take effect using 

```shell
sudo systemctl reload apache2
```

> to test with a PHP script, `vi /var/www/projectlamp/index.php`

![dareyio_pbl_screen grabs](./attachments/Pasted_image_20230317140302.png)

![dareyio_pbl_screen grabs](./attachments/Pasted_image_20230317140328.png)
