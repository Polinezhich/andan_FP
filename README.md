# Итоговый проект

Выполнили:

| Студенты         | 
| :-----:         | 
| Осенева Полина  | 
| Сёмушкина Софья |   
| Чигир Андрей    | 

## Описание темы проекта

__Экзопланета__, или внесолнечная планета — планета, находящаяся вне Солнечной системы.

__«Ке́плер»__ — космическая обсерватория НАСА, орбитальный телескоп со сверхчувствительным фотометром, специально предназначенный для поиска экзопланет, подобных Земле. Это первый космический аппарат, созданный с такой целью. Обсерватория могла одновременно наблюдать более чем 100 тыс. звёзд. Наличие планеты у звезды определяется по периодическим изменениям яркости последней, вызываемым прохождениями планеты перед звездой.

> "Kepler looks at over 170,000 stars simultaneously, looking for planets that cross their star and block some light. 
By the blocking of that light we can tell how big the planet is compared to the star, and when it repeats we can tell the orbital period. From Kepler's third law we can deduce how far the planet is from the star. And by looking at the properties of the star we can tell how hot that planet might be."

<img src="https://github.com/Polinezhich/andan_FP/blob/main/imgs/The_model_of_a_transit.gif" width="500" height="500" />

## Сбор данных

В качестве датасета (`cumulative.csv`) мы используем данные о точках интереса обсерватории Кеплер (Kepler Objects of Interest, KOI). Данные взяты с [сайта NASA](https://exoplanetarchive.ipac.caltech.edu/cgi-bin/TblView/nph-tblView?app=ExoTbls&config=cumulative). В дальнейшем нами было принято решение обогатить данный датасет при помощи [другого датасета](https://exoplanetarchive.ipac.caltech.edu/cgi-bin/TblView/nph-tblView?app=ExoTbls&config=PSCompPars) NASA, хранящего информацию обо всех подтвержденных экзопланетах (`additional_exo_data.csv`). Оттуда для каждой подтвержденной экзопланеты первоначального датасета мы достали ряд дополнительных переменных. Результат объединения датасетов мы сохранили в качестве третьего датасета. Причиной этого служит факт того, что объединенный датасет был полезен нам на этапе EDA и проверки гипотез, однако на этапе обучения моделей нам вновь понадобился оригинальный "чистый" датасет.


## Состав проекта

В конечном итоге мы имеем два датасета `cumulative.csv`, `additional_exo_data.csv`. Подробное описание выполнения проекта и, соответственно, код отражены в файле `main.ipynb`. Там же находятся детальные описания датасетов и выводы по проекту.
