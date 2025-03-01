# git
Для початку роботи з Git потрібно встановити Git на свій комп'ютер. Git можна встановити з офіційного сайту Git: https://git-scm.com/downloads

Після встановлення Git на комп'ютер, можна розпочати роботу з Git. Ось кілька кроків, які можна виконати для початку роботи з Git:

1. Створіть репозиторій Git для свого проекту. Репозиторій Git зберігає всі файли проекту та його історію змін.
1. Ініціалізуйте репозиторій Git за допомогою команди "git init". Ця команда створює новий локальний репозиторій Git на вашому комп'ютері.
1. Додайте файли до репозиторію Git за допомогою команди "git add". Ця команда додає файли до індексу Git, щоб вони були готові до збереження.
1. Збережіть зміни до репозиторію Git за допомогою команди "git commit". Ця команда зберігає зміни до історії репозиторію Git.
1. Створіть віддалений репозиторій Git на хостинг-сервісі, наприклад, GitHub або GitLab.
1. Завантажте локальний репозиторій Git на віддалений репозиторій Git за допомогою команди "git push". Ця команда завантажує ваші зміни на віддалений репозиторій Git.

Після цих кроків ваш проект буде збережено в Git і ви зможете використовувати Git для керування змінами і спільної роботи з іншими розробниками.

## Збереження змін до репозиторію Git

Після того, як ви додали файли до індексу Git за допомогою команди "git add", необхідно зберегти зміни до історії репозиторію Git. Це можна зробити за допомогою команди "git commit". Наприклад, якщо ви хочете зберегти зміни у файлі "index.html", ви можете використати таку команду:
```sh
git commit -m "Added new content to index.html"
```
Ця команда зберігає зміни до історії репозиторію Git з повідомленням "Added new content to index.html". Це повідомлення має бути коротким описом ваших змін, щоб інші розробники могли легко зрозуміти, що було змінено.

## Створення віддаленого репозиторію Git

Віддалений репозиторій Git зазвичай зберігається на хостинг-сервісі, наприклад, на GitHub або GitLab. Щоб створити віддалений репозиторій Git, вам спочатку потрібно створити обліковий запис на хостинг-сервісі і створити новий репозиторій Git.

Якщо ви використовуєте GitHub, наприклад, ви можете створити новий репозиторій, натиснувши кнопку "New repository" на своїй домашній сторінці. Виберіть назву репозиторію та опис і натисніть кнопку "Create repository".

## Завантаження локального репозиторію на віддалений репозиторій Git

Щоб завантажити ваш локальний репозиторій Git на віддалений репозиторій Git, вам потрібно виконати команду "git push". Наприклад, якщо ви створили віддалений репозиторій Git на GitHub з назвою "my-project", ви можете використати таку команду:
```sh
git remote add origin https://github.com/your-username/my-project.git
git push -u origin master
```

## Робота з форком репозиторію
Для роботи з домашніми завданнями та створенням Pool requests вам необхідно буде створити форк цього учбового репозиторію.
Основні кроки для форку гіт з гілками:
1. Зайдіть на сторінку репозиторію на GitHub.
2. Натисніть кнопку "Fork" в верхньому правому куті сторінки, щоб скопіювати репозиторій до вашого акаунту.

**УВАГА !!!**
Якщо вам треба інші гілки, то приберіть галочку "Copy the `main` branch only"

![image](https://user-images.githubusercontent.com/10905223/232206733-4d13c518-ff14-4633-8e73-3bef0315dd77.png)

Якщо ви все зробили вірно, то у вас буде напис `forked from alex-pancho/aqa_py` та три гілки:

![image](https://user-images.githubusercontent.com/10905223/232207281-33202a10-7038-4c9a-9839-8931c212e246.png)


Далі ви виконуєте команду `git clone` для свого форку:
![image](https://user-images.githubusercontent.com/10905223/232208533-023437da-2745-4e42-b369-2e25b24dc439.png)

Переходите у папку з кодом `cd aqa_py`

Щоб побачити віддалені гіли виконайте команду `git brancw -r`

![image](https://user-images.githubusercontent.com/10905223/232208710-5f5c830d-1319-497b-bd0b-959a63b6c7a7.png)

Щоб переключитися на віддалену гілку after_lession виконайте команду `git checkout after_lession`

### Оновленя коду форку
Оскільки код у гілках `main` та `after_lession` періодично оновлюється, у вас може виникнути необхідність отримати новішу версію коду.

Для додавання upstream слід виконати такі дії:
1. Вказати учбовий репозиторій як upstream з яким може синхроніхуватися fork.
```sh
git remote add upstream https://github.com/alex-pancho/aqa_py.git
```
2. Виконати команду `git remote -v`, щоб переконатися, що upstream додався.

Для оновленя коду:
1. Перемикнутися на гілку, що треба оновити, напр. `git checkout after_lession`
2. Перевірити, що робоче дерево чисте.
3. Втягнути зміни: `git pull upstream after_lession`
4. Оновити свій код: `git push`

# УВАГА! для уникнення конфліктів всі домашні роботи виконуйте у власних гілках. Не робіть коміти у гілку `main`


# Конфлікти у версіях і вирішення конфліктів

Конфлікт може виникнути, коли два або більше розробники вносять зміни в один і той же файл або одну й ту ж гілку репозиторію Git. Наприклад, якщо один розробник вносить зміни в рядок 10 файла, а інший розробник вносить зміни в цей самий рядок, але на іншому робочому комп'ютері, під час спроби збереження змін одного з розробників може виникнути конфлікт.

Ось приклад вирішення конфлікту:

1. Спочатку вам потрібно отримати останню версію репозиторію, виконавши команду "git pull". Це дозволить оновити ваш робочий каталог з останніми змінами з віддаленого репозиторію Git.
```sh
git pull
```
1. Потім ви можете відкрити файл, в якому виник конфлікт, та переглянути його. Git додаватиме маркери конфлікту до файлу, що показує, де виникла проблема. Наприклад:
    ```
    <<<<<<< HEAD
    Ви змінили рядок 10 файла.
    =======
    Інший розробник змінив цей самий рядок.
    >>>>>>> 83a7c89
    ```
1. Далі вам потрібно вирішити конфлікт, змінивши код відповідно до вашого завдання. Ви можете видалити маркери конфлікту та зберегти файл.
1. Після того, як ви вирішили конфлікт, ви можете зберегти зміни до історії репозиторію Git за допомогою команди `git add .`
1. Після того, як ви додали файли до індексу Git, ви можете зберегти зміни до віддаленого репозиторію Git за допомогою команди "git commit".
    ```sh
    git commit -m "Resolved merge conflict in file_name"
    ```
1. Нарешті, ви можете завантажити свої зміни на віддалений репозиторій Git за допомогою команди `git push`

Ці кроки допоможуть вам вирішити конфлікт та зберегти зміни до репозиторію Git. ***Важливо виконувати ці кроки у зазначеній послідовності*** та переконатися, що зміни зберігаються вірно, перш ніж відправляти їх до віддаленого репозиторію.