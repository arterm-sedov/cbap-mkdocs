---
title: Отправка запросов данных в «СФЕРА Курьер».
kbId: 5062
kbTitle: Отправка запросов данных в «СФЕРА Курьер». Настройка подключения, пути передачи данных и сценария
tags:
    - СФЕРА Курьер
    - электронный документооборот
    - отправка документов
    - сценарий
hide: tags
---

# Отправка запросов данных в «СФЕРА Курьер» {: #esphere_send_configure}

## Введение

<!--intro-start-->
В **{{ productName }}** можно настроить подключение к системе электронного документооборота «СФЕРА Курьер». Интеграция с этой системой позволяет:

- осуществлять поиск контрагентов по реквизитам и проверять корректность реквизитов;
- осуществлять обмен документами с контрагентами;
- производить с документами и квитанциями различные действия:
    - создавать,
    - отправлять,
    - подписывать,
    - принимать,
    - отзывать,
    - аннулировать,
    - отклонять;
- подписывать документы квалифицированной электронной подписью;
- контролировать сроки подписания документов.
<!--intro-end-->

## Прикладная задача

Здесь приведён пример настройки подключения, пути передачи данных, шаблона и сценария для синхронизации данных о контрагентах с системой «СФЕРА Курьер».

Имеется шаблон _«Реестр контрагентов»_, в котором хранятся сведения о контрагентах.

Требуется настроить кнопку для синхронизации данных контрагентов с «СФЕРА Курьер».

## Порядок настройки

1. Настройте [подключение](#configure_connection_send_request) типа «**Отправка сообщений в систему «СФЕРА Курьер**».
2. Настройте [путь передачи данных](#настройка-пути-передачи-данных) «**Отправка сообщений в «СФЕРА Курьер**», использующий созданное подключение.
3. Настройте [шаблон записи](#настройка-шаблона-записи) для хранения данных контрагентов.
4. Настройте [сценарий](#настройка-сценария) для получения данных о контрагенте из «СФЕРА Курьер».

## Настройка подключения {: #configure_connection_send_request }
<!--connection-start-->
1. Откройте страницу «**Администрирование**» — «**[Подключения][connections]**».
2. В списке подключений откройте или создайте подключение типа «**Пользовательские подключения**» — «**Отправка сообщений в систему «СФЕРА Курьер**».<!--connection-properties-start-->
3. Настройте свойства подключения:

    - **Системное имя** — введите уникальное имя подключения.
    --8<-- "systemNameRequirements.md"
    - **Отключить** — установите этот флажок, если требуется временно деактивировать данное подключение.
    - **Описание** — введите наглядное описание подключения.
    - **Запись в файловые журналы** — выберите, какие события следует записывать в журналы:
         - **Полные сведения об обработке сообщения**;
         - **Только ошибки**;
         - **Отключить** — не регистрировать в журнале события отправки сообщений.
    - **Тестовый сервер** — установите этот флажок, чтобы настроить подключение к тестовому серверу.
    - **Интервал запроса данных, в минутах** — укажите интервал запроса к серверу.
    - **ApiKey** — введите ключ API для подключения к «СФЕРА Курьер».
    - **Имя пользователя** — укажите учётную запись для подключения к «СФЕРА Курьер».
    - **Пароль** — введите пароль для подключения к «СФЕРА Курьер».
    - **Идентификатор участника ЭДО получателя документа** — укажите идентификатор, присвоенный участнику «СФЕРА Курьер».

4. Нажмите кнопку «**Проверить соединение**» и удостоверьтесь, что соединение установлено.
5. Чтобы просмотреть журнал событий отправки сообщений, нажмите кнопку «**Скачать журнал**».
6. Сохраните подключение.
<!--connection-properties-end-->
<!--connection-end-->

## Настройка пути передачи данных

<!--route-start-->
1. Откройте страницу «**Администрирование**» — «**[Пути передачи данных][communication_routes]**».
2. Откройте двойным нажатием в списке или путь передачи данных типа «**Пользовательские подключения**» — «**Отправка сообщений в «СФЕРА Курьер**» типа «**Зачитывает данные об организации**.
3. Настройте свойства пути передачи данных на следующих вкладках:

    - [**Основные свойства**](#configure_communication_route_send_request_main_properties)
    - [**Атрибуты сообщения**](#configure_communication_route_send_request_message_attributes)

4. Сохраните путь передачи данных.
<!--route-end-->

### Основные свойства {: #configure_communication_route_send_request_main_properties }

<!--route-main-properties-start-->
На вкладке «**Основные свойства**» настройте параметры использования пути передачи данных.

- **Подключение** — выберите [подключение для отправки сообщений в систему «СФЕРА Курьер»](#configure_connection_send_request).
- **Системное имя** — введите уникальное имя пути передачи данных.
--8<-- "systemNameRequirements.md"
- **Отключить** — установите этот флажок, если требуется временно деактивировать данный путь передачи данных.
- **Описание** — введите наглядное описание пути передачи данных.
- **Номер шины данных** — выберите номер от 0 до 3, если требуется распределить потоки данных нескольких путей для повышения производительности.
<!--route-main-properties-end-->

### Атрибуты сообщений {: #configure_communication_route_send_request_message_attributes }

На вкладке «**Атрибуты сообщения**» настройте атрибуты, значения которых будут подставляться в содержимое сообщений в зависимости от его типа.

1. Выберите **тип сообщения** «**Зачитывает данные об организации**». Предусмотрены следующие типы сообщений:

    - **Добавить новый документ**;
    - **Отправить подпись для документа**;
    - **Получить документ**;
    - **Найти документы**;
    - **Изменить стадии документооборота**;
    - **Отклонить документ**;
    - **Зачитывает данные об организации**.

2. В таблицах «**Запрос**», «**Ответ**» и «**Ответ с ошибкой**» отобразятся готовые атрибуты, соответствующие выбранному **типу сообщения**.

<!--esphere-attribute-reference-start-->
Подробные сведения об атрибутах, которые используются при обмене сообщениями с системой «СФЕРА Курьер», см. в _[Справочном руководстве API СФЕРА Курьер](https://www.esphere.ru/assets/download/integration/ws-courier.pdf)_.
<!--esphere-attribute-reference-end-->

## Настройка шаблона записи

1. Создайте шаблон записи _«Реестр контрагентов»_.
2. Создайте следующие атрибуты типа «**Текст**»:

    - _Код участника ЭДО_
    - _ИНН_
    - _КПП_

3. Создайте кнопку _«Синхронизировать данные контрагента»_ со следующими свойствами:

    - **Контекст операции: запись**
    - **Операция: вызвать событие «Нажата кнопка»**
    - **Результат выполнения: обновить данные**

4. Поместите атрибуты _«Код участника ЭДО»_, _«ИНН»_, _«КПП»_ на **основную форму**.
5. Поместите кнопку _«Синхронизировать данные контрагента»_ на **основную форму**.

## Настройка сценария

1. Создайте сценарий:

    - **Название:** _Синхронизация контрагента со «СФЕРА Курьер»_
    - **Контекст выполнения: от инициатора**

2. Отобразится конструктор сценария.
3. Настройте событие «**Нажата кнопка**»:

    - **Контекстный шаблон:** _Реестр контрагентов_
    - **Кнопка:** _Синхронизировать данные контрагента_

4. Создайте и настройте действие «**Изменить значение переменных**»:

    - **Операция со значениями переменных: добавить**
    - **Набор переменных:** _Request_
    - Добавьте переменную:
        - **Имя переменной:** _CompanyCode_
        - **Значение: атрибут** _Код участника ЭДО_

5. Добавьте действие «**Отправить сообщение**» со следующими свойствами:

    - **Подключение:** выберите [подключение для отправки сообщений в систему «СФЕРА Курьер»](#configure_connection_send_request)
    - **Путь передачи данных:** выберите [путь передачи данных для отправки сообщений в «СФЕРА Курьер»](#настройка-пути-передачи-данных)
    - **Переменная с сообщением:** _Request_
    - **Переменная для успешного ответа:** _Response_
    - **Переменная для ответа с ошибкой:** _Error_

6. Добавьте действие «**Изменить значение атрибутов**» со следующими свойствами:

    | Атрибут      | Операция со значениями     | Значение                       |
    |---           |---                         |---                             |
    | _ИНН_        | **Заменить**               | **Формула:** `$$Response->Inn` |
    | _КПП_        | **Заменить**               | **Формула:** `$$Response->Kpp` |

_![Сценарий отправки запроса в «СФЕРА Курьер» для синхронизации данных контрагента](esphere_send_configure_scenario.png)_

## Тестирование

1. Создайте новую запись в шаблоне _«Реестр контрагентов»_.
2. Введите в поле _«Код участника ЭДО»_ действительный код контрагента.
3. Нажмите кнопку _«Синхронизировать данные контрагента»_.
4. В полях _«ИНН»_ и _«КПП»_ должны отобразиться данные контрагента.

--8<-- "related_topics_heading.md"

- _[Получение документов через «СФЕРА Курьер»][esphere_receive_configure]_
- _[Подключения. Определения, типы, создание, настройка, удаление][connections]_
- _[Пути передачи данных][communication_routes]_

{% include-markdown ".snippets/hyperlinks_mkdocs_to_kb_map.md" %}
