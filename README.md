# Если на проекте есть доступ к серверу, то тестировщик может просматривать логи или другие артефакты на нем. Для этого используют команды bash и git.
# Работа с базовыми командами bash и git

- [Вариан 1](https://github.com/user-attachments/files/21036824/bash1.txt)
- [Вариант 2](https://github.com/user-attachments/files/21036827/bash2.txt)
___
- # Пример 1
# Открыть домашнюю директорию
- cd ~

# Определить имя текущей папки
- pwd

# Создать каталог test1
- mkdir test1

# Перейти в test1
- cd test1

# Создать файлы 1, 2, 3
- touch 1 2 3

# Проверить содержимое test1
- ls

# Вернуться в домашнюю директорию
- cd ~

# Создать папку test2
- mkdir test2

# Удалить папку test2
- rmdir test2

# Удалить файл 2 из test1
- rm ~/test1/2

# Создать папку test3 и два файла внутри
- mkdir ~/test3
- touch ~/test3/filetool
- touch ~/test3/filemouse

# Удалить папку test3
- rm -r ~/test3

# Создать папку test4
- mkdir ~/test4

# Переместить файлы 1 и 3 в test4
- mv ~/test1/1 ~/test4/
- mv ~/test1/3 ~/test4/

# Добавить в файл 1 три строки со словами line
- echo -e "line\nline\nline" >> ~/test4/1

# Посмотреть содержимое файла 1
- cat ~/test4/1

# Добавить в файл 3 три строки со словами line
- echo -e "line\nline\nline" >> ~/test4/3

# Просмотреть содержимое файлов 1 и 3
- cat ~/test4/1 ~/test4/3

# Заменить все строки в файле 1 (например, на "замененная строка")
- sed -i 's/.*/chest/' ~/test4/1
___
- # Пример 2

# Создать файл bash2.txt
- touch bash2.txt

# Зайти в домашнюю директорию
- cd ~

# Создать папку test3
- mkdir test3

# В папке test3 создать файлы 4, 5, 6 с 4 строками
- touch 4
- touch 5
- touch 6
- echo -e "row\nrow\nrow\nrow" > test3/4
- echo -e "row\nrow\nrow\nrow" > test3/5
- echo -e "row\nrow\nrow\nrow" > test3/6

# Найти строку row2 в файле 5
- grep "row" test3/5

# Найти строку row в папке test3 (во всех файлах)
- grep "row" test3/*

# Посчитать сколько строк с содержимым row в файле 6
- grep -c "row" test3/6

# Найти файл 5 внутри папки test3
- find test3 -name "5"

# Удалить файл 5 с помощью find
- find test3 -name "5" -delete

# Добавить слово test в файл 4 (без сохранения содержимого)
- echo "test" > test3/4

# Заменить слово test на fail в файле 4
- sed -i 's/test/fail/' test3/4

# Добавить слово test в файл 4, сохранив содержимое
- echo "test" >> test3/4

# Просмотреть все процессы для всех пользователей
- ps aux

# Убить процесс с PID 666 
- kill 666

# Проверить доступность ресурса rusau.net с помощью ping
- ping -c rusau.net
- ping -c 5 rusau.net

# Получить информацию о зарегистрированных питомцах с любым статусом через curl (GET-запрос)
- curl -X GET "https://petstore.swagger.io/v2/pet/findByStatus?status=available"

# Создать нового пользователя через curl (POST-запрос)
- curl -X POST "https://petstore.swagger.io/v2/user" -H "Content-Type: application/json" -d '{
  "id": 12345,
  "username": "testuser",
  "firstName": "Vasya",
  "lastName": "Kamushkin",
  "email": "vasya.kamushkin@example.com",
  "password": "password123",
  "phone": "1234567890",
  "userStatus": 1
}'
___
# Команды git

# Создайте репозиторий с именем вашего пользователя
- git init osukhorukova
# Клонируйте ваш репозиторий на компьютер
- git clone git@github.com:osukhorukova/osukhorukova.git
# Клонируйте репозиторий testrusau
- git clone git@github.com:testrusau/testrusau.git
# Перейдите в папку с клонированным репозиторием testrusau
- cd testrusau
- Перенесите нужные файлы или изменения в ваш репозиторий (например, скопируйте файлы или сделайте изменения)
# Вернитесь в папку с вашим репозиторием
- cd ..
# Добавьте изменения
- git add .
# Зафиксируйте изменения с описанием
- git commit -m "Описание изменений"
# Отправьте изменения в ваш репозиторий на GitHub
- git push origin main
