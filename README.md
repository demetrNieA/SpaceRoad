SpaceRoad
=========

Android game repo


План игры “Космическая одиссея”
Challenge
Сетевая игра без активного участия сервера (можно играть без доступа в интернет)
При этом очень сложно считить
Сюжет
Вы являетесь капитаном космической станции дрейфующей по просторам вселенной. Ваша цель - познать секреты этого мира и выжить.

Станция привязана к объекту реального мира - сотовому телефону\планшету. Она может быть в двух состояниях - в гиперпространстве и в обычном пространстве. В гиперпространстве она недоступна для сигналов извне - программа выключена\в режиме без сетей. В обычном же пространстве она может контактировать с другими кораблями.

Взаимодействия происходят между как-либо связанными по локальной сети или аналогу аппаратами. К примеру один из телефонов создаёт соединение блютуз, а другой к нему подключается (автоматически или через обычный блютуз?).

Движок и правила

Главным ресурсом игры является изучение окружающего мира. Этот ресурс может только увеличиваться, но ценность конкретных фактов о мире падает тем более, чем больше о них знают на других кораблях. Узнавать новое о мире можно двумя способами: тратить время и мощности на исследования или воровать технологии у других игроков анализируя обломки их юнитов.

В случае военного конфликта игроки используют свои знания о мире, чтобы определить количество и характеристики своих юнитов, которые потом используются в пошаговой битве. По результатам битвы на основе её результата решается какую часть технологий у друг друга получилось своровать игрокам. 
Мат модель
Факты об окружающем мире - это решение какой-либо математической задачи на каком-либо отрезке. Эта математическая задача должна соответствовать таким условиям:
Решения должны занимать значительно меньше места, чем все возможные варианты
С увеличением размера отрезка количество новых решений должно уменьшаться, т.е. должна возрастать сложность поиска
Решения должны быть приватно проверяемыми, т.е. перед началом игры один игрок должен мочь проверить что у другого игрока действительно есть те решения, которые он утверждает
Решения должны быть считаемыми параллельно. Т.е. для нахождения значений на отрезке не обязательно знать о значениях на других отрезках
Пример
Пусть наша функция обладает этими свойствами и результатом являются натуральные числа разреженные примерно так же, как и простые числа, но в отличии от последних для проверки на принадлежность не обязательно знать других чисел. (не решето Эратосфена). 

Тогда пусть есть игроки Алиса и Боб. Они оба обладают знаниями о решениях на отрезке с 0 до 10^9 ~ 1000 решений. Кроме того Алиса знает ещё 500 решений из области (5*10^12, 5.1*10^12), а Боб - 2000 решений из области (6.37*10^12, 6.73*10^12). Они начинают битву с юнитами по которым распределены улучшения на основе количества решений, который каждый знает (1500 очков у Алисы, 3000 очков у Боба, максимальное количество юнитов = ln количества очков, т.е. 7 у Алисы, 8 у Боба). 

Пусть в результате столкновения Алиса получила 1500 очков. После этого оба аппарата игроков генерируют случайные числа на основе совмещения которых будет определяться как много из этих 1500 очков Алиса сумеет успешно изучить и какие именно это будут очки. Т.е. в этом примере из 1500 очков Алиса может получить 300 решений из которых 200 будут из уже известных, а 100 - новых из областей Боба и по результатам боя Алиса будет иметь 1600 решений.
