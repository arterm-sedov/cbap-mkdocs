---
title: Восстановление экземпляра продукта из резервной копии в ОС Windows
kbId: 2038
---

# Восстановление экземпляра продукта из резервной копии в ОС Windows {: #restore_windows}

## Введение

Экземпляр продукта можно восстановить из резервной копии в формате `CDBBZ`.

Сведения о создании файла резервной копии см. статьях *«[Резервное копирование и восстановление {{ productName }}. Краткое руководство для ОС Windows][backup_restore_windows]»*.

## Порядок восстановления экземпляра продукта

1. Выберите экземпляр, который требуется восстановить в списке «**Экземпляры продукта**» в главном окне Утилиты администрирования.
2. Нажмите кнопку «**Восстановить**».

![Выбор экземпляра продукта и переход к его восстановлению](https://kb.comindware.ru/assets/img_667ec3011e2b3.png)

Выбор экземпляра продукта и переход к его восстановлению
3. Отобразится окно «**Восстановление экземпляра**».
4. Выберите пункт «**Восстановить экземпляр из файла резервной копии**».
5. Нажмите кнопку «**Далее**».

![Переход к восстановлению экземпляра продукта из файла резервной копии](https://kb.comindware.ru/assets/img_667ec594b626a.png)

Переход к восстановлению экземпляра продукта из файла резервной копии
6. В отобразившемся окне укажите путь к файлу резервной копии с расширением `.CDBBZ`.
7. Нажмите кнопку «**Восстановить**».

![Выбор файла резервной копии для восстановления](https://kb.comindware.ru/assets/img_667ec602a787b.png)

Выбор файла резервной копии для восстановления
8. Отобразится запрос на подтверждение восстановления экземпляра продукта.
9. Нажмите кнопку «**Да**».


![Подтверждение восстановления экземпляра продукта](https://kb.comindware.ru/assets/img_667ec66609299.png)

Подтверждение восстановления экземпляра продукта
10. Утилита администрирования восстановит экземпляр продукта из резервной копии.
11. В процессе восстановления может отобразиться окно программы `powershell.exe`. Не закрывайте это окно и дождитесь завершения работы программы `powershell.exe`.
12. В процессе восстановления отобразится индикатор прогресса восстановления. Не закрывайте окно и дождитесь завершения восстановления экземпляра продукта.
13. В случае успешного восстановления отобразится сообщение «**Экземпляр восстановлен из резервной копии**».
14. Нажмите кнопку «**Закрыть**».
15. Если восстановить экземпляр не удастся, отобразится окно «**Сообщения об ошибках**».

    - Чтобы просмотреть файл журнала ошибок, нажмите кнопку «**Журнал**».

    ![Сообщения об ошибках при восстановлении экземпляра продукта из резервной копии](https://kb.comindware.ru/assets/img_667ec6c1ea3c9.png)

## Настройка конфигурации восстановленного экземпляра продукта

После восстановления экземпляра продукта может потребоваться проверить и настроить его конфигурацию.

1. Запустите экземпляр.
2. Если откроется страница настройки подключения к службе Elasticsearch:

    1. В поле «URI» введите адрес своего сервера Elasticsearch.
    2. Введите **префикс индекса**, **имя пользователя** и **пароль сервера Elasticsearch**.
    3. Нажмите кнопку «**Далее**».

    _[Настройка подключения к Elasticsearch](https://kb.comindware.ru/assets/Picture16.png)_

3. Если откроется страница инициализации данных в Elasticsearch, нажмите кнопку «**Обновить**».

    _![Страница инициализации данных в Elasticsearch](https://kb.comindware.ru/assets/Picture17.png)_

4. Дождитесь открытия начальной страницы **{{ productName }}**.
5. Откройте страницу «**Администрирование**» — «**Подключения**».

    _![Переход к свойства подключения к Elasticsearch](https://kb.comindware.ru/assets/img_64d09fd6ec3ba.png)_

6. Откройте подключение к серверу Elasticsearch.
7. Удостоверьтесь, что корректно указаны **префикс индекса** и **URL подключения** к серверу Elasticsearch.

    _![Свойства подключения к серверу Elasticsearch](https://kb.comindware.ru/assets/img_64d0a41fc5e0b.png)_

Проверка свойств подключения к серверу Elasticsearch
8. Откройте страницу «**Администрирование**» — «**Глобальная конфигурация**».
9. Удостоверьтесь, что указан корректный **URL-адрес сервера**.

    _![URL-адрес сервера в глобальной конфигурации](https://kb.comindware.ru/assets/img_64d0a4feebc80.png)_

10. Откройте страницу **[«Администрирование» — «Резервное копирование»][backup]**.
11. Удостоверьтесь, что в конфигурациях резервного копирования правильно указаны пути для сохранения резервных копий.
12. При необходимости измените конфигурации резервного копирования, указав корректные пути к файлам.

    _![Настройка пути к файлам резервной копии](https://kb.comindware.ru/assets/img_6683f69f9922d.png)_

--8<-- "related_topics_heading.md"

**[Резервное копирование. Настройка и запуск {{ productName }}][backup]**

**[Резервное копирование и восстановление {{ productName }} в ОС Windows][backup_restore_windows]**

{% include-markdown ".snippets/hyperlinks_mkdocs_to_kb_map.md" %}