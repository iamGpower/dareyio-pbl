#### update and upgrade of machine

```bash
sudo apt update -y && sudo apt upgrade -y
```

![dareyio_pbl_screen grabs](./attachments/Pasted_image_20230319103116.png)

```bash
sudo apt -y install curl dirmngr apt-transport-https lsb-release ca-certificates
```

#### ![dareyio_pbl_screen grabs](./attachments/Pasted_image_20230319103509.png)

```bash
curl -sL https://deb.nodesource.com/setup_12.x | sudo -E bash -

```

![dareyio_pbl_screen grabs](./attachments/Pasted_image_20230319113335.png)
![dareyio_pbl_screen grabs](./attachments/Pasted_image_20230319113545.png)

#### installing MongoDB

```bash
sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 0C49F3730359A14518585931BC711F9BA15703C6

```

```bash
echo "deb [ arch=amd64 ] https://repo.mongodb.org/apt/ubuntu trusty/mongodb-org/3.4 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-3.4.list

```

![dareyio_pbl_screen grabs](./attachments/Pasted_image_20230319120412.png)

```bash
sudo apt install -y mongodb

```

![dareyio_pbl_screen grabs](./attachments/Pasted_image_20230319120725.png)

#### start the mongo server

```bash
sudo systemctl start mongodb.service
```

![dareyio_pbl_screen grabs](./attachments/Pasted_image_20230319120834.png)
![dareyio_pbl_screen grabs](./attachments/Pasted_image_20230319121349.png)
![dareyio_pbl_screen grabs](./attachments/Pasted_image_20230319155154.png)

#### install other required dependencies

![dareyio_pbl_screen grabs](./attachments/Pasted_image_20230319155220.png)
![dareyio_pbl_screen grabs](./attachments/Pasted_image_20230319155425.png)

![dareyio_pbl_screen grabs](./attachments/Pasted_image_20230320043809.png)

#### app tested on port 3300

![dareyio_pbl_screen grabs](./attachments/Pasted_image_20230320043444.png)

#### app working on cli

![dareyio_pbl_screen grabs](./attachments/Pasted_image_20230320043706.png)

#### important point to note

#### The app needed `NodeJS version 14` and above to run due to some unsupported newer syntax

![dareyio_pbl_screen grabs](./attachments/Pasted_image_20230320044254.png)

#### There are some mongoose function that no longer support call back and hence the need to use `async await` promised based syntax

![dareyio_pbl_screen grabs](./attachments/Pasted_image_20230320044158.png)
