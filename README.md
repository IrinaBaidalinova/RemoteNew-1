Logo
Работа с Git и GitHub
Проверка наличия установленного Git В терминале выполнить команду git version Если Git установлен появиться сообщние с информацией о версии программы. Иначе будет сообщение с ошибкой.
2. Установка Git
Загружаем последнюю версию Git с сайта https://git-scm.com/downloads. Устанавливаем с настройками по умолчанию.

3. Настройка Git
При первом использовании Git неоходимо прдставиться. Для этого нужно ввести в терминале две команды:

git config --global user.name «Ваше имя английскими буквами»
git config --global user.email ваша почта@example.com
4. Инициализация ропозитория
Получить репозиторий можно двумя способами.

В терминале перейти к папке, в которой хотим создать репозиторий. Выполняем команду:
git init
В исходной папке появиться скрытая папка .git 2. Клонировать существующий репозиторий Git из любого места. Сделать это можно с помощью команды:

git clone <адрес репозитория>
5. Запись изминений в репозиторий
1.Для того, что бы зафиксировать изменения, необходимо выбрать то что нужно сохранить и выполнить .commit. Для выбора нужных изменений из совершенных испульзуется команда .git add 2.Все файлы в рабочей директории могут находится в двух состояниях:

- Под контролем системы упрвления.
- Не под контролем системы упрвления.
2.1 Что бы проверить статус файла под контолем системы он или нет, нужно нажать комманду git status

В случае с новыми файлами - ..добавление файла под версинонный контроль осуществляется коммандой git add 4.После комманды *git add* вводим комманду git commit -m "Комментарий к изменению"
6. Шпаргалка по основным командам
git add
Команда git add добавляет содержимое рабочей директории в индекс (staging area) для последующего коммита. По умолчанию git commit использует лишь этот индекс, так что вы можете использовать git add для сборки слепка вашего следующего коммита.

git status
Команда git status показывает состояния файлов в рабочей директории и индексе: какие файлы изменены, но не добавлены в индекс; какие ожидают коммита в индексе. Вдобавок к этому выводятся подсказки о том, как изменить состояние файлов.

git diff
Команда git diff используется для вычисления разницы между любыми двумя Git деревьями. Это может быть разница между вашей рабочей директорией и индексом (собственно git diff), разница между индексом и последним коммитом (git diff --staged), или между любыми двумя коммитами (git diff master branchB).

git difftool
Команда git difftool просто запускает внешнюю утилиту сравнения для показа различий в двух деревьях, на случай если вы хотите использовать что-либо отличное от встроенного просмотрщика git diff.

git commit
Команда git commit берёт все данные, добавленные в индекс с помощью git add, и сохраняет их слепок во внутренней базе данных, а затем сдвигает указатель текущей ветки на этот слепок.

git reset
Команда git reset, как можно догадаться из названия, используется в основном для отмены изменений. Она изменяет указатель HEAD и, опционально, состояние индекса. Также эта команда может изменить файлы в рабочей директории при использовании параметра --hard, что может привести к потере наработок при неправильном использовании, так что убедитесь в серьёзности своих намерений прежде чем использовать его.

git log
Команда git log перечисляет коммиты, сделанные в репозитории в обратном к хронологическому порядке — последние коммиты находятся вверху.

git rm
Команда git rm используется в Git для удаления файлов из индекса и рабочей директории. Она похожа на git add с тем лишь исключением, что она удаляет, а не добавляет файлы для следующего коммита.

git mv
Команда git mv — это всего лишь удобный способ переместить файл, а затем выполнить git addдля нового файла и git rm для старого.

git clean
Команда git clean используется для удаления мусора из рабочей директории. Это могут быть результаты сборки проекта или файлы конфликтов слияний.

7. Просмотр истории коммитов
После того, как создали несколько коммитов или же клонировали репозиторий с уже существующей историей коммитов, вероятно вам понадобится возможность посмотреть что было сделано — историю коммитов. Одним из основных и наиболее мощных инструментов для этого является команда

git log
8. Перемещение между сохранениями (коммитами)
Git сохраняет изменения в файле в репозитории целиком, что позволяет перемещаться между коммитами командой git checkout [name branch]. Узнать хеш коммита можно командой git log. Перемещаться между коммитами можно для просмотра удаленных частей кода или восстановления удаленных файлов. Премещение по веткам

9. Игнорирование файлов
Для того что бы исключить из отслеживания определенные файлы или папки необходимо создать там фаил .gitignore и записать в него их название или шаблоны. К шаблонам в файле .gitignore применяются следующие правила:

Пустые строки, а также строки, начинающиеся с #, игнорируются.
Можно использовать стандартные glob шаблоны.
Можно заканчивать шаблон символом слэша (/) для указания каталога.
Можно инвертировать шаблон, использовав восклицательный знак (!) в качестве первого символа.  
10. Создание веток в Git
Ветка «master» в Git — это не какая-то особенная ветка. Она точно такая же, как и все остальные ветки. Она существует почти во всех репозиториях только лишь потому, что её создаёт команда git init, а большинство людей не меняют её название. Создать новую ветку можно командой:

git branch + name branch
Список веток в репозитории можно посмотреть с помощью команды git branch. Текущая ветка будет отмечена звездочкой: * master Второй вариант создания ветки можно с помощью команды :

 *Gt checkout -b + name branch* (данная команда позволяет создать и перейти в ветку)
11. Слияние веток и разрешение конфликтов
Для слияния выбронной ветки с текущей нужно вымолнить команду:

git merge + name branch
Если была изменена одна и таже часть файла в обеих ветках, то может возникнуть конфликт, потребует участие пользователя. VSCod Предлагает варианты разрешения:

Принять входящие изминения.
Оставить без изминений.
Оставить оба изминения.
Сравнить изминения. Чтобы разрешить конфликт нужно выбрать один из вариантов, либо объеденить содержимое по-своему.
12. Удаление веток
Чтобы удалить локальную ветку, мы можем использовать git-branch команда с -d или же -D вариант.

git branch (-d | -D) <branchname>
Опция -d-D это псевдоним для --delete (--force), которые позволяют удалять ветку незовисимо от ее статуса слияние:

git branch -D + name branch
Чтобы удалить удаленные ветки с помощью git-branch команда, укажите -r вариант вместе с -d вариант.

git branch -d -r <branchname>
13 Работа с удаленными репозиториями
Чтобы добавить новый удаленный репозиторий, выполните команду git remote add в терминале в каталоге, в котором хранится репозиторий.

Команда git remote add принимает два аргумента:

имя удаленного репозитория, например, origin; URL-адрес удаленного репозитория, например, https://github.com/OWNER/REPOSITORY.git. Пример:

$ git remote add origin https://github.com/OWNER/REPOSITORY.git
# Set a new remote
$ git remote -v

Verify new remote
origin https://github.com/OWNER/REPOSITORY.git (fetch) origin https://github.com/OWNER/REPOSITORY.git (push)

14 Заключение.
Вот и все! Наше руководство окончено. Мы очень старались собрать всю самую важную информацию и изложить ее как можно более сжато и кратко. Git довольно сложен, и в нем есть еще много функций и трюков. Finish
