Vagrant (CentOS-7.0) Example
==========================================================

Для чего это нужно?
-------------------
Наверное, каждый сталкивался с проблемой разворачивания локального окружения для разработки.
С помощью Vagrant эта проблема решается достаточно просто. Под каждый проект создается своя виртуалка со своими необходимыми настройками. Если вдруг виртуалка сломалась по неизвестным никому причинам, просто соберите ее заново.

```bash
vagrant destroy
vagrant up
```
И продолжайте разработку.

Установка
-------------------

Устанавливаем [VirtualBox](https://www.virtualbox.org/wiki/Downloads) и [Vagrant](http://www.vagrantup.com/downloads)

Клонируем проект

```bash
git clone git@github.org:nikashitsa/vagrant-example.git
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

Подключение по ssh (логин: vagrant, пароль: vagrant)

```bash
vagrant ssh
```

Все команды смотреть [тут](https://docs.vagrantup.com/v2/cli/index.html)

XDEBUG (для PHP девелоперов)
-------------------

Чтобы заюзать Xdebug нужно:
1. Установите плагин, который будет добавлять специальную куку в ваши запросы к серверу. Типа вот [этого] (https://chrome.google.com/webstore/detail/xdebug-helper/eadndfjplgieldjbigjakmdgkmoaaaoc). 
2. Включить в PphStorm прослушку "Start Listening For PHP Debug Connections".
3. Поставить брэйкпойнт.
4. Перезагрузить страницу в браузере.

Чтобы заюзать Xdebug для выполнения CLI скрипта нужно:
1. Зайти в Vagrant по ssh `vagrant ssh`
2. Выполнить команду `xdebug_console`
