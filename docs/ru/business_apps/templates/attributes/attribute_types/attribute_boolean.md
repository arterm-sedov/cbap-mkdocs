---
title: Атрибут типа «Логический»
---

# Атрибут типа «Логический»

Атрибут типа «**Логический**» содержит булево значение «true» или «false».

## Свойства атрибута

Помимо **[общих свойств](attribute_common_properties.md)** для атрибута типа «**Логический**» предусмотрены перечисленные ниже свойства.

--8<-- "attribute_property_calculated.md"

*![Свойства атрибута типа «Тест»](attribute_boolean_properties.png)*

## Пример использования

!!! Tip "Контроль согласования сметы с помощью логического атрибута"

    **Конфигурация приложения**

    * Атрибут _«Смета согласована»_
        - **Тип данных**: **Логический**.
    * Поле _«Смета согласована»_ на форме
        -  **Отображать как**: **Переключатель**.

    **Результирующее поведение**

    1. Значение `true` в поле _«Смета согласована»_ будет отображаться как
          -  `Да`.
    2. Значение `false` в поле _«Смета согласована»_ будет отображаться как 
          - `Нет`.
    *![Переключатель для логического атрибута на форме](attribute_boolean_example.png)*

--8<-- "related_topics_heading.md"

**[Общие свойства атрибутов](attribute_common_properties.md)**

**[Просмотр и настройка свойств атрибута](attribute_setup.md)**

**[Создание атрибута](attribute_creation.md)**