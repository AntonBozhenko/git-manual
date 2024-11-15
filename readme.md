<h1 align="center">
Расширенное руководство по GIT
<br>
<image 
src="./images/git-logo.png" 
style="margin-top: 20px; width: 30vw;"
>
</h1>
    
<b style="font-size: 24px;">Разделы</b>

<details> 
<summary style="font-size: 20px;">Установка</summary>

*Установка Git на компьютер*

<blockquote style="margin: 0; padding: 5px">
    <h3>Установка Git на Windows</h3>
    <ol>
        <li>Перейдите на официальный сайт Git по ссылке https://git-scm.com/</li>
        <li>Нажмите на кнопку "Downloads" и выберите версию для установки на вашу операционную систему.</li>
        <li>Запустите загруженный файл и следуйте инструкциям установщика</li>
        <li>После установки, откройте командную строку и введите команду <code>git --version</code>, чтобы проверить, что Git установлен</li>
    </ol>
</blockquote>

<blockquote style="margin: 0; padding: 5px">
    <h3>Установка Git на Mac</h3>
    <ol>
        <li>Откройте терминал</li>
        <li>Установите Homebrew, если он еще не установлен, введя в терминале команду <code>/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"</code></li>
        <li>Установите Git, введя в терминале команду <code>brew install git</code></li>
        <li>После установки, откройте терминал и введите команду <code>git --version</code>, чтобы проверить, что Git установлен</li>
    </ol>
</blockquote>

</details>

<details> 
<summary style="font-size: 20px;">Первоначальная настройка</summary>

*Настройка информации о пользователе для всех локальных репозиториев*

<blockquote style="margin: 0; padding: 5px">Устанавливает имя, которое будет отображаться в поле автора у выполняемых вами коммитов</blockquote>

    git config --global user.name "[имя]"

<blockquote style="margin: 0; padding: 5px">Устанавливает адрес электронной почты, который будет отображаться в информации о выполняемых вами коммитах</blockquote>

    git config --global user.email "[адрес электронной почты]"
    
</details>

<details> 
<summary style="font-size: 20px;">Генерация ssh-ключа</summary>

*Генерация ssh-ключа для использования на Github(или подобных сервисах)*

<blockquote style="margin: 0; padding: 5px">
    <h3>На Windows</h3>
    <ol>
        <li>Откройте Git Bash</li>
        <li>Введите команду <code>ssh-keygen -t rsa -b 4096 -C "your_email@example.com"</code>. Эта команда создаст новый SSH-ключ с указанным email-адресом</li>
        <li>Нажмите Enter, чтобы сохранить ключ в файл по умолчанию. Обычно это C:\Users\your_username\.ssh\id_rsa</li>
        <li>Введите парольную фразу, если хотите добавить дополнительный уровень безопасности и нажмите Enter. Это необязательно, но рекомендуется</li>
        <li>Добавьте ключ в ssh-agent с помощью команды <code>eval "$(ssh-agent -s)"</code> и <code>ssh-add ~/.ssh/id_rsa</code>. Это позволит использовать ключ без необходимости вводить парольную фразу каждый раз</li>
        <li>Скопируйте содержимое файла id_rsa.pub в буфер обмена. Вы можете сделать это с помощью команды <code>clip < ~/.ssh/id_rsa.pub</code></li>
        <li>Откройте GitHub(или другой подобный сервис) и перейдите в настройки своей учетной записи</li>
        <li>Нажмите на "SSH and GPG keys" и затем на "New SSH key"</li>
        <li>Введите заголовок и вставьте содержимое файла id_rsa.pub</li>
        <li>Нажмите "Add SSH key"</li>
    </ol>
</blockquote>

<blockquote style="margin: 0; padding: 5px">
    <h3>На Mac</h3>
    <ol>
        <li>Откройте терминал</li>
        <li>Введите команду <code>ssh-keygen -t rsa -b 4096 -C "your_email@example.com"</code> Эта команда создаст новый SSH-ключ с указанным email-адресом</li>
        <li>Нажмите Enter, чтобы сохранить ключ в файл по умолчанию. Обычно это ~/.ssh/id_rsa</li>
        <li>Введите парольную фразу, если хотите добавить дополнительный уровень безопасности и нажмите Enter. Это необязательно, но рекомендуется</li>
        <li>Добавьте ключ в ssh-agent с помощью команды <code>eval "$(ssh-agent -s)"</code> и <code>ssh-add -K ~/.ssh/id_rsa</code> Это позволит использовать ключ без необходимости вводить парольную фразу каждый раз</li>
        <li>Скопируйте содержимое файла id_rsa.pub в буфер обмена. Вы можете сделать это с помощью команды <code>pbcopy < ~/.ssh/id_rsa.pub</code></li>
        <li>Откройте GitHub(или другой подобный сервис) и перейдите в настройки своей учетной записи</li>
        <li>Нажмите на "SSH and GPG keys" и затем на "New SSH key"</li>
        <li>Введите заголовок и вставьте содержимое файла id_rsa.pub</li>
        <li>Нажмите "Add SSH key"</li>
    </ol>
</blockquote>

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
<summary style="font-size: 20px;">Работа с тегами</summary>

*Использование тегов на проекте*

<blockquote style="margin: 0; padding: 5px">
   Теги в Git - это ссылки на определенные моменты в истории Git. Они используются для создания снимков состояния репозитория Git и помечают определенные моменты в истории как важные. Теги могут быть аннотированными или облегченными. Аннотированные теги содержат дополнительную информацию, такую как имя тега, дату создания и сообщение описания. Облегченные теги - это просто ссылки на коммиты.
</blockquote>

<blockquote style="margin: 0; padding: 5px">
   Теги могут использоваться для различных целей, например, для пометки релизов, версий, важных моментов в истории проекта и т.д.. Использование тегов может помочь разработчикам ориентироваться в истории проекта и быстро находить нужные моменты.
</blockquote>

<blockquote style="margin: 0; padding: 5px">Просмотр имеющихся тегов</blockquote>

    git tag

<blockquote style="margin: 0; padding: 5px">Создание нового облегченного тега (например v1.0)</blockquote>

    git tag <tag_name>

<blockquote style="margin: 0; padding: 5px">Создание нового аннотированного тега (после выполнения откроется текстовый редактор, где нужно будет ввести сообщение описания тега)</blockquote>

    git tag -a <tag_name> -m "<tag_message>"

<blockquote style="margin: 0; padding: 5px">Удаление существующего тега</blockquote>

    git tag -d <tag_name>

<blockquote style="margin: 0; padding: 5px">Отправка тегов на сервер</blockquote>

    git push --tags

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
