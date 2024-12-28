# Выбор локации для скважины

Допустим, вы работаете в добывающей компании «ГлавРосГосНефть». Нужно решить, где бурить новую скважину.

Вам предоставлены пробы нефти в трёх регионах: в каждом 10 000 месторождений, где измерили качество нефти и объём её запасов. Постройте модель машинного обучения, которая поможет определить регион, где добыча принесёт наибольшую прибыль. Проанализируйте возможную прибыль и риски техникой *Bootstrap.*

Шаги для выбора локации:

- В избранном регионе ищут месторождения, для каждого определяют значения признаков;
- Строят модель и оценивают объём запасов;
- Выбирают месторождения с самым высокими оценками значений. Количество месторождений зависит от бюджета компании и стоимости разработки одной скважины;
- Прибыль равна суммарной прибыли отобранных месторождений.

## Описание данных

Данные геологоразведки трёх регионов находятся в файлах: 

- /datasets/geo_data_0.csv. Скачать датасет
- /datasets/geo_data_1.csv. Скачать датасет
- /datasets/geo_data_2.csv. Скачать датасет
- id — уникальный идентификатор скважины;
- f0, f1, f2 — три признака точек (неважно, что они означают, но сами признаки значимы);
- product — объём запасов в скважине (тыс. баррелей).

## Условия задачи:

- Для обучения модели подходит только линейная регрессия (остальные — недостаточно предсказуемые).

- При разведке региона исследуют 500 точек, из которых с помощью машинного обучения выбирают 200 лучших для разработки.

- Бюджет на разработку скважин в регионе — 10 млрд рублей.

- При нынешних ценах один баррель сырья приносит 450 рублей дохода. Доход с каждой единицы продукта составляет 450 тыс. рублей,      поскольку объём указан в тысячах баррелей.

- После оценки рисков нужно оставить лишь те регионы, в которых вероятность убытков меньше 2.5%.  Среди них выбирают регион с    наибольшей средней прибылью.  

Данные синтетические: детали контрактов и характеристики месторождений не разглашаются.

## Цель исследования

 Цель исследования — разработать  модель машинного обучения, которая поможет определить регион, где добыча принесёт наибольшую прибыль.

## Ход исследования:

   1. Загрузка и подготовка данных.
   2. Обучение и проверка модели.
   3. Подготовка к расчёту прибыли.
   4. Расчёт прибыли и рисков.
   5. Общий вывод.

## Общий вывод

- Написали функцию для применения техники Bootstrap.

- Рассчитали риск и прибыль для каждого региона:

  - Cредняя прибыль в регионе 0 достаточно высокая (435,9 млн рублей), риск убытков составляет 6,1%.Это указывает на вероятность убыточных разработок, что может сделать регион менее привлекательным с точки зрения инвестиций. Диапазон прибыли также имеет значительный разброс — возможны как значительные убытки, так и прибыль.

  - Регион 1 показывает наилучшие результаты по средней прибыли (489,7 млн рублей) и имеет самый низкий риск убытков (1,1%).Диапазон доверительного интервала не включает отрицательные значения на уровне 2.5%-квантили, что делает этот регион наиболее надёжным для разработки. Он обладает лучшей сбалансированностью между возможной прибылью и минимальными рисками.
  
  - Регион 2 показывает самую низкую среднюю прибыль (403,7 млн рублей) среди всех регионов. Риск убытков самый высокий — 7,1%. Это делает регион 2 менее предпочтительным для инвестиций, так как высокая вероятность убытков и значительный разброс в диапазоне возможной прибыли делают его наименее стабильным.

- Рекомендую на основе анализа bootstrap и модели:

  - Наиболее прибылным  для разработки является регион 1, так как он имеет наибольшую среднюю прибыль, минимальный риск убытков и качество модели наименьшее.
  
  - Регион 0  требует более тщательного анализа рисков, так как вероятность убытков выше (6,1%).

  - Регион 2 представляет наибольшие риски и наименьшую среднюю прибыль, что делает его менее подходящим для инвестиций.
  