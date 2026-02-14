# Домашнее задание №2. twol

*Дедлайн: 26 февраля 23:59.*

*После дедлайна работы не принимаются.*

В качестве ответа загрузите файлы .lexd и .twol.

```
Surname_hw2_01.lexd
Surname_hw2_01_01.twol
Surname_hw2_01_02.twol

Surname_hw2_02.lexd
Surname_hw2_02.twol

Surname_hw2_03.lexd
Surname_hw2_03.twol
```

Неправильные формат файла и название штрафуются.

Если вы дорешали задание до промежуточного пункта, укажите это в названии: `Surname_hw2_03_02.lexd` - решение 3его задания до 2ого пункта включительно.

При возникновении вопросов, пишите Тане в тг.

Все пункты стоят 1 балл.

### 1. Глоссируем английский
**1.1** Перед вами черновик lexd файла. Поправьте его при необходимости и напишите twol файл так, чтоб получались правильные формы глаголов в начальной форме и c -ing.

Пример: `quiz<pl>:quizzes`

Тест: test_hw2_01_01

Название файлов: Surname_hw2_01.lexd, Surname_hw2_01_01.twol

```
%%writefile task.lexd
PATTERNS
NounRoot NounInfl

LEXICON NounRoot
dog
cat
bus
fox
watch
wish
quiz

LEXICON NounInfl
<sg>:
<pl>:{S}
```

**1.3** Измените twol файл так, чтоб на выходе получались сегментированные формы:

Пример: `go<:quiz`, `quiz<pl>:quizz>es`

Тест: test_hw2_01_02

Название файла: Surname_hw2_01_02.twol
