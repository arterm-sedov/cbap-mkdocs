---
title: Атрибут типа «Запись»
kbId: 2243
---

# Атрибут типа «Запись»

## Свойства атрибута

Атрибут типа «**Запись**» содержит одну или несколько ссылок на записи в связанном [шаблоне записи](record_templates.md). Ссылка представляет собой уникальный идентификатор записи.

Помимо [общих свойств][attribute_common_properties] для атрибута типа «**Запись**» предусмотрены перечисленные ниже свойства.

- «**Формат отображения**» — выберите способ отображения заголовков связанных записей в полях на формах и в таблицах (см. раздел «**[Атрибут-заголовок записей шаблона](displayed_attribute.md)**»):
- «**Гиперссылка**» — гиперссылка, по которой можно перейти к связанной записи;
- «**Простой текст**» — текст с заголовком связанной записи.
- «**Связанный шаблон**» (**обязательное поле**) — укажите [шаблон записи](record_templates.md), на который будет ссылаться данный атрибут.
  
--8<-- "attribute_property_attribute_interlinking.md"

- «**Хранить несколько значений**» — установите этот флажок, чтобы в атрибуте можно было хранить ссылки на несколько записей из **связанного шаблона** (сформируется связь «один ко многим»).
    
- «**Удалять связанные записи**» — установите этот флажок, чтобы разрешить удаление записей из **связанного шаблона** посредством полей данного атрибута в таблицах и на формах.
--8<-- "attribute_property_displayed.md"
--8<-- "attribute_property_calculated.md"

_![Свойства атрибута типа «Запись»](attribute_record_properties.png)_

--8<-- "attribute_property_attribute_linking_example.md"

--8<-- "related_topics_heading.md"

**[Общие свойства атрибутов][attribute_common_properties]**

**[Атрибуты. Определения, типы, настройка, архивирование, удаление][attributes]**

**[Атрибут типа «Аккаунт»](attribute_account.md)**

{%
include-markdown ".snippets/hyperlinks_mkdocs_to_kb_map.md"
%}