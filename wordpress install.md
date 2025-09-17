---
tags:
status: test/1
---

### 🔥 Шаг 1: Установка Apache (httpd)


**Обновите систему (обязательно!):**
```bash
sudo pacman -Syu
```
**Установите Apache**:
```bash
sudo pacman -S apache
```
**Запустите и добавьте в автозагрузку**:
```bash
sudo systemctl enable --now httpd
```
4. **Проверьте работу**:  Откройте в браузере:
```bash
http://localhost
```
→ Должна появиться страница _"It works!"_ (стандартная заглушка Apache).
- ### 🔥 **Шаг 2: Установка MariaDB (MySQL)**

1. **Установите MariaDB**:
    
``` bash
sudo pacman -S mariadb
```
    
- **Инициализируйте базу данных**:
    
```bash
sudo mysql_install_db --user=mysql --basedir=/usr --datadir=/var/lib/mysql
sudo systemctl enable --now mariadb
```
    
- **Настройте безопасность**:
    
```bash
sudo mysql_secure_installation
```

- Задайте пароль для root-пользователя.
    
- Отвечайте `Y` (Yes) на все вопросы (удаление анонимных пользователей, отключение удаленного доступа root и т.д.).
- ### **Шаг 3: Установка PHP и модулей**

1. **Установите PHP и необходимые модули**:
```bash
sudo pacman -S php php-fpm php-gd 
```

Для поддержки MySQL/MariaDB в PHP 8.x+ в Arch Linux:

1. Драйвер MySQL теперь включён в основной пакет `php`
    
2. Дополнительно можно установить:
```bash
sudo pacman -S php-pdo
```

Проверь установленные модули:

```bash
php -m | grep -E 'mysql|pdo'
```
    
2. **Включите PHP-FPM** (для обработки PHP-скриптов):
    
```bash
sudo systemctl enable --now php-fpm
```
    
3. **Проверьте версию PHP**:
    
```bash
php -v
```

→ Убедитесь, что версия совпадает с той, что будет на Хостинге (например, PHP 8.1).

### 🔥 **Шаг 4: Настройка базы данных для WordPress**

1. **Зайдите в MariaDB**:
    
```bash
sudo mysql -u root -p
```
    
- **Создайте базу данных и пользователя**:
    wpuser - название бызы(типо так принято по умолчанию можно сменить)
```sql
CREATE DATABASE wordpress;
CREATE USER 'wpuser'@'localhost' IDENTIFIED BY 'ваш_надежный_пароль';
GRANT ALL PRIVILEGES ON wordpress.* TO 'wpuser'@'localhost';
FLUSH PRIVILEGES;
EXIT;
```
    `CREATE USER 'wpmaster'@'localhost' IDENTIFIED BY 'Wp2906200614352890';`
### 🔥 **Шаг 5: Установка WordPress**

1. **Скачайте WordPress**:
    
```
    bash
    

- wget https://wordpress.org/latest.tar.gz
```
    
- **Распакуйте в корневую папку Apache**:
    
```
    bash
    
- sudo tar -xzvf latest.tar.gz -C /srv/http/
```
    
- **Настройте права**:
    
```
    bash
    

sudo chown -R http:http /srv/http/wordpress
```
### 🔥 **Шаг 6: Настройка Apache для WordPress**

1. **Отредактируйте конфиг Apache**:  
    Откройте файл `/etc/httpd/conf/httpd.conf`:
    
```
    bash
    

- sudo nano /etc/httpd/conf/httpd.conf
```
    
- **Добавьте в конец файла**:
    
```apache
<VirtualHost *:80>
    ServerName localhost
    DocumentRoot "/srv/http/wordpress"
    <Directory "/srv/http/wordpress">
        Options FollowSymLinks
        AllowOverride All
        Require all granted
        DirectoryIndex index.php
        FallbackResource index.php
    </Directory>
</VirtualHost>
```
    
- **Включите модуль `mod_rewrite`** (для ЧПУ):  
    Найдите строку:
    
```
    apache
    

#LoadModule rewrite_module modules/mod_rewrite.so
```

Раскомментируйте её (удалите `#`):

```
apache

- LoadModule rewrite_module modules/mod_rewrite.so
```
    
- **Перезапустите Apache**:
    
```
    bash
    

sudo systemctl restart httpd
```

MariaDB [(none)]> CREATE USER 'wpmaster'@'localhost' IDENTIFIED BY 'WP2906200614352890';


![[Pasted image 20250730203614.png]]![[Pasted image 20250730203639.png]]