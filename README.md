```
export GITHUB_USERNAME=nastyaiva
```
```
export GITHUB_EMAIL=nastyadina2005@gmail.com
```
```
export GITHUB_TOKEN=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
```
```
alias edit=nvim
```
```
cd ${GITHUB_USERNAME}/workspace
```
```
source scripts/activate
```
```
mkdir ~/.config
```
```
cat > ~/.config/hub <<EOF
> github.com:
> user: ${GITHUB_USERNAME}
> oauth_token: ${GITHUB_TOKEN}
> protocol: https
> EOF
```
```
git config --global hub.protocol https
```
```
mkdir projects/lab02 && cd projects/lab02
```
```
git init
```
```
git config --global user.name ${GITHUB_USERNAME}
```
```
git config --global user.email ${GITHUB_EMAIL}
```
```
git config -e --global
```
```
git remote add origin git@github.com:nastyaiva/lab02.git
```
```
git pull origin main
remote: Enumerating objects: 3, done.
remote: Counting objects: 100% (3/3), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
Распаковка объектов: 100% (3/3), 863 байта | 863.00 КиБ/с, готово.
Из github.com:nastyaiva/lab02
 * branch            main       -> FETCH_HEAD
 * [новая ветка]     main       -> origin/main

```
```
touch TEST.md
```
```
git status

Текущая ветка: master
нечего коммитить, нет изменений в рабочем каталоге
```
```
git add TEST.md
```
```
git commit -m "added TEST.md"

Текущая ветка: master
нечего коммитить, нет изменений в рабочем каталоге
```
```
git push origin master

Перечисление объектов: 3, готово.
Подсчет объектов: 100% (3/3), готово.
Запись объектов: 100% (3/3), 215 байтов | 215.00 КиБ/с, готово.
Всего 3 (изменений 0), повторно использовано 0 (изменений 0), повторно использовано пакетов 0
remote: 
remote: Create a pull request for 'master' on GitHub by visiting:
remote:      https://github.com/nastyaiva/lab02/pull/new/master
remote: 
To github.com:nastyaiva/lab02.git
* [new branch]      master -> master
```
```
git pull origin master

Из github.com:nastyaiva/lab02
 * branch            master     -> FETCH_HEAD
Уже актуально.
```
```
git log 

ommit 8581dcfa99b6d978259bf80d5cec057c85caebf0 (HEAD -> master, origin/master)
Author: nastyaiva <nastyadina2005@gmail.com>
Date:   Sun Apr 28 14:50:28 2024 +0300

    added TEST.md
```
```
mkdir sources && mkdir include && mkdir examples
```
```
cat > sources/print.cpp <<EOF

> #include <print.hpp>

void print(const std::string& text, std::ostream& out)
{
  out << text;
}

void print(const std::string& text, std::ofstream& out)
{
  out << text;
}
> EOF
```
```
cat > include/print.hpp <<EOF

> #include <fstream>
#include <iostream>
#include <string>

void print(const std::string& text, std::ofstream& out);
void print(const std::string& text, std::ostream& out = std::cout);
> EOF
```
```
cat > examples/example1.cpp <<EOF

> #include <print.hpp>

int main(int argc, char** argv)
{
  print("hello");
}
> EOF
```
```
cat > examples/example2.cpp <<EOF

> #include <print.hpp>

#include <fstream>

int main(int argc, char** argv)
{
  std::ofstream file("log.txt");
  print(std::string("hello"), file);
}
> EOF
```
```
edit README.md

[1]+  Остановлен    nvim README.md
```
```
git status

Текущая ветка: master
Неотслеживаемые файлы:
  (используйте «git add <файл>...», чтобы добавить в то, что будет включено в коммит)
	examples/
	include/
	sources/

индекс пуст, но есть неотслеживаемые файлы
(используйте «git add», чтобы проиндексировать их)
```
```
git add .
```
```
git commit -m "added sources"

[master d56bd0f] added sources
 4 files changed, 32 insertions(+)
 create mode 100644 examples/example1.cpp
 create mode 100644 examples/example2.cpp
 create mode 100644 include/print.hpp
 create mode 100644 sources/print.cpp
```
```
git push origin master

Перечисление объектов: 10, готово.
Подсчет объектов: 100% (10/10), готово.
При сжатии изменений используется до 8 потоков
Сжатие объектов: 100% (7/7), готово.
Запись объектов: 100% (9/9), 896 байтов | 896.00 КиБ/с, готово.
Всего 9 (изменений 0), повторно использовано 0 (изменений 0), повторно использовано пакетов 0
To github.com:nastyaiva/lab02.git
   8581dcf..d56bd0f  master -> master

```
```
git branch main
```
```
git commit -am "Idea"

Текущая ветка: master
Неотслеживаемые файлы:
  (используйте «git add <файл>...», чтобы добавить в то, что будет включено в коммит)
	.gitignore 

индекс пуст, но есть неотслеживаемые файлы
(используйте «git add», чтобы проиндексировать их)
```
```
git push origin main -f

Перечисление объектов: 15, готово.
Подсчет объектов: 100% (15/15), готово.
При сжатии изменений используется до 8 потоков
Сжатие объектов: 100% (10/10), готово.
Запись объектов: 100% (15/15), 1.30 КиБ | 332.00 КиБ/с, готово.
Всего 15 (изменений 1), повторно использовано 0 (изменений 0), повторно использовано пакетов 0
remote: Resolving deltas: 100% (1/1), done.
To github.com:nastyaiva/lab02.git
 + d6d8c71...29bbbb0 main -> main (forced update)
```

```
edit REPORT.md
```
```
gist REPORT.md
```

