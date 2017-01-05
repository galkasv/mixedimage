# mixedimage

mixedImage - modx custom TV  

![mixedImage](mixedImage-logo_small.png)



##### Скриншот
![mixedImage](mixedImage.png)

Добавляет новый тип TV поля: **Смешанная загрузка файла/Mixed Image Input**

*Является сместью FastUploadTV и стандартной загрузки файлов, часть кода взята из [FastUploadTV](https://github.com/promo360/fastuploadtv)*

Данный тип поля позволяет прикреплять изображения к ресурсам используя стандартный менеджер файлов, либо напрямую с компьютера пользователя, минуя все остальные шаги.
Предназначен для загрузки изображений, но может загружать и другие типы файлов, разрешенные для загрузки в системных настройках сайта, но в данном случае необходимо отключить показ миниатюр, чтобы не было битой картинки.

#### При создании TV такого типа можно указать следующие настройки: 

**- Путь сохранения** - папку в которую будут загружаться картинки с компьютера пользователя (ВАЖНО: при указании источника файлов отличным от стандартного, этот путь будет браться с учетом папки источника файлов)
*Например вы создали новый источник файлов IMAGES и указали ему путь assets/images/ (в настройках источника файлов), а в поле Путь сохранения указали папку uploads/ - итоговая папка загрузки файлов будет такой: assets/images/uploads/*

**- Префикс имени файла** - добавляет данную строку в начало наименования файла, можно использовать различные плейсхолдеры. Пример: {rand}_

* {id} - ID ресурса
* {pid} - ID ресурса родителя
* {alias} - Алиас ресурса
* {palias} - Алиас ресурса родителя
* {tid} - ID доп. поля (tv)
* {uid} - ID юзера
* {rand} - Случайная строка *(количество символов указывается в системных настройках)*
* {t} - Время в формате timestamp
* {y} - Год
* {m} - Месяц
* {d} - День
* {h} - Час
* {i} - Минута
* {s} - Секунда

**- Принимаемые типы MIME** - указывает какие типы файлов можно загружать (по умолчанию те что указаны в системных настройках modx)
*Например: image/jpeg, image/png, application/pdf*

**- Использовать префикс как имя файла** - позволяет не обращать внимания на пользовательское название файла и полностью заменить его на значение из поля **Префикс имени файла**

**- Показать изображение** - выводить под полем изображение миниатюры или нет *(по умолчанию выводит)*. 

**- Показывать значение TV** - выводить под полем путь к загруженному файлу или нет *(по умолчанию выводит)*

---------

###Системные настройки

**- mixedimage.random_lenght** - Длина строки для плейсхолдера {rand} 

**- mixedimage.translit** - Транслитерация файлов, позволяет заменять кириллицу на латиницу в названии файла во избежание возможных проблем на некоторых хостингах. Настройка работает только при установленном дополнении "translit"