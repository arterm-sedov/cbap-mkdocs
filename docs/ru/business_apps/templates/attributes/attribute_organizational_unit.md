
---
title: Атрибут типа «Организационная единица»
kbId: 2258
---

# Атрибут типа «Организационная единица»

## Свойства атрибута

Атрибут типа «**Организационная единица**» содержит одну или несколько ссылок на записи в связанном **[шаблоне организационной единицы](organizational_unit_templates.md)**. Ссылка представляет собой уникальный идентификатор записи.

Помимо **[общих свойств][attribute_common_properties]** для атрибута типа «**Организационная единица**» предусмотрены перечисленные ниже свойства.

--8<-- "attribute_property_attribute_interlinking.md"

- «**Хранить несколько значений**» — установите этот флажок, чтобы в атрибуте можно было хранить ссылки на несколько ролей (сформируется связь «один ко многим»).
--8<-- "attribute_property_calculated.md"

_![Свойства атрибута типа «Организационная единица»](attribute_organizational_unit_properties.png)_

## Пример использования

!!! Tip "Добавление ссылки на роль в таблицу с данными заказчиков"

    **Конфигурация приложения**

    - В приложении имеется роль _«Внутренний заказчик»_.
    - Атрибут _«Тип заказчика»_ в шаблоне аккаунта _«Заказчики»_
        - **тип данных**: **Организационная единица**.
        - **Хранить несколько значений**: флажок снят.
        - **Взаимная связь с атрибутом**: **не используется**.

    **Результирующее поведение**

    1. В шаблоне аккаунта _«Заказчики»_ создана запись `«Бухгалтерия»`.
    2. В записи `«Бухгалтерия»` в атрибуте _«Тип заказчика»_ указана роль _«Внутренний заказчик»_.
    3. В таблице _«Все заказчики»_ в столбце _«Тип заказчика»_ будет отображаться ссылка для перехода к записи _«Внутренний заказчик»_.

--8<-- "related_topics_heading.md"

**[Общие свойства атрибутов][attribute_common_properties]**

**[Шаблон организационной единицы](organizational_unit_templates.md)**

**[Атрибуты. Определения, типы, настройка, архивирование, удаление][attributes]**

{%
include-markdown ".snippets/hyperlinks_mkdocs_to_kb_map.md"
%}