---
## Front matter
lang: ru-RU
title: "Лабораторная работа №3"
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

- Получение практических навыков работы в консоли с атрибутами файлов для групп пользователей.

# Ход выполнения лабораторной работы

## 1. В установленной операционной системе создал учётную запись пользователя guest. Задайте пароль для пользователя guest. Аналогично создал второго пользователя guest2. Добавил пользователя guest2 в группу guest (рис. 1).
![Рис. 1.](images/1.png){ #fig:001 width=70% }

## 2. Осуществил вход в систему от двух пользователей на двух разных консолях: guest на первой консоли и guest2 на второй консоли. Для обоих пользователей определил директорию,в которой нахожусь: /home/guest и /home/guest2, что соответствует приглашениям командной строки. Для пользователя guest: имя пользователя - guest, его группа 1001(guest), принадлежит к группе guest. Для пользователя guest2: имя пользователя - guest2, его группа 1002(guest2), принадлежит к группам guest и guest2.Вывод команды groups аналогичем выводам команд id -Gn и id -G (рис. 2-3).
![Рис. 2.](images/2.png){ #fig:002 width=70% }
![Рис. 3.](images/3.png){ #fig:003 width=70% }

## 3. Сравнил полученную информацию с содержимым файла /etc/group (рис. 4).
![Рис. 4.](images/4.png){ #fig:004 width=70% }

## 4. От имени пользователя guest2 выполнил регистрацию пользователя guest2 в группе guest (рис. 5).
![Рис. 5.](images/5.png){ #fig:005 width=70% }

## 5. От имени пользователя guest изменил права директории /home/guest, разрешив все действия для пользователей группы. Снял с директории /home/guest/dir1 все атрибуты проверил правильность снятия атрибутов (рис. 6).
![Рис. 6.](images/6.png){ #fig:006 width=70% }

## 6. Заполнил таблицы (рис. 7, 8).
![Рис. 7.](images/7.png){ #fig:006 width=70% }
![Рис. 8.](images/8.png){ #fig:006 width=70% }

# Выводы

## Выводы

Получил практические навыки работы в консоли с атрибутами файлов для групп пользователей.

## {.standout}

Спасибо за внимание!
