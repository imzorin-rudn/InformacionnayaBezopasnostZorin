---
## Front matter
lang: ru-RU
title: "Лабораторная работа №8"
author: |
	Zorin Ilya\inst{1}

institute: |
	\inst{1}RUDN University, Moscow, Russian Federation
	
date: 01 September, Moscow, Russian Federation

## Formatting
toc: false
slide_level: 2
theme: metropolis
header-includes: 
 - \metroset{progressbar=frametitle,sectionpage=progressbar,numbering=fraction}
 - '\makeatletter'
 - '\beamer@ignorenonframefalse'
 - '\makeatother'
aspectratio: 43
section-titles: true
---

# Цель выполнения лабораторной работы

## Цель выполнения лабораторной работы

- Освоить на практике применение режима однократного гаммирования на примере кодирования различных исходных текстов одним ключом.

# Ход выполнения лабораторной работы

## Напишем программу на языке Python 
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
'''
## Напишем программу на языке Python 
'''
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
## Результаты
![Рис. 1. Итоговый результат](images/1.png){ #fig:001 width=70% }

# Выводы

## Выводы

Освоил на практике применение режима однократного гаммирования на примере кодирования различных исходных текстов одним ключом.

## {.standout}

Спасибо за внимание!