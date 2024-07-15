# Системные атрибуты

!!! Question "Определение"

    * Системные атрибуты имеются у каждого объекта, например у приложения, шаблона и даже у самого атрибута.
    * Набор системных атрибутов зависит от типа объекта.
    * Системные атрибуты не подлежат изменению, удалению и архивированию.
    * Системные атрибуты создаются автоматически при создании объекта.

## Перечень системных атрибутов

- «**ID**» (id) — уникальный идентификатор объекта. Тип: **[Запись](attribute_record.md)**.
- «**Создатель**» (_creator) — аккаунт, создавший объект. Тип: **[Аккаунт](attribute_account.md)**.
- «**Дата создания**» (_creationDate) — дата и время создания объекта. Тип: **[Дата и время](attribute_date_time.md)**.
- «**Дата изменения**» (_lastWriteDate) — дата и время последнего изменения данных объекта. Тип: **[Дата и время](attribute_date_time.md)**.
- «**Архивный**» (_isDisabled) — флаг нахождения объекта в архиве (по умолчанию `false`). Тип: **[Логический](attribute_boolean.md)**. См. разделы «**[Архивирование и разархивирование атрибута](attribute_archive_unarchive.md)**» и «**[Архивирование и разархивирование шаблона](template_archiving.md)**».