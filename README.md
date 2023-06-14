# Итоговый проект

Выполнили:

| Студент         | 
| :-----:         | 
| Осенева Полина  | 
| Сёмушкина Софья |   
| Чигир Андрей    | 

## Введение

__Экзопланета__, или внесолнечная планета — планета, находящаяся вне Солнечной системы.

__«Ке́плер»__ — космическая обсерватория НАСА, орбитальный телескоп со сверхчувствительным фотометром, специально предназначенный для поиска экзопланет, подобных Земле. Это первый космический аппарат, созданный с такой целью. Обсерватория могла одновременно наблюдать более чем 100 тыс. звёзд. Наличие планеты у звезды определяется по периодическим изменениям яркости последней, вызываемым прохождениями планеты перед звездой.

> "Kepler looks at over 170,000 stars simultaneously, looking for planets that cross their star and block some light. 
By the blocking of that light we can tell how big the planet is compared to the star, and when it repeats we can tell the orbital period. From Kepler's third law we can deduce how far the planet is from the star. And by looking at the properties of the star we can tell how hot that planet might be."

<img src="https://github.com/Polinezhich/andan_FP/blob/main/imgs/The_model_of_a_transit.gif" width="500" height="500" />

## Сбор данных

В качестве датасета мы используем данные о точках интереса обсерватории Кеплер (Kepler Objects of Interest, KOI). Данные взяты с [сайта NASA](https://exoplanetarchive.ipac.caltech.edu/cgi-bin/TblView/nph-tblView?app=ExoTbls&config=cumulative).

## Описание столбцов датасета

* `kepid`: KepID - номер идентификации цели, указанный в Каталоге Входных Данных Kepler (KIC).
* `kepoi_name`: KOI Name - номер, используемый для идентификации и отслеживания Kepler Object of Interest (KOI).
* `kepler_name`: Kepler Name - имя экзопланеты, присвоенное ей после подтверждения ее существования.
* `koi_disposition`: Exoplanet Archive Disposition - решение Архива Экзопланет о том, является ли KOI кандидатом на экзопланету или ложным срабатыванием.
* `koi_pdisposition`: Disposition Using Kepler Data - решение о том, является ли KOI кандидатом на экзопланету или ложным срабатыванием, основанное на данных Kepler.
* `koi_score`: Disposition Score - оценка достоверности решения о том, является ли KOI кандидатом на экзопланету или ложным срабатыванием.
* `koi_fpflag_nt`: Not Transit-Like False Positive Flag - флаг, указывающий на то, что KOI был помечен как ложное срабатывание из-за того, что его сигнал не похож на транзит.
* `koi_fpflag_ss`: Stellar Eclipse False Positive Flag - флаг, указывающий на то, что KOI был помечен как ложное срабатывание из-за того, что его сигнал вызван затмением звезды.
* `koi_fpflag_co`: Centroid Offset False Positive Flag - флаг, указывающий на то, что KOI был помечен как ложное срабатывание из-за смещения центра масс.
* `koi_fpflag_ec`: Ephemeris Match Indicates Contamination False Positive Flag - флаг, указывающий на то, что KOI был помечен как ложное срабатывание из-за загрязнения эфемериды.


Остальные колонки содержат информацию об орбитальных и физических характеристиках экзопланет и их звезд-хозяев. Например:

* `koi_period`: Orbital Period [days] - орбитальный период экзопланеты в днях.
* `koi_time0bk`: Transit Epoch [BKJD] - эпоха транзита в формате Barycentric Kepler Julian Date (BKJD).
* `koi_impact`: Impact Parameter - импактный параметр.
* `koi_duration`: Transit Duration [hrs] - продолжительность транзита в часах.
* `koi_depth`: Transit Depth [ppm] - глубина транзита в частях на миллион (ppm).
* `koi_prad`: Planetary Radius [Earth radii] - радиус планеты в радиусах Земли.
* `koi_teq`: Equilibrium Temperature [K] - равновесная температура планеты в кельвинах.
* `koi_insol`: Insolation Flux [Earth flux] - поток инсоляции планеты в единицах потока инсоляции Земли.
* `koi_model_snr`: Transit Signal-to-Noise - отношение сигнала к шуму транзитного сигнала.
* `koi_steff`: Stellar Effective Temperature [K] - эффективная температура звезды в кельвинах.
* `koi_slogg`: Stellar Surface Gravity [log10(cm/s**2)] - поверхностная гравитация звезды в логарифмической шкале (log10) в единицах ускорения свободного падения (см/с^2).
* `koi_srad`: Stellar Radius [Solar radii] - радиус звезды в радиусах Солнца.


Колонки с суффиксами `_err1` и `_err2` содержат информацию о верхней и нижней неопределенности соответствующих параметров, целесообразность учитывания этих параметров будет рассмотрена при корреляционном анализе данных.

## Дальнейшие действия

* Исключение колонок с неинформативными данными на основе корреляционного анализа
* Проверка гипотезы о наличии связи между характеристиками звезды-хозяина (например, температурой и радиусом) и характеристиками экзопланеты (например, радиусом и температурой).
* Проверка гипотезы о наличии связи между радиусом звезды-хозяина и радиусом экзопланеты.
* Построение модели классификации для предсказания значения колонки koi_disposition (является ли KOI кандидатом на экзопланету или ложным срабатыванием) на основе других колонок в датасете.
* Из датасета будут удалены тела, статус которых все еще не определен, а также сгруппированы подтвержденные и непотвержденные экзопланеты
