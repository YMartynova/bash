<h1><img src="https://upload.wikimedia.org/wikipedia/commons/thumb/4/4b/Bash_Logo_Colored.svg/1024px-Bash_Logo_Colored.svg.png?20180723054350" title="bash" alt="bash" width="40" height="40"/> bash</h1>

Тестировщики часто используют Bash для работы с логами, тестирования API, взаимодействия с базами данных и автоматизации процессов. В ходе обучения я применяла базовые команды для решения различных практических задач.
```bash
cd ~                                  # Открыть домашнюю директорию через терминал 
pwd                                   # Определить имя папки, в которой вы находитесь
mkdir test1                           # Создать внутри этой папки каталог с именем test1
cd test1                              # Перейти в папку test1
touch 1 2 3                           # Создать файл 1,2 и 3 внутри каталога test1
ls                                    # Проверить содержимое каталога test1 
mkdir test2                           # Создать папку test2 внутри домашней директории
rmdir test2                           # Удалить папку test2
cd test1                              # Удалить файл 2 из папки test1
rm 2
mkdir ~/test3                         # Создать папку в домашней директории test3 и добавить в нее два файла
cd ~/test3
touch file1 file2                   
cd ~                                  # Удалить папку test3
rm -r test3
rmdir -rf test3                       
mkdir ~/test4                         # Создать папку test4 в домашней директории
mv ~/test1/1 ~/test1/3 ~/test4        # Переместить файлы 1 и 3 из папки test1 в папку test4
cd test4                              # Добавить в файл 1 три строки со словами line
echo -e "line\nline\nline" >> 1            
cat 1                                 # Посмотреть содержимое файла 1
echo -e "line\nline\nline" >> 3       # Добавьте в файл 3 три строки со словами line
cat 1 3                               # Просмотрите содержимое двух файлов (1 и 3) сразу
nano 1                                # Используя один из редакторов замените все строки в файле 1
```
```bash
mkdir test3                           # Создать папку test 3 
echo -e "row1\nrow2\nrow3\nrow4" > 4  # Добавить в папку test3 файлы: 4,5 и 6, в каждом должно быть по 4 строки
echo -e "row1\nrow2\nrow3\nrow4" > 5    
echo -e "row1\nrow2\nrow3\nrow4" > 6 
grep "row2" 5                         # Найдите строку row2 в файле 5 
grep "row" test3/*                    # Найдите строку row в папке test3
grep -c "row" test3/6                 # Посчитайте сколько строк с содержимым row в файле 6
find test3 -type f -name "5"          # Найдите файл 5 внутри папки test3
find test3 -type f -name "5"          # Используя команду find, удалите файл 5
-exec rm {} \;              
echo "test" > 4                       # Используя echo, добавьте test в файл 4 (без сохранения содержимого)
find test3 -type f -name "4" -exec    # Замените слово test в файле 4 на fail
sed -i '' 's/test/fail/g' {} \;                 
echo "test" >> 4                      # Добавьте в файл 4 слово test так, чтобы сохранилось содержимое
ps aux                                # Просмотрите все процессы, которые происходят в системе
kill 666                              # Убейте процесс 666 в консоли
ping rusau.net                        # Узнайте доступность ресурса rusau.net, используя ping
ping -c 5 rusau.net                   # Отправьте 5 пакетов на сайт rusau.net 
```
```bash
### API testing
# Используя GET и curl, получите информацию о питомцах с любым статусом на https://petstore.swagger.io/                            
curl -X 'GET' \                      
  'https://petstore.swagger.io/v2/pet/findByStatus?status=available,sold,pending' \
  -H 'accept: application/json'

# Используя POST и команду curl, создайте нового пользователя на https://petstore.swagger.io/
curl -X 'POST' \                    
  'https://petstore.swagger.io/v2/user' \
  -H 'accept: application/json' \
  -H 'Content-Type: application/json' \
  -d '{
  "id": 1456,
  "username": "Ianch",
  "firstName": "Iana",
  "lastName": "Martynova",
  "email": "test@email.com",
  "password": "qwer",
  "phone": "+79990000000",
  "userStatus": 0
}'
```
