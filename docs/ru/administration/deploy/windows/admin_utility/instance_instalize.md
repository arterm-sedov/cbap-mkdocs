---
title: Инициализация экземпляра продукта
kbId: 4630
---

# Инициализация экземпляра продукта {: #admin_utility_instance_instalize}

## Введение

При первом запуске экземпляр продукта требуется инициализировать: создать аккаунт администратора, активировать продукт, настроить подключение к серверу Elasticsearch. В данном разделе представлены инструкции по инициализации экземпляра продукта.

## Порядок инициализации экземпляра продукта

1. В списке «**Экземпляры продукта**» в главном окне Утилиты администрирования щёлкните правой кнопкой мыши экземпляр продукта, который требуется запустить впервые и инициализировать.
2. В контекстном меню выберите пункт «**Перейти на веб-сайт**».

    _![Переход на веб-сайт экземпляра продукта](https://kb.comindware.ru/assets/img_668264014c41e.png)_

3. Дождитесь запуска и отображения веб-сайта с экземпляром продукта.
4. Откроется страница создания аккаунта администратора продукта.

    _![Страница создания аккаунта администратора](https://kb.comindware.ru/assets/administration_tool6.png)_

5. Введите учётные данные аккаунта администратора и нажмите кнопку «**Создать аккаунт**».

    !!! warning "Внимание!"

        В экземпляре ПО всегда должен оставаться хотя бы один аккаунт администратора. Он может потребоваться для восстановления продукта. Аккаунт администратора, созданный при инициализации экземпляра ПО, не следует удалять, даже если впоследствии аккаунты будут синхронизироваться с Сервером каталогов.

6. Откроется страница активации экземпляра продукта.
7. Для первоначального ознакомления с системой этап активации можно пропустить, нажав кнопку «**Пропустить**». См. статью *«[Лицензирование. Активация продукта, использование ключей, назначение, отзыв и продление лицензий][licensing]*».

    _![Страница активации экземпляра системы](https://kb.comindware.ru/assets/administration_tool7.png)_

8. Откроется страница настройки подключения к службе Elasticsearch. См. параграф *«[Использование службы Elasticsearch, установленной Утилитой администрирования][admin_utility_sw_install]»*.
9. В поле «**URI**» введите адрес сервера Elasticsearch, например: `http://localhost:9200`.
10. При необходимости введите учётные данные для сервера Elasticsearch в поля «**Имя пользователя**» и «**Пароль**».
11. Укажите необходимый **префикс индекса** Elasticsearch.
12. Нажмите кнопку «**Далее**».

    _![Настройка подключения к Elasticsearch](https://kb.comindware.ru/assets/administration_tool8.png)_

13. Откроется страница инициализации данных в Elasticsearch.
14. Нажмите кнопку «**Обновить**».

    _![Страница инициализации данных в Elasticsearch](https://kb.comindware.ru/assets/administration_tool9.png)_

15. Дождитесь открыти{{ productName }}ss Application Platform**.

    _![Начальная страниц{{ productName }}rm](https://kb.comindware.ru/assets/administration_tool10.png)_

16. На этом этапе развёртывание экземпляра продукта завершено и можно приступать к созданию и использованию приложений.

<div class="relatedTopics" markdown="block">

--8<-- "related_topics_heading.md"{{ productName }}

- _[Установка продукта {{ productName }}][admin_utility_sw_install]_
- _[Установка Elasticsearch. Краткое руководство для Windows][elasticsearch_deploy_windows]_

</div>

{% include-markdown ".snippets/hyperlinks_mkdocs_to_kb_map.md" %}