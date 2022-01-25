# Продажа квартир в Санкт-Петербурге — анализ рынка недвижимости


## Данные

Были предоставлены следующие данные о квартирах:
- airports_nearest — расстояние до ближайшего аэропорта в метрах (м)
- balcony — число балконов
- ceiling_height — высота потолков (м)
- cityCenters_nearest — расстояние до центра города (м)
- days_exposition — сколько дней было размещено объявление (от публикации до снятия)
- first_day_exposition — дата публикации
- floor — этаж
- floors_total — всего этажей в доме
- is_apartment — апартаменты (булев тип)
- kitchen_area — площадь кухни в квадратных метрах (м²)
- last_price — цена на момент снятия с публикации
- living_area — жилая площадь в квадратных метрах (м²)
- locality_name — название населённого пункта
- open_plan — свободная планировка (булев тип)
- parks_around3000 — число парков в радиусе 3 км
- parks_nearest — расстояние до ближайшего парка (м)
- ponds_around3000 — число водоёмов в радиусе 3 км
- ponds_nearest — расстояние до ближайшего водоёма (м)
- rooms — число комнат
- studio — квартира-студия (булев тип)
- total_area — площадь квартиры в квадратных метрах (м²)
- total_images — число фотографий квартиры в объявлении

## Задача

Используя данные сервиса Яндекс.Недвижимость, определить рыночную стоимость объектов недвижимости и типичные параметры квартир.

## Используемый стэк
*Python*, *Pandas*, *Matplotlib*, *Plotly Express*

## Основные шаги

В ходе исследования были изучены данные, заполнены пропуски (часть - медианными значениями), данные приведены к необходимым типам. 

Далее к данным были добавлены столбцы с информацией о цене за квадратный метр, категорией этажа квартиры (первый, последний, другой), а также разбили столбец даты публикации объявления на несколько отдельных - для дня недели, месяца и года публикации.

Далее мы исследовали ключевые параметры квартир - площадь, цену, количество комнат, высоту потолков. 

После этого было проанализировано время продажи квартир.

Далее были убраны редкие и выделяющиеся значения.

Далее мы приступили к анализу факторов, влияющих на цену квартиры. Как можно ожидать, главный фактор, который влияет на цену - общая площадь (коэффициент корреляции 0,7). Число комнат влияет менее сильно, чем можно было бы ожидать - коэффициент всего 0,42. Еще слабее влияет расстояние от центра.

Далее мы исследовали цены в разных населенных пунктах. Здесь сюрпризов не произошло - самые дорогие квартиры в Санкт-Петербурге, за ним следует город Пушкин. Самые дешевые квартиры из населенные пунктов, входящих в десятку с наибольшим количеством предложений - в Выборге.

После этого мы пришли к выводу, что область примерно в 8 километрах от центра Петербурга входит в центральную зону - после удаления на большее расстояние от центра цена за квадратный метр существенно падает. 

Дальнейшие исследования центральной зоны подтвердили, что она является самобытной по отношению к общегородским тенденциям. 