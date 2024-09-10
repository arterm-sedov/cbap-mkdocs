---
tags:
    - процессная архитектура
    - конструктор диаграмм
    - операции в конструкторе диаграмм
    - диаграмма процесса
    - диаграмма бизнес-способностей
hide:
    - tags
---

# Конструктор диаграмм

В **{{ productNameArchitect }}** предусмотрен визуальный конструктор диаграмм процессов в нотации BMPN 2.0 и диаграмм бизнес-способностей.

## Переход к конструктору диаграмм

1. Выберите элемент процессной архитектуры в [панели навигации][navigation_panel] или дважды нажмите его строку в [реестре процессов][просмотр-реестра-процессов].
2. Откроется диаграмма процесса или бизнес-способностей в режиме просмотра.
3. Нажмите кнопку «**Редактировать**».
4. Отобразится конструктор диаграмм.

*![Переход к конструктору диаграмм](process_architecture_modeling_edit_diagram.png)*

## Элементы конструктора диаграмм

*![Конструктор диаграмм процессов](process_architecture_modeling_process_diagram_designer.png)*

*![Конструктор диаграмм бизнес-способностей](process_architecture_modeling_business_capabilities_diagram_designer.png)*

1. Кнопки типовых операций
    * **Просмотр** <i class="fa-light fa-eye"></i> — переход в режим просмотра диаграммы.
    * **Очистить** <i class="fa-light fa-trash"></i> — безвозвратное удаление всех элементов с диаграммы. При нажатии этой кнопки отобразится запрос подтверждения.
    * **Обсуждение** <i class="fa-light fa-comment-dots"></i> — отображение чата для обсуждения диаграммы.
    * **Версии** <i class="fa-light fa-code-branch"></i> — управление версиями диаграммы.
    * **Свойства** <i class="fa-light fa-sidebar-flip"></i> — [настройка свойств](configuring_process_entity_properties.md) выбранного элемента или всей диаграммы.
2. Кнопки «**Импорт**» <i class="fa-light fa-arrow-down-to-bracket"></i> и «**Проверить**» <i class="fa-light  fa-circle-exclamation-check"></i> — позволяют [импортировать](importing_process_entity.md) и [проверить диаграмму](verify_diagram.md). Кнопка «**Проверить**» отображается только для диаграмм процессов. Проверка диаграмм бизнес-способностей не предусмотрена.
3. Палитра элементов — содержит либо элементы нотации BPMN 2.0, либо элементы нотации бизнес-способностей.
--8<-- "process_architecture_diagram_zoom_controls.md"
6. Панель свойств. В этой области также отображаются панель обсуждения и панель версий диаграммы.

### Меню элемента

При выборе любого элемента на диаграмме отображается его контекстное меню с перечисленными ниже пунктами.

*![Меню элемента в конструкторе диаграмм](process_architecture_modeling_diagram_designer_element_menu.png)*

* **Быстрое создание** — создание элемента, связанного посредством потока управления с текущим элементом. Набор доступных элементов зависит от типа текущего элемента.
* **Изменить тип** — смена типа элемента, набор доступных типов зависит от типа текущего элемента.
* **Модификаторы** — доступны для задач и процессов.
* **Изменить цвет** — выбор цвета рамки и фона элемента.
* **Свойства** — данный пункт в текущей версии {{ productNameArchitect }} действует только для элементов «**Вызов процесса**» и «**Скрытый пул**» на диаграммах процессов и элементов «**Процесс**», «**Ссылка на процесс**», «**Ссылка на группу процессов**».
* **Удалить** — удаление текущего элемента.

{%
include-markdown "../viewing_diagram.md"
start="<!--navigating-to-child-start-->"
end="<!--navigating-to-child-end-->"
%}

--8<-- "related_topics_heading.md"

**[Просмотр реестра процессов][просмотр-реестра-процессов]**

**[Редактирование диаграммы](edit_diagram.md)**

**[Просмотр диаграммы](viewing_diagram.md)**