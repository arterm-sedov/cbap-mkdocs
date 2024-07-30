---
kbId: 2564
---

# Получение эл. почты в процессе. Настройка подключения и пути передачи данных

## Введение

В этой статье представлены инструкции по настройке подключения и пути передачи передачи данных из эл. писем в бизнес-процесса.

Кроме того, потребуется настроить **[начальное](receive_message_start_event.md)** или **[промежуточное](receive_message_intermediate_event.md) событие-получение сообщения** на диаграмме процесса.

Подробный пример настройки приложения для обмена данными посредством эл. почты см. в статье _«[Пример: согласование заявлений по эл. почте. Настройка подключений, путей передачи данных и диаграммы процесса]({{ kbArticleURLPrefix }}2515)»_.

## Порядок настройки получения эл. писем

1. [Настройте подключение](#настройка-подключения) типа «**Получение эл. почты из процесса**».
    
2. [Настройте путь передачи данных](#настройка-пути-передачи-данных) типа «**Получение эл. почты из процесса**».
3. Настройте **[начальное](receive_message_start_event.md)** или [**промежуточное**](receive_message_intermediate_event.md) **событие-получение сообщения** на диаграмме процесса:
    - укажите настроенный **путь передачи данных**;
    - настройте сопоставление **данных сообщения**.

## Настройка подключения

!!! warning "Логика чтения писем на почтовом сервере"

    При подключении к почтовому серверу для получения эл. почты **{{ productName }}** выступает как почтовый клиент.

    При каждой проверке почтового ящика **{{ productName }}**:

    - обрабатывает новые письма;
    - отмечает новые письма как прочтённые.

    Поэтому для автоматической обработки входящих писем рекомендуется использовать отдельный адрес эл. почты_._

    Если использовать ящик, на который поступают прочие письма, они тоже будут отмечены как прочитанные.

1. Откройте страницу **«Администрирование» – «Подключения»**.
2. Выберите пункт **«Создать» – «Подключения к электронной почте» – «Получение эл. почты в процессе»**.

    _![Настройка свойств подключения для получения эл. почты в процессе](process_receiving_connection_settings.png)_

3. Настройте подключение к IMAP-серверу:
    - **Отключить** — установите этот флажок, если требуется временно деактивировать данное подключение.
    - **Название** — наименование подключения.
    - **Протокол** — выберите почтовый протокол:
        - **SMTP**;
        - **Microsoft Exchange**.
    - **Адрес почтового сервера** — укажите URL почтового сервера.
    - **Порт** — укажите порт для подключения к почтовому серверу.
    - **Имя пользователя** — укажите учётную запись для подключения к почтовому серверу.
    - **Пароль** — введите пароль к учётной записи для подключения к почтовому серверу.
    - **Интервал опроса** — укажите интервал, с которым **{{ productName }}** будет проверять наличие новых писем.
    - **Защита данных** — выберите протокол шифрования:
        - **Нет**;
        - **SSL**;
        - **TLS**.
    - **Проверить соединение** — нажмите эту кнопку, чтобы проверить соединение с почтовым сервером.
4. Нажмите кнопку «Создать».

## Настройка пути передачи данных

1. Откройте страницу **«Администрирование»** — «**Архитектура**» или страницу «**Администрирование**» приложения.
2. Выберите пункт «**Пути передачи данных**» _‌_.
3. Отобразится список путей передачи данных.
4. Создайте или откройте путь передачи данных типа «**Получение эл. почты в процессе**». 
5. [Настройте свойства](#свойства-пути-передачи-данных) пути передачи данных.
6. Сохраните путь передачи данных.

## Свойства пути передачи данных

### Основные свойства

На вкладке «**Основные свойства**» настройте базовые параметры пути передачи данных:

- **Отключить** — установите этот флажок, чтобы временно деактивировать путь передачи данных.
- **Название** — введите наглядное наименование пути передачи данных.
- **Подключение** — выберите подключение типа «**Получение эл. почты в процессе**».
- **Имя сообщения** — введите уникальное имя сообщения, проходящего по данному пути передачи данных.
- **Приложение** — выберите бизнес-приложение, в котором будет использоваться путь передачи данных.
- **Процесс** — выберите процесс из приложения, в котором будет использоваться путь передачи данных;
- **Назначение** — укажите полученным сообщением:
    - **Новый экземпляр процесса** — полученное сообщение будет создавать новый экземпляр указанного процесса;
    - **Существующий экземпляр процесса** — полученное сообщение будет отправлено в определенный экземпляр указанного процесса.
- **Ключевое поле** — атрибут для поиска существующего экземпляра процесса. Доступно при указании «**Существующий экземпляр процесса**» в «**Назначении**».

_![Настройка основных свойств пути передачи данных для получения эл. почты в процессе](process_receiving_connection_settings_properties.png)_

### Атрибуты сообщения

На вкладке «**Атрибуты сообщения**» заполните таблицу соответствия атрибутов сообщения с атрибутами электронного письма.

!!! tip "Извлечение значений атрибутов из эл. письма"

    Путь передачи данных для получения эл. почты служит для передачи данных из эл. письма в **{{ productName }}**.

    - На вкладке «[**Атрибуты сообщения**](#атрибуты-сообщения)» пути передачи данных задайте набор атрибутов, значения которых требуется извлечь из письма. Для этого создайте атрибуты и сопоставьте их с полями эл. письма.
        - Например, поместите текст эл. письма в атрибут _EmailBody_:
            - **Название:** _Текст письма_
            - **Системное имя:** _Email__Body_
            - **Тип данных: текст**
            - **Поместить тело ответа в этот атрибут:** _Сообщение_
    - Передайте значения атрибутов сообщения в атрибуты записи с помощью вкладки «**[Данные сообщения](receive_message_start_event.md#данные-сообщения)**» в свойствах **события-получения сообщения**, использующего этот путь передачи данных.

Чтобы создать атрибут сообщения и сопоставить его с полем письма, нажмите кнопку «**Создать**» и заполните строку таблицы сопоставления:

- **Название** — введите наглядное название атрибута.
- **Системное имя** — введите уникальное имя атрибута.
- **Тип данных** — выберите тип данных:
    - **Текст**
    - **Число**
    - **Длительность**
    - **Дата и время**
    - **Логический**
    - **Документ**
    - **Аккаунт**
- **Поместить тело ответа в атрибут** — выберите поле электронного письма, значение которого требуется присвоить атрибуту сообщения:
    - **Адрес отправителя**
    - **Имя отправителя**
    - **Адрес получателя**
    - **Тема**
    - **Сообщение**
    - **Адрес для отправки копии**
    - **Адрес для отправки скрытой копии**
    - **Прикрепленные файлы**

_![Настройка атрибутов сообщения в пути передачи данных для получения эл. почты в процессе](process_receiving_connection_attributes_settings.png)_

--8<-- "related_topics_heading.md"

**[Пример: согласование заявлений по эл. почте. Настройка подключений, путей передачи данных и диаграммы процесса]({{ kbArticleURLPrefix }}2515)**

**[Начальное событие-получение сообщения](receive_message_start_event.md)**

**[Промежуточное событие-получение сообщения](receive_message_intermediate_event.md)**

**[Отправка эл. почты из процесса. Настройка подключения, пути передачи данных и события на диаграмме процесса](process_sending_connection.md)** 

**[Получение эл. почты через Exchange. Настройка подключения](exchange_receiving_connection.md)**

**[Получение эл. почты через IMAP. Настройка подключения](imap_receiving_connection.md)**

**[Отправка эл. почты через Exchange. Настройка подключения](exchange_sending_connection.md)**

**[Отправка эл. почты через SMTP. Настройка подключения](smtp_sending_connection.md)**