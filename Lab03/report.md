---
# Front matter
lang: ru-RU
title: "Отчёт по лабораторной работе №3"
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

Получение практических навыков работы в консоли с атрибутами файлов для групп пользователей.

# Выполнение лабораторной работы

1. В установленной операционной системе создал учётную запись пользователя guest. Задайте пароль для пользователя guest. Аналогично создал второго пользователя guest2. Добавил пользователя guest2 в группу guest (рис. 1).
![Рис. 1.](images/1.png){ #fig:001 width=70% }

2. Осуществил вход в систему от двух пользователей на двух разных консолях: guest на первой консоли и guest2 на второй консоли. Для обоих пользователей определил директорию,в которой нахожусь: /home/guest и /home/guest2, что соответствует приглашениям командной строки. Для пользователя guest: имя пользователя - guest, его группа 1001(guest), принадлежит к группе guest. Для пользователя guest2: имя пользователя - guest2, его группа 1002(guest2), принадлежит к группам guest и guest2.Вывод команды groups аналогичем выводам команд id -Gn и id -G (рис. 2-3).
![Рис. 2.](images/2.png){ #fig:002 width=70% }
![Рис. 3.](images/3.png){ #fig:003 width=70% }

3. Сравнил полученную информацию с содержимым файла /etc/group (рис. 4).
![Рис. 4.](images/4.png){ #fig:004 width=70% }

4. От имени пользователя guest2 выполнил регистрацию пользователя guest2 в группе guest (рис. 5).
![Рис. 5.](images/5.png){ #fig:005 width=70% }

5. От имени пользователя guest изменил права директории /home/guest, разрешив все действия для пользователей группы. Снял с директории /home/guest/dir1 все атрибуты проверил правильность снятия атрибутов (рис. 6).
![Рис. 6.](images/6.png){ #fig:006 width=70% }

6. Заполнил таблицы (рис. 7, 8).
![Рис. 7.](images/7.png){ #fig:006 width=70% }
![Рис. 8.](images/8.png){ #fig:006 width=70% }

# Выводы

Получил практические навыки работы в консоли с атрибутами файлов для групп пользователей.
