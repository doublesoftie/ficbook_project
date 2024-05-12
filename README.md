# Проект
Целью проекта является создание модели для предсказания количества лайков фанфиков и определение показателей, которые на это влияют. 
## Экипаж корабля
- Лойко Анна
- Беданокова Джанета
- Ихсанова Софья
## План-капкан
- [Сбор данных](#Сбор_данных)
- [Предварительная обработка и визуализация](#Предварительная_обработка_и_визуализация)
- [Гипотезы](#Гипотезы)
- [Машинное обучение](#Машинное_обучение)
# Сбор данных
Для парсинга нами был выбран самый популярный сайт фанфиков(на территории стран СНГ) ficbook.ru. 
Полученные данные сохраняются в формате [CSV](ficbook/ficbook.csv) для дальнейшей обработки.
 
**Описание переменных:**
- **количественные**
- `количество меток` - количество жанров
- `количество отзывов`
- `количество лайков` - количество пользователей, которым понравилась работа
- `количество страниц по фандому` - при помощи этого показателя мы решили замерять популярность фандома
- **категориальные**
- `тип отношений` - вид отношений между главными героями(романтические/неромантические) и их наличие
- `возрастной рейтинг` - ограничения по возрасту аудитории, для которой предназначена работа
- `статус завершенности` - завершен/заморожен(фанфик на перерыве на неопределенное время)/в процессе(еще не завершен)
- `размер` - на сайте фанфики могут иметь 4 размера:драббл, миди, мини и макси. Каждый размер имеет свои жанровые особенности
- `описание` - аннотация фанфика
# Предварительная обработка и визуализация
На этом шаге были удалены дубликаты и пропуски. Также переменная `размер` была заменена на `количество страниц`, а  `описание` на `количество символов в описании`. 
Для визуализации были использованы гистограммы и диаграммы рассеяния.
# Гипотезы
1. Жанр PWP добавляет работе популярности:без комментариев)
2. Количество меток, количество знаков в описании и количество страниц по фандому(его популярность) имеет положительную корреляцию с количеством лайков:чем подробнее описание фанфика, тем больше шансов зацепить читателя или высветиться при поиске по меткам
3. Слэш - самый популярный жанр любовных отношений, NC-17 - самый популярный возрастной рейтинг:[так было в 2013 году](https://ficbook.net/readfic/1172038), изменилось ли что-то за 10 лет?
# Машинное обучение
Планируется использовать различные методы машинного обучения, такие как построение линейной регрессии и подбор оптимальных параметров для регуляризации, метод случайного леса и прочие регрессоры.
