# Natural Language Processing with Disaster Tweets

*Ссылка на проект в Kaggle:* https://www.kaggle.com/code/sombrahacker/robert-for-nlp

Twitter стал важным каналом коммуникации во время чрезвычайных ситуаций. Повсеместное распространение смартфонов позволяет людям сообщать о чрезвычайной ситуации, которую они наблюдают, в режиме реального времени. Из-за этого все больше агентств заинтересованы в программном мониторинге Twitter (например, организации по оказанию помощи при стихийных бедствиях и информационные агентства).

Но не всегда ясно, действительно ли слова человека возвещают о катастрофе. Например: автор может использовать слово “ПЫЛАЮЩИЙ”, но он имеет в виду его метафорически. Это сразу становится ясно человеку, особенно с помощью наглядного пособия. Но для машины это менее понятно.

В этом чемпионате необходимо было создать модель машинного обучения, которая предсказывает, какие твиты посвящены реальным катастрофам, а какие нет. Для этого был предоставлен доступ к набору данных из 10 000 твитов, которые были классифицированы вручную.

## Описание данных

### Признаки
**train.csv** - обучающий набор данных:
- *id* — уникальный идентификатор для каждого твита
- *text* — текст твита
- *location* — местоположение, из которого был отправлен твит (может быть пустым)
- *keyword* — конкретное ключевое слово из целевого твита (может быть пустым)
- *target* — только в train.csv, целевой признак указывает, касается ли твит реальной катастрофы (1) или нет (0)
**test.csv** - тестовый набор данных

## Задача

Создать модель машинного обучения, которая предсказывает, какие твиты посвящены реальным катастрофам, а какие нет. Результаты оцениваются с использованием коэффициента F1 между прогнозируемыми и ожидаемыми ответами.

## Результаты

Для выполнения поставленной задачи была использована модель RoBERT, показавшая результаты, равные 0.78, что является неплохим результатом. Однако в будущем мной планируются и другие эксперементы с различными NLP моделями. Изменения будут отображены в данном README файле.

## Используемые библиотеки

*Scikit-learn, numpy, transformers, torch*

## Статус проекта: *Закончен. Возможны будущие доработки, улучшающие результат*
