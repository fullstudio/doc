# Генерация нового приватного и публичного ключа для репозитория
№1 Открываем консоль Git bash и вставляем строку с измененным почтовым адресом и нажимаем ENTER
```ch
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
# Creates a new ssh key, using the provided email as a label
Generating public/private rsa key pair.
```
№2 Появится запись которая приведена ниже, это месторазположение по умолчинию ключа, жмем ENTER
```ch
Enter a file in which to save the key (/Users/you/.ssh/id_rsa): [Press enter]
```
№3 Далее он выдаст сообщение, для того чтоб ввести пароль который вы указали при регистрации аккаунта на https://github.com/
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
#
*Больше информации https://help.github.com/articles/generating-an-ssh-key/*
