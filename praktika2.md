## Задача 1
Вывести служебную информацию о пакете matplotlib (Python). Разобрать основные элементы содержимого файла со служебной информацией из пакета. Как получить пакет без менеджера пакетов, прямо из репозитория?
google colab
```bash
localhost:~# pip3 show matplotlib
Name: matplotlib
Version: 3.2.1
Summary: Python plotting package
Home-page: https://matplotlib.org
Author: John D. Hunter, Michael Droettboom
Author-email: matplotlib-users@python.org
License: PSF
Location: /usr/lib/python3.8/site-packages
Requires: cycler, kiwisolver, numpy, pyparsing, python-dateutil
Required-by: 
```
```bash
git clone https://github.com/matplotlib/matplotlib.git
cd matplotlib
python setup.py install
```
## Задача 2

Вывести служебную информацию о пакете express (JavaScript). Разобрать основные элементы содержимого файла со служебной информацией из пакета. Как получить пакет без менеджера пакетов, прямо из репозитория?
```bash
localhost:~# npm show express
 
express@4.21.0 | MIT | deps: 31 | versions: 279
Fast, unopinionated, minimalist web framework
http://expressjs.com/
 
keywords: express, framework, sinatra, web, http, rest, restful, router, app, ap
i
 
dist
.tarball: https://registry.npmjs.org/express/-/express-4.21.0.tgz
.shasum: d57cb706d49623d4ac27833f1cbc466b668eb915
.integrity: sha512-VqcNGcj/Id5ZT1LZ/cfihi3ttTn+NJmkli2eZADigjq29qTlWi/hAQ43t/VLP
q8+UX06FCEx3ByOYet6ZFblng==
.unpackedSize: 220.8 kB
 
dependencies:
accepts: ~1.3.8      etag: ~1.8.1         qs: 6.13.0           
body-parser: 1.20.3  finalhandler: 1.3.1  range-parser: ~1.2.1 
content-type: ~1.0.4 fresh: 0.5.2         safe-buffer: 5.2.1   
cookie: 0.6.0        http-errors: 2.0.0   send: 0.19.0         
debug: 2.6.9         methods: ~1.1.2      statuses: 2.0.1      
depd: 2.0.0          on-finished: 2.4.1   type-is: ~1.6.18     
encodeurl: ~2.0.0    parseurl: ~1.3.3     utils-merge: 1.0.1   
escape-html: ~1.0.3  proxy-addr: ~2.0.7   vary: ~1.1.2         
(...and 7 more.)
 
maintainers:
- wesleytodd <wes@wesleytodd.com>
- dougwilson <doug@somethingdoug.com>
- linusu <linus@folkdatorn.se>
- sheplu <jean.burellier@gmail.com>
- blakeembrey <hello@blakeembrey.com>
- ulisesgascon <ulisesgascondev@gmail.com>
- mikeal <mikeal.rogers@gmail.com>
 
dist-tags:
latest: 4.21.0  next: 5.0.0     
 
published 3 weeks ago by wesleytodd <wes@wesleytodd.com>
```
```bash
git clone https://github.com/expressjs/express.git
cd express
```
## Задача 3

Сформировать graphviz-код и получить изображения зависимостей matplotlib и express.

## Задача 4

Решить на MiniZinc задачу о счастливых билетах. Добавить ограничение на то, что все цифры билета должны быть различными (подсказка: используйте all_different). Найти минимальное решение для суммы 3 цифр.

```minizinc
include "globals.mzn";

% массив из 6 цифр от 1 до 9
array[1..6] of var 0..9: digits;
constraint all_different(digits);

constraint
  digits[1] + digits[2] + digits[3] = digits[4] + digits[5] + digits[6];

% Минимизация суммы
var int: sum_digits = digits[1] + digits[2] + digits[3];
solve minimize sum_digits;

output ["\(show(digits[1]))\(show(digits[2]))\(show(digits[3]))\(show(digits[4]))\(show(digits[5]))\(show(digits[6]))\n"];
```
