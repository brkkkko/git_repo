# Что такое Git
Git — самая популярная распределённая система контроля версиями.

Проект был создан Линусом Торвальдсом для управления разработкой ядра Linux, первая версия выпущена 7 апреля 2005 года. На сегодняшний день его поддерживает Джунио Хамано.

# Подготовка репозитория

Для создания нового репозитория используется команда **git init**. Команду **git init** выполняют только один раз для изначальной настройки нового репозитория. Выполнение команды приведет к созданию нового подкаталога *.git* в вашем рабочем каталоге. Кроме того, будет создана новая главная ветка.

 Создание "сохранений"
Команда **git add** добавляет изменение из рабочего каталога в раздел проиндексированных файлов. Она сообщает Git, что вы хотите сделать изменения в конкретном файле в следующий коммит. Но на самом деле команда git add не оказывает существенного влияния на репозиторий: изменения регистрируются в нем только после выполнения команды **git commit**.

>**git commit**

Коммит проиндексированного состояния кода. Эта команда откроет текстовый редактор с предложением ввести комментарий к коммиту. После ввода комментария сохраните файл и закройте текстовый редактор, чтобы выполнить коммит.

>**git commit -a**

Выполнение коммита состояния со всеми изменениями в рабочем каталоге. Эта команда включает только изменения отслеживаемых файлов (тех, которые были в какой-то момент добавлены в историю с помощью команды git add).

>**git commit -m "commit message"**

Быстрая команда, которая создает коммит с указанным комментарием. По умолчанию команда git commit открывает локально настроенный текстовый редактор с предложением ввести комментарий к коммиту. При передаче параметра -m текстовый редактор не открывается, а используется подставленный комментарий.

>**git branch**

Это команда для управления ветками в репозитории Git.

Ветка в Git'е — это просто «скользящий» указатель на один из коммитов. Когда вы создаёте новые коммиты, указатель ветки автоматически сдвигается вперёд, к вновь созданному коммиту.

Ветка, создаваемая первой в новом репозитории, по умолчанию называется master.

Чтобы создать новую ветку:

>**git branch <branch-name>**

Просмотреть список всех веток в текущем репозитории:

>**git branch**

То же, включая удаленные (remote) ветки:

>**git branch --all**

Переключиться на другую ветку:

>**git checkout <имя-ветки>**

Создать новую ветку, указывающую на текущий HEAD:

>**git branch <имя-новой-ветки>**

То же, плюс переключиться на нее одной командой:

>**git checkout -b <имя-новой-ветки>**

Удалить ветку:

>**git branch -d <имя-ветки>**

Взять текущие изменения (после последнего коммита) и создать из них новую ветку:

>**git stash**

>**git stash branch <имя-ветки>**

# Переключение между "сохранениями"
Команда **git checkout** позволяет перемещаться между ветками, созданными командой **git branch**. При переключении ветки происходит обновление файлов в рабочем каталоге в соответствии с версией, хранящейся в этой ветке, а Git начинает записывать все новые коммиты в этой ветке. Рассматривайте эту команду как способ выбрать направление своей разработки.

Иногда команду **git checkout** можно спутать с командой **git clone**. Разница между этими двумя командами заключается в том, что при клонировании (clone) выполняется извлечение кода из удаленного репозитория, тогда как при переключении (checkout) происходит переключение между версиями кода, который уже находится в локальной системе.

Команда **git checkout** часто используется вместе с командой **git branch**. С помощью команды **git branch** можно создать новую ветку. Когда вы захотите начать работу над новой функцией, создайте новое ответвление от ветки main с помощью команды **git branch new_branch**. Затем переключитесь на новую ветку с помощью команды **git checkout new_branch**. Команда **git checkout** также принимает аргумент **-b**, который действует как вспомогательный метод, позволяя создать новую ветку и сразу переключиться на нее. Вы можете работать сразу с несколькими функциями в одном репозитории, переключаясь между ними с помощью **git checkout**.
