########## Начинаем запись правил чтобы заблокировать основные эксплойты
#
# Блокируем любой скрипт пытающийся получить значение mosConfig через URL
RewriteCond %{QUERY_STRING} mosConfig_[a-zA-Z_]{1,21}(=|%3D) [OR]
# Блокируем любой скрипт пытающийся отправить любое дерьмо через base64_encode по URL
RewriteCond %{QUERY_STRING} base64_encode.*(.*) [OR]
# Блокируем любой скрипт который содержит тег < script> в URL
RewriteCond %{QUERY_STRING} (<|%3C).*script.*(>|%3E) [NC,OR]
# Блокируем любой скрипт, который пытается установить глобальную переменную PHP через URL
RewriteCond %{QUERY_STRING} GLOBALS(=|[|%[0-9A-Z]{0,2}) [OR]
# Блокируем любой скрипт пытающийся изменить _REQUEST переменную через URL
RewriteCond %{QUERY_STRING} _REQUEST(=|[|%[0-9A-Z]{0,2}) [OR]
# Блокируем любой скрипт, который пытается установить CONFIG_EXT (баг в com_extcal2)
RewriteCond %{QUERY_STRING} CONFIG_EXT([|%20|%5B).*= [NC,OR]
# Блокируем любой скрипт, который пытается установить sbp or sb_authorname через URL (баг simpleboard)
RewriteCond %{QUERY_STRING} sbp(=|%20|%3D) [OR]
RewriteCond %{QUERY_STRING} sb_authorname(=|%20|%3D)
# Отправляем все заблокированный запросы на главную с ошибкой 403 Forbidden!
RewriteRule ^(.*)$ index.php [F,L]
#
########## Заканчиваем запись правил чтобы заблокировать основные эксплойты


# вывод ошибок для отладки
php_flag  display_errors 1
php_flag  display_startup_errors 1
php_value  error_reporting “E_ALL & ~E_NOTICE” 

#Включение ошибок на время отладки
php_flag display_errors on

 
 # запрещает копирование файла htaccess
<Files .htaccess>
order allow,deny
deny from all
</Files>

#Перекодировка
 CharsetSourceEnc WINDOWS-1251

#PHP сжатие
php_value zlib.output_compression 16386


#Использование сжатия Gzip код будет сжимать follwing типов файлов: текстовых, HTML, XML, CSS, JS
# BEGIN GZIP
AddOutputFilterByType DEFLATE text/plain text/html text/xml text/css application/x-javascript application/javascript
# END GZIP

# Запрет выдачи листинга пустого каталога
Options -Indexes
 
 php_value sendmail_from root@beget.ru

 ServerSignature EMail
SetEnv SERVER_ADMIN mail@your-site.com 

#Разрешите поисковым системам доступ к изображениям
SetEnvIfNoCase user-Agent ^FrontPage [NC,OR]
SetEnvIfNoCase user-Agent ^Java.* [NC,OR]
SetEnvIfNoCase user-Agent ^Microsoft.URL [NC,OR]
SetEnvIfNoCase user-Agent ^MSFrontPage [NC,OR]
SetEnvIfNoCase user-Agent ^Offline.Explorer [NC,OR]
SetEnvIfNoCase user-Agent ^[Ww]eb[Bb]andit [NC,OR]
SetEnvIfNoCase user-Agent ^Zeus [NC]
Order Allow,Deny
Allow from all
Deny from env=bad_bot

#разрешает использовать изображения поисковикам
RewriteCond% {HTTP_REFERER}! ^ Http:// (. + \.)? MyDomain \. COM / [NC]
RewriteCond% {HTTP_REFERER}! ^ Http:// (. + \.)? Google \. (. +) / [NC]
RewriteCond% {HTTP_REFERER}! ^ Http:// (. + \.)? (. * \.)? Google \. (. +) / [NC]
RewriteCond% {HTTP_REFERER}! ^ Http:// (. + \.)? Бинг \. (. +) / [NC]
RewriteCond% {HTTP_REFERER}! ^ Http:// (. + \.)? (. * \.)? Бинг \. (. +) / [NC]
RewriteCond% {HTTP_REFERER}! ^ Http:// (. + \.)? Yahoo \. (. +) / [NC]
RewriteCond% {HTTP_REFERER}! ^ Http:// (. + \.)? (. * \.)? Yahoo \. (. +) / [NC]
RewriteCond% {HTTP_REFERER}! ^ $
RewriteRule * \ (JPE г |? GIF | PNG). $. / Transparent.gif [L]



#Разрешаем выполнение php внутри JavaScript
AddType application/x-httpd-php .js

AddHandler x-httpd-php5 .js

<filesmatch «\.(js|php)$»>

SetHandler application/x-httpd-php

</filesmatch>


php_flag short_open_tag On // включение короткого синтаксиса

#Block bad bots
SetEnvIfNoCase user-Agent ^FrontPage [NC,OR]
SetEnvIfNoCase user-Agent ^Java.* [NC,OR]
SetEnvIfNoCase user-Agent ^Microsoft.URL [NC,OR]
SetEnvIfNoCase user-Agent ^MSFrontPage [NC,OR]
SetEnvIfNoCase user-Agent ^Offline.Explorer [NC,OR]
SetEnvIfNoCase user-Agent ^[Ww]eb[Bb]andit [NC,OR]
SetEnvIfNoCase user-Agent ^Zeus [NC]
Order Allow,Deny
Allow from all
Deny from env=bad_bot

#для SEO
Options +FollowSymlinks
RewriteEngine On
RewriteBase /
RewriteCond %{REQUEST_FILENAME} !-f
RewriteCond %{REQUEST_FILENAME} !-d
RewriteRule ^([^?]*) index.php?_route_=$1 [L,QSA] 
 
