---
# Front matter
lang: ru-RU
title: "Отчёт по лабораторной работе №6"
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

Развить навыки администрирования ОС Linux. Получить первое практическое знакомство с технологией SELinux. Проверить работу SELinx на практике совместно с веб-сервером Apache.

# Выполнение лабораторной работы

1. Вошёл в систему с полученными учётными данными и убедился, что SELinux работает в режиме enforcing политики targeted. Обратился с помощью браузера к веб-серверу, запущенному на компьютере, и убедился, что последний работает (рис. 1).
![Рис. 1](images/1.png){ #fig:001 width=70% }

2. Нашёл веб-сервер Apache в списке процессов, определил его контекст безопасности и занёс эту информацию в отчёт (рис. 2).  
![Рис. 2](images/2.png){ #fig:002 width=70% }

3. Посмотрел текущее состояние переключателей SELinux для Apache (рис. 3).
![Рис. 3](images/3.png){ #fig:003 width=70% }

4. Посмотрел статистику по политике с помощью команды seinfo, также определил множество пользователей, ролей, типов (рис. 4).
![Рис. 4](images/4.png){ #fig:004 width=70% }

5. Определил тип файлов и поддиректорий, находящихся в директории /var/www. Определил тип файлов, находящихся в директории /var/www/html. Определил круг пользователей, которым разрешено создание файлов в директории (рис. 5).
![Рис. 5](images/5.png){ #fig:005 width=70% }

6. Создал от имени суперпользователя html-файл (рис. 6).
![Рис. 6](images/6.png){ #fig:006 width=70% }

7. Проверил контекст созданного файла. Контекст, присваиваемый по умолчанию вновь созданным файлам в директории /var/www/html: httpd_sys_content (рис. 7).
![Рис. 7](images/7.png){ #fig:007 width=70% }

8. Обратился к файлу через веб-сервер, введя в браузере адрес http://127.0.0.1/test.html. Убедился, что файл успешно отображён (рис. 8).
![Рис. 8](images/8.png){ #fig:008 width=70% }

9. Изменил контекст файла /var/www/html/test.html с httpd_sys_content_t на samba_share_t. После этого проверил, что контекст поменялся (рис. 9).
![Рис. 9](images/9.png){ #fig:009 width=70% }

10. Попробовал ещё раз получить доступ к файлу через веб-сервер, введя в браузере адрес http://127.0.0.1/test.html (рис. 10).
![Рис. 10](images/10.png){ #fig:010 width=70% }

11. Проанализировал ситуацию. Почему файл не был отображён,если права доступа позволяют читать этот файл любому пользователю? Просмотрел log-файлы веб-сервера Apache. Также просмотрите системный лог-файл. Если в системе окажутся запущенными процессы setroubleshootd и audtd, то вы также сможете увидеть ошибки, аналогичные указанным выше, в файле /var/log/audit/audit.log. Проверьте это утверждение самостоятельно (рис. 11-12).
![Рис. 11](images/11.png){ #fig:011 width=70% }
![Рис. 12](images/12.png){ #fig:012 width=70% }

12. Попробовал запустить веб-сервер Apache на прослушивание ТСР-порта 81. Для этого в файле /etc/httpd/httpd.conf нашёл строчку Listen 80 и заменил её на Listen 81 (рис. 13).
![Рис. 13](images/13.png){ #fig:013 width=70% }

13. Выполнил перезапуск веб-сервера Apache. Произошёл сбой. Поясните почему? (рис. 14).
![Рис. 14](images/14.png){ #fig:014 width=70% }

14. Проанализировал лог-файлы. Просмотрел файлы /var/log/http/error_log, /var/log/http/access_log и /var/log/audit/audit.log и выясните, в каких файлах появились записи (рис. 15-18).
![Рис. 15](images/15.png){ #fig:015 width=70% }
![Рис. 16](images/16.png){ #fig:016 width=70% }
![Рис. 17](images/17.png){ #fig:017 width=70% }
![Рис. 18](images/18.png){ #fig:018 width=70% }

15. Выполнил команду semanage port -a -t http_port_t -р tcp 81. После этого проверил список портов. Убедился, что порт 81 появился в списке (рис. 19).
![Рис. 19](images/19.png){ #fig:019 width=70% }

16. Вернул контекст httpd_sys_cоntent__t к файлу/var/www/html/test.html (рис. 20).
![Рис. 20](images/20.png){ #fig:020 width=70% }

17. Исправил обратно конфигурационный файл apache, вернув Listen80 (рис. 21).
![Рис. 21](images/21.png){ #fig:021 width=70% }

18. Удалил привязку http_port_t к 81 порту и проверил, что порт 81 удалён. Удалил файл /var/www/html/test.html (рис. 22).
![Рис. 22](images/22.png){ #fig:022 width=70% }

# Выводы

Развил навыки администрирования ОС Linux. Получил первое практическое знакомство с технологией SELinux. Проверил работу SELinx на практике совместно с веб-сервером Apache.