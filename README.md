 

linux_hints
======
{tested of centOS v.7}

Описание
------ 
Примеры использования команд Linux в личных целях:

### date

- Установка времени (если нет ntp-сервера)

```sh
			date -s 17:00:00
```

### setfacl

- Добавление\изменение acl-правила для пользователя

```sh
			setfacl -m u:uname:rX file_name
```

- Добавление\изменеие acl-правила для группы

```sh
			setfacl -m g:gname:rw file_name
```

- Добавление\изменение acl-правила для остальных

```sh
			setfacl -m o::- file_name
```

- Добавление\изменение нескольких правил

```sh
			setfacl -m u::rwx,g:students:rX,o::- file_name
```

- Копирование acl-правил с одного файла и применение их для другого

```sh
			getfacl file_name1 | setfacl --set-file=- file_name2
```

- Настройка маски acl-правил для файла (запрет не явного изменения маски)

```sh
			setfacl -m m::r[n] file_name
```

- Рекурсивное задание acl-правила для всех вложений директории

```sh
			setfacl -R u:uname:rX dir_name
```

- Удаление acl-правил для заданного пользователя

```sh
			setfacl -x u:uname file_name
```

- Удаление acl-правил для заданной группы

```sh
			setfacl -x g:gname file_name
```

- Добавление acl-правила 'по-умолчанию'

```sh
			setfacl -m d:u:uname:rx dir_name
```

- Удаление acl-правила 'по-умолчанию'

```sh
			setfacl -x d:u:uname dir_name
```

- Удаление всех acl-правил 'по-умолчанию'

```sh
			setfacl -k /dir_name
```

- Удаление acl-каталога

```sh
			setfacl -b /dir_name
```

Лицензионное соглашение
------
Эту справочную информацию можно использовать бесплатно по лицензии **MIT**.