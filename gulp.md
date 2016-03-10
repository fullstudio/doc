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
npm uninstall --global gulp-cli	- для глобального удаления Gulp
npm uninstall gulp	- для удаления Gulp из проекта
npm cache clear	- очистка кеша npm
npm init - создаем фаил package.json с зависимостями
```
## Установка и удаление пакетов package.json
```ch
npm install	- установить все пакеты из package.json
npm install <package> название модуля --save - установка пакета в проект package.json dependencies
npm install <package> название модуля --save-dev - установка пакета в проект package.json devDependencies
npm install --force - установка принудительно пакеты
npm uninstall название модуля <package> - удаление пакета
npm update название модуля	- обновления версий пакетов
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
