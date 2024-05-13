## Laboratory work II
### Part I

1. Создайте пустой репозиторий на сервисе github.com (или gitlab.com, или bitbucket.com).
https://github.com/grigsha/lab02.git
2. Выполните инструкцию по созданию первого коммита на странице репозитория, созданного на предыдещем шаге.
git add .
git commit -m "a"
git remote add origin
git push -u origin main
3. Создайте файл `hello_world.cpp` в локальной копии репозитория (который должен был появиться на шаге 2). Реализуйте программу **Hello world** на языке C++ используя плохой стиль кода. 
cat > Hello_world.cpp <<EOF
#include <iostream>

using namespace std;

int main(){
cout << "Hello world" << endl;
}

EOF
4. Добавьте этот файл в локальную копию репозитория.
git add Hello-world.cpp
5. Закоммитьте изменения с *осмысленным* сообщением.
git commit -m "Added new cpp file"
6. Изменитьте исходный код так, чтобы программа через стандартный поток ввода запрашивалось имя пользователя. А в стандартный поток вывода печаталось сообщение `Hello world from @name`, где `@name` имя пользователя.
cat > Hello_world.cpp <<EOF
#include <iostream>
#include <string> 

using namespace std;
ы
int main(){
string name;
cout << "enter name: " << endl;
cin >> name;
cout << "Hello world " << name << endl;
}
EOF

7. Закоммитьте новую версию программы. Почему не надо добавлять файл повторно `git add`? Повторно писать команду git add не надо, так как файл уже был добавлен в шаге 4.
git commit -m "Changed cpp file"
8. Запуште изменения в удалёный репозиторий.
git push origin
9. Проверьте, что история коммитов доступна в удалёный репозитории.
git log
commit b1e9365b53fe982c6437862d551fc11d733143b9 (HEAD -> main, origin/main, orig
commit b1e9365b53fe982c6437862d551fc11d733143b9 (HEAD -> main, origin/main, orig
commit b1e9365b53fe982c6437862d551fc11d733143b9 (HEAD -> main, origin/main, orig
commit b1e9365b53fe982c6437862d551fc11d733143b9 (HEAD -> main, origin/main, orig
commit b1e9365b53fe982c6437862d551fc11d733143b9 (HEAD -> main, origin/main, orig
commit b1e9365b53fe982c6437862d551fc11d733143b9 (HEAD -> main, origin/main, orig
commit b1e9365b53fe982c6437862d551fc11d733143b9 (HEAD -> main, origin/main, orig
commit b1e9365b53fe982c6437862d551fc11d733143b9 (HEAD -> main, origin/main, orig
commit b1e9365b53fe982c6437862d551fc11d733143b9 (HEAD -> main, origin/main, orig
commit b1e9365b53fe982c6437862d551fc11d733143b9 (HEAD -> main, origin/main, orig
commit b1e9365b53fe982c6437862d551fc11d733143b9 (HEAD -> main, origin/main, orig
in/HEAD)
Author: grigsha <mari.aa05@mail.ru>
Date:   Mon May 13 11:17:37 2024 +0300

    Changed cpp file

commit b2c785378f59598588cce5414840c02b165c78cf
Author: grigsha <mari.aa05@mail.ru>
Date:   Mon May 13 11:02:14 2024 +0300

    Added new cpp file

commit 4e4ad28c75649c222248be34b1f7933f7785d465
Author: grigsha <mari.aa05@mail.ru>
Date:   Mon May 13 10:55:00 2024 +0300

    a

commit 62bd6376804a675e472e83eb635be8ca314485a5
Author: grigsha <144799664+grigsha@users.noreply.github.com>
Date:   Sun May 12 03:17:51 2024 +0300

    Initial commit

### Part II

**Note:** *Работать продолжайте с теми же репоззиториями, что и в первой части задания.*
1. В локальной копии репозитория создайте локальную ветку `patch1`.
2. Внесите изменения в ветке `patch1` по исправлению кода и избавления от `using namespace std;`.
3. **commit**, **push** локальную ветку в удалённый репозиторий.
4. Проверьте, что ветка `patch1` доступна в удалёный репозитории.
5. Создайте pull-request `patch1 -> master`.
6. В локальной копии в ветке `patch1` добавьте в исходный код комментарии.
7. **commit**, **push**.
8. Проверьте, что новые изменения есть в созданном на **шаге 5** pull-request
9. В удалённый репозитории выполните  слияние PR `patch1 -> master` и удалите ветку `patch1` в удаленном репозитории.
10. Локально выполните **pull**.
11. С помощью команды **git log** просмотрите историю в локальной версии ветки `master`.
12. Удалите локальную ветку `patch1`.

### Part III

**Note:** *Работать продолжайте с теми же репоззиториями, что и в первой части задания.*
1. Создайте новую локальную ветку `patch2`.
2. Измените *code style* с помощью утилиты [**clang-format**](http://clang.llvm.org/docs/ClangFormat.html). Например, используя опцию `-style=Mozilla`.
3. **commit**, **push**, создайте pull-request `patch2 -> master`.
4. В ветке **master** в удаленном репозитории измените комментарии, например, расставьте знаки препинания, переведите комментарии на другой язык.
5. Убедитесь, что в pull-request появились *конфликтны*.
6. Для этого локально выполните **pull** + **rebase** (точную последовательность команд, следует узнать самостоятельно). **Исправьте конфликты**.
7. Сделайте *force push* в ветку `patch2`
8. Убедитель, что в pull-request пропали конфликтны. 
9. Вмержите pull-request `patch2 -> master`.

