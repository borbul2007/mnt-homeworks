# Домашнее задание к занятию 5 «Тестирование roles»

## Подготовка к выполнению

1. Установите molecule и его драйвера: `pip3 install "molecule molecule_docker molecule_podman`.
2. Выполните `docker pull aragast/netology:latest` —  это образ с podman, tox и несколькими пайтонами (3.7 и 3.9) внутри.

## Основная часть

Ваша цель — настроить тестирование ваших ролей. 

Задача — сделать сценарии тестирования для vector. 

Ожидаемый результат — все сценарии успешно проходят тестирование ролей.

### Molecule

1. Запустите  `molecule test -s ubuntu_xenial` (или с любым другим сценарием, не имеет значения) внутри корневой директории clickhouse-role, посмотрите на вывод команды. Данная команда может отработать с ошибками или не отработать вовсе, это нормально. Наша цель - посмотреть как другие в реальном мире используют молекулу И из чего может состоять сценарий тестирования.
2. Перейдите в каталог с ролью vector-role и создайте сценарий тестирования по умолчанию при помощи `molecule init scenario --driver-name docker`.
3. Добавьте несколько разных дистрибутивов (oraclelinux:8, ubuntu:latest) для инстансов и протестируйте роль, исправьте найденные ошибки, если они есть.
4. Добавьте несколько assert в verify.yml-файл для  проверки работоспособности vector-role (проверка, что конфиг валидный, проверка успешности запуска и др.). 
5. Запустите тестирование роли повторно и проверьте, что оно прошло успешно.
5. Добавьте новый тег на коммит с рабочим сценарием в соответствии с семантическим версионированием.

![mnt-homeworks-05-task1-1](https://github.com/user-attachments/assets/c10b1730-bdd6-48f8-b9c2-babfe62e0631)

![mnt-homeworks-05-task1-2](https://github.com/user-attachments/assets/5d0aeef1-9863-4b11-92d3-025a9c84f138)

![mnt-homeworks-05-task1-3](https://github.com/user-attachments/assets/f9f4ac61-2cd5-4820-b4f6-853eceb0577a)

![mnt-homeworks-05-task1-4](https://github.com/user-attachments/assets/0ae457b7-a2d3-495f-afb7-94e59cb76c99)

![mnt-homeworks-05-task1-5](https://github.com/user-attachments/assets/60786459-4495-4c52-915c-e2ab57988f73)

### Tox

1. Добавьте в директорию с vector-role файлы из [директории](./example).
2. Запустите `docker run --privileged=True -v <path_to_repo>:/opt/vector-role -w /opt/vector-role -it aragast/netology:latest /bin/bash`, где path_to_repo — путь до корня репозитория с vector-role на вашей файловой системе.
3. Внутри контейнера выполните команду `tox`, посмотрите на вывод.
5. Создайте облегчённый сценарий для `molecule` с драйвером `molecule_podman`. Проверьте его на исполнимость.
6. Пропишите правильную команду в `tox.ini`, чтобы запускался облегчённый сценарий.
8. Запустите команду `tox`. Убедитесь, что всё отработало успешно.
9. Добавьте новый тег на коммит с рабочим сценарием в соответствии с семантическим версионированием.

![mnt-homeworks-05-task2-1](https://github.com/user-attachments/assets/c0aaa708-dd05-4413-b999-ccd03e785d5d)
![mnt-homeworks-05-task2-2](https://github.com/user-attachments/assets/0503a06a-098c-4adf-af84-27fb9066867e)
![mnt-homeworks-05-task2-3](https://github.com/user-attachments/assets/ccf0f777-971c-42df-bf09-a6d09ebec044)
![mnt-homeworks-05-task2-4](https://github.com/user-attachments/assets/913d8887-70b5-430f-86ba-077dae271ea2)
![mnt-homeworks-05-task2-5](https://github.com/user-attachments/assets/f0c659df-4eac-481a-9c23-fd23b7959fa7)
![mnt-homeworks-05-task2-6](https://github.com/user-attachments/assets/9163e017-f861-4eb6-944d-5082571335ec)
![mnt-homeworks-05-task2-7](https://github.com/user-attachments/assets/586f5fdc-7820-415b-ae4b-a1f63f0a6dd4)

После выполнения у вас должно получится два сценария molecule и один tox.ini файл в репозитории. Не забудьте указать в ответе теги решений Tox и Molecule заданий. В качестве решения пришлите ссылку на  ваш репозиторий и скриншоты этапов выполнения задания. 

## Необязательная часть

1. Проделайте схожие манипуляции для создания роли LightHouse.
2. Создайте сценарий внутри любой из своих ролей, который умеет поднимать весь стек при помощи всех ролей.
3. Убедитесь в работоспособности своего стека. Создайте отдельный verify.yml, который будет проверять работоспособность интеграции всех инструментов между ними.
4. Выложите свои roles в репозитории.

В качестве решения пришлите ссылки и скриншоты этапов выполнения задания.

---

### Как оформить решение задания

Выполненное домашнее задание пришлите в виде ссылки на .md-файл в вашем репозитории.
