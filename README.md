Vagrant (CentOS-7.0) Example
==========================================================

Для чего это нужно?
-------------------
Наверное, каждый сталкивался с проблемой разворачивания локального окружения для разработки.
С помощью Vagrant эта проблема решается просто. Под каждый проект создается своя виртуалка со своими необходимыми настройками. Если вдруг виртуалка сломалась, просто соберите ее заново.

```
vagrant destroy
vagrant up
```
И продолжайте разработку.

В примере: виртуалка с CentOS-7.0, apache, mariadb, php, xdebug, composer, bash алиасы.

Установка
-------------------

Устанавливаем [VirtualBox](https://www.virtualbox.org/wiki/Downloads) и [Vagrant](http://www.vagrantup.com/downloads)

Клонируем проект

```
git clone git@github.com:nikashitsa/vagrant-example.git
```

Устанавливаем vagrant плагин (ускоряет повторное разворачивание в разы!)

```
vagrant plugin install vagrant-cachier
```

Врубаем vagrant

```
vagrant up
```

> Конфигом Vagrant является Vagrantfile из корня проекта.
> Для установки различных программ в данном примере используется `vagrant/setup.sh` скрипт. [Vagrant документация](https://docs.vagrantup.com/v2/).

Добавляем в файл `/etc/hosts` строчку

```
192.168.56.101	cent.loc
```

Готово! [http://cent.loc/](http://cent.loc/)

Vagrant
-------------------

Запуск

```
vagrant up
```

Сохранение

```
vagrant suspend
```

Удаление

```
vagrant destroy
```

Подключение по ssh (логин: vagrant, пароль: vagrant)

```
vagrant ssh
```

Все команды смотреть [тут](https://docs.vagrantup.com/v2/cli/index.html)

XDEBUG (для PHP девелоперов)
-------------------

Чтобы заюзать Xdebug нужно:

1. Установить плагин, который будет добавлять специальную куку в ваши запросы к серверу. Типа вот [этого] (https://chrome.google.com/webstore/detail/xdebug-helper/eadndfjplgieldjbigjakmdgkmoaaaoc). 
2. Включить в PhpStorm прослушку "Start Listening For PHP Debug Connections".
3. Поставить брэйкпойнт.
4. Перезагрузить страницу в браузере.

Xdebug для CLI .php скрипта:

1. Зайти в Vagrant по ssh `vagrant ssh`.
2. Выполнить команду `xdebug_console`.
3. Поставить брэйкпойнт.
4. Запустить скрипт.
