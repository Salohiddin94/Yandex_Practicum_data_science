# Прогнозирование заказов такси

Компания «Чётенькое такси» собрала исторические данные о заказах такси в аэропортах. Чтобы привлекать больше водителей в период пиковой нагрузки, нужно спрогнозировать количество заказов такси на следующий час. Постройте модель для такого предсказания.

Значение метрики *RMSE* на тестовой выборке должно быть не больше 48.

Вам нужно:

1. Загрузить данные и выполнить их ресемплирование по одному часу.
2. Проанализировать данные.
3. Обучить разные модели с различными гиперпараметрами. Сделать тестовую выборку размером 10% от исходных данных.
4. Проверить данные на тестовой выборке и сделать выводы.


Данные лежат в файле `taxi.csv`. Количество заказов находится в столбце `num_orders` (от англ. *number of orders*, «число заказов»).

## Общий вывод

- Разработали модель машинного обучения, которая прогнозирует количество заказов такси на следующий час.

- Провели предобработку данных: Сортировали по индексу и ресемпировали данные по одному часу.

- Для поиска лучшего моделя использовали пайплан с гиперпараметрами модели LinearRegression() и два бустинга LGBMRegressor, CatBoostregressor и поиска лучшего параметра RandomizedSearchCV.

- Лучшая модель CatBoostRegressor с параметрамы {'loss_function': 'RMSE', 'random_state': 42, 'max_depth': 5, 'iterations': 100} и метрика на тесте rmse_score=44.5 .

- Худшая модель оказалось LinearRegression() .

- По время обучения и по метрика rmse_score  на тренировочной выборке  лучшая модель CatBoostRegressor.

- Рекомендую использовать для прогнозирования количество заказов такси на следующий час  модель CatBoostRegressor с параметрамы {'loss_function': 'RMSE', 'random_state': 42, 'max_depth': 5, 'iterations': 100} .