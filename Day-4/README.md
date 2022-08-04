# День - 4. Архитектуры MVP, MVC

[Ссылка на презентацию](https://drive.google.com/file/d/19z66AxKGZAUyYRAP-mzl6tym6z2vs3NF/view?usp=sharing)

[Запись лекции](https://drive.google.com/file/d/1bOlnaz3Spfceqj8lPkC3dr-UgfqTlu5H/view?usp=sharing)

>Сегодня на занятии мы рассмотрели две популярные базовые архитектуры MVC и MVP, реализовали главный экран приложения с моковыми данными, рассмотрели работу с UICollectionView, а также базовую работу с версткой.

## Полезные материалы

### Architecture

🏄‍♀️ [Документация MVC от Apple](https://developer.apple.com/library/archive/documentation/General/Conceptual/DevPedia-CocoaCore/MVC.html)

🏄‍♀️ [Простая статья о MVC на русском](https://habr.com/ru/post/500870/)

🏄‍♀️ [Статья, демонстрирующая разницу между MVP и MVC](https://saad-eloulladi.medium.com/ios-swift-mvp-architecture-pattern-a2b0c2d310a3)

🏄‍♀️ [Статья про разные архитектуры](https://habr.com/ru/company/badoo/blog/281162/)

### UICollectionView

🏄‍♀️ [UICollectionView documentation](https://developer.apple.com/documentation/uikit/uicollectionview)

🏄‍♀️ [CollectionView Ray Wenderlich Tutorial](https://www.raywenderlich.com/136159/uicollectionview-tutorial-getting-started)

🏄‍♀️ [CollectionView with NSHipster](https://nshipster.com/uicollectionview/)

### Внутренее устройство навигации (как навигация хранит контроллеры)
Повторить азы!

Влад КЛимов iOS разработчик Surf
(собеседовал меня?)
UIViewCollection

### Layout что и зачем

Базовая работа с версткой

Какие подходы сущетсвуют

### Архитектуры

Зачем нужны?
ПОзволяют разработчикам договорить как строить код
и разделять логику

Нужно обращать на них внимание

### MVC
Откуда взялось - Apple презентовали
В отличии от классической
жестко разделили на слои

модель - данные которые лижат
в архитектурах модель - бизнес логика
абстрактные данные которые можно получить

модель не взаимодействует с вью

вью только работает с интерфейсом

контроллер - жизненный цикл объектов
посредник между моделью и вью

### MVP

заменяет контроллер
презентер обраюатывает взаимодействия

Surf - mvp

и сервисы
модели = микросервисы

Навигация роутер
или координаторы

один флоу = 1 координатор


### Способы навигации
- из кода
- сегуэй
- кнопка в сторибоард

Чаще всего навигация из кода у сюрф

на больших проектах сторибоарды не удобно


### Коллекии

Объект, который управляет упорядоченной коллекцией элементов
и показывает их используя кастомизированный лэйоут

Лэйоут настраивается под нужды
вверх вниз и тп

переиспользование ячеек
reusable cell
UICollectionViewLayout
кастомизация верстки
UICollectionViewDataSource
отвеает за наполнение данных
секции типы и тп

UICollectionViewDiffableDataSource - class
это эпл взяли из опен соурс
таблица перезаполняется автоматически
происходит снепшот

### КОротко про верстку
попробовать клиент git Fork

IB отображать приватными

при инициализации didSet не отработает

CALayer второй слой под UIKit

лайфхак с идентификаторм - круто! "\(.self)"


### Домашнее задание
Реализовать экран поиска с помощью архитектуры
открывать пустой экран с выбранной архитекторой
