# interns-test-march-21

## Задачи

1. Есть сайт https://yandex.ru/covid19/stat. Нужно написать парсер, который бы получал данные о заражениях, смертях и тестах в динамике по всем странам на графике и формировал бы CSV файл на каждый момент начала запуска парсера.

![image](https://user-images.githubusercontent.com/30187683/111162102-e2bf7780-85ac-11eb-9676-886302013f42.png)

2. Нужно написать SQL-выражение, которое бы складывало полученные из п.1 данные в следующую таблицу:

![image](https://user-images.githubusercontent.com/30187683/111163785-780f3b80-85ae-11eb-879c-b272891161fd.png)

  - **Название таблицы**: ydata_main_data

  - **Первичный ключ**: составной, на основе полей PK

  - **Индексы**: version_dt, обычный

3. Из полученной таблицы `ydata_main_data` нужно составить таблицу `ydata_detail_main_data`, дедублицировав записи на основе поля `version_dt` (брать самое последнее). Нужно показать 2 способа, как это сделать.

4. Основывясь на данных таблицы `ydata_detail_main_data` составить SQL-запрос, который позволит посчитать следующие метрики на каждую из дат `data_date`:
  - Те страны и значение метрики "Смерти / Ср.Заражения за 14 дат назад", где показатель выше `X%` (выбрать самостоятельно), отсортировав страны по убыванию данной метрики.

  - Те страны и значение метрики "Заражения / Тесты", отфильтровав только те страны, где показатель метрики выше `X%` (выбрать самостоятельно) и ТОП-5 самых маленьких значений "Смерти / Ср. Заражения". 

    Полученный датасет отсортировать по убыванию метрики "Заражения / Тесты".

5. (бонус). Запустить REST-API на Flask, которон бы позволило получать данные из `ydata_detail_main_data`, вводя в query params параметры: `country` - название страны, по которой нужны данные, `data_date` - дата, на которую нужны данные. 

6. Весь код положить в форк данного проекта у себя на странице.
