---
# Front matter
lang: ru-RU
title: "Отчёт по лабораторной работе №2"
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

Получение практических навыков работы в консоли с атрибутами файлов, закрепление теоретических основ дискреционного разграничения доступа в современных системах с открытым кодом на базе ОС Linux.

# Выполнение лабораторной работы

**1. Рассмотрим подробнее уравнения**

1. В установленной при выполнении предыдущей лабораторной работы операционной системе создал учётную запись пользователя guest. Задал пароль для пользователя guest (рис. 1).
![Рис. 1.](images/1.png){ #fig:001 width=70% }

2. Вошёл в систему от имени пользователя guest (рис. 2).
![Рис. 2.](images/2.png){ #fig:002 width=70% }

3. Директория, в которой я нахожусь: /home/guest. Данная директория является домашней, что соответствует приглашению командной строки. Имя моего пользователя guest. С помощью команды id уточнил следующие данные: имя моего пользователя (guest), его группу (1001 - guest), группы, куда входит пользователь (1001 - guest). По сравнению с командой id команда groups показывает только название группы, в которую входит пользователь (рис. 3).
![Рис. 3.](images/3.png){ #fig:003 width=70% }

4. Просмотрел файл /etc/passwd. Нашёл в нём свою учётную запись: uid и gid пользователя - 1001. Данные соотвутствуют тем, что были получены в предыдущих шагах (рис. 4).
![Рис. 4.](images/4.png){ #fig:004 width=70% }

5. Определил существующие в системе директории. Обе директории имеют права на чтение, запись и исполнение только для владельца директорий. Посмотреть расширенные атрибуты удалось только для пользователя guest. Они отсутствуют. Создал в домашней директории поддиректорию dir1 (рис. 5).
![Рис. 5.](images/5.png){ #fig:005 width=70% }

6. Определил командами ls -l и lsattr, какие права доступа и расширенные атрибуты были выставлены на директорию dir1. Снял с директории dir1 все атрибуты и проверил с её помощью правильность выполнения команды ls -l (рис. 6).
![Рис. 6.](images/6.png){ #fig:006 width=70% }

7. Попытался создать в директории dir1 файл file1 (рис. 7).
![Рис. 7.](images/7.png){ #fig:007 width=70% }

8. Проверил, файл действительно не находится в директории dir1(рис. 8).
![Рис. 8.](images/8.png){ #fig:008 width=70% }

9. Заполнил таблицу «Установленные права и разрешённые действия».
![Рис. 9.](images/9.png){ #fig:008 width=70% }

10. На основании заполненной таблицы определил иные минимально необходимые права для выполнения операций внутри директории dir1.
![Рис. 10.](images/10.png){ #fig:008 width=70% }

# Выводы

Получил практические навыков работы в консоли с атрибутами файлов, закрепил теоретические основы дискреционного разграничения доступа в современных системах с открытым кодом на базе ОС Linux.
