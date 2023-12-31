# ICR - Identifying Age-Related Conditions

*Ссылка на проект в Kaggle:* https://www.kaggle.com/code/sombrahacker/catboostclassifier-and-optuna

Необходимо предсказать, есть ли у человека одно или несколько из трех заболеваний (класс 1) или ни одно из трех (класс 0) по имеющимся характеристикам здоровья.

## Описание данных

### Признаки
**train.csv** - обучающий набор данных:
- *Id* — уникальный идентификатор для каждого наблюдения
- *AB-GL* — пятьдесят шесть анонимизированных характеристик здоровья. Все они являются числовыми, за исключением *EJ*, который является категориальным

**greeks.csv** - дополнительные метаданные, доступные только для обучающего набора:
- *Alpha* —  тип возрастного заболевания, если оно присутствует
  - *A* — никаких возрастных изменений. Соответствует классу 0
  - *B*, *D*, *G*  — три возрастных состояния. Соответствуют классу 1
- *Beta*, *Gamma*, *Delta* —  три экспериментальные характеристики
- *Epsilon* —  дата, когда были собраны данные по данному пациенту

### Целевой признак
- *Class* — бинарный целевой признак: 1 указывает на то, что у пациента было диагностировано одно из трех заболеваний, 0 указывает на то, что у него их нет

## Задача

Качество предсказаний в чемпионате оценивается с помощью **сбалансированного логарифмического коэффициента потерь**(Log Loss). При этом учитывается, что каждый класс примерно одинаково важен для получения итоговой оценки.
Каждое наблюдение относится либо к классу 0, либо к классу 1. Для каждого наблюдения нужно указать вероятность для каждого класса.

## Результаты

- В результате около 20 попыток модификаций кода, наилучший счёт чемпионата, который мне удалось достичь, составил 0.3 на промежуточном наборе данных и 0.52 на финальном наборе данных (чем ближе к нулю, тем лучше оценка и качество предсказаний модели машинного обучения). В открытый доступ выложены все мои варианты кода
- Помимо модели CatBoostClassifier мной были испробованы модели LGBMClassifier и XGBoost Classifier с использованием optuna при подборе лучших гиперпараметров. Однако эти модели проигрывали по качеству модели CatBoostClassifier
- При объединении тренировочного датасета (train.csv) с датасетом с дополнительной информацией о пациентах (greeks.csv) модели градиентного бустинга выдавали менее качественные результаты предсказаний классов. Поэтому мной было принято отказаться от использования метаданных.

## Используемые библиотеки

*pandas, Scikit-learn, numpy, catboost, optuna*

## Статус проекта: *Закончен*
