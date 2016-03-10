# Gulp
##Скачиваем и устанавливаем
* Node https://nodejs.org/en/download/
* Git Bach https://git-scm.com/downloads
* Pyton https://www.python.org/downloads/ (иногда он нужен, лучше установить, не забудь поставит галочку для установки PATH)

##Установка Gulp
* https://github.com/gulpjs/gulp/blob/master/docs/getting-started.md (установка может быть продолжительной)
```ch
npm install --global gulp-cli - установить глобально Gulp (на машину)
npm install --save-dev gulp - установка Gulp в проект
npm install	- установить пакеты из package.json
npm install --force - установка принудительно пакеты
npm uninstall --global gulp-cli	- для глобального удаления Gulp
npm uninstall gulp	- для удаления Gulp из проекта
npm uninstall название модуля
npm update gulp	- обновления версий плагинов
npm cache clear	- очистка кеша npm
npm init - создаем фаил package.json с зависимостями
```
## Узнать версию Node, Gulp, NPM
```ch
node --version
gulp --version
npm --version
```
## Некоторые приятности
```ch
gulp --tasks-simple показывает все основные зависимости
gulp --tasks создает дерево зависимостей
gulp --color - отображает все в цвете
gulp <task> - запускает отдельно <task>
```
## Поиск устанавливаемых пакетов
* https://www.npmjs.com/

## Bower install
* документация http://bower.io/
* npm install -g bower - установка bower глобально
* bower install jquery - установка пакета jquery
* bower install git://github.com/user/package.git - установка с git репозитория
* bower install http://example.com/script.js - установка с URL сайта
* bower install - установка пакетов с bower.json если он уже есть
* bower install <package> --save - установка в bower.json dependencies
* bower install <package> --save-dev - bower.json devDependencies
* bower init - создаем фаил bower.json с зависимостями
* bower uninstall jquery - удаление пакета jquery
* bower cache clean - очистка кеша bower
* http://bower.io/docs/api/ - больше о командах 
```
Фаил .bowerrc хранит путь к bower папке где будут храниться установленные пакеты
{
 "directory" : "/bower_components"
}
В данном случае это корень проекта в папке bower_components.
```
# Поиск устанавливаемых пакетов
* http://bower.io/search

