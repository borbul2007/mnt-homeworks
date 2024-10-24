# Домашнее задание к занятию 10 «Jenkins»

## Подготовка к выполнению

1. Создать два VM: для jenkins-master и jenkins-agent.
2. Установить Jenkins при помощи playbook.
3. Запустить и проверить работоспособность.
4. Сделать первоначальную настройку.

## Основная часть

1. Сделать Freestyle Job, который будет запускать `molecule test` из любого вашего репозитория с ролью.

![mnt-homeworks-09-04-task1](https://github.com/user-attachments/assets/5a400f5b-f64a-4356-b19c-8cce77e73f46)
![mnt-homeworks-09-04-task2](https://github.com/user-attachments/assets/04b17c89-7480-403e-b880-7d138350b090)

2. Сделать Declarative Pipeline Job, который будет запускать `molecule test` из любого вашего репозитория с ролью.

![ter-homeworks-02-task2-1](https://github.com/user-attachments/assets/08f6e456-785a-48ff-bc68-ec897d0beba7)
![ter-homeworks-02-task2-2](https://github.com/user-attachments/assets/b283d579-f7a9-4be8-b00e-a6ea757eac32)

3. Перенести Declarative Pipeline в репозиторий в файл `Jenkinsfile`.
4. Создать Multibranch Pipeline на запуск `Jenkinsfile` из репозитория.

![mnt-homeworks-09-04-task3-1](https://github.com/user-attachments/assets/4d89f38f-9b64-4eac-8158-6b3499f33f8d)
![mnt-homeworks-09-04-task3-2](https://github.com/user-attachments/assets/6c1e355e-f7d0-471b-9b4c-be8dbc177d1a)

6. Создать Scripted Pipeline, наполнить его скриптом из [pipeline](./pipeline).
7. Внести необходимые изменения, чтобы Pipeline запускал `ansible-playbook` без флагов `--check --diff`, если не установлен параметр при запуске джобы (prod_run = True). По умолчанию параметр имеет значение False и запускает прогон с флагами `--check --diff`.
8. Проверить работоспособность, исправить ошибки, исправленный Pipeline вложить в репозиторий в файл `ScriptedJenkinsfile`.
9. Отправить ссылку на репозиторий с ролью и Declarative Pipeline и Scripted Pipeline.
 
   [Jenkinsfiles](https://github.com/borbul2007/jenkins/tree/main)
   
11. Сопроводите процесс настройки скриншотами для каждого пункта задания!!

## Необязательная часть

1. Создать скрипт на groovy, который будет собирать все Job, завершившиеся хотя бы раз неуспешно. Добавить скрипт в репозиторий с решением и названием `AllJobFailure.groovy`.
2. Создать Scripted Pipeline так, чтобы он мог сначала запустить через Yandex Cloud CLI необходимое количество инстансов, прописать их в инвентори плейбука и после этого запускать плейбук. Мы должны при нажатии кнопки получить готовую к использованию систему.

---

### Как оформить решение задания

Выполненное домашнее задание пришлите в виде ссылки на .md-файл в вашем репозитории.

---
