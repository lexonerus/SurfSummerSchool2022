# День 6. Сетевой слой.

[Ссылка на презентацию](https://drive.google.com/file/d/1gPHkUr72QVXA23lF7796KAde5jRPfoTU/view?usp=sharing)

[Запись лекции](https://drive.google.com/file/d/1vQyKV8xKKF4een36K55v_wvlQHj4QClc/view?usp=sharing)

>Сегодня мы познакомились с сетевым взаимодействием в iOS-приложениях, поговорили про URLSession, Codable. Разобрали на практике, как сделать сетевой слой в приложении. 

## Полезные материалы

### Работа с сетью в iOS
- [Официальная документация URLSession от Apple](https://developer.apple.com/documentation/foundation/urlsession)
- [Networking in iOS от Swift by Sundell](https://www.swiftbysundell.com/basics/networking)
- [Статья про взаимодействие с сетью в iOS из habr.ru](https://habr.com/ru/post/414359/)
- [URLSession + Combine, так же от Apple](https://developer.apple.com/documentation/foundation/urlsession/processing_url_session_data_task_results_with_combine)

### Decoding
- [Туториал по декодингу данных  от Apple](https://developer.apple.com/documentation/foundation/archives_and_serialization/encoding_and_decoding_custom_types)
- [Гайд по Codable](https://benscheirman.com/2017/06/swift-json/)
- [Статья про парсинг данных в iOS](https://habr.com/ru/post/414221/)

### Про сеть
[Про REST](https://medium.com/@andr.ivas12/rest-%D0%BF%D1%80%D0%BE%D1%81%D1%82%D1%8B%D0%BC-%D1%8F%D0%B7%D1%8B%D0%BA%D0%BE%D0%BC-90a0bca0bc78)

## Спикер:
Илья Князьков
пришел в Серф после подобной школы

## Сетевое взаимодействие
Напишем на практике сетевой слой

## URI
Uniform Resource Identifier

URI.contains(URL) -> true

URL - часть URI

## Methods

- Get
- Post
- Put
- Delete

Методы это часть HTTP протокола, которые позволяют
производить действия на сервере

## Параметры и хедеры

Параметры и хедеры не одно и тоже
но суть примерно одинаковая
хедеры описывают протоколы
параметры кастомная штука созданная в бэкэнд
для исполнения ограничений на контроллере

НА СЛАЙДЕ ПЕРЕПУТАНЫ key-value Headers !

## Parameters
Параметры нельзя передавать в GET запросе

Назначение параметров нужно понимать
POST не мутирующий запрос

# Networking iOS

- URLSessiont
- URLDataTask

## URLSessiont

Массивный комплекс компонентов, который позволяет производить взаимодействие с интернет-протоколами

## URLDataTask
Возвращает загруженные объекты в виде NSData

## Responce

Ответ по сетевому взаимодействую приходит в виде Responce

Состоит из кода ошибки (100 - 500)
и других артефактов

Посмотреть виды сетевых ошибок


## JSON

## Errors

## Практика
Что такое ПТР - пулт рефреш

## AssociatedtType
Generic
Result
Error

## Домашнее задание
Домашнее задание на сегодня:

1. На время загрузки на главной нужно заимплементить лоадинг-стейт. Дизайн: https://www.figma.com/file/DskQkoBqXewHFzyqlKkao3/Surf-education-iOS?node-id=8%3A1280 
2. После загрузки в случае появления ошибки,  обработать ее, показав соответствующий стейт.Дизайн: https://www.figma.com/file/DskQkoBqXewHFzyqlKkao3/Surf-education-iOS?node-id=13%3A8983
3. Если при загрузке картинки на детальном экране появляется проблема (не сразу появляется, лагает),  попытаться найти баг и пофиксить это
4. Загрузить изменения в репозиторий
