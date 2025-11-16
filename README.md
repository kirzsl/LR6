# LR6

Лабораторная работа №6



\# Система контроля версий



\## Цель работы

Изучение базовых возможностей системы управления версиями, опыт работы с Git Api, опыт работы с локальным и удаленным репозиторием.



\## 1. Клон репозитория, настройка клиента git и добавление файла через интерфейс GitHub.

Для начала работы необходимо настроить клиент git (указать имя пользователя и электронную почту), 

а также клонировать личный удалённый репозиторий на компьютер.

Для клонирования репозитория необходимо использовать команду git clone, это действие отображено на следующем скриншоте.

!\[Демонстрация работы команды git clone](screenshots/clone\\ repository.jpg)



Настройка клиента git происходит при помощи команды git config (см. следующий скриншот).

!\[Ввод персональных данных](screenshots/my\\ personal\\ data.jpg)



При помощи интерфейса GitHub происходит создание файла, в котором указывается любой текст (например, added file by GitHub).



\## 2. Получение истории операций каждой из веток, просмотр изменений и выполнение слияния в ветку master.

Следующий шаг - слияние веток. Это важный этап, так как на нём может появиться проблема слияния файлов с одинаковых названием,

что необходимо исправить. Для начала происходит создание новой ветки с помощью git branch "название ветки", для перехода в неё используется

git checkout "название ветки". При изменении mergefile с помощью git status надо удостовериться, что изменения были внесены, после чего

следует коммит с понятным названием внесённых изменений.

!\[Изменение mergefile с побочной ветки](screenshots/change\\ mergefile\\ from\\ feature\\ branch.jpg)



Аналогичные действия необходимо произвести и в главной ветке, для этого осуществляется обратный переход при помощи той же команды.

!\[Изменение mergefile c главной ветки](screenshots/change\\ mergefile\\ from\\ master\\ branch.jpg)



В качестве убеждения и проверки в достоверности выполненных действий выполняется просмотр истории операций при помощи команды git log,

где в качестве параметра указывается oneline, позволяющий выводить информацию с новой строки.

!\[История операций веток](screenshots/history\\ from\\ feature\\ and\\ main\\ branch.jpg)



Именно на данном этапе происходит конфликт, который разрешается вручную путём удаления информации из побочной ветки, то есть

производится слияние в ветку master. Осуществляется проверка с помощью git status, после чего коммит и удаление ветки feature.

!\[Разрешение конфликта](screenshots/resolv\\ the\\ conflict.jpg)



\## 3. Применение изменений, их фиксация и откат.

Производится создание файла changes.txt, в котором добавлен какой-либо текст, осуществляется проверка выполнения и последующий коммит.

Все использованные команды уже были перечислены выше.

!\[Создание changes и anotherChanges](screenshots/commits\\ about\\ changes.jpg)



По условию задания происходит откат коммита.

!\[Откат коммита](screenshots/reset\\ second\\ changes.jpg)



\## 4. Лог команд



```bash

&nbsp;  1  git clone https://github.com/kirzsl/LR6.git

&nbsp;  2  cd LR6

&nbsp;  3  git config user.name "4414 Легконравов К.С."

&nbsp;  4  git config user.email "klegkonravov@mail.ru"

&nbsp;  5  git branch feature

&nbsp;  6  git checkout feature

&nbsp;  7  git status

&nbsp;  8  git add .

&nbsp;  9  git commit -m "change mergefile.txt from feature branch"

&nbsp;  10  git checkout master

&nbsp;  11  git status

&nbsp;  12  git status

&nbsp;  13  git add .

&nbsp;  14  git commit -m "changed mergefile.txt from master branch"

&nbsp;  15  git log --oneline

&nbsp;  16  git checkout feature

&nbsp;  17  git log --oneline

&nbsp;  18  git status

&nbsp;  19  git commit -m "Conflict was resolved manually"

&nbsp;  20  git branch -d feature

&nbsp;  21  git status

&nbsp;  22  git add .

&nbsp;  23  git commit -m "Create a changes.txt"

&nbsp;  24  git status

&nbsp;  25  git add .

&nbsp;  26  git commit -m "Create a anotherChanges.txt"

&nbsp;  27  git reset --hard HEAD~1

```



\## 5. История операций



```bash

git log --pretty=format:"%h | %ad | %an | %s" --date=short

017b008 | 2025-11-16 | 4414 Легконравов К.С. | Edited the second step, added history of branch operations. Started and filled third step, made two commits and did reset last of them.

be689aa | 2025-11-16 | 4414 Легконравов К.С. | Continue fill report, added second step (change mergefile from main and feature branch, resolv the conflict)

8d393ce | 2025-11-16 | 4414 Легконравов К.С. | added the screenshots folder and completed first step of report (clone repository, input personal data and add file by GitHub)

aaf7039 | 2025-11-15 | 4414 Легконравов К.С. | Create a changes.txt

b3efe87 | 2025-11-15 | 4414 Легконравов К.С. | Conflict was resolved manually

4e07116 | 2025-11-15 | 4414 Легконравов К.С. | changed mergefile.txt from master branch

5580560 | 2025-11-15 | 4414 Легконравов К.С. | change mergefile.txt from feature branch

4425e6f | 2025-11-15 | kirzsl | added the file by github

921f53b | 2020-11-21 | Kurtyanik | Обновление информации

c08a654 | 2020-11-21 | Kurtyanik | Файл создан пустым

3c6e913 | 2020-11-21 | Kurtyanik | Initial commit

```



