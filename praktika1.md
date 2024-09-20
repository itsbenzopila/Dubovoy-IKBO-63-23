# Задача 1
Вывести отсортированный в алфавитном порядке список имен пользователей в файле passwd (вам понадобится grep).

## Выполнение
```bash
localhost:~# grep '.*' /etc/passwd | cut -d: -f1 | sort
adm
at
bin
cron
cyrus
daemon
dhcp
ftp
games
guest
halt
lp
mail
man
news
nobody
ntp
operator
postmaster
root
shutdown
smmsp
squid
sshd
svn
sync
uucp
vpopmail
xfs
localhost:~#
```

# Задача 2
Вывести данные /etc/protocols в отформатированном и отсортированном порядке для 5 наибольших портов.

## Выполнение
```bash
localhost:~# awk '{print $2, $1}' /etc/protocols | tail -n 5 | sort -nr
103 pim
98 encap
94 ipip
89 ospf
81 vmtp
localhost:~# 
```
# Задача 3
Написать программу banner средствами bash для вывода текстов, как в следующем примере (размер баннера должен меняться!).

## Выполнение
```bash
localhost:~# touch test.sh
localhost:~# nano test.sh
```
```bash
#!/bin/bash
 
input=$*
len=${#input}
 
for i in $(seq 1 $((len + 2))); do
        line+="-"
done
 
echo "+${line}+"
echo "| ${input} |"
echo "+${line}+"
```
```bash
localhost:~# ./test.sh "test"
+------+
| test |
+------+
localhost:~# 
```

# Задача 4
Написать программу для вывода всех идентификаторов (по правилам C/C++ или Java) в файле (без повторений).

## Выполнение
```bash
localhost:~# grep -oE '\b[a-zA-Z_][a-zA-Z0-9_]*\b' hello.c | grep -vE '\b(int|vo
id|return|if|else|for|while|include|printf|main)\b' | sort | uniq
h
hello
n
stdio
world
localhost:~#
```
# Задача 5
Написать программу для регистрации пользовательской команды (правильные права доступа и копирование в /usr/local/bin).

## Выполнение
```bash
localhost:~# touch reg.sh
localhost:~# nano reg.sh
```
```bash
#!/bin/bash
 
file=$1
chmod +x "./$file"
sudo cp "$file" /usr/local/bin/
```
```bash
localhost:~# ./reg.sh banner.sh
```
