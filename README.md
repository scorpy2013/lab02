## Laboratory work II

<a href="https://yandex.ru/efir/?stream_id=vMPJl0nEKr_0"><img src="https://raw.githubusercontent.com/tp-labs/lab02/master/preview.png" width="640"/></a>

Данная лабораторная работа посвещена изучению систем контроля версий на примере **Git**.

```bash
$ open https://git-scm.com
```

## Tasks

- [x] 1. Создать публичный репозиторий с названием **lab02** и с лиценцией **MIT**
- [x] 2. Сгенирировать токен для доступа к сервису **GitHub** с правами **repo**
- [x] 3. Ознакомиться со ссылками учебного материала
- [x] 4. Выполнить инструкцию учебного материала
- [x] 5. Составить отчет и отправить ссылку личным сообщением в **Slack**

## Tutorial

# Устанавлиаем параметры окружения среды
$ export GITHUB_USERNAME=scorpy2013
$ export GITHUB_EMAIL=scorpy2013@gmail.com
$ export GITHUB_TOKEN=0dc94d9c9fe7556bc832fbc82e5b22c21b58328c 
$ alias edit=vs
```

# заходим в workspace
$ cd ${GITHUB_USERNAME}/workspace
$ source scripts/activate
```
# создаем скрытую папку .config и добавить в нее файл hub 
$ mkdir ~/.config
$ cat > ~/.config/hub <<EOF
github.com:
- user: ${GITHUB_USERNAME}
  oauth_token: ${GITHUB_TOKEN}
  protocol: https
EOF
$ git config --global hub.protocol https
```
$ mkdir projects/lab02 && cd projects/lab02
$ git init
Initialized empty Git repository in C:/Users/User/lab02/scorpy2013/workspace/workspace/projects/lab02/.git/
$ git config --global user.name ${GITHUB_USERNAME}
$ git config --global user.email ${GITHUB_EMAIL}
61156928+scorpy2013@users.noreply.github.com
# check your git global settings
$ git config -e --global
[filter "lfs"]
	clean = git-lfs clean -- %f
	smudge = git-lfs smudge -- %f
	process = git-lfs filter-process
	required = true
[user]
	name = scorpy2013
	email = 61156928+scorpy2013@users.noreply.github.com
[core]
	editor = \"C:\\Users\\User\\AppData\\Local\\Programs\\Microsoft VS Code\\Code.exe\" --wait
[hub]
	protocol = https
$ git remote add origin https://github.com/${GITHUB_USERNAME}/lab02.git
$ git pull origin master
remote: Enumerating objects: 24, done.
remote: Counting objects: 100% (24/24), done.
remote: Compressing objects: 100% (22/22), done.
remote: Total 96 (delta 7), reused 5 (delta 2), pack-reused 72
Unpacking objects: 100% (96/96), 1.29 MiB | 96.00 KiB/s, done.
From https://github.com/scorpy2013/lab02
 * branch            master     -> FETCH_HEAD
 * [new branch]      master     -> origin/master
$ touch README.md
$ git status
On branch master
nothing to commit, working tree clean
$ git add README.md
$ git commit -m"added README.md"

*** Please tell me who you are.

Run

  git config --global user.email "you@example.com"
  git config --global user.name "Your Name"

to set your account's default identity.
Omit --global to set the identity only in this repository.

fatal: unable to auto-detect email address (got 'User@User-PC.(none)')
$ git push origin master
```

Добавить на сервисе **GitHub** в репозитории **lab02** файл **.gitignore**
со следующем содержимом:

```sh
*build*/
*install*/
*.swp
.idea/
```

```sh
$ git pull origin master
From https://github.com/scorpy2013/lab02
 * branch            master     -> FETCH_HEAD
Already up to date.
$ git log
commit 3f84b8805c2e5ff4059b3526e473b7b0c11dc161 (HEAD -> master, origin/master)
Author: scorpy2013 <61156928+scorpy2013@users.noreply.github.com>
Date:   Tue Apr 14 16:29:35 2020 +0300

    Update README.md

commit af8687b21746c774d987f07e8d89e3c9a3f821c2
Author: rusdevops <rusdevops@gmail.com>
Date:   Fri Apr 10 14:14:56 2020 +0300

    Update README.md

...skipping...
commit 3f84b8805c2e5ff4059b3526e473b7b0c11dc161 (HEAD -> master, origin/master)
Author: scorpy2013 <61156928+scorpy2013@users.noreply.github.com>
Date:   Tue Apr 14 16:29:35 2020 +0300

    Update README.md

commit af8687b21746c774d987f07e8d89e3c9a3f821c2
Author: rusdevops <rusdevops@gmail.com>
Date:   Fri Apr 10 14:14:56 2020 +0300

    Update README.md
...skipping...
commit 3f84b8805c2e5ff4059b3526e473b7b0c11dc161 (HEAD -> master, origin/master)
Author: scorpy2013 <61156928+scorpy2013@users.noreply.github.com>
Date:   Tue Apr 14 16:29:35 2020 +0300

    Update README.md

commit af8687b21746c774d987f07e8d89e3c9a3f821c2
Author: rusdevops <rusdevops@gmail.com>
Date:   Fri Apr 10 14:14:56 2020 +0300

    Update README.md

commit 4162a0f6677e33bf76de5a06cad3385f35ccde43
Author: rusdevops <rusdevops@gmail.com>
Date:   Fri Apr 10 14:14:39 2020 +0300

    Update README.md

commit 7542e7739792b8fcd0dbdfed0e45eb6d7a36c5f8
Author: rusdevops <rusdevops@gmail.com>
Date:   Fri Apr 10 13:46:51 2020 +0300

    Update README.md

commit 2a8a860ea41d9c2c7016cd97d7be44dbd7e2bee0
Author: rusdevops <rusdevops@gmail.com>
Date:   Fri Apr 10 13:27:26 2020 +0300

    Add files via upload

commit 82117e11305224ce9449d948f87ce0f8f1d83df0
Author: rusdevops <rusdevops@gmail.com>
Date:   Sat Mar 28 11:52:48 2020 +0300

    changed syntax tag for blocks

commit 9add2dc648d09840ba42601027705253b6903e2b
Author: Vyacheslav.Vershinin <Vyacheslav.Vershinin@acronis.com>
Date:   Thu Mar 12 16:50:53 2020 +0300

    fixed #3 report scenario

commit c0d965996c9929e4e33f4c3ff04aa38d37ccefd4
Author: rusdevops <rusdevops@gmail.com>
Date:   Thu Mar 5 20:17:45 2020 +0300

    Update README.md

commit 7370432f9c661d97a72c36d35d4c346b11159184
Merge: ed14855 36da062
Author: rusdevops <rusdevops@gmail.com>
Date:   Thu Feb 28 17:24:16 2019 +0300

    Merge pull request #1 from drewxa/patch-1

    added homework

commit 36da062d807b544e0af524275c3c79e73320f2b0
Author: drewxa <bo.ro.da@mail.ru>
Date:   Tue Feb 26 19:48:32 2019 +0300

    added homework

    Добавлено задания для самоподготовки:
    * init
    * commit
    * log
    * push
    * rebase

commit ed14855954e0f21b177e3e7e541eb763b86dd674
Author: rusdevops <rusdevops@gmail.com>
Date:   Sun Jan 20 11:28:59 2019 +0000

    fixed lab ID

commit 457bbf6275564245978ae511ed8aea53cda81de5
Author: rusdevops <rusdevops@gmail.com>
Date:   Sun Jan 20 11:25:58 2019 +0000

    move hub installation to lab00

commit 2565c654e3cf8322c6e7b02210cfbb04d25ba2e3
Author: rusdevops <rusdevops@gmail.com>
Date:   Sun Jan 20 13:29:16 2019 +0300

    Update README.md

commit 3e78c8c11ae5fba16a7e74e11b495c6584e018f7
Author: rusdevops <rusdevops@gmail.com>
Date:   Sun Jan 20 13:26:47 2019 +0300

    Update README.md

commit 4e04eb75d8c2f607770c264631910fdbe33c650c
Author: rusdevops <rusdevops@gmail.com>
Date:   Sun Jan 20 13:05:32 2019 +0300

    Update README.md

commit 82e7b76a958b4609b76804f0303cf5780c0d6d3b
Author: rusdevops <rusdevops@gmail.com>
Date:   Thu Oct 26 19:00:56 2017 -0800

    refactored

commit dc253c16edc221bf23bcbe38a26608c5530333e6
Author: justcppdev <justcppdev@ya.ru>
Date:   Mon Sep 25 13:06:08 2017 +0300

    Update README.md

commit 97d9e6396164a2fbc9de30332ecfda968fac8222
Author: justcppdev <justcppdev@ya.ru>
Date:   Mon Sep 25 13:05:25 2017 +0300

    Update README.md

commit 9f9171c543d7ea6754d70f6135cfa81a60fcb8ec
Author: rusdevops <rusdevops@gmail.com>
Date:   Sun Jun 25 10:10:33 2017 +0300

    Update README.md

commit 5ae6ba5711dfd69566d777d4e5441c7130eeae02
Author: rusdevops <rusdevops@gmail.com>
Date:   Tue Jun 13 10:54:05 2017 +0300

    Create README.md

commit 1ae112f815f66860c8d4723e552577b27fa945b5
Author: rusdevops <rusdevops@gmail.com>
Date:   Mon May 22 09:40:11 2017 +0300

    Update README.md

commit 93cdc0fbcb421f69504b9ffaff6271c93fbeeda7
Author: rusdevops <rusdevops@gmail.com>
Date:   Wed May 17 19:02:47 2017 +0300

    refactoring

commit dd2b22e9e8520ccb53aea44e2f54362fc7b8ae9b
Author: rusdevops <rusdevops@gmail.com>
Date:   Wed May 17 11:45:05 2017 +0300

    refactoring

commit fc7458fe1df6051ad3ee2c57ce41b6d1d79dc03c
Author: rusdevops <rusdevops@gmail.com>
Date:   Wed May 17 09:14:56 2017 +0300

    Update README.md

commit 5939fa15345c24caa0b598505a654d92fc3f9d05
Author: rusdevops <rusdevops@gmail.com>
Date:   Wed May 17 09:00:00 2017 +0300

    Update

commit d15c811a75d24aba9fc09ca1b576553624c97096
Author: rusdevops <rusdevops@gmail.com>
Date:   Wed May 17 08:59:48 2017 +0300

    Update README.md

commit 7d508e748267619b63d43353cc29d127ee6b4046
Author: rusdevops <rusdevops@gmail.com>
Date:   Wed May 17 08:58:49 2017 +0300

    Update README.md

commit 5f55ce3d2159e63800d9881d2c0ead0d8fcceea6
Author: rusdevops <rusdevops@gmail.com>
Date:   Wed May 17 08:20:16 2017 +0300

    Update README.md

commit a061595ee7a0691eff577586e4314f4335a6abdc
Author: rusdevops <rusdevops@gmail.com>
Date:   Mon May 15 12:08:42 2017 +0300

    Update README.md

commit c54d4a0762bf19080da724657259dcc36ec302ca
Author: rusdevops <rusdevops@gmail.com>
Date:   Sun Apr 30 11:12:04 2017 +0300

    refactoring

commit 3f1c1f6e462687e4f51909628167965f5ba70b67
Author: rusdevops <rusdevops@gmail.com>
Date:   Thu Apr 27 15:13:25 2017 +0300

    Update README.md

commit a968e67febbb7cca46125868032c5f785a445f81
Author: rusdevops <rusdevops@gmail.com>
Date:   Thu Apr 27 14:45:43 2017 +0300

    Create README.md

commit 550513f0218a8737ebbc17d40135afae4155b674
Author: rusdevops <rusdevops@gmail.com>
Date:   Thu Apr 27 14:44:04 2017 +0300

    Initial commit
```

```sh
$ mkdir sources
$ mkdir include
$ mkdir examples
$ cat > sources/print.cpp <<EOF
#include <print.hpp>

void print(const std::string& text, std::ostream& out)
{
  out << text;
}

void print(const std::string& text, std::ofstream& out)
{
  out << text;
}
EOF
```

```sh
$ cat > include/print.hpp <<EOF
#include <fstream>
#include <iostream>
#include <string>

void print(const std::string& text, std::ofstream& out);
void print(const std::string& text, std::ostream& out = std::cout);
EOF
```

```sh
$ cat > examples/example1.cpp <<EOF
#include <print.hpp>

int main(int argc, char** argv)
{
  print("hello");
}
EOF
```

```sh
$ cat > examples/example2.cpp <<EOF
#include <print.hpp>

#include <fstream>

int main(int argc, char** argv)
{
  std::ofstream file("log.txt");
  print(std::string("hello"), file);
}
EOF
```

```sh
$ edit README.md
```

```sh
$ git status
On branch master
Your branch is up to date with 'origin/master'.

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        examples/
        include/
        scorpy2013/
        sources/

nothing added to commit but untracked files present (use "git add" to track)

$ git add .
warning: LF will be replaced by CRLF in examples/example1.cpp.
The file will have its original line endings in your working directory
warning: LF will be replaced by CRLF in examples/example2.cpp.
The file will have its original line endings in your working directory
warning: LF will be replaced by CRLF in include/print.hpp.
The file will have its original line endings in your working directory
warning: adding embedded git repository: scorpy2013/workspace/workspace/projects/lab02
hint: You've added another git repository inside your current repository.
hint: Clones of the outer repository will not contain the contents of
hint: the embedded repository and will not know how to obtain it.
hint: If you meant to add a submodule, use:
hint: 
hint:   git submodule add <url> scorpy2013/workspace/workspace/projects/lab02
hint: 
hint: If you added this path by mistake, you can remove it from the
hint: index with:
hint: 
hint:   git rm --cached scorpy2013/workspace/workspace/projects/lab02
hint: 
hint: See "git help submodule" for more information.
warning: LF will be replaced by CRLF in sources/print.cpp.
The file will have its original line endings in your working directory
$ git commit -m"added sources"
$ git status
On branch master
Your branch is up to date with 'origin/master'.

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        examples/
        include/
        scorpy2013/
        sources/

nothing added to commit but untracked files present (use "git add" to track)

User@User-PC MINGW64 ~/lab02 (master)
$ git add .
warning: LF will be replaced by CRLF in examples/example1.cpp.
The file will have its original line endings in your working directory
warning: LF will be replaced by CRLF in examples/example2.cpp.
The file will have its original line endings in your working directory
warning: LF will be replaced by CRLF in include/print.hpp.
The file will have its original line endings in your working directory
warning: adding embedded git repository: scorpy2013/workspace/workspace/projects/lab02
hint: You've added another git repository inside your current repository.
hint: Clones of the outer repository will not contain the contents of
hint: the embedded repository and will not know how to obtain it.
hint: If you meant to add a submodule, use:
hint: 
hint:   git submodule add <url> scorpy2013/workspace/workspace/projects/lab02
hint: 
hint: If you added this path by mistake, you can remove it from the
hint: index with:
hint: 
hint:   git rm --cached scorpy2013/workspace/workspace/projects/lab02
hint: 
hint: See "git help submodule" for more information.
warning: LF will be replaced by CRLF in sources/print.cpp.
The file will have its original line endings in your working directory

User@User-PC MINGW64 ~/lab02 (master)
$ git commit -m"added sources"

*** Please tell me who you are.

Run

  git config --global user.email "you@example.com"
  git config --global user.name "Your Name"

to set your account's default identity.
Omit --global to set the identity only in this repository.

fatal: unable to auto-detect email address (got 'User@User-PC.(none)')
$ git push origin master
```

## Report

```sh
$ cd ~/workspace/
$ export LAB_NUMBER=02
$ git clone https://github.com/tp-labs/lab${LAB_NUMBER}.git tasks/lab${LAB_NUMBER}
Cloning into 'tasks/lab02'...
remote: Enumerating objects: 21, done.
remote: Counting objects: 100% (21/21), done.
remote: Compressing objects: 100% (19/19), done.
remote: Total 93 (delta 6), reused 5 (delta 2), pack-reused 72R
Receiving objects: 100% (93/93), 1.28 MiB | 237.00 KiB/s, done.
Resolving deltas: 100% (28/28), done.
$ mkdir reports/lab${LAB_NUMBER}
$ cp tasks/lab${LAB_NUMBER}/README.md reports/lab${LAB_NUMBER}/REPORT.md
$ cd reports/lab${LAB_NUMBER}
$ edit REPORT.md
$ gist REPORT.md
```

## Homework

### Part I

1. Создайте пустой репозиторий на сервисе github.com (или gitlab.com, или bitbucket.com).
2. Выполните инструкцию по созданию первого коммита на странице репозитория, созданного на предыдещем шаге.
3. Создайте файл `hello_world.cpp` в локальной копии репозитория (который должен был появиться на шаге 2). Реализуйте программу **Hello world** на языке C++ используя плохой стиль кода. Например, после заголовочных файлов вставьте строку `using namespace std;`.
cat > helloworld.cpp<<EOF
#include <iostream>
using namespace std;
int main() {
    cout<<"Hello world!"<<endl;
    system("pause");
    return 0;
}
4. Добавьте этот файл в локальную копию репозитория.
	git add .
5. Закоммитьте изменения с *осмысленным* сообщением.
	git commit -m "Hello everyone! I'm Alex!"
6. Изменитьте исходный код так, чтобы программа через стандартный поток ввода запрашивалось имя пользователя. А в стандартный поток вывода печаталось сообщение `Hello world from @name`, где `@name` имя пользователя.
	cat > helloworld.cpp<<EOF
> #include <iostream>
> #include <string>
> using namespace std;
> int main() {
> string name;
> cin>>name;	
> cout<<"Hello, "<<name<<" !"<<endl;
> system("pause")
> return 0;
> EOF
7. Закоммитьте новую версию программы. Почему не надо добавлять файл повторно `git add`?
8. Запушьте изменения в удалёный репозиторий.
	git commit -m "HelloWorld for Lab02"
9. Проверьте, что история коммитов доступна в удалёный репозитории.
	git show
	commit 0dc94d9c9fe7556bc832fbc82e5b22c21b58328c (HEAD -> master, origin/master, origin/HEAD)
Author: scorpy2013 <scorpy2013@gmail.com>
Date:   Tue Apr 14 15:45:32 2020 +0400

    Helloworld version 1

diff --git a/helloworld.cpp b/helloworld.cpp
new file mode 100644
index 0000000..83d90e0
--- /dev/null
+++ b/helloworld.cpp
@@ -0,0 +1,8 @@
+#include <iostream>
+#include <string>
+using namespace std;
+int main() {
+string name;
+cin>>name;
+cout<<"Hello world, "<<name<<" !"<<endl;
+system("pause")
+return 0;

### Part II

**Note:** *Работать продолжайте с теми же репоззиториями, что и в первой части задания.*
- [x] 1. В локальной копии репозитория создайте локальную ветку `patch1`.
 git checkout -b patch1
 Switched to a new branch 'patch1'
- [x] 2. Внесите изменения в ветке `patch1` по исправлению кода и избавления от `using namespace std;`.
- [x] 3. **commit**, **push** локальную ветку в удалённый репозиторий.
 git add "helloworld.cpp"
 git commit -m "new helloworld"
 git push origin patch1
Enumerating objects: 19, done.
Counting objects: 100% (19/19), done.
Delta compression using up to 4 threads
Compressing objects: 100% (9/9), done.
Writing objects: 100% (15/15), 3.13 KiB | 3.13 MiB/s, done.
Total 15 (delta 1), reused 9 (delta 1), pack-reused 0
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
remote:
remote: Create a pull request for 'patch1' on GitHub by visiting:
remote:      https://github.com/scorpy2013/Homework/pull/new/patch1
remote:
To https://github.com/scorpy2013/Homework.git
 * [new branch]      patch1 -> patch1
- [x] 4. Проверьте, что ветка `patch1` доступна в удалёный репозитории.
git show
commit 3f84b8805c2e5ff4059b3526e473b7b0c11dc161 (HEAD -> patch1, origin/patch1, master)
Author: scorpy2013 <61156928+scorpy2013@users.noreply.github.com>
Date:   Tue Apr 14 16:29:35 2020 +0300
diff --git a/README.md b/README.md
index 84f6801..81df17c 100644
--- a/README.md
+++ b/README.md
@@ -10,22 +10,22 @@ $ open https://git-scm.com
- [x] 5. Создайте pull-request `patch1 -> master`.
- [x] 6. В локальной копии в ветке `patch1` добавьте в исходный код комментарии.
- [x] 7. **commit**, **push**.
git commit -m "add comments"
- [x] 8. Проверьте, что новые изменения есть в созданном на **шаге 5** pull-request
- [x] 9. В удалённый репозитории выполните  слияние PR `patch1 -> master` и удалите ветку `patch1` в удаленном репозитории.
- [x] 10. Локально выполните **pull**.
git pull
Updating e6ac6e8..0852a1d 
Fast-forward
 helloworld.cpp | 6 ++++--
 1 file changed, 4 insertions(+), 2 deletions(-)
- [x] 11. С помощью команды **git log** просмотрите историю в локальной версии ветки `master`.
git log
commit 3f84b8805c2e5ff4059b3526e473b7b0c11dc161 (HEAD -> patch1, origin/patch1, master)
Author: scorpy2013 <61156928+scorpy2013@users.noreply.github.com>
Date:   Tue Apr 14 16:29:35 2020 +0300

commit af8687b21746c774d987f07e8d89e3c9a3f821c2
Author: rusdevops <rusdevops@gmail.com>
Date:   Fri Apr 10 14:14:56 2020 +0300

- [x] 12. Удалите локальную ветку `patch1`.
git branch -d patch1

### Part III

**Note:** *Работать продолжайте с теми же репоззиториями, что и в первой части задания.*
- [x] 1. Создайте новую локальную ветку `patch2`.
  $ git checkout -b patch2
Switched to a new branch 'patch2'
  Switched to a new branch 'patch2'
- [x] 2. Измените *code style* с помощью утилиты [**clang-format**](http://clang.llvm.org/docs/ClangFormat.html). Например, используя опцию `-style=Mozilla`.
  brew install -g clang-format
  clang-format -i -style=Mozilla hello_world.cpp
- [x] 3. **commit**, **push**, создайте pull-request `patch2 -> master`.
 git commit -m "added styles" 
 git push origin patch2 
- [x] 4. В ветке **master** в удаленном репозитории измените комментарии, например, расставьте знаки препинания, переведите комментарии на другой язык.
- [x] 5. Убедитесь, что в pull-request появились *конфликтны*.
- [x] 6. Для этого локально выполните **pull** + **rebase** (точную последовательность команд, следует узнать самостоятельно). **Исправьте конфликты**.
   git add .
   git pull
   git checkout master
   git pull origin master
   git checkout patch2
   git rebase master
   git commit -m "delete conflict"
   git rebase --continue
   git checkout master
   git merge patch2
   Fast-forward
 helloworld.cpp | 15 +++++++++++++++
 1 file changed, 15 insertions(+)
- [x] 7. Сделайте *force push* в ветку `patch2`
   git push -f origin patch2
   Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 4 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 585 bytes | 585.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
To https://github.com/scorpy2013/Homework.git
- [x] 8. Убедитель, что в pull-request пропали конфликтны. 
- [x] 9. Вмержите pull-request `patch2 -> master`.

## Links

- [hub](https://hub.github.com/)
- [GitHub](https://github.com)
- [Bitbucket](https://bitbucket.org)
- [Gitlab](https://about.gitlab.com)
- [LearnGitBranching](http://learngitbranching.js.org/)

```
Copyright (c) 2015-2020 The ISC Authors
```
