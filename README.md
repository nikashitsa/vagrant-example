Vagrant (CentOS-7.0) Example
==========================================================

Установка
-------------------

Устанавливаем [VirtualBox](https://www.virtualbox.org/wiki/Downloads) и [Vagrant](http://www.vagrantup.com/downloads)

Клонируем проект

```bash
git clone git@bitbucket.org:nikashitsa/vagrant-example.git
```

Устанавливаем vagrant плагин (ускоряет повторное разворачивание в разы!)

```bash
vagrant plugin install vagrant-cachier
```

Врубаем vagrant

```bash
vagrant up
```

Добавляем в файл `/etc/hosts` строчку

```text
192.168.56.101	cent.loc
```

Готово! [http://cent.loc/](http://cent.loc/)

Vagrant
-------------------

Запуск

```bash
vagrant up
```

Сохранение

```bash
vagrant suspend
```

Удаление

```bash
vagrant destroy
```

Подключение по ssh

```bash
vagrant ssh
```

Все команды смотреть [тут](https://docs.vagrantup.com/v2/cli/index.html)