# Генерация нового приватного и публичного ключа для репозитория
* Открываем консоль Git bash и вставляем строку с измененным почтовым адресом и нажимаем ENTER
```ch
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
# Creates a new ssh key, using the provided email as a label
Generating public/private rsa key pair.
```
* Появится запись которая приведена ниже, это месторазположение по умолчинию ключа, жмем ENTER
```ch
Enter a file in which to save the key (/Users/you/.ssh/id_rsa): [Press enter]
```
* Далее он выдаст сообщение, для того чтоб ввести пароль который вы указали при регистрации аккаунта на https://github.com/
```ch
Enter passphrase (empty for no passphrase): [Type a passphrase]
Enter same passphrase again: [Type passphrase again]
```
*Больше информации https://help.github.com/articles/generating-an-ssh-key/*

## Добавить SSH key в ssh-agent
* Добавить в Git Bash
```ch
# start the ssh-agent in the background
eval "$(ssh-agent -s)"
Agent pid 59566
```
###### Добавить если используете не только Git Bash но и другие консольные программы
```ch
# start the ssh-agent in the background
eval $(ssh-agent -s)
Agent pid 59566
```
* Добавить ключ в ssh-agent
```ch
ssh-add ~/.ssh/id_rsa
```
### НЕЗАБУДЬТЕ публичный ключь добавить на сайт

*Больше информации https://help.github.com/articles/generating-an-ssh-key/*

#### Для проверки выполните команду
```ch
ssh -T git@github.com
# Attempts to ssh to GitHub
```
В ответ вы получите приветствие
```ch
Hi username! You've successfully authenticated, but GitHub does not
provide shell access.
```
*больше информации https://help.github.com/articles/testing-your-ssh-connection/*

#Adding keys to Heroku
*Добавление ключа уже сгенерированного на Heroku 
```
$heroku keys:add
Found existing public key: /Users/adam/.ssh/id_rsa.pub
Uploading SSH public key /Users/adam/.ssh/id_rsa.pub... done
```
* Если нужно удалить ключ
```
heroku keys:remove adam@workstation.local
```
* Проверка на то что он добавился на Heroku 
```
 heroku keys
=== joe@example.com Keys
ssh-dss AAAAB8NzaC...DVj3R4Ww== adam@workstation.local
```
* Проверка подключения соединения
```
 ssh -v git@heroku.com
```
*Больше информации можно найти тут https://devcenter.heroku.com/articles/keys*
