---
# Front matter
lang: ru-RU
title: "Отчёт по лабораторной работе №8"
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

Освоить на практике применение режима однократного гаммирования на примере кодирования различных исходных текстов одним ключом.

# Выполнение лабораторной работы

1. Для выполнения лабораторной работы был использован язык Python.
2. Для реализации алгоритма в начале опишем необходимые функции:
  - create_key: создание ключа
  - hexadical_form: перевод ключа в 16-ичную форму
  - gamming: гаммирование
3. Зададим в качестве примера два текста и реализуем алгоритм. Листинг программы выглядит следующим образом:
'''
#Импортируем необходимые библиотеки
import random as rnd
import string as str

#Пишем небоходимые функции
def create_key(size=6, chars=str.ascii_letters + str.digits):
    return ''.join(rnd.choice(chars) for _ in range(size))

def hexadical_form(s):
    return ' '.join("{:02x}".format(ord(c)) for c in s)

def gamming(fst_text, sec_text):
    fst_text_ascii = [ord(i) for i in fst_text]
    sec_text_ascii = [ord(i) for i in sec_text]
    return ''.join(chr(s^k) for s,k in zip(fst_text_ascii,sec_text_ascii))

#Выполним шифрование
P1, P2 = 'ПримерТекста1', 'ПримерДругогоТекста'
print('Исходные тексты:')
print(P1)
print(P2)

key=create_key(len(P1))
print('\nКлюч для кодирования текстов:', create_key(len(P1)))
print('Шестнадцатиричный ключ для кодирования текстов:', hexadical_form(key))

print('\nШифротекст для открытого текста 1 и ключа:', gamming(P1, key))
print('Шифротекст для открытого текста 2 и ключа:', gamming(P2, key))

print('\nПолучим тексты путём гаммирования двух шифровок и исходного текста:')
print(gamming(gamming(P1, key)+gamming(P2, key), P1))
print(gamming(gamming(P1, key)+gamming(P2, key), P2))
'''

4. Результат выполнения кода:
![Рис. 1. Итоговый результат](images/1.png){ #fig:001 width=70% }

# Выводы

Освоил на практике применение режима однократного гаммирования на примере кодирования различных исходных текстов одним ключом.
