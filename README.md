# Takeout (TrashCraft)

Игра под Android

Вы будете играть за Гринмена - обычного героя, который решил спасти человечество. Спасти от мусора, который заполонил улицы, дома, города. Но ему нужна ваша помощь. Поможете ли вы ему достигнуть своей цели?

Google Play: https://play.google.com/store/apps/details?id=ru.SeriousDim.Takeout

---
---
# Информация для разработки

## ВАЖНО! Работа с физикой
1. Все префабы должны иметь **минимум полигонов**
1. CompositeCollider2D у TileMap должен иметь поле GeometryType = Polygons

## Deprecated forever
1. Тег _StairCollider_
1. Тайлмап _StairMap_
1. Префаб _MainHero_ --> префаб _entity000_

## Структура _entity000_
* bone_000 - главная кость
* MainCollider - содержит основные коллайдеры
* StairListener - поведение со ступенями
	* Upper - смотрит, нет ли препятствия, мешающего подняться по ступени
	* Lower - смотрит, есть ли перед персонажем ступень

---

## Новые правила работы с персонажем
1. Префаб персонажа располагается теперь в папке _Assets/Animation/Chistoman/_, так как он меняется после изменения анимаций в Spriter
1. Все кости должны быть вложены __прямо в сам префаб__. Все остальное должно быть вложено во __внутренние объекты префаба__

## Новые правила создания карт
1. __ВАЖНО!__ Все ассеты для палитр тайлов должны храниться в папке _Assets/Palletes_
1. Все ступени и прочие приступки, по которым персонаж должен подниматься __автоматически__, должны быть встроены в _Tilemap_ - основной тайлмап с тегом _Collider_
1. Ступени и приступки должны располагаться ниже объекта _StairListener.Lower_ 

## Импорт анимаций из Spriter
1. Скачиваем .unitypackage [с этой страницы](https://brashmonkey.com/forum/index.php?/topic/3993-spriter-for-unity-50/) (Package Link или подобное)
2. Вставляем .unitypackage в папку Plugins (возможно, это необязательно). Импортируем все
3. Вствляем в проект (в любое место) папку с анимацией (спрайты и файл .scml)
4. ПКМ по файлу .scml -> Нажимаем Reimport
5. Должен появиться префаб и AnimatorController (префаб сохраняет свои компоменты после изменения анимации)
