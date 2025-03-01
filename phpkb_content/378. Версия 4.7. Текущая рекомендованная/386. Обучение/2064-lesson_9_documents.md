---
title: Урок 9.  Формирование документов
kbId: 2064
---

# Урок 9. Формирование документов

## Введение

Следуя указаниям в этом уроке, вы настроите автоматический экспорт отчета о затратах на основе данных процесса и по шаблону, созданному с помощью Microsoft Excel.

**Предусловие:** пройден [Урок 6. Усовершенствованный процесс](https://kb.comindware.ru/article.php?id=2059).

**Расчетная продолжительность:** 15 мин.

**Примечание:** в данном уроке представлен продукт **{{ productName }}** версии 4.2.219.0, внешний вид страниц и меню в других версиях продукта может отличаться.

## Формирование авансового отчета

Настроим генерацию отчета по затратам по кнопке в задаче *«Выполнение рейса»*.

**Примечание**


Настройка экспорта данных состоит из следующих этапов: сначала мы создадим файл Excel с шаблоном, по которому будет формироваться отчет (также можно создать шаблон в формате Word), затем загрузим этот файл в систему и настроим операцию, которая будет выполняться при нажатии кнопки.
Создадим файл для шаблона экспорта…

 **1.**  Создайте файл Excel (в формате XLSX).

 **2.**  Заполните лист Excel, как показано на следующей иллюстрации.

Внимание!

В файле шаблона экспорта необходимо указывать те системные имена, которые вы фактически использовали в своём приложении.

Например, если вы присвоили атрибуту *«Номер заявки»* системное имя `Nomerzayavki123`, то именно это имя следует использовать в файле шаблона экспорта.

То есть, если системные имена, приведённые в уроках, не совпадают с фактическими системными именами в вашем приложении, используйте фактические системные имена, а не копируйте их из текста уроков.

_![Шаблон авансового отчета в формате Excel](https://kb.comindware.ru/assets/img_624594abce6ec.png)_

## Синтаксис файла шаблона экспорта

Подробные сведения об использовании шаблонов экспорта см. в разделе *«[Шаблоны экспорта](https://kb.comindware.ru/category.php?id=468)»*.

В файле шаблона экспорта в фигурных скобках `{ }` указывайте системные имена **атрибутов**, значения которых должны отображаться в отчете.

Текст без фигурных скобок будет отображаться как обычный текст.

Для вывода значений из шаблона, связанного с атрибутом типа «**Запись***»*, используйте оператор `foreach`:

- в начале строки в фигурных скобках указываются оператор `foreach` и системное имя атрибута типа «**Запись**» — `{foreach:Zatraty}`;
- затем перечисляются системные имена атрибутов из связанного с этим атрибутом шаблона записи, также в фигурных скобках — `{Tipzatrat.Nazvanie}` `{Summa}`;
- в конце строки указывается оператор `end` и системное имя атрибута типа «**Запись**» — `{end:Zatraty}`;
- `Zatraty` — системное имя атрибута типа «**Запись***» шаблона *«Заявка на автомобиль»*, связанного с шаблоном *«Затраты»*.*
- `Summa` и `Tipzatrat` — системные имена атрибутов шаблона *«Затраты»*.
- `Tipzatrat` — атрибут типа «**Запись**» в шаблоне *«Затраты»*, связанный с шаблоном *«Тип затрат»*. С помощью символа точки мы обращаемся к атрибуту `Nazvanie` шаблона *«Тип затрат»*.

Кроме того, мы используем системные имена следующих атрибутов шаблона *«Заявка на автомобиль»*:

- `Itogovayasummazatrat`  — итоговая сумма затрат;
- `Nomerzayavki`  — номер заявки;
- `Vremyapodachi`  — время подачи.

## Настройка шаблона экспорта

 **1.**  Перейдите на вкладку «**Шаблоны экспорта**» шаблона записи *«Заявка на автомобиль»*.

 **2.**  Нажмите кнопку «**Создать**».

![Создание шаблона экспорта для шаблона записи «<em>Заявка на автомобиль</em>»](https://kb.comindware.ru/assets/img_63175c2c30b3d.png)

Создание шаблона экспорта для шаблона записи *«Заявка на автомобиль»*

 **3.** Отобразится окно «**Новый шаблон экспорта**».

**4.** Укажите **название** шаблона экспорта *«Авансовый отчет»*.

 **5.** В поле «**Файл шаблона**» выберите пункт «****Значение****  »  и загрузите созданный ранее файл шаблона в формате XLSX.

**6.** В поле «**Имя выходного файла**» выберите пункт «**Значение**» и укажите требуемое имя экспортируемого файла с данными.

**7.** Установите флажок «**Экспортировать как PDF**».

**8.** Нажмите кнопку «**Сохранить**».

_![Настройка свойств шаблона экспорта](https://kb.comindware.ru/assets/img_63175def9edd8.png)_

## Настройка кнопки экспорта отчета

При создании шаблона экспорта автоматически создается кнопка экспорта. Удостоверимся, что эта кнопка экспорта соответствует нашим требованиям…

 **1.**  Перейдите на вкладку «**Кнопки***» шаблона *«Заявка на автомобиль»*.*

_![Список кнопок шаблона записи](https://kb.comindware.ru/assets/img_6317c3362c2cf.png)_

 **2.**  Откройте кнопку *«Авансовый отчет»*. Проверьте корректность её свойств:

- **отображаемое название** — Авансовый отчет;
- **контекст операции**— **Запись**;
- **операция —** **Экспорт записи**;
- **результат выполнения** — **Скачать документ**;
- **шаблон экспорта** — Авансовый отчет.

_![Свойства кнопки экспорта документа, сформированному по шаблону экспорта](https://kb.comindware.ru/assets/img_6475e53906e3b.png)_

Добавим кнопку для экспорта данных на экранную форму. Для этого создадим новую форму…

 **1.**  Перейдите на вкладку «**Формы**» шаблона *«Заявка на автомобиль»*.

 **2.**  Нажмите кнопку «**Создать**»*.*

 **3.**  Введите **отображаемое название** формы — *«Выгрузка отчета»*.

 **4.**  Измените **отображаемое название** автоматически созданной **новой области** на *«Выгрузка отчета»*.

 **5.**  Выделите область кнопок *«Выгрузка отчета»* и перетащите на неё кнопку *«Авансовый отчет»*.

**6.** Сохраните форму.

_![Добавление кнопки на форму выгрузки отчета](https://kb.comindware.ru/assets/img_6317c544eb9bd.png)_

Теперь добавим созданную форму на форму задачи *«Выполнить рейс»*…

 **1.**  Перейдите на вкладку «**Диаграмма***» шаблона процесса *«Заказ автотранспорта»* и нажмите кнопку* «**Редактировать**».

 **2.**  Выберите задачу *«Выполнить рейс»* и в меню элемента нажмите кнопку «**Форма**».

 **3.** Разверните в панели элементов шаблон *«Заявка на автомобиль»* и перетащите форму *«Выгрузка отчета»* под область *«Выполнить рейс»*.

 **4.**  Сохраните форму.

![Добавление вложенной формы с кнопкой выгрузки отчета на форму задачи «<em>Выполнить рейс</em>»](https://kb.comindware.ru/assets/img_6317c6a560b8b.png)

Добавление вложенной формы с кнопкой выгрузки отчета на форму задачи *«Выполнить рейс»*

**5.**  Опубликуйте диаграмму бизнес-процесса *«Заказ автотранспорта»*.

## Настройка разрешения на использование кнопки

Для того, чтобы водитель мог воспользоваться кнопкой *«Авансовый отчет»*, необходимо предоставить ему соответствующее разрешение с помощью роли *«Водитель»*.

**1.** Откройте раздел «**Роли***» приложения *«Управление автопарком»*.*

**2.** Откройте роль *«Водитель»* и перейдите на вкладку «**Разрешения**»**.**

**3.** Раскройте в панели ресурсов шаблон *«Заявка на автомобиль»* и перетащите из него на таблицу разрешений кнопку *«Авансовый отчет»*.

**4.** Установите для кнопки *«Авансовый отчет»* разрешение «**Использование кнопки**»*.*

**5.** Сохраните роль.

![Добавление для роли «<em>Водитель</em>» разрешения на использование кнопки «<em>Авансовый отчет</em>»](https://kb.comindware.ru/assets/img_6317c77750dd6.png)

*Добавление для роли *«Водитель»* разрешения на использование кнопки *«Авансовый отчет»**

## Тестирование

**Примечание**


Если вы проходите этот урок после прохождения [Урока 8 *«Аккаунты»*](https://kb.comindware.ru/article.php?id=2063), то для тестирования работы приложения вы можете выполнять пользовательские задачи одним из трех способов:

- войти в систему несколько раз с разными учетными записями: заказчик, секретарь, водитель, диспетчер;
- создать заявку на автомобиль, затем открыть диаграмму запущенного бизнес-процесса *«Заказ автотранспорта»* и переходить к задачам с помощью кнопки «**Перейти***»  ![Перейти](https://kb.comindware.ru/assets/img_6317c8a89172d.png)  в панели «***Токены****  »;
- назначить себя исполнителем всех пользовательских задач.

 **1.**  Перейдите к списку экземпляров шаблона *«Заказ автотранспорта»* и создайте новую заявку.

 **2.**  С помощью раздела «**Мои задачи**» пройдите бизнес-процесс до задачи **«Выполнение рейса»*.*

 **3.**  Откройте форму задачи *«Выполнить рейс»* и заполните коллекцию затрат.

**4.** Нажмите кнопку «**Сохранить**».

 **5.**  Нажмите кнопку *«Авансовый отчет»* и дождитесь экспорта (скачивания) сформированного PDF-документа. 

_![Выгрузка сформированного по шаблону экспорта документа с помощью кнопки на форме](https://kb.comindware.ru/assets/img_6317ca7944c7f.png)_

**6.**  Откройте экспортированный документ. 

**7.**  Завершите задачу.

![PDF-документ авансового отчета, экспортированный по шаблону в формате Excel из {{ productName }}](https://kb.comindware.ru/assets/img_6245b16fd7334.png)

PDF-документ авансового отчета, экспортированный по шаблону в формате Excel из {{ productName }}

## Результаты

Поздравляем! Вы научились автоматически формировать и экспортировать документы по шаблонам, подставляя в них фактические данные из бизнес-приложения.

В  [следующем уроке](https://kb.comindware.ru/article.php?id=2065)  вы научитесь работать с контентом.

{% include-markdown ".snippets/hyperlinks_mkdocs_to_kb_map.md" %}
