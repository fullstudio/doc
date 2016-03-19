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
npm install	- устанавливает все пакеты, перечисленные в package.json
npm install <package> название модуля --save - устанавливает <package> и вносит запись о нем в package.json в секцию dependencies
npm install <package> название модуля --save-dev - устанавливает <package> и вносит запись о нем в package.json в секцию devDependencies
npm install --force - установка принудительно пакеты
npm uninstall название модуля <package> - удаление пакета
npm update название модуля	- обновления версий пакетов
npm install <package>@1.5.0 - если нужно устонавить модуль определенной версии
```
Варианты с --save и --save-dev сделают запись в package.json только, если он уже существует.

*install	i
*uninstall	r
*config		c
*update		up
*list		ls
*--save		-S
*--save-dev	-D

```
npm install express --save cовершенно то же самое npm i express -S
```

## Выведет список всех возможных настроек
```
npm config ls -l
```
## Бывает полезно сделать прежде чем делать update
```
npm outdated
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
