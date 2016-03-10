# Bower
## Bower install
```
документация http://bower.io/
npm install -g bower - установка bower глобально
bower install jquery - установка пакета jquery
bower install git://github.com/user/package.git - установка с git репозитория
bower install http://example.com/script.js - установка с URL сайта
bower install - установка пакетов с bower.json если он уже есть
bower install <package> --save - установка в bower.json dependencies
bower install <package> --save-dev - bower.json devDependencies
bower init - создаем фаил bower.json с зависимостями
bower uninstall jquery - удаление пакета jquery
bower cache clean - очистка кеша bower
http://bower.io/docs/api/ - больше о командах
```
### Примечание
```
Фаил .bowerrc хранит путь к bower папке где будут храниться установленные пакеты
{
 "directory" : "/bower_components"
}
В данном случае это корень проекта в папке bower_components.
```
# Поиск устанавливаемых пакетов
* http://bower.io/search
