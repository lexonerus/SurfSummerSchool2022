# День 3. Инициализация экранов.

[Ссылка на презентацию](https://drive.google.com/file/d/1aA-PQ7VGVPh_3WeqSybaMkpsArEovKGK/view?usp=sharing)

>Сегодня было круто! Спасибо за вашу активность ❤️
Мы узнали об основных ViewController-ах и их LifeCyrcle. Изучили основные контейнеры хранения и как они используются для навигации. Реализовали свой TabBar.

## Полезные материалы:

- [Документация Apple UIViewController](https://developer.apple.com/documentation/uikit/view_controllers)
- [Статья Хабр про жизненный цикл UIViewController](https://habr.com/ru/post/129557/)
- [Документация Apple UINavigationController](https://developer.apple.com/documentation/uikit/uinavigationcontroller)
- [Документация Apple UITabBarController](https://developer.apple.com/documentation/uikit/uitabbarcontroller)
- [Основы мобильной навигации](https://vc.ru/flood/24327-navigationpatterns)
- [I/UX Design Glossary. Navigation Elements](https://uxplanet.org/ui-ux-design-glossary-navigation-elements-b552130711c8)


## Виды контроллеров
UIView
общее представление элементов экрана, касания, элементы, конфигурации


UIViewController
Выполняет похожую роль, но еще имеет возможности навигации между экранами, конфигурирует UIView
передает информацию

UITableViewController - база, которая используется повсеместно.
UITableViewController - внутри таблица. Компонует внутри себя вью и обрабатывает взаимодействия пользователя.
Таблица и коллекция отличается композицией лэйоутов


UICollectionViewController


Рассказывает про сторибоард
как добавить элемент


- RootViewController
- Виды контроллеров - пропустил, пересмотреть!

## Жизненный цикл UIViewController
- loadView
- loadViewIfNeeded
- viewDidLoad

Вызываются единожды при создании view
Хороший слайд, пересмотреть

ViewWillAppear


Вызывается каждый раз, когда view появляется на экране
Вызывается несколько раз
см слайд
В нем лучше конфигурировать navigationController

ViewDidAppear


Перед тем как вид появился на экране

VIewWillDisappear


Вызывается когда вид собирается исчезнуть
Многократно
см слайд

ViewDidDisappear


Когда вид закрывается другими вью
Входящий вызов, пуш уведомления и тд
многократно

Преимущество ксибов
быстрота и наглядность

Практика - таб бар
создание и контроллеры

ссылка на info.plist в конце
