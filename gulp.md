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
* gulp --tasks-simple показывает все основные зависимости
* gulp --tasks создает дерево зависимостей
* gulp --color - отображает все в цвете
* gulp <task> - запускает отдельно <task>
```

