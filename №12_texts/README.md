### Тексты. Поиск токсичных комментариев

### Задача

- Обучите модель классифицировать комментарии на позитивные и негативные
- Постройте модель со значением метрики качества F1 не меньше 0.75

### Решение

1. Анализ данных
2. Выявление дисбаланса классов 
3. Удаление лишних пробелов и работа с регулярными выражениями (удаление ненужных для анализа символов)
4. Лемматизация текста 
5. Исправление ошибок
6. Удаление стоп-слов, TF-IDF
7. Построение моделей для машинного обучения: Дерево решений, Дерево решений с использованием GridSearchCV, Логистическая регрессия, 

### Вывод

Лучшей моделью оказалась линейная регрессия. В целом линейные модели лучше справляются с подобными  задачами
Матрица confusion_matrix показывает, что результаты модели на тестовой выборке дают хорошие показатели: 

55314 положительных предсказаний, когда они действительно были правдой
5267 отрицательных предсказаний, когда они были toxic

ошибки первого и второго рода в матрице равны 2006 и 1242 соответвенно. Это около одного процента от предсказаний.

Наилучшие результаты показала модель логистической регрессии со следующими параметрами:  
- 'penalty': ['l2'],
- 'C':[0.15],
- 'intercept_scaling':range(5),
- 'solver':['liblinear']

F1_score  на этой модели равен 0.7686

`pymystem3` `NLTK` `GridSearchCV` `f1_score`  `LogisticRegression` `DecisionTreeClassifier`  `TfidfVectorizer` `matplotlib` `value_counts` `Mystem` `Лемматизация spaCy` `pyspellchecker`
