# Домашнее задание №1. lexd

*Дедлайн: 19 февраля 23:59.*

*После дедлайна работы не принимаются.*

В качестве ответа загрузите 2 файла .lexd.

```
Surname_hw1_01.lexd для первого задания

Surname_hw1_02.lexd для второго задания
```
При возникновении вопросов, пишите Тане в тг.

Все пункты кроме 2.5 стоят 1 балл, 2.5 стоит 2 балла.

## Задание 1

**1.1** Перед вами фрагмент эвенской (< тунгусо-маньчжурские) парадигмы спряжения глаголов в прошедшем времени из (Бурыкин 2002). Попробуйте смоделировать ее при помощи lexd.

Пример разбора: *aŋarit* 'мы с тобой открыли' — `aŋa<v><pst><p1><inc><pl>`

| форма    |   открыть   |  нарисовать|  убить    |
|----------|-------------|------------|-----------|
| 1SG      | _aŋariwu_   | _oɲariwu_  | _mariwu_  |
| 2SG      | _aŋariš_    | _oɲariš_   | _mariš_   |
| 3SG      | _aŋarin_    | _oɲarin_   | _marin_   |
| 1PL.INC  | _aŋarit_    | _oɲarit_   | _marit_   |
| 1PL.EXC  | _aŋariwun_  | _oɲariwun_ | _mariwun_ |
| 2PL      | _aŋarišan_  | _oɲarišan_ | _marišan_ |
| 3PL      | _aŋaritan_  | _oɲaritan_ | _maritan_ |

Тест: test_hw1_01_01

**1.2** В эвенском есть показатели "Motion cum purpose" для выражения движения с целью:
- *manariwun* 'мы с без тебя пошли убить' — `ma<v><mcp><pst><p1><exc><pl>`
- *maniriwun* 'мы с без тебя ходили убивать' — `ma<v><mcp><atl><pst><p1><exc><pl>` (atl - atelic)

Теперь ваш трансдьюсер должен разбирать глаголы и с этими суффиксами, и без них.

| форма    |  убить    |  убить<mcp> |  убить<mcp><atl>| ... |
|----------|-----------|-------------|-----------------|-----|
| 1SG      | _mariwu_  | _manariwu_  | _maniriwu_      | ... |
| 2SG      | _mariš_   | _manariš_   | _maniriš_       | ... |
| 3SG      | _marin_   | _manarin_   | _manirin_       | ... |
| 1PL.INC  | _marit_   | _manarit_   | _manirit_       | ... |
| 1PL.EXC  | _mariwun_ | _manariwun_ | _maniriwun_     | ... |
| 2PL      | _marišan_ | _manarišan_ | _manirišan_     | ... |
| 3PL      | _maritan_ | _manaritan_ | _maniritan_     | ... |

Тест: test_hw1_01_02

**1.3** В эвенском есть вербализаторы, которые могут сделать из основы существительного глагольную основу (mi - добывать на охоте `<hunt>`, ti - есть `<eat>`). Ваш анализатор должен разбирать слова с основами: olla 'рыба', kabew 'куропатка', boŋga 'баран'.

- *olla* 'рыба' — `olla<n>`
- *ollamirin* 'поймал рыбу' — `olla<hunt><v><pst><p3><sg>`
- *ollatirin* 'съел рыбу' — `olla<eat><v><pst><p3><sg>`
- *ollaminarin* 'пошёл поймать рыбу' — `olla<hunt><v><mcp><pst><p3><sg>`
- *ollatinarin* 'пошёл съесть рыбу' — `olla<eat><v><mcp><pst><p3><sg>`
- *ollatinirin* 'ходил есть рыбу' — `olla<eat><v><mcp><alt><pst><p3><sg>`

Примечание: формы с сочетанием *mi-ni* <hunt><v><mcp><alt> автору задания не встречались, но давайте наш трансдьюсер будет способен их разобрать.

Теперь можно разобрать 192 формы.

Тест: test_hw1_01_03

**1.4** А ещё в эвенском есть вербализаторы, которые могут сделать из глагольной основы существительное. Например, *-nmaj* `<n><prc>` для названий процессов или мест.

- *oɲanmaj* 'рисование' — `oɲa<n><prc>`
- *ollaminmaj* 'ловля рыбы' — `olla<hunt><n><prc>`
- \* *oɲananmaj* после показателей MCP суффикса *-nmaj* не бывает

Всего теперь должна разбираться 201 форма.

Для ориентира: в нашем task.lexd файле 44 строки (с учётом пустых строк между разделами с лексиконами).

Тест: test_hw1_01_04

## Задание 2

Перед вами парадигма некоторых глаголов в христианском урмийском (арамейские < семитские, Khan 2016). Попробуйте смоделировать ее при помощи lexd. Знаком плюс исследователи ассирийского обозначают специальную просодию корня.

Глаголы одной породы устроены одинаково. Q - от quadrilateral, это породы, в которых четырехконсонантные корни.


| Порода | I | I | I | II | II | II | III | III | III | QI | QI | QI | QII |
|--------|---|---|---|----|----|----|-----|-----|-----|----|----|----|-----|
| Корень | _p-t-x_ ‘открывать’ | _d-m-x_ ‘спать’ | _+p-l-ṭ_ 'выходить' | _b-s-m_ ‘лечить’ | _t-l-k_ 'терять' | _+p-l-ṭ_ 'выгонять' | _m-gd-l_ 'заморозить(ся)' | _m-dm-x_ ‘усыплять’ | _+m-pl-ṭ_ 'выманивать' | _g-rg-š_ ‘тащить’ | _b-rb-z_ 'распространяться' | _+k-ṭk-ṭ_ 'рубить' | _mg-rg-š_ ‘to cause to drag’ |
| `<prs><p3><m><sg>`| _patəx_ | _daməx_ | _+paləṭ_ | _basəm_ | _talək_ | _+paləṭ_ | _magdəl_ | _madməx_ | _+mapləṭ_ | _gargəš_ | _barbəz_ | _+kaṭkəṭ_ | _mgargəš_ |
| `<prs><p3><f><sg>` | _patxa_ | _damxa_ | _+palṭa_ | _basma_ | _talka_ | _+palṭa_ | _magdəlla_ | _madməxxa_ | _+mapləṭṭa_ | _gargəšša_ | _barbəzza_ | _+kaṭkəṭṭa_ | _mgargəšša_ |
| `<prs><p3><pl>`    | _patxi_ | _damxi_ | _+palṭi_ | _basmi_ | _talki_ | _+palṭi_ | _magdəlli_ | _madməxxi_ | _+mapləṭṭi_ | _gargəšši_ | _barbəzzi_ | _+kaṭkəṭṭi_ | _mgargəšši_ |
| `<prs><p2><m><sg>` | _patxət_ | _damxət_ | _+palṭət_ | _basmət_ | _talkət_ | _+palṭət_ | _magdəllət_ | _madməxxət_ | _+mapləṭṭət_ | _gargəššət_ | _barbəzzət_ | _+kaṭkəṭṭət_ | _mgargəššət_ |
| `<prs><p2><f><sg>` | _patxat_ | _damxat_ | _+palṭat_ | _basmat_ | _talkat_ | _+palṭat_ | _magdəllat_ | _madməxxat_ | _+mapləṭṭat_ | _gargəššat_ | _barbəzzat_ | _+kaṭkəṭṭat_ | _mgargəššat_ |
| `<prs><p2><pl>`    | _patxitun_ | _damxitun_ | _+palṭitun_ | _basmitun_ | _talkitun_ | _+palṭitun_ | _magdəllitun_ | _madməxxitun_ | _+mapləṭṭitun_ | _gargəššitun_ | _barbəzzitun_ | _+kaṭkəṭṭitun_ | _mgargəššitun_ |
| `<prs><p1><m><sg>` | _patxən_ | _damxən_ | _+palṭən_ | _basmən_ | _talkən_ | _+palṭən_ | _magdəllən_ | _madməxxən_ | _+mapləṭṭən_ | _gargəššən_ | _barbəzzən_ | _+kaṭkəṭṭən_ | _mgargəššən_ |
| `<prs><p1><f><sg>` | _patxan_ | _damxan_ | _+palṭan_ | _basman_ | _talkan_ | _+palṭan_ | _magdəllan_ | _madməxxan_ | _+mapləṭṭan_ | _gargəššan_ | _barbəzzan_ | _+kaṭkəṭṭan_ | _mgargəššan_ |
| `<prs><p1><pl>`    | _patxax_ | _damxax_ | _+palṭax_ | _basmax_ | _talkax_ | _+palṭax_ | _magdəllax_ | _madməxxax_ | _+mapləṭṭax_ | _gargəššax_ | _barbəzzax_ | _+kaṭkəṭṭax_ | _mgargəššax_ |
| `<pst><p3><m><sg>` | _ptəxlə_ | _dməxlə_ | _+pləṭlə_ | _busəmlə_ | _tuləklə_ | _+puləṭlə_ | _mugdəllə_ | _mudməxlə_ | _+mupləṭlə_ | _gurgəšlə_ | _burbəzlə_ | _+kuṭkəṭlə_ | _mgurgəšlə_ |
| `<pst><p3><f><sg>` | _ptəxla_ | _dməxla_ | _+pləṭla_ | _busəmla_ | _tuləkla_ | _+puləṭla_ | _mugdəlla_ | _mudməxla_ | _+mupləṭla_ | _gurgəšla_ | _burbəzla_ | _+kuṭkəṭla_ | _mgurgəšla_ |
| `<pst><p3><pl>`    | _ptəxlun_ | _dməxlun_ | _+pləṭlun_ | _busəmlun_ | _tuləklun_ | _+puləṭlun_ | _mugdəllun_ | _mudməxlun_ | _+mupləṭlun_ | _gurgəšlun_ | _burbəzlun_ | _+kuṭkəṭlun_ | _mgurgəšlun_ |
| `<pst><p2><m><sg>` | _ptəxlux_ | _dməxlux_ | _+pləṭlux_ | _busəmlux_ | _tuləklux_ | _+puləṭlux_ | _mugdəllux_ | _mudməxlux_ | _+mupləṭlux_ | _gurgəšlux_ | _burbəzlux_ | _+kuṭkəṭlux_ | _mgurgəšlux_ |
| `<pst><p2><f><sg>` | _ptəxlax_ | _dməxlax_ | _+pləṭlax_ | _busəmlax_ | _tuləklax_ | _+puləṭlax_ | _mugdəllax_ | _mudməxlax_ | _+mupləṭlax_ | _gurgəšlax_ | _burbəzlax_ | _+kuṭkəṭlax_ | _mgurgəšlax_ |
| `<pst><p2><pl>`    | _ptəxloxun_ | _dməxloxun_ | _+pləṭloxun_ | _busəmloxun_ | _tuləkloxun_ | _+puləṭloxun_ | _mugdəlloxun_ | _mudməxloxun_ | _+mupləṭloxun_ | _gurgəšloxun_ | _burbəzloxun_ | _+kuṭkəṭloxun_ | _mgurgəšloxun_ |
| `<pst><p1><sg>` | _ptəxli_ | _dməxli_ | _+pləṭli_ | _busəmli_ | _tuləkli_ | _+puləṭli_ | _mugdəlli_ | _mudməxli_ | _+mupləṭli_ | _gurgəšli_ | _burbəzli_ | _+kuṭkəṭli_ | _mgurgəšli_ |
| `<pst><p1><pl>` | _ptəxlan_ | _dməxlan_ | _+pləṭlan_ | _busəmlan_ | _tuləklan_ | _+puləṭlan_ | _mugdəllan_ | _mudməxlan_ | _+mupləṭlan_ | _gurgəšlan_ | _burbəzlan_ | _+kuṭkəṭlan_ | _mgurgəšlan_ |
| `<res><ptc><m>` | _ptixa_ | _dmixa_ | _+pliṭa_ | _busma_ | _tulka_ | _+pulṭa_ | _mugdəlla_ | _mudməxxa_ | _+mupləṭṭa_ | _gurgəšša_ | _burbəzza_ | _+kuṭkəṭṭa_ | _mgurgəšša_ |
| `<res><ptc><f>` | _ptəxta_ | _dməxta_ | _+pləṭta_ | _busəmta_ | _tuləkta_ | _+puləṭta_ | _mugdəlta_ | _mudməxta_ | _+mupləṭta_ | _gurgəšta_ | _burbəzta_ | _+kuṭkəṭta_ | _mgurgəšta_ |
| `<res><ptc><pl>`| _ptixə_ | _dmixə_ | _+pliṭə_ | _busmə_ | _tulkə_ | _+pulṭə_ | _mugdəllə_ | _mudməxxə_ | _+mupləṭṭə_ | _gurgəššə_ | _burbəzzə_ | _+kuṭkəṭṭə_ | _mgurgəššə_ |
| `<imp>`         | _ptux_ | _dmux_ | _+pluṭ_ | _basəm_ | _talək_ | _+paləṭ_ | _magdəl_ | _madməx_ | _+mapləṭ_ | _gargəš_ | _barbəz_ | _+kaṭkəṭ_ | _mgargəš_ |
| `<inf>`         | _ptaxa_ | _dmaxa_ | _+plaṭa_ | _basumə_ | _talukə_ | _+paluṭə_ | _magdulə_ | _madmuxə_ | _+mapluṭə_ | _gargušə_ | _barbuzə_ | _+kaṭkuṭə_ | _mgargušə_ |
| `<prog>`        | _bəptaxa_ | _bədmaxa_ | _+bəplaṭa_ | _basumə_ | _talukə_ | _+paluṭə_ | _magdulə_ | _madmuxə_ | _+mapluṭə_ | _gargušə_ | _barbuzə_ | _+kaṭkuṭə_ | _mgargušə_ |
| `<verbal_noun>` | _ptaxta_ | _dmaxta_ | _+plaṭta_ | _basamta_ | _talakta_ | _+palaṭta_ | _magdalta_ | _madmaxta_ | _+maplaṭta_ | _gargašta_ | _barbazta_ | _+kaṭkaṭta_ | _mgargašta_ |
| `<active><ptc><m>` | _patxana_ | _damxana_ | _+palṭana_ | _basmana_ | _talkana_ | _+palṭana_ | _magdəllana_ | _madməxxana_ | _+mapləṭṭana_ | _gargəššana_ | _barbəzzana_ | _+kaṭkəṭṭana_ | _mgargəššana_ |
| `<active><ptc><f>` | _patxanta_ | _damxanta_ | _+palṭanta_ | _basmanta_ | _talkanta_ | _+palṭanta_ | _magdəllanta_ | _madməxxanta_ | _+mapləṭṭanta_ | _gargəššanta_ | _barbəzzanta_ | _+kaṭkəṭṭanta_ | _mgargəššanta_ |
| `<active><ptc><pl>` | _patxanə_ | _damxanə_ | _+palṭanə_ | _basmanə_ | _talkanə_ | _+palṭanə_ | _magdəllanə_ | _madməxxanə_ | _+mapləṭṭanə_ | _gargəššanə_ | _barbəzzanə_ | _+kaṭkəṭṭanə_ | _mgargəššanə_ |

**2.1** Напишите правила для глаголов первой породы для настоящего и прошедшего времён.

*patəx* 'он открывает' — `ptx<prs><p3><m><sg>`

*dməxlan* 'мы спали' — `dmx<pst><p1><pl>`

Тест: test_hw2_01_01

**2.2** Добавьте для глаголов второй породы для настоящего и прошедшего времён.

*patəx* 'он открывает' — `ptx<prs><p3><m><sg>`

*busəmlan* 'мы лечили' — `bsm<pst><p1><pl>`

Тест: test_hw2_01_02

**2.3** Добавьте правила для глаголов третьей породы для настоящего и прошедшего времён.

*patəx* 'он открывает' — `ptx<prs><p3><m><sg>`

*mudməxlan* 'мы усыпили' — `mdmx<pst><p1><pl>`

Тест: test_hw2_01_03

**2.4** Добавьте правила для глаголов QI и QII пород для настоящего и прошедшего времён.

*patəx* 'он открывает' — `ptx<prs><p3><m><sg>`

*gurgəšlan* 'мы тащили' — `grgš<pst><p1><pl>`

*mgurgəšlan* 'мы заставили тащить' — `mgrgš<pst><p1><pl>`

Тест: test_hw2_01_04

**2.5** Допишите правила для всех оставшихся форм.

*patəx* 'он открывает' — `ptx<prs><p3><m><sg>`

*mgargəš* 'заставь тащить' — `mgrgš<imp>`

Тест: test_hw2_01_05

Всего, получается, анализатор должен разбирать 351 форму (на самом деле 339, потому что часть форм *+p-l-ṭ* 'выходить' (I) и *+p-l-ṭ* 'выгонять' (II) совпадают).

В нашем task.lexd файле 77 строк (с учётом пустых строк между разделами с лексиконами).
