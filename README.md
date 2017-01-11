1C:Enterprise 8. Tech Journal loader<br/>
Приложение позволяет выполнить разбор текстовых файлов технологического журнала с расширением *.log на события и записать эти события в таблицу базы MS SQL.
Обработка файлов производится в многопоточном режиме, что позволяет загружать большие объемы информации за относительно небольшое время.<br/>
Для начала использования приложения требуется:<br/>
1) создать на сервере MS SQL новую пустую базу<br/>
2) заполнить строку соединения с сервером по шаблону:<br/>
для windows-авторизации Data Source=MSSQL1;Server=имя сервера;Database=имя базы;Integrated Security=true;<br/>
для обычной авторизации  Data Source=MSSQL1;Server=имя сервера;Database=имя базы;Password=Пароль;User ID=Имя пользователя;<br/>
3) нажать кнопку "Создать служебную таблицу" для создания целевой таблицы для событий<br/>
<br/>
Порядок загрузки файлов:<br/>
1) указать строку соединения как описано выше;<br/>
2) указать каталог, содержащий файлы тех.журнала с расширением *.log, вложенные каталоги обрабатываются рекурсивно;<br/>
3) указать число параллельных потоков, в которых программа будет обрабатывать файлы. Диапазон от 1 до 100, но ставить больше 20-30 нет особого смысла, хотя все зависит от конкретной машины, на которой выполняется запуск.<br/>
4) нажать кнопку "Заполнить список файлов" - программа найдет все файлы ТЖ в указанном каталоге и отобразит их список;<br/>
5) нажать кнопку "Запустить разбор" - программа начнет параллельное чтение файлов, их разбор и запись полученных событий в структурированном виде в базу данных.<br/>
<br/>
Исходные коды опубликованы по лицензии GNU GPL - https://ru.wikipedia.org/wiki/GNU_General_Public_License<br/>
Информация об ошибках и опыте применения приветствуется в комментариях к публикации http://infostart.ru/public/117023/<br/>
