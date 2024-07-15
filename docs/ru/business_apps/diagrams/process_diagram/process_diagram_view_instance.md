---
tags:
  - диаграмма экземпляра процесса
  - цепочка событий
  - токены
  - позиции токенов
  - остановка процесса
  - перезапуск токена
  - перезапуск процесса
  - создание токена
  - удаление токена
  - переход к задаче по процессу
  - журнал изменений
  - экземпляр процесса
  - диаграмма процесса
  - шаблон процесса
  - процесс
hide:
  - tags
---

# Использование диаграммы экземпляра процесса

Диаграмма экземпляра процесса позволяет просмотреть текущие позиции токенов на элементах выполняющегося процесса, [создавать](#создание-токена), [перезапускать и удалять токены](#tokens-tab), остановить процесс, просмотреть [цепочку событий](#просмотр-цепочки-событий) процесса.

## Переход к диаграмме экземпляра процесса

### Переход из списка экземпляров

1. Откройте [список экземпляров процесса](template_view_records.md).
2. Дважды нажмите строку экземпляра в списке.
3. Отобразится диаграмма экземпляра.

### Переход из списка версий

1. Откройте [список версий](process_diagram_version_control.md#process-diagram-version-list) диаграммы процесса со страницы «**Диаграмма**» шаблона процесса.
2. В столбце «**Запущенные экземпляры**»  нажмите гиперссылку с ID экземпляра процесса.
3. Отобразится диаграмма экземпляра.

*![Диаграмма экземпляра процесса](process_diagram_view_instance.png)*

## Области на странице диаграммы экземпляра процесса

1. **Кнопки операций с экземпляром и элементами процесса**
      
      * **Остановить процесс** — удаление всех токенов с диаграммы экземпляра процесса. **[Статус](#process-status)** процесса сменится на «**Отменён**». Эта кнопка отображается, если на элементах диаграммы имеются токены и не выбран ни один элемент.
      * **Архивировать** — архивирование экземпляра процесса. Архивные экземпляры не отображаются в списке экземпляров, если в конфигурации соответствующей таблицы не установлен флажок «**Показывать архивные записи**».
      * **Создать токен** — [создание токена](#создание-токена) на выбранном элементе. Эта кнопка отображается, если выбран элемент диаграммы.

2. **Панель информации**

      * **Свойства** — сведения об экземпляре процесса.
          * **Статус**
          {: #process-status}
              * **Активен** — на элементах процесса есть токены.
              * **Неактивен** — на элементах процесса нет токенов.
              * **Завершён** — процесс был завершён ожидаемым образом, на элементах нет токенов.
              * **Отменён** — процесс был остановлен с удалением всех токенов.
          * **Дата создания** — дата и время создания экземпляра.
          * **Создатель** — ссылка на аккаунт создателя экземпляра.
          * **Шаблон процесса** — ссылка на страницу настройки шаблона процесса.
          * **Запись** — ссылка на запись, связанную с экземпляром процесса.
          * **Шаблон записи** — ссылка на список записей шаблона, связанного с шаблоном данного процесса.
      * **Токены** — список элементов процесса, на которых находятся токены. При выборе элемента отображается панель «**Действия**» со следующими кнопками:
      {: #tokens-tab}
          * **Перейти** <i class="fa-light  fa-external-link-square"></i> к форме пользовательской задачи или к диаграмме подпроцесса. Для этого также можно дважды нажать пользовательскую задачу или подпроцесс на диаграмме.
          * **Перезапустить токен** <i class="fa-light  fa-redo"></i> на данном элементе.
          * **Удалить токен** <i class="fa-light  fa-trash"></i> с данного элемента.
      * **Журнал изменений** — [список событий](#просмотр-цепочки-событий), произошедших в ходе выполнения процесса.

3. **Кнопки масштабирования диаграммы**

      --8<-- "process_diagram_scale_buttons.md"

4. **Позиции токенов** — элементы, на которых находятся токены, выделяются желтой или зеленой рамкой.

## Создание токена

1. Выберите элемент на диаграмме.
2. Нажмите кнопку «**Создать новый токен**».
3. В отобразившемся окне выберите, следует ли выполнять сценарий на входе в выбранный элемент.
4. Созданный токен отобразится на вкладке «**Токены**».

## Просмотр цепочки событий

1. Перейдите на вкладку «**Журнал изменений**».
2. Нажмите значок слева от события.

    *![Значок события в журнале изменений](process_diagram_view_instance_event_icon.png)*

3. Отобразится окно «**Цепочка событий**».
4. Первоначально выбранное событие будет выделено в цепочке и отмечено кружком.
5. В правой панели отобразятся сведения о событии.
6. Выбирайте события в цепочке, чтобы просмотреть сведения о них.

    *![Цепочка событий экземпляра процесса](process_diagram_view_instance_events_chain.png)*

--8<-- "related_topics_heading.md"

**[Управление версиями диаграммы процесса](process_diagram_version_control.md)**

**[Публикация диаграммы процесса](process_diagram_publish.md)**

**[Просмотр диаграммы процесса](process_diagram_view.md)**