---
# Front matter
lang: ru-RU
title: "Отчёт по лабораторной работе №4"
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

Получение практических навыков работы в консоли с расширенными атрибутами файлов.

# Выполнение лабораторной работы

1. От имени пользователя guest определил расширенные атрибуты файла /home/guest/dir1/file. Установил командой на файл file1 права, разрешающие чтение и запись для владельца файла. (рис. 1)
![Рис. 1.](images/1.png){ #fig:001 width=70% }

2. Попробовал установить на файл/home/guest/dir1/file1 расширенный атрибут a от имени пользователя guest. Попробовал установить расширенный атрибут a на файл /home/guest/dir1/file1 от имени суперпользователя. От пользователя guest проверил правильность установления атрибута. Выполнил дозапись в файл file1 слова «test». После этого выполнил чтение файла file1. Убедился, что слово test было успешно записано в file1. Попробовал удалить файл file1. Попробовал переименовать файл. Попробовал установить на файл file1 права, например, запрещающие чтение и запись для владельца файла. Не удалось успешно выполнить указанные команды? Снял расширенный атрибутa с файла/home/guest/dirl/file1 от имени суперпользователя. Повторил операции, которые ранее не удавалось выполнить. Они были успешно исполнены (рис. 2).
![Рис. 2.](images/2.png){ #fig:002 width=70% }

3. Повторил действия по шагам,заменив атрибут «a» атрибутом «i». Дозаписать информацию не удалось (рис. 3).
![Рис. 3.](images/3.png){ #fig:003 width=70% }

# Выводы

Получил практические навыки работы в консоли с расширенными атрибутами файлов.
