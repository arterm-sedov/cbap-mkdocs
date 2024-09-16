---
title: Задача-вызов сервиса
kbId: 2609
---

# Задача-вызов сервиса {: #service_call_task}

!!! question "Определения"

    **Задачу-вызов сервиса** выполняет система.

    При переходе токена на этот элемент автоматически выполняется назначенная задаче **[функция][functions]**.

    По завершении выполнения скрипта токен переходит на следующий элемент диаграммы процесса.

!!! note "Примечание"

    Создание новых функций в **{{ productName}}** версии 4 не предусмотрено, возможно только редактировать имеющиеся функции, созданные в предыдущих версиях **{{ productName}}**.

_![Задача-вызов сервиса и её меню элемента](service_call_task_menu.png)_

## Операции в меню элемента «Задача-выполнение сценария»

- **Действия**
    - **Свойства** <i class="fa-light fa-gear">‌</i> — переход к окну [свойств задачи-вызова сервиса][service_call_task_properties].
    - **Сценарий на входе** <i class="fa-light fa-arrow-right-to-bracket">‌</i> — переход к конструктору сценария на входе в данный элемент.
    - **Сценарий на выходе** <i class="fa-light fa-arrow-right-from-bracket">‌</i> — переход к конструктору сценария на выходе из данного элемента.
    - **Удалить** <i class="fa-light fa-trash-can">‌</i> — удаление данного элемента из диаграммы процесса.
- **Изменить тип** — смена типа задачи.
- **Быстрое создание** — добавление связанного элемента на диаграмму процесса.

## Свойства задачи-вызова сервиса {: #service_call_task_properties}

В окне свойств **задачи-вызова сервиса** предусмотрены перечисленные ниже вкладки.

### Основные

На этой вкладке можно настроить [общие свойства элемента диаграммы процесса][process_diagram_element_common_properties].

!!! note "Примечание"

    Параметры «**Макс. время выполнения**», «**Интервал между попытками**», «**Количество попыток**» в текущей версии ПО не используются и не влияют на выполнение сценария.

_![Настройка основных свойств задачи-выполнения сценария](service_call_task_properties_setting.png)_

### Дополнительные

На этой вкладке следует выбрать [функцию][functions], которая будет выполняться при переходе токена на задачу-выполнение сценария.

_![Выбор глобальной функции для задачи-вызова сервиса](service_call_task_global_function_choice.png)_

## Настройка данных на входе

На этой вкладке следует настроить таблицу соответствия атрибутов сигнатуры функции с атрибутами шаблона записи для передачи данных из процесса в глобальную функцию.

Первые три столбца таблицы характеризуют атрибуты сигнатуры глобальной функции.

Последний столбец «_**Значение**_» позволяет задать статическое или вычисляемое значение, которое будет передаваться в функцию:

- **Значение** — введите фиксированное значение.
- **Атрибут** — выберите атрибута текущего или связанного шаблона записи, значение которого следует передать. Тип данных атрибута должен совпадать с типом данных атрибута сигнатуры функции.
- **Формула** — введите [формулу][formula_introduction], вычисляющую значение.
- **C#**— введите скрипт, возвращающий значение.

## Настройка данных на выходе

На этой вкладке следует настроить таблицу соответствия атрибутов сигнатуры функции с атрибутами шаблона записи для передачи полученных в результате исполнения глобальной функции данных в процесс.

Первые три столбца таблицы характеризуют атрибуты сигнатуры функции.

В последнем столбце «**Значение**» позволяет выбрать атрибут текущего или связанного шаблона записи. Тип данных атрибута должен совпадать с типом данных атрибута сигнатуры функции.

--8<-- "related_topics_heading.md"

**[Функции][functions]**

**[Пользовательская задача][user_task]**

**[Общие свойства элементов диаграммы процесса][process_diagram_element_common_properties]**

**[Элементы диаграммы процесса][process_diagram_elements]**

**[Редактирование диаграммы процесса][diagrams]**

{%
include-markdown ".snippets/hyperlinks_mkdocs_to_kb_map.md"
%}