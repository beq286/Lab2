# Lab2

### Part I

1. Создайте пустой репозиторий на сервисе github.com (или gitlab.com, или bitbucket.com).
2. Выполните инструкцию по созданию первого коммита на странице репозитория, созданного на предыдещем шаге.

```sh
$ echo "# Lab2" >> README.md
$ git init
$ git add README.md
$ git commit -m "first commit"
$ git branch -M main
$ git remote add origin https://github.com/beq286/Lab2.git
$ git push -u origin main
```



```sh
Перечисление объектов: 3, готово.
Подсчет объектов: 100% (3/3), готово.
Запись объектов: 100% (3/3), 215 байтов | 107.00 КиБ/с, готово.
Всего 3 (изменений 0), повторно использовано 0 (изменений 0), повторно использовано пакетов 0
To https://github.com/beq286/Lab2.git
 * [new branch]      main -> main
Ветка «main» отслеживает внешнюю ветку «main» из «origin».
```

```sh
$ git remote add origin https://github.com/beq286/Lab2.git
$ git branch -M main
$ git push -u origin main
```



```sh
Ветка «main» отслеживает внешнюю ветку «main» из «origin».
Everything up-to-date
```

```sh
$ git clone  https://github.com/beq286/Lab2.git
```



```sh
Клонирование в «Lab2»...
remote: Enumerating objects: 3, done.
remote: Counting objects: 100% (3/3), done.
remote: Total 3 (delta 0), reused 3 (delta 0), pack-reused 0
Получение объектов: 100% (3/3), готово.

```

3. Создайте файл `hello_world.cpp` в локальной копии репозитория . Реализуйте программу **Hello world** на языке C++ используя плохой стиль кода.

```sh
$ cd Lab2
$ touch hello_ world.cpp
```



**hello_world.cpp:**
```sh
#include <iostream>
using namespace std;

int main()
{
    cout << "Hello world!" << endl;
    return 0;
}
```


4. Добавьте этот файл в локальную копию репозитория.



```sh
$ git add hello_world.cpp
```



5. Закоммитьте изменения с *осмысленным* сообщением.

```sh
$ git commit -m "Added initial version of Hello world program with bad code style"
```


```sh
[main 6991008] Added initial version of Hello world program with bad code style
 1 file changed, 9 insertions(+)
 create mode 100644 hello_world.cpp
```
6. Изменитьте исходный код так, чтобы программа через стандартный поток ввода запрашивалось имя пользователя. А в стандартный поток вывода печаталось сообщение `Hello world from @name`, где `@name` имя пользователя.

**hello_world.cpp with greet user by name:**

```sh
#include <iostream>
#include <string>
using namespace std; 
int main()
{
  string name;
  cout << "Enter your name: ";
  cin >> name;
  cout << "Hello world from " << name << endl;
  return 0;
}
```




7. Закоммитьте новую версию программы. Почему не надо добавлять файл повторно `git add`?



```sh
$ git commit -am "Modified program to greet user by name"
```




```sh
[main 305998b] Modified program to greet user by name
 1 file changed, 5 insertions(+), 1 deletion(-)
```



Почему не надо добавлять файл повторно `git add`?


```sh
Потому что при первом добавлении файла в Git, он уже отслеживается системой контроля версий, и при последующем коммите изменений в этом файле, Git автоматически учитывает его изменения.
```



8. Запуште изменения в удалёный репозиторий.



```sh
$ git push origin main
```




```sh
Перечисление объектов: 7, готово.
Подсчет объектов: 100% (7/7), готово.
При сжатии изменений используется до 4 потоков
Сжатие объектов: 100% (6/6), готово.
Запись объектов: 100% (6/6), 806 байтов | 403.00 КиБ/с, готово.
Всего 6 (изменений 0), повторно использовано 0 (изменений 0), повторно использовано пакетов 0
To https://github.com/beq286/Lab2.git
   654292d..b21614e  main -> main

```

### Part II

**Note:** *Работать продолжайте с теми же репоззиториями, что и в первой части задания.*
1. В локальной копии репозитория создайте локальную ветку `patch1`.



```sh
$ git checkout -b patch1
```



```sh
Переключились на новую ветку «patch1»
```



2. Внесите изменения в ветке `patch1` по исправлению кода и избавления от `using namespace std;`.




**hello_world.cpp with greet user by name without `using namespace std;`:**

```sh
#include <iostream>
#include <string>

int main()
{
    std::string name;
    std::cout << "Enter your name: ";
    std::cin >> name;
    std::cout << "Hello world from " << name << std::endl;
    return 0;
}
```




```sh
$ git add .
$ git commit -m "Removed using namespace std;"
```

```sh
[patch1 664f229] Removed using namespace std;
 1 file changed, 4 insertions(+), 5 deletions(-)
```



3. **commit**, **push** локальную ветку в удалённый репозиторий.



```sh
$ git push origin patch1
```





```sh
Перечисление объектов: 5, готово.
Подсчет объектов: 100% (5/5), готово.
При сжатии изменений используется до 4 потоков
Сжатие объектов: 100% (3/3), готово.
Запись объектов: 100% (3/3), 449 байтов | 449.00 КиБ/с, готово.
Всего 3 (изменений 0), повторно использовано 0 (изменений 0), повторно использовано пакетов 0
remote: 
remote: Create a pull request for 'patch1' on GitHub by visiting:
remote:      https://github.com/beq286/Lab2/pull/new/patch1
remote: 
To https://github.com/beq286/Lab2.git
 * [new branch]      patch1 -> patch1

```

4. В локальной копии в ветке `patch1` добавьте в исходный код комментарии.



**hello_world.cpp with greet user by name, without `using namespace std;`, with commentaries:**



```sh
#include <iostream>
#include <string>

int main()
{
  std::string name;
  std::cout << "Enter your name: ";
  std::cin >> name; // write here your name, please!
  std::cout << "Hello world from " << name << std::endl;
  return 0;
}
```





```sh
$ git add .
$ git commit -m "Added comments to the code"
$ git push origin patch1
```





```sh
Перечисление объектов: 5, готово.
Подсчет объектов: 100% (5/5), готово.
При сжатии изменений используется до 4 потоков
Сжатие объектов: 100% (3/3), готово.
Запись объектов: 100% (3/3), 344 байта | 344.00 КиБ/с, готово.
Всего 3 (изменений 2), повторно использовано 0 (изменений 0), повторно использовано пакетов 0
remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
To https://github.com/beq286/Lab2.git
   f5a55bc..0e8ebc2  patch1 -> patch1

```




5. Локально выполните **pull**.



```sh
$ git checkout main  
$ git pull origin main 
```





```sh
Switched to branch 'main'
Your branch is up-to-date with 'origin/main'.
remote: Enumerating objects: 1, done.
remote: Counting objects: 100% (1/1), done.
remote: Total 1 (delta 0), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (1/1), 908 bytes | 908.00 KiB/s, done.
From https://github.com/beq286/Lab2
 * branch            main       -> FETCH_HEAD
   305998b..ec396b6  main       -> origin/main
Updating 305998b..ec396b6
Fast-forward
 hello_world.cpp | 9 ++++-----
 1 file changed, 4 insertions(+), 5 deletions(-)
```




6. С помощью команды **git log** просмотрите историю в локальной версии ветки `master`.




```sh
$ git log
```




```sh
commit b21614e1c95e2f2c9f34fe1926f6bf4462caf11e (HEAD -> main, origin/main)
Author: beq286 <beqisma@yandex.ru>
Date:   Mon Apr 15 23:37:58 2024 +0300

    Modified program to greet user by name

commit 328ce58866911eef8d843a67043f1fcd20152e6b
Author: beq286 <beqisma@yandex.ru>
Date:   Mon Apr 15 23:36:16 2024 +0300

    Added initial version of Hello world program with bad code style

commit 654292dc349c911a24e90ac93dab877e3964d4db
Author: beq286 <beqisma@yandex.ru>
Date:   Mon Apr 15 23:28:49 2024 +0300
    first commit
```





7. Удалите локальную ветку `patch1`.



```sh
$ git branch -d patch1
```




```sh
Ветка patch1 удалена (была 0e8ebc2).
```

### Part III

**Note:** *Работать продолжайте с теми же репоззиториями, что и в первой части задания.*
1. Создайте новую локальную ветку `patch2`.
```sh
git checkout -b patch2
```
2. Измените *code style* с помощью утилиты [**clang-format**](http://clang.llvm.org/docs/ClangFormat.html). Например, используя опцию `-style=Mozilla`.
3. **commit**, **push**, создайте pull-request `patch2 -> master`.



```sh
$ clang-format -i -style=Mozilla hello_world.cpp
$ git checkout -b patch2
$ git add .
$ git commit -m "Changed code style using clang-format"
```




```sh
Переключились на ветку «patch2»
[patch2 4aac1fe] Changed code style using clang-format
 1 file changed, 7 insertions(+), 7 deletions(-)
```




4. В ветке **master** в удаленном репозитории измените комментарии, например, расставьте знаки препинания, переведите комментарии на другой язык.




**hello_world.cpp with greet user by name, without `using namespace std;`, with new commentaries. Code style: clang-format:**




```sh
#include <iostream>
#include <string>

int
main()
{
  std::string name;
  std::cout << "Enter your name: ";
  std::cin >> name; // напишите имя  std::cout << "Hello world from " << name << std::endl;
  return 0;
}
```


```sh
$ git add .
$ git commit -m "Updated comments in the code"
$ git push origin main
```




```sh
[patch2 11cf720] Updated comments in the code
 1 file changed, 1 insertion(+), 1 deletion(-)
Everything up-to-date
```



```sh
git push origin patch2
```




```sh
Перечисление объектов: 8, готово.
Подсчет объектов: 100% (8/8), готово.
При сжатии изменений используется до 4 потоков
Сжатие объектов: 100% (6/6), готово.
Запись объектов: 100% (6/6), 734 байта | 367.00 КиБ/с, готово.
Всего 6 (изменений 2), повторно использовано 0 (изменений 0), повторно использовано пакетов 0
remote: Resolving deltas: 100% (2/2), completed with 1 local object.
remote: 
remote: Create a pull request for 'patch2' on GitHub by visiting:
remote:      https://github.com/beq286/Lab2/pull/new/patch2
remote: 
To https://github.com/beq286/Lab2.git
 * [new branch]      patch2 -> patch2
```



5. Для этого локально выполните **pull** + **rebase** (точную последовательность команд, следует узнать самостоятельно). **Исправьте конфликты**.

```sh
$ git checkout patch2
$ git pull --rebase origin main
$
```





```sh
From https://github.com/beq286/Lab2
 * branch            main       -> FETCH_HEAD
```

**Исправьте конфликт**.


```sh
$ git add .
   git rebase --continue
```




```sh
fatal: Нет перемещения в процессе?
```



6. Сделайте *force push* в ветку `patch2`




```sh
$    git push origin patch2 --force
```



```sh
Everything up-to-date
```

**проверка запуска программы**:


```sh
$ gcc hello_world.cpp -o hello_world -lstdc++
./hello_world
```

```sh
Enter your name: beq
Hello world from beq
```
