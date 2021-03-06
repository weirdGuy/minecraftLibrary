# Minecraft Personal Area Library
**MPAL** — это библиотека для создателей личных кабинетов, главная цель которой, максимально упростить создание онных.

### Установка
Для того что бы установить **MPAL** нужно сделать несколько простых шагов:
* Composer
```sh
    composer require mpal/mpal dev-master
```
* В .php файле добавить
```sh
    use MPAL\MPAL;
```

### Использование
Укажите основные параметры в массиве $config
```sh
    $config = [
        'DB_HOST' => 'localhost',
        'DB_NAME' => 'test',
        'DB_USER' => 'root',
        'DB_PASS' => '',
        'USERS_TABLE' => 'users',
        'USERNAME_COLUMN' => 'username',
    ];
```
Для начала использования, необходимо инициализировать скрипт следующим образом:
*
```sh
    $mpal = new MPAL($config);
```

Далее использовать все возможные функции.

### Функции
Существует 7 функций(пока что, функционал будет расширяться):
* Начисление денег пользователю, необходимо указать **имя пользователя** и **кол-во начисляемых средств**
```sh
    $mpal->updateBalance($username, $amount);
```
* Списание средств с баланса пользователя, данные, которые необходимо указывать, идентичны с предыдущей функцией
```sh
    $mpal->removeFunds($username, $amount);
```
* Изменение префикса пользователя в PEX'e
```sh
    $mpal->prefixChange($username, $prefix);
```
* Изменение суффикса пользователя в PEX'e
```sh
    $mpal->suffixChange($username, $suffix);
```
* Изменение группы пользователя в PEX'e
```sh
    $mpal->groupChange($username, $group);
```
* Создание новой группы в PEX'e. Данные: название группы, ее идентификатор(числовой), permissions группы, мир, доп.параметры группы.
```sh
    $mpal->groupCreate($name, $type, $permission, $world, $value);
```
* Удаление группы. Так же перенесет всех пользователей с такой группой в default группу(значение, которое по умолчанию установленно в Вашей Базе Данных).
```sh
    $mpal->groupDelete($name);
```

### Todo's

 - Добавить функционал

Лицензия
----

Распространяется по [MIT](https://github.com/I7uoHep/minecraftLibrary/blob/master/LICENSE) лицензии.
