# Профильное задание на стажировку MLE VK

## Важно

Github не поддерживает виджеты plotly, поэтому смотреть решение лучше тут:

1. https://www.kaggle.com/code/l1ghtsource/ranker-task/notebook
2. https://nbviewer.org/github/l1ghtsource/ranking-task/blob/main/solution.ipynb

## О задаче

Есть датасет для ранжирования [intern_task.csv](https://drive.google.com/file/d/1viFKqtYTtTiP9_EdBXVpCmWbNmxDiXWG/view).

- query_id - айди поисковой сессии
- rank - оценка релевантности
- feature_i (0 <= i <= 143) - фичи релевантности документа запросу

## Решение

*Стэк*: lightgbm, optuna, bluecast, sklearn, plotly

- Был проведён разведочный анализ данных (изучено распределение фичей, корреляционные матрицы)
- Был произведён отбор фичей: по матрице корреляций и на основе их дисперсии
- Были обучены 2 модели LGBMRanker (с указание дисбаланса классов и без), гиперпараметры были подобраны с помощью optuna
- Было получено распределение важностей фичей и были сохранены обе модели (в папке models)
- Были посчитаны метрики ndcg@1, ndcg@3, ndcg@5, ndcg@10, ndcg@20
 
## Результат
