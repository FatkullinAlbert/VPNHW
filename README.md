# VPNHW
Домашнее задание на тему "Мосты, туннели, VPN"
Задание:
1)Настроить VPN между двумя ВМ в tun/tap режимах, замерить скорость в туннелях, сделать вывод об отличающихся показателях
2)Поднять RAS на базе OpenVPN с клиентскими сертификатами, подключиться с локальной машины на ВМ
Для начала скачаем иснтументы для выполнения ДЗ: Ansible, VirtualBox, Vagrant.
Устновка Ansible:
apt install software-properties-common
$ sudo add-apt-repository --yes --update ppa:ansible/ansible
$ sudo apt install ansible
Устновка VirtualBox:
apt install virtualbox
Устновка Vagrant:
wget -O - https://apt.releases.hashicorp.com/gpg | sudo gpg --dearmor -o /usr/share/keyrings/hashicorp-archive-keyring.gpg
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] https://apt.releases.hashicorp.com $(grep -oP '(?<=UBUNTU_CODENAME=).*' /etc/os-release || lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/hashicorp.list
sudo apt update && sudo apt install vagrant
После установки создаём директорию для работы
Пишем Vagrantfile, скрипты в дирректории и запускаем их
Если всё запустилось - проверяем.
После успешного развёртывания результаты замеров iperf3 будут доступны на клиенте в /tmp/iperf3_tun.log и /tmp/iperf3_tap.log.
Для подключения к RAS скопируйте содержимое /vagrant/ras_client/ на хост и выполните sudo openvpn --config client.ovpn.
Домашнее задание выполненено!
