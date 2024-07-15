---
tags:
 - диаграммы
 - диаграмма процесса
 - диаграмма бизнес-процесса
 - шаблон процесса
 - процесс
 - бизнес-процесс
 - диаграмма
 - проверка диаграммы
 - ошибки диаграммы процесса
 - публикация диаграммы
hide:
 - tags
---

# Проверка диаграммы процесса

Перед [публикацией](process_diagram_publish.md) диаграммы будет автоматически выполнена её проверка. 

Для проверки диаграммы вручную, нажмите кнопку «**Проверить**».

!!! Note "Примечание"
      Опубликовать диаграмму с ошибками невозможно, поэтому после проверки все ошибки необходимо устранить.

* После проверки элементы с ошибками выделяются красной рамкой с восклицательным знаком <i class="fa-light fa-triangle-exclamation"></i> и на верхней информационной панели отображается флаг <i class="fa-light fa-flag"></i> с количеством ошибок.

* Для просмотра списка [сообщений об ошибках](#типичные-ошибки-диаграммы-процесса) нажмите флаг <i class="fa-light fa-flag"></i> в верхней информационной панели.

* Для просмотра сообщения об ошибке для элемента нажмите восклицательный знак <i class="fa-light fa-triangle-exclamation"></i> рядом с ним.

*![Просмотр ошибок диаграммы процесса](process_diagram_validation_errors.png)*

## Типичные ошибки диаграммы процесса

Проверка диаграммы процесса может выявить ошибки, которые не позволяют опубликовать диаграмму. В следующей таблице представлены некоторые типичные ошибки с описанием причин их возникновения и способами устранения.

| Ошибка | Элемент диаграммы | Причина | Способ устранения  |
| ------ | ----------------- | -------- | ------------------ |
| Диаграмма пуста                                                                         | Диаграмма                   | Диаграмма не содержит ни одного элемента | Добавьте на диаграмму элементы: как минимум начальное и конечное события |
| Диаграмма должна содержать хотя бы одно начальное событие                               | Диаграмма                   | На диаграмме отсутствует начальное событие | Добавьте на диаграмму начальное событие |
| У этого элемента должен быть один исходящий поток управления                            | Начальное событие           | У начального события отсутствует исходящий поток или несколько исходящих потоков | Подсоедините только один исходящий поток к начальному событию |
| На диаграмме не может быть более одного простого (нетипизированного) начального события | Простое начальное событие   | На диаграмме имеется несколько простых начальных событий | Удалите все простые начальные события кроме одного либо измените типы начальных событий |
| Необходим хотя бы один входящий поток управления                                        | Конечное событие            | У конечного события отсутствует входящий поток | Подсоедините входящий поток к конечному событию |
| Необходим хотя бы один входящий поток управления                                        | Пользовательская задача     | У пользовательской задачи отсутствует входящий поток | Подсоедините входящий поток к пользовательской задаче |
| У этого элемента должен быть один исходящий поток управления                            | Пользовательская задача     | У пользовательской задачи отсутствует исходящий поток или несколько исходящих потоков | Подсоедините только один исходящий поток к пользовательской задаче |
| У этого элемента нет потоков управления или к нему невозможно перейти из начального с события | Пользовательская задача | У пользовательской задачи отсутствует входящий поток или ни входящий поток не соединён с начальным событием | Подсоедините к пользовательской задаче входящий поток, соединённый с начальным событием напрямую или через другие элементы |
| Пользовательская задача должна иметь минимум одного ответственного                      | Пользовательская задача     | В свойствах пользовательской задачи не указан исполнитель данной задачи | В свойствах пользовательской задачи выберите исполнителей на вкладке «Дополнительные» |
| Необходимо указать исходящий поток управления «иначе»                                   | Развилка «или/или»          | В свойствах развилки «или/или» не указан поток «иначе» | В свойствах развилки укажите указать один поток «иначе» на вкладке «Дополнительные» в соответствии с логикой процесса. |
| У этого элемента нет потоков управления или к нему невозможно перейти из начального с события  | Развилка «или/или»   | У развилки «или/или» отсутствует входящий поток или ни один входящий поток не соединён с начальным событием | Подсоедините к развилке «или/или» входящий поток, соединённый с начальным событием напрямую или через другие элементы |
| Необходим хотя бы один входящий поток                                                   | Развилка «или/или»          | У развилки «или/или» отсутствует входящий поток | Подсоедините входящий поток к развилке «или/или» |
| Недопустимое определение потока управления                                              | Развилка «или/или»          | У развилки «или/или» несколько исходящих потоков, но не указан поток «иначе» или не задано условие для одного из исходящих потоков | В свойствах развилки «или/или» на вкладке «Дополнительные» укажите поток «иначе» и настройте условия для всех остальных потоков |
| В событии-таймере не настроен таймер                                                    | Промежуточное событие-таймер | В свойствах промежуточного события-таймера не задан интервал | В промежуточного свойствах события-таймера настройте интервал таймера на вкладке «Дополнительные» |
| Необходим хотя бы один входящий поток управления                                        | Промежуточное событие       | У промежуточного события отсутствует входящий поток | Добавить входящий поток промежуточному событию |
| У этого элемента должен быть один исходящий поток управления                            | Промежуточное событие       | У промежуточного события отсутствует исходящий поток или несколько исходящих потоков  | Добавить исходящий поток промежуточному событию |
| В начальном событии не настроен таймер                                                  | Начальное событие-таймер    | В свойствах начального события-таймера не настроен таймер | В свойствах начального события-таймера настройте таймер на вкладке «Дополнительные» |
| Поток управления не соединен с конечной точкой                                          | Поток управления            | Поток управления не соединен с целевым элементом | Соедините поток управления с целевым элементом диаграммы

--8<-- "related_topics_heading.md"

**[Редактирование диаграммы процесса](process_diagram_edit.md)**

**[Публикация диаграммы процесса](process_diagram_publish.md)**