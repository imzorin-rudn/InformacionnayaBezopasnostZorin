---
# Front matter
lang: ru-RU
title: "Отчёт по лабораторной работе №1"
subtitle: "дисциплина: Информационная безопасность"
author: "Зорин Илья Михайлович"

# Formatting
toc-title: "Содержание"
toc: true # Table of contents
toc_depth: 2
lof: true # List of figures
lot: true # List of tables
fontsize: 12pt
linestretch: 1.5
papersize: a4paper
documentclass: scrreprt
polyglossia-lang: russian
polyglossia-otherlangs: english
mainfont: PT Serif
romanfont: PT Serif
sansfont: PT Sans
monofont: PT Mono
mainfontoptions: Ligatures=TeX
romanfontoptions: Ligatures=TeX
sansfontoptions: Ligatures=TeX,Scale=MatchLowercase
monofontoptions: Scale=MatchLowercase
indent: true
pdf-engine: lualatex
header-includes:
  - \linepenalty=10 # the penalty added to the badness of each line within a paragraph (no associated penalty node) Increasing the value makes tex try to have fewer lines in the paragraph.
  - \interlinepenalty=0 # value of the penalty (node) added after each line of a paragraph.
  - \hyphenpenalty=50 # the penalty for line breaking at an automatically inserted hyphen
  - \exhyphenpenalty=50 # the penalty for line breaking at an explicit hyphen
  - \binoppenalty=700 # the penalty for breaking a line at a binary operator
  - \relpenalty=500 # the penalty for breaking a line at a relation
  - \clubpenalty=150 # extra penalty for breaking after first line of a paragraph
  - \widowpenalty=150 # extra penalty for breaking before last line of a paragraph
  - \displaywidowpenalty=50 # extra penalty for breaking before last line before a display math
  - \brokenpenalty=100 # extra penalty for page breaking after a hyphenated line
  - \predisplaypenalty=10000 # penalty for breaking before a display
  - \postdisplaypenalty=0 # penalty for breaking after a display
  - \floatingpenalty = 20000 # penalty for splitting an insertion (can only be split footnote in standard LaTeX)
  - \raggedbottom # or \flushbottom
  - \usepackage{float} # keep figures where there are in the text
  - \floatplacement{figure}{H} # keep figures where there are in the text
---

# Цель работы

- Приобретение практических навыков установки операционной системы на виртуальную машину, настройки минимально необходимых для дальнейшей работы сервисов.
- Изучить идеологию и применение средств контроля версий.
- Научиться оформлять отчёты с помощью легковесного языка разметки Markdown.

# Выполнение лабораторной работы

1. Создал именную папку и добавил туда образ вирутальной машины (рис. 1). 
![Рис. 1](images/1.png){ #fig:001 width=70% }

2. Изменил папку по умолчанию для мастоположения каталога виртуальной машины (рис. 2). 
![Рис. 2](images/2.png){ #fig:002 width=70% }

3. Настроил виртуальную машину перед запуском (рис. 3). 
![Рис. 3](images/3.png){ #fig:003 width=70% }

4. Установил ОС (рис. 4). 
![Рис. 4](images/4.png){ #fig:004 width=70% }

5. Подключился с помощью пользователя (рис. 5). 
![Рис. 5](images/5.png){ #fig:005 width=70% }

6. Обновил системные файлы (рис. 6). 
![Рис. 6](images/6.png){ #fig:006 width=70% }

# Выводы

- Приобрёл практические навыки установки операционной системы на виртуальную машину, настройки минимально необходимых для дальнейшей работы сервисов.
- Изучил идеологию и применение средств контроля версий.
- Научился оформлять отчёты с помощью легковесного языка разметки Markdown.

# Ответы на контрольные вопросы

1. Что такое системы контроля версий (VCS) и для решения каких задач они предназначаются?
- *Это - программное обеспечение для облегчения работы с изменяющейся информацией.*
2. Объясните следующие понятия VCS и их отношения:
- *хранилище - место, где система управления версиями хранит все документы вместе с историей их изменения и другой служебной информацией,*
- *commit - дерево и некая дополнительная информация,*
- *история - данные о версиях файла,*
- *рабочая копия - актулаьная версия файла.*
3. Что представляют собой и чем отличаются централизованные и децентрализованные VCS? Приведите примеры VCS каждого вида.
- *Централизованные VCS имеют модель клиент-сервер: один центральный репозиторий, с которым разработчики взаимодействуют по сети. В отличие от централизованной модели, децентрализованная модель может существовать несколько экземпляров репозитория, которые время от времени синхронизируются между собой.*
- *Пример централизованной VCS - SVN. Одна из самых распространенных систем контроля версий. Для децентрализованной модели примером является git.*
4. Опишите действия с VCS при единоличной работе с хранилищем.
- **
5. Опишите порядок работы с общим хранилищем VCS.
- **
6. Каковы основные задачи, решаемые инструментальным средством git?
- *Системы контроля версий поддерживают возможность отслеживания и разрешения конфликтов, которые могут возникнуть при работе нескольких человек над одним файлом.*
- *Tакже они могут поддерживать работу с несколькими версиями одного файла, сохраняя общую историю изменений до точки ветвления версий и собственные истории изменений каждой ветви.*
7. Назовите и дайте краткую характеристику командам git.
- *С основными командами можно ознакомиться [тут](https://git-scm.com/book/ru/v2/Приложение-C%3A-Команды-Git-Основные-команды.md)*
8. Приведите примеры использования при работе с локальным и удалённым репозиториями.
- *При создании локального репозитория достаточно сначала сделаем предварительную конфигурацию, указав имя и email владельца репозитория:*
- *git config --global user.name "Имя Фамилия"*
- *git config --global user.email "work@mail"*
- *При работе с удалёнными репозиториями необходимо сначала зарегистрироваться на сервере, например, github.*
9. Что такое и зачем могут быть нужны ветви (branches)?
- *Ветвь — направление разработки, независимое от других. Ветвь представляет собой копию части (как правило, одного каталога) хранилища, в которую можно вносить свои изменения, не влияющие на другие ветви. Документы в разных ветвях имеют одинаковую историю до точки ветвления и разные — после неё.*
10. Как и зачем можно игнорировать некоторые файлы при commit?
- *Во время работы над проектом так или иначе могут создаваться файлы, которые не требуется добавлять в последствии в репозиторий. Например, временные файлы, создаваемые редакторами, или объектные файлы, создаваемые компиляторами. Можно прописать шаблоны игнорируемых при добавлении в репозиторий типов файлов в файл .gitignore с помощью сервисов.*