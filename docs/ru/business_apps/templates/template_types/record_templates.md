# Шаблон записи

!!! Question "Определение"
    Для хранения и обработки данных, описывающих бизнес-сущности, в **{{ productName }}** используются шаблоны записей.

    Например, шаблон записи «Заявка на автомобиль» позволяет определить поля заявки на автотранспорт, оформлять и хранить заявки.

См. также сведения о следующих шаблонах:

* [шаблон аккаунта][шаблон-аккаунта];
* [шаблон роли][шаблон-роли];
* [шаблон организационной единицы][шаблон-организационной-единицы];

## Операции с шаблоном записи

На странице свойств шаблона записи предусмотрены кнопки для типовых [операций с шаблоном](template_properties_operations.md).

## Свойства шаблона записи

Помимо [общих свойств](template_common_properties.md) на странице «**Свойства**» шаблона записи отображаются перечисленные ниже поля.

* «**Является справочником**» — установите этот флажок, если шаблон является хранилищем справочных данных, например названий городов, стран, марок автомобилей и т. п. Если установлен этот флажок, отображаются следующие два пункта:
    * «**Переносить данные при трансфере**» — установите этот флажок, чтобы записи из этого шаблона переносились вместе с шаблоном при экспорте и импорте приложения с помощью [управления версиями][управление-версиями-приложения].
    * «**Ключевой атрибут**» — выберите атрибут, который будет использоваться в качестве ключевого при переносе записей.

!!! Note "Примечание"
    * В шаблоне-справочнике атрибуты типа «**[Запись](attribute_record.md)**» могут ссылаться только на шаблоны-справочники.
    * В качестве ключевого можно выбрать только атрибут  типа «**[Текст](attribute_text.md)**» или «**[Число](attribute_text.md)**» с установленным флажком «**Контролировать уникальность значений**».
    * Если у записи ключевой атрибут не имеет значения, то при импорте приложения запись не переносится.

* «**Используется в шаблонах**» — список всех шаблонов процессов, в которых задействован данный шаблон записи.
* «**Связанные процессы**» — список шаблонов процессов, связанных с данным шаблоном записи.

*![Свойства шаблона записи](record_templates_properties.png)*

--8<-- "related_topics_heading.md"

**[Общие свойства шаблонов](template_common_properties.md)**

**[Операции на странице «Свойства» шаблона](template_properties_operations.md)**