# Определение возраста покупателей

## Описание проекта

Сетевой супермаркет «Хлеб-Соль» внедряет систему компьютерного зрения для обработки фотографий покупателей. Фотофиксация в прикассовой зоне поможет определять возраст клиентов, чтобы:

- Анализировать покупки и предлагать товары, которые могут заинтересовать покупателей этой возрастной группы;
- Контролировать добросовестность кассиров при продаже алкоголя.

Постройте модель, которая по фотографии определит приблизительный возраст человека. В вашем распоряжении набор фотографий людей с указанием возраста.

## **Инструкция по выполнению проекта**

- Проведите исследовательский анализ набора фотографий.
- Подготовьте данные к обучению.
- Обучите нейронную сеть и рассчитайте её качество.

## Описание данных

Данные взяты с сайта ChaLearn Looking at People. Они находятся в папке /datasets/faces/. 
В вашем распоряжении одна папка со всеми изображениями (/final_files) и CSV-файл labels.csv с двумя колонками: file_name и real_age. 

## Общий вывод

- Разработали модель машинного обучения, которая по фотографии определит приблизительный возраст человека на супермаркет «Хлеб-Соль».

- Провели предобработку данных: Проверили пропушенные значения, неявные дубликаты и соответствия данных.

- Для поиска лучшего моделя взяли архитектуру свёрточной нейронной сети ResNet предобученной на наборе ImageNet. Для выполнения быстрее кода, взяли загруженный веса модели ResNet50   на сервере.Чтобы  избежать случайные предсказания на тестовой выборке заморозили часть сети.

- Использовали оптимизатор Adam,для loss функции mean_squared_error и метрика mae.

- При обучении взяли гиперпараметры learning_rate=0.0001,batch_size=32,epochs=40.

- Можно было обучить модель ещё глубже но это требует мошные вычислительные ресурсы. К сожалению это у нас ограничено.

- Рекомендую использовать для определения приблизительный возраст человека  модель архитектуру свёрточной нейронной сети ResNet50.