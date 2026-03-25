## IWNO4: Использование контейнеров как среды выполнения

### Цель работы
Данная лабораторная работа призвана напомнить основные команды ОС Debian/Ubuntu. Также она позволит познакомиться с Docker и его основными командами.

### Задание
Запустить контейнер Ubuntu, установить Web-сервер Apache и вывести в браузере страницу с текстом "Hello, World!".

#### **Шаг 1**
Перед выполнением работы, создаю репозиторий и клонирую себе на компьютер.

Выполняю первую команду для создания и запуска контейнера: 

```bash
docker run -ti -p 8000:80 --name containers04 ubuntu bash
```
![image1](./images/image1.png)

#### **Шаг 2**
Поочередно выполняю следующие команды: 

```bash
apt update
```
![image2](./images/image2.png)

```bash
apt install apache2 -y
```
![image3](./images/image3.png)

```bash
service apache2 start
```
![image4](./images/image4.png)

Открываю браузер и вижу стандартную страницу Apache.

![image5](./images/image5.png)

#### Шаг 4

Выполняю следующие команды: 
```bash
ls -l /var/www/html/
echo '<h1>Hello, World!</h1>' > /var/www/html/index.html
```
Обновляя страницу, вижу заголовок "Hello, World!"

![image6](./images/image6.png)

//ДОБАВИТЬ ЕЩЕ 

#### Шаг 5

Закрываю терминал, просматриваю список всех контейнеров командой `docker ps -a` и удаляем контейнер `docker rm containers04`

