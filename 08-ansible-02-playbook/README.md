# Домашнее задание к занятию 2 «Работа с Playbook»

## Подготовка к выполнению

1. * Необязательно. Изучите, что такое [ClickHouse](https://www.youtube.com/watch?v=fjTNS2zkeBs) и [Vector](https://www.youtube.com/watch?v=CgEhyffisLY).
2. Создайте свой публичный репозиторий на GitHub с произвольным именем или используйте старый.
3. Скачайте [Playbook](./playbook/) из репозитория с домашним заданием и перенесите его в свой репозиторий.
4. Подготовьте хосты в соответствии с группами из предподготовленного playbook.

## Основная часть

1. Подготовьте свой inventory-файл `prod.yml`.
2. Допишите playbook: нужно сделать ещё один play, который устанавливает и настраивает [vector](https://vector.dev). Конфигурация vector должна деплоиться через template файл jinja2. От вас не требуется использовать все возможности шаблонизатора, просто вставьте стандартный конфиг в template файл. Информация по шаблонам по [ссылке](https://www.dmosk.ru/instruktions.php?object=ansible-nginx-install). не забудьте сделать handler на перезапуск vector в случае изменения конфигурации!
3. При создании tasks рекомендую использовать модули: `get_url`, `template`, `unarchive`, `file`.
4. Tasks должны: скачать дистрибутив нужной версии, выполнить распаковку в выбранную директорию, установить vector.
5. Запустите `ansible-lint site.yml` и исправьте ошибки, если они есть.

![mnt-homeworks-02-task5-1](https://github.com/user-attachments/assets/12256908-9944-4928-8550-a60887a37d59)

![mnt-homeworks-02-task5](https://github.com/user-attachments/assets/1b553382-4184-472a-ab9b-fe59096ec37d)
  
6. Попробуйте запустить playbook на этом окружении с флагом `--check`.

![mnt-homeworks-02-task6](https://github.com/user-attachments/assets/a9125140-21a2-4dfb-a545-bf7a90d5b237)

7. Запустите playbook на `prod.yml` окружении с флагом `--diff`. Убедитесь, что изменения на системе произведены.

![mnt-homeworks-02-task7-1](https://github.com/user-attachments/assets/af0c5edf-d6d2-4ce4-9a1a-5988a587de44)

![mnt-homeworks-02-task7-2](https://github.com/user-attachments/assets/cd16a777-3fdd-4973-a0b3-c0d1e86eb0ca)

8. Повторно запустите playbook с флагом `--diff` и убедитесь, что playbook идемпотентен.

![mnt-homeworks-02-task7-3](https://github.com/user-attachments/assets/e04b9fca-c29e-43d0-ae75-ecff4c05e9d2)

9. Подготовьте README.md-файл по своему playbook. В нём должно быть описано: что делает playbook, какие у него есть параметры и теги. Пример качественной документации ansible playbook по [ссылке](https://github.com/opensearch-project/ansible-playbook). Так же приложите скриншоты выполнения заданий №5-8
10. Готовый playbook выложите в свой репозиторий, поставьте тег `08-ansible-02-playbook` на фиксирующий коммит, в ответ предоставьте ссылку на него.

---

### Как оформить решение задания

Выполненное домашнее задание пришлите в виде ссылки на .md-файл в вашем репозитории.

---
