# День 5. Layout, Основы анимации, UITableViewController

[Ссылка на презентацию](https://drive.google.com/file/d/1ge8eooXDg9jRhoszvIC_q35aPe5Z74Mv/view?usp=sharing)

[Запись лекции](https://drive.google.com/file/d/117rTHozsIKAkflHXyKctik6QK7ImW62C/view?usp=sharing)

>Сегодня на занятии мы реализовали детальный экран карточки. Поглубже рассмотрели возможности layout-а и как с ним работать, а также посмотрели базовые анимации.

## Полезные материалы

### Layout
- [Отличная статья про Update Cycle и все его методы](https://tech.gc.com/demystifying-ios-layout/)
- [Крутой тутотариал про CALayer](https://www.raywenderlich.com/10317653-calayer-tutorial-for-ios-getting-started#toc-anchor-012)
- [Документация от Apple по layoutSubviews()](https://developer.apple.com/documentation/uikit/uiview/1622482-layoutsubviews)
- [Простая статья по CALayer](https://habr.com/ru/company/badoo/blog/281162/)
- [Подробный гайд AutoLayout от Apple](https://developer.apple.com/library/archive/documentation/UserExperience/Conceptual/AutolayoutPG/index.html#//apple_ref/doc/uid/TP40010853-CH7-SW1)
- [Гайд по AutoLayout от Ray Wenderlich](https://www.raywenderlich.com/160527/auto-layout-tutorial-ios-11-getting-started)
- [Короткая статья о AutoLayout](https://hackernoon.com/understanding-auto-layout-in-xcode-9-2719710f0706)
- [Статья на русском](https://habr.com/post/312782/)
- [Appcoda Beginners Guide](https://www.appcoda.com/auto-layout-guide/)
- [От Apple про адаптивный дизайн](https://developer.apple.com/design/adaptivity/)
- [Математические основы Autolayout](https://habr.com/ru/company/oleg-bunin/blog/437584/)

### UITableView
- [UITableView documentation](https://developer.apple.com/documentation/uikit/uitableview?changes=_6)
- [Подробный разбор UITableView](https://medium.com/@andycherkashyn/everything-you-need-to-know-about-ios-uitableview-79b766bf1a42)
- [UITableView Tutorial For Beginners](http://www.thomashanning.com/uitableview-tutorial-for-beginners)
- [Список статей Ray Wenderlich про TableView](https://www.raywenderlich.com/tag/uitableview)

## Замечание:
обращение к классу через .init - быстрее сборка проекта

Илья Князьков - Surf разработчик

Детальный экран для коллекции элементов
Рассмотрим Layout
Чуть анимации
CALayer

## Layout

- Frame Based Layout
- Auto Layout

С помощью constraints удобно располагать View
Есть view которые имеют размер по умолчанию
базовый UIView не имеет считать размер
Есть свойство intrinsicContentSize (вычисляемое get свойство, его можно переопределить)
- кнопки
- лэйбл
- текст филд

Свойство huggingPriority (работает ли в стеках? применить в калькуляторе)
Свойство на расширение

## Update cycle
Когда сработает отрисовка?
Отвечает за компоновку и перерисовку объектов
в eventLoop

## Frame Bounds
- Frame расположение координат в superview
- Bounds расположение view в его собственной системе акоординат

Классный пример с вращением view в лекции

## ViewDidLayoutSubview()
Вызывается каждый раз, когда view
- обновляется
- поворачивается
- изменяется

## LayoutSubviews()
Рассчитывает размеры и позции view на основе констрейнтов
Вызывается при см презентацию
**Никогда не вызывается на прямую!**

## setNeedsLayout()
Сообщает системе о том что нужно обновить Layout
во время следующего цикла рисования

## layoutIfNeeded()
Перерисовка сейчас
принудительно

### Схема работы layout см презентацию!


## CALayer
Используется для например закруглений или тень
Уровень ниже уровня Layout
Более низкоуровневый слой

UIKit / AppKit - база
Core Animation
Metal - Core Graphics
Graphics Hardware (на уровне драйверов)
