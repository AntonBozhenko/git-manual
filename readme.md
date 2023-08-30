<h1 align="center">
Расширенное руководство по GIT
<br>
<image 
src="./images/git-logo.png" 
style="margin-top: 20px; width: 40vw;"
>
</h1>
    
<b style="font-size: 24px;">Разделы</b>

<details> 
<summary style="font-size: 20px;">Первоначальная настройка</summary>

*Настройка информации о пользователе для всех локальных репозиториев*

<blockquote style="margin: 0; padding: 5px">Устанавливает имя, которое будет отображаться в поле автора у выполняемых вами коммитов</blockquote>

    git config --global user.name "[имя]"

<blockquote style="margin: 0; padding: 5px">Устанавливает адрес электронной почты, который будет отображаться в информации о выполняемых вами коммитах</blockquote>

    git config --global user.email "[адрес электронной почты]"
</details>

<details>
<summary style="font-size: 20px;">Создание репозитория</summary>

*Создание нового репозитория или получение его по существующему URL-адресу*

<blockquote style="margin: 0; padding: 5px">Создаёт новый локальный репозиторий с заданным именем</blockquote>

    git init [название проекта]

<blockquote style="margin: 0; padding: 5px">Скачивает репозиторий вместе со всей его историей изменений</blockquote>

    git clone [url-адрес]

</details>

<details>
<summary style="font-size: 20px;">Внесение изменений</summary>

*Просмотр изменений и создание коммитов (фиксация изменений)*
<blockquote style="margin: 0; padding: 5px">Перечисляет все новые или изменённые файлы, которые нуждаются в фиксации</blockquote>

    git status

<blockquote style="margin: 0; padding: 5px">Показывает различия по внесённым изменениям в ещё не проиндексированных файлах</blockquote>

    git diff

<blockquote style="margin: 0; padding: 5px">Индексирует указанный файл для последующего коммита</blockquote>

    git add [файл]

<blockquote style="margin: 0; padding: 5px">Показывает различия между проиндексированной и последней зафиксированной версиями файлов</blockquote>

    git diff --staged

<blockquote style="margin: 0; padding: 5px">Отменяет индексацию указанного файла, при этом сохраняет его содержимое</blockquote>

    git reset [файл]

<blockquote style="margin: 0; padding: 5px">Фиксирует проиндексированные изменения и сохраняет их в историю версий</blockquote>

    git commit -m "[сообщение с описанием]"

</details>

<details>
<summary style="font-size: 20px;">Коллективная работа</summary>

*Именованные серии коммитов и соединение результатов работы*

<blockquote style="margin: 0; padding: 5px">Список именованных веток коммитов с указанием выбранной ветки</blockquote>

    git branch

<blockquote style="margin: 0; padding: 5px">Создаёт новую ветку</blockquote>

    git branch [имя ветки]

<blockquote style="margin: 0; padding: 5px">Переключается на выбранную ветку и обновляет рабочую директорию до её состояния</blockquote>

    git switch -c [имя ветки]

<blockquote style="margin: 0; padding: 5px">Вносит изменения указанной ветки в текущую ветку</blockquote>

    git merge [имя ветки]

<blockquote style="margin: 0; padding: 5px">Удаляет выбранную ветку</blockquote>

    git branch -d [имя ветки]

</details>

<details>
<summary style="font-size: 20px;">Операции с файлами</summary>

*Перемещение и удаление версий файлов репозитория*

<blockquote style="margin: 0; padding: 5px">Удаляет конкретный файл из рабочей директории и индексирует его удаление</blockquote>

    git rm [файл]

<blockquote style="margin: 0; padding: 5px">Убирает конкретный файл из контроля версий, но физически оставляет его на своём месте</blockquote>

    git rm --cached [файл]

<blockquote style="margin: 0; padding: 5px">Перемещает и переименовывает указанный файл, сразу индексируя его для последующего коммита</blockquote>

    git mv [оригинальный файл] [новое имя]

</details>

<details>
<summary style="font-size: 20px;">Игнорирование некоторых файлов</summary>

*Исключение временных и вторичных файлов и директорий*

<blockquote style="margin: 0; padding: 5px">Git будет игнорировать файлы и директории, перечисленные в файле .gitignore с помощью wildcard синтаксиса</blockquote>

    *.log
    build/
    temp-*

<blockquote style="margin: 0; padding: 5px">Список всех игнорируемых файлов в текущем проекте</blockquote>

    git ls-files --others --ignored --exclude-standard

</details>

<details>
<summary style="font-size: 20px;">Сохранение фрагментов</summary>

*Сохранение и восстановление незавершённых изменений*  

<blockquote style="margin: 0; padding: 5px">Временно сохраняет все незафиксированные изменения отслеживаемых файлов</blockquote>

    git stash

<blockquote style="margin: 0; padding: 5px">Восстанавливает состояние ранее сохранённых версий файлов</blockquote>

    git stash pop

<blockquote style="margin: 0; padding: 5px">Выводит список всех временных сохранений</blockquote>

    git stash list

<blockquote style="margin: 0; padding: 5px">Сбрасывает последние временно сохранённыe изменения</blockquote>

    git stash drop

</details>

<details>
<summary style="font-size: 20px;">Просмотр истории</summary>

*Просмотр и изучение истории изменений файлов проекта*

<blockquote style="margin: 0; padding: 5px">История коммитов для текущей ветки</blockquote>

    git log

<blockquote style="margin: 0; padding: 5px">История изменений конкретного файла, включая его переименование</blockquote>

    git log --follow [файл]

<blockquote style="margin: 0; padding: 5px">Показывает разницу между содержанием коммитов двух веток</blockquote>

    git diff [первая ветка]...[вторая ветка]

<blockquote style="margin: 0; padding: 5px">Выводит информацию и показывает изменения в выбранном коммите</blockquote>

    git show [коммит]

</details>

<details>
<summary style="font-size: 20px;">Откат коммитов</summary>

*Удаление ошибок и корректировка созданной истории*

<blockquote style="margin: 0; padding: 5px">Отменяет все коммиты после заданного, оставляя все изменения в рабочей директории</blockquote>

    git reset [коммит]

<blockquote style="margin: 0; padding: 5px">Сбрасывает всю историю вместе с состоянием рабочей директории до указанного коммита.</blockquote>

    git reset --hard [коммит]

</details>

<details>
<summary style="font-size: 20px;">Синхронизация с удалённым репозиторием</summary>

*Регистрация удалённого репозитория и обмен изменениями*

<blockquote style="margin: 0; padding: 5px">Скачивает всю историю из удалённого репозитория</blockquote>

    git fetch [удалённый репозиторий]

<blockquote style="margin: 0; padding: 5px">Вносит изменения из ветки удалённого репозитория в текущую ветку локального репозитория</blockquote>

    git merge [удалённый репозиторий]/[ветка]

<blockquote style="margin: 0; padding: 5px">Загружает все изменения локальной ветки в удалённый репозиторий</blockquote>

    git push [удалённый репозиторий] [ветка]

<blockquote style="margin: 0; padding: 5px">Загружает историю из удалённого репозитория и объединяет её с локальной. pull = fetch + merge</blockquote>

    git pull

</details>
