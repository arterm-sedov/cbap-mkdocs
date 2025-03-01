---
title: Отправка HTTP-запросов типа GET. Пример: настройка подключения, пути передачи данных и сценария для обработки запросов в формате JSON
kbId: 2509
---

# Отправка HTTP-запросов типа GET. Пример: настройка подключения, пути передачи данных и сценария для обработки запросов в формате JSON

## Введение

**{{ productName }}** позволяет отправлять HTTP-запросы типов `GET`, `POST`, `PUT`, `DELETE` для взаимодействия с внешними системами.

Здесь представлен пример настройки подключения, пути передачи данных и [сценария][scenarios] для отправки HTTP-запросов типа `GET` в формате JSON и записи данных из ответа сервера в атрибуты шаблона записи.

Настройка для обработки данных в формате XML и простого текста будет аналогичной.

## Прикладная задача

Здесь мы рассмотрим настройку отправки GET-запросов на сервер *http://example.com*.

Во всех примерах подставьте реальный адрес своего сервера вместо `http://example.com/api`

- Базовый URL для HTTP-запросов: `http://example.com/api`
- Путь для запроса данных заказов: `http://example.com/api/orders`
- [Сценарий](#настройка-сценария-отправки-http-запроса) формирует и отправляет HTTP-запрос на сервер и записывает полученные данные в атрибуты.
- Запрос содержит параметры `orderDate` с датой создания заказов и `clientName` с идентификатором клиента.
- В ответ на запрос сервер возвращает JSON-ответ с массивом данных заказов следующего вида:

```
{
    "error": false,
    "status": "ok",
    "statusCode": 200,
    "orders": [
        {
         "orderAmount": 1000,
         "orderNumber": "Order-1",
         "orderStatus": "Fulfilled"
        },
        {
         "orderAmount": 5000,
         "orderNumber": "Order-2",
         "orderStatus": "Canceled"
        },
     ]
}
```

## Настройка подключения

1. Откройте раздел «**Администрирование**» — «**Подключения**».
2. В меню «**Создать**» выберите пункт «**Подключения REST и OData**» — «**Отправка HTTP-запросов**».

_![Создание подключения для отправки HTTP-запросов](https://kb.comindware.ru/assets/send_http_example_create.png)_
3. Настройте подключение для отправки HTTP-запросов со следующими параметрами:

    - **URI** — http://example.com/api. Символ `/` в конце URI не требуется.
    - **Формат данных** — **JSON**. Также поддерживаются **XML** и **простой текст**, но здесь рассматривается обработка данных в формате JSON.
4. Остальные параметры подключения настройте в соответствии с используемым сервером. См. статью «*[Отправка HTTP-запросов. Настройка подключения][send_http_connection]*».

_![Настройка подключения для отправки HTTP-запросов](https://kb.comindware.ru/assets/send_http_example_settings.png)_

## Настройка пути передачи данных

1. Откройте раздел «**Администрирование**» — «**Пути передачи данных**».
2. В меню «**Создать**» выберите пункт «**Подключения REST и OData**» — «**Отправка HTTP-запросов**».

_![Создание пути передачи данных для отправки HTTP-запросов](https://kb.comindware.ru/assets/send_http_example_path_create.png)_
3. Настройте путь передачи данных для отправки HTTP-запросов на вкладках «**Основные свойства**», «**Атрибуты сообщений**», «**Интеграция**».

### Основные свойства

- **Подключение** — выберите ранее созданное [подключение для отправки HTTP-запросов](#настройка-подключения).
- **Системное имя** — введите системное имя пути передачи данных латинскими буквами.
- **Отключить** — установите этот флажок, если требуется деактивировать путь передачи данных.
- **Описание** — введите наглядное описание назначения пути передачи данных.

_![Настройка подключения для отправки HTTP-запросов](https://kb.comindware.ru/assets/send_http_example_new_path.png)_

### Атрибуты сообщений

- **Тип сообщения** — выберите пункт «**Отправка HTTP-запросов**».
- **Запрос** — добавьте атрибут `queryParams` (произвольное системное имя, которое будет указано в поле «**Атрибут для параметров запроса**» на вкладке «[**Интеграция**](#интеграция)» и в действии сценария «**Изменить значения переменных**») типа «**Объект**».

    - Установите флажок «**Массив**».
    - Установите флажок у атрибута `queryParams` и добавьте его дочерние атрибуты:
    
    
        - `name` (предопределённое системное имя) типа «**Строка**» — этот атрибут будет содержать имена параметров запроса.
        - value (предопределённое системное имя) типа «**Строка**» — этот атрибут будет содержать значения параметров запроса.В эти атрибуты будут передаваться пары ключ-значение параметров запроса.
- **Ответ** — добавьте атрибут с системным именем `orders` (совпадает с именем массива данных заказов в ответе сервера на HTTP-запрос) типа «**Объект**».

    - Установите флажок «**Массив**»
    - Установите флажок у атрибута `orders` и добавьте его дочерние атрибуты:
    
    
        - orderAmount (совпадает с именем параметра из ответа сервера) типа «**Число**» — этот атрибут будет содержать сумму заказа.
        - orderNumber  (совпадает с именем параметра из ответа сервера) типа «**Строка**» — этот атрибут будет содержать номер заказа.
        - orderStatus (совпадает с именем параметра из ответа сервера) типа «**Строка**» — этот атрибут будет содержать статус заказа. В эти атрибуты будут записываться значения из ответа сервера на запрос.
- **Ответ с ошибкой** — настройте атрибуты для получения ответа сервера с ошибкой аналогично атрибутам **запроса** и **ответа**.

_![Настройка атрибутов сообщения в свойствах пути передачи данных для отправки HTTP-запросов](https://kb.comindware.ru/assets/send_http_example_attribute_settings.png)_

### Интеграция

- **Метод запроса** — выберите пункт «**GET**».
- **Шаблон пути запроса** — введите `orders` (фактический путь к HTTP-запросу на сервере), этот суффикс будет добавлен к **URI**, указанному в [свойствах подключения для отправки HTTP-запросов](send_http_connection.html). Например, для **URI** `http://example.com/api` результирующий путь запроса будет `http://example.com/api/orders`.
- **Атрибут для сериализации в тело запроса** — этот атрибут используется для методов `POST` и `PUT`, в него следует вводить через запятую системные имена атрибутов из таблицы «**Запрос**» на вкладке «**Атрибуты сообщений**». В данной статье это поле не используется.
- **Атрибут для параметров запроса** — введите системное имя атрибута из таблицы «**Запрос**» на вкладке «**Атрибуты сообщений**».

_![Настройка интеграции в свойствах пути передачи данных для отправки HTTP-запросов](https://kb.comindware.ru/assets/send_http_example_integration_settings.png)_
- **Атрибуты для десериализации ответа без ошибки** и  **Атрибуты для десериализации ответа с ошибкой** 

    - Создайте одну строку в каждой таблице и введите символ `$` в столбцы «**Путь к атрибуту**» и «**Выражение на языке запросов**».
    
    
    ![Настройка атрибутов для десериализации ответа в пути передачи данных для отправки HTTP-запросов](https://kb.comindware.ru/assets/send_http_example_attribute_serialization_settings.png)
    
    
    Настройка атрибутов для десериализации ответа в пути передачи данных для отправки HTTP-запросов

## Настройка сценария отправки HTTP-запроса

1. Создайте [сценарий][scenarios], например, выполняющийся по нажатию кнопки.

_![Исходный сценарий, выполняющийся по нажатию кнопки](https://kb.comindware.ru/assets/send_http_example_scenario.png)_
2. В свойствах автоматически созданного действия «**Сменить контекст**» укажите **целевой шаблон записи**, содержащий атрибуты для HTTP-запроса и ответа.

_![Настройка контекстного шаблона для отправки HTTP-запроса](https://kb.comindware.ru/assets/send_http_example_template_settings.png)_
3. Добавьте и настройте действие «**Изменить значения переменных**».

    - **Операция со значениями переменных** — **Добавить.**
    - **Набор переменных** — `queryParamsContainer` (произвольное системное имя), из этого массива последующее действие «**Отправить сообщение**» передаст параметры в HTTP-запрос.
    - В таблице атрибутов создайте два атрибута `queryParams` (это системное имя массива атрибутов **запроса**, указанное на вкладке «[**Атрибуты сообщений**](#атрибуты-сообщений)» в свойствах пути передачи данных), которые будут содержать пары ключ-значение для параметров HTTP-запроса в двух дочерних атрибутах:
    
    
        - `name` — введите формулу с именем параметра HTTP-запроса (например, `"orderDate"`, `"clientName"`).
        - `value` — введите **формулу**, выражение на **N3** или выберите **атрибут** с необходимым значением параметра HTTP-запроса.
        
        
        
        Примечание
        
        
        Чтобы передать в HTTP-запрос несколько параметров, создайте необходимое количество атрибутов с одинаковым системным именем и настройте их дочерние атрибуты.
        
        
        
        ![Настройка переменных для передачи в качестве параметров HTTP-запроса](https://kb.comindware.ru/assets/send_http_example_scenario_settings.png)
        
        
        Настройка переменных для передачи в качестве параметров HTTP-запроса
4. Добавьте и настройте действие «**Отправить сообщение**».

    - **Подключение** — выберите [подключение для отправки HTTP-запросов][send_http_connection].
    - **Путь передачи данных** — выберите ранее настроенный [путь для передачи данных](#настройка-пути-передачи-данных) HTTP-запроса.
    - **Переменная с сообщением** — введите системное имя **набора переменных**, указанное в предшествующем действии «**Изменить значения переменных**».
    - **Переменная для успешного ответа** — введите системное имя переменной, в которую будет помещён ответ сервера на HTTP-запрос, эта переменная будет использоваться в последующем действии «**Повторять по количеству объектов**».
    - **Переменная для ответа с ошибкой** — введите системное имя переменной, в которую будет помещён ответ сервера в случае ошибки.
    
    
    ![Настройка действия сценария для отправки HTTP-запроса](https://kb.comindware.ru/assets/send_http_example_scenario_settings1.png)
    
    
    Настройка действия сценария для отправки HTTP-запроса
5. Добавьте и настройте действие «**Повторять по количеству объектов**».

    - **Переменная** — введите имя переменной, в которую будут помещены объекты, полученные из ответа на HTTP-запрос. Эта переменная будет использоваться для обращения к объектам в ответе от сервера в последующем действии «**Изменить значения атрибутов**».
    - **Атрибут или выражение для поиска объектов** — введите **формулу** вида `$$response->orders`, где `response` — имя **переменной для успешного ответа**, указанное в свойствах действия «**Отправить сообщение**», `orders` — системное имя атрибута **ответа**, указанное на вкладке «[**Атрибуты сообщений**](#атрибуты-сообщений)» в свойствах пути передачи данных.
    
    
    ![Настройка цикла в сценарии для получения данных из ответа на HTTP-запрос](https://kb.comindware.ru/assets/send_http_example_scenario_cycle_settings.png)
    
    
    Настройка цикла в сценарии для получения данных из ответа на HTTP-запрос
6. Внутри действия «**Повторять по количеству объектов**» добавьте и настройте действие «**Изменить значения атрибутов**».

    - В таблице атрибутов добавьте атрибуты, значения которых следует заполнить из полученного ответа от сервера.
    - В столбце «**Значение**» для каждого атрибута введите **формулу** вида `$$loopiterator->objectName`, где `loopiterator` — имя **переменной**, заданное в действии «**Повторять по количеству объектов**», а `objectName` — имя объекта в ответе от сервера (см. [пример ответа сервера](#прикладная-задача)).
    
    
    ![Настройка действия в сценарии для передачи данных из ответа на HTTP-запроса в атрибуты шаблона записи](https://kb.comindware.ru/assets/send_http_example_scenario_send_settings.png)
    
    
    Настройка действия в сценарии для передачи данных из ответа на HTTP-запроса в атрибуты шаблона записи
7. Результирующий сценарий должен выглядеть, как показано на следующей иллюстрации.

_![Сценарий для отправки HTTP-запроса и получения данных из ответа сервера](https://kb.comindware.ru/assets/send_http_example_scenario_send.png)_
8. Проверьте работу приложения: сценарий должен отправлять HTTP-запрос и записывать данные из ответа сервера в атрибуты шаблона.

--8<-- "related_topics_heading.md"

**[Отправка HTTP-запросов. Настройка подключения][send_http_connection]**

**[Событие и действия сценария. Определения, типы, свойства, настройка][scenario_elements]**

{% include-markdown ".snippets/hyperlinks_mkdocs_to_kb_map.md" %}
