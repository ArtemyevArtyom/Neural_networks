Данная модель нейронной сети предназначена для классификации дефектов поверхности стали. 

После загрузки тренировочных данных выполняется преобразование фотографий к формату 120х120. Затем, выполняется one-hot кодировка. Для борьбы с дисбалансом выполняется аугментация случайным семплированием. После проверки, мы видим, что полученные данные становятся сбалансированными. Далее, выполняется категоризация данных. Происходит разделение на тренировку и валидацию.
Построение нейронной сети производится в 3 теста с разным количеством нейронных слоёв. 
Первый тест: 

1)	Точность на обучающем наборе увеличилась с 0.2922 (эпоха 1) до 0.9339 (эпоха 10).
2)	На валидационном наборе точность также повысилась с 0.3553 до 0.8934.
3)	Значение потерь снижается с 10.8642 (эпоха 1) до 0.2216 (эпоха 10) на обучающем наборе данных.
4)	На валидационном наборе данных потери уменьшились с 10.5712 до 0.4076 за те же 10 эпох.

Второй тест:
1)	Точность на обучающем наборе увеличивается с каждой эпохой, достигая 93.01% к концу обучения, что меньше, чем на предыдущем тесте.
2)	Точность на валидационном наборе также повышается, но после 5 эпохи наблюдается небольшое снижение с 80.20% (Эпоха 5) до 77.66% на 7 эпохе, затем небольшой рост и падение до 82.74% (Эпоха 10).
3)	Потери на обучающем наборе снижаются, что указывает на улучшение модели в обучении. Однако, данный результат хуже, чем в предыдущем случае - 0.4988 (против 0.2216 в 1 тесте).
4)	Потери на валидационном наборе показывают уменьшение с 1.9741 (Эпоха 1) до 0.4988 (Эпоха 10), что также указывает на улучшение, несмотря на легкий подъем с 0.6303 на 0.6080 (сравнение Эпох 6 и 7).

Третий тест:
1)	Точность обучения растёт, но не так быстро, как в предыдущих вариантах. Достигает всего 61,63%.
2)	Точность на валидационном наборе растёт до 3-й эпохи и падает. Затем происходит незначительный рост до 66,5% на 10-й эпохе.
3)	Показатель потерь на обучающем наборе снижается в каждой эпохе, однако остаётся сравнительно высоким - 0.8464. В предыдущих тестах показатель был ниже.
4)	Потери на валидационном наборе уменьшаются с 1.3396 до 0.7733

На основании этих данных можно сделать вывод, что нейронная сеть успешно обучается и демонстрирует улучшение результатов за 10 эпох в каждом из тестов. Однако, наилучшие результаты по показателям точности и минимального значения потерь показала модель 1. Значит, в данном случае 3 скрытых слоя – наиболее оптимальны для решения задачи классификации.

Попробуем улучшить модель 1. Для этого увеличим количество эпох. В модели с тремя слоями время обучения увеличивается не так значительно, как в моделях с большим количеством слоёв. 

Четвёртый тест:
1)	Точность на обучающем наборе увеличивается с 29.86% до 95.81%. Данный показатель точности является самым высоким из всех проведенных тестов.
2)	Точность на валидационном наборе растёт с 25.38% (Эпоха 1) до 92.39% (Эпоха 5)
3)	Потери на обучающем наборе снижаются с 17.29 (Эпоха 1) до 0.17 (Эпоха 15)
4)	Потери на валидационном наборе уменьшаются с 13.92 до 0.32

Четвёртый тест показал лучшие результаты, модель удалось улучшить в показателях точности и уменьшить потери, незначительно увеличив время. 
Наблюдается небольшое увеличение потерь на валидационном наборе к концу обучения, но точность все равно остается высокой. Это может указывать на то, что модель немного переобучается, но не в значительной степени.

Вывод: Обучение модели кажется стабильным, без резких колебаний в точности или потерях. Постепенное улучшение показателей как на обучающем, так и на валидационном наборе свидетельствует об успешном процессе обучения.
