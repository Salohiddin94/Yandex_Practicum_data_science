# Проект для «Викишоп» 

Интернет-магазин «Викишоп» запускает новый сервис. Теперь пользователи могут редактировать и дополнять описания товаров, как в вики-сообществах. То есть клиенты предлагают свои правки и комментируют изменения других. Магазину нужен инструмент, который будет искать токсичные комментарии и отправлять их на модерацию.

Обучите модель классифицировать комментарии на позитивные и негативные. В вашем распоряжении набор данных с разметкой о токсичности правок.

Постройте модель со значением метрики качества *F1* не меньше 0.75.

**Инструкция по выполнению проекта**

1. Загрузите и подготовьте данные.
2. Обучите разные модели.
3. Сделайте выводы.

Для выполнения проекта применять *BERT* необязательно, но вы можете попробовать.

**Описание данных**

Данные находятся в файле `toxic_comments.csv`. Столбец *text* в нём содержит текст комментария, а *toxic* — целевой признак.

## Выводы

- Разработали модель машинного обучения, которая классифицирует комментарии на позитивные и негативные.

- Провели предобработку данных: очищали текст.

- Для поиска лучшего моделя использовали пайплан с гиперпараметрами модели LogisticRegression(),DecisionTreeClassifier,KNeighborsClassifier() и поиска лучшего параметра RandomizedSearchCV.

- Лучшая модель LogisticRegression с параметрами penalty='l1', random_state=42, solver='liblinear' и метрика на тесте f1_score=0.781 .

- Рекомендую использовать для классификация комментарии  модель LogisticRegression с параметрами penalty='l1', random_state=42, solver='liblinear' .