# День 7. Storage and cache.

[Ссылка на презентацию](https://drive.google.com/file/d/1-oAzKLHA_AgU-tvynFfL8xWhzvPsie_V/view?usp=sharing)

[Запись лекции](https://drive.google.com/file/d/1X1czwuUiIVNLmyEIK4ndetVRSsU56CQd/view?usp=sharing)

>Сегодня мы познакомились с хранением данных в iOS-приложениях, поговорили про временные и постоянные хранилища, выяснили их особенности и недостатки. Разобрали на практике как закешировать данные в приложении.

## Полезные материалы

### Base

- [File System Basics](https://developer.apple.com/library/archive/documentation/FileManagement/Conceptual/FileSystemProgrammingGuide/FileSystemOverview/FileSystemOverview.html)

### Temporary

- [Официальная документация URLCache от Apple](https://developer.apple.com/documentation/foundation/urlcache)
- [Официальная документация NSCache от Apple](https://developer.apple.com/documentation/foundation/nscache)
- [Cache with NSCache from SwiftBySundell](https://www.swiftbysundell.com/articles/caching-in-swift/)
- [Официальная документация Core Data от Apple](https://developer.apple.com/documentation/coredata)Persistent

### DB

- [Официальная документация Core Data от Apple](https://developer.apple.com/documentation/coredata)
- [Core Data + Swift для самых маленьких](https://habr.com/ru/post/303512/)
- [Синхронизация API с CoreData](https://medium.com/swift2go/fetching-remote-data-with-core-data-background-context-in-ios-app-224dad15ef6c)

### Key-Value

- [Storing Keys in the Keychain от Apple](https://developer.apple.com/documentation/security/certificate_key_and_trust_services/keys/storing_keys_in_the_keychain)
- [Статья про KeyChain API](https://habr.com/ru/post/526510)
- [Официальная документация UserDefaults от Apple](https://developer.apple.com/documentation/foundation/userdefaults)
- [Пример использования UserDefaults](https://medium.com/@nimjea/userdefaults-in-swift-4-d1a278a0ec79)
- [Официальная документация FileManager от Apple](https://developer.apple.com/documentation/foundation/filemanager)

## Заметки
конфигуратор кнопки поиска создать переиспользуемый
стиль в extension к navigation bar

typeAlias узнать подробнее

# Storage in iOS
Хранилища
- постоянные
- временные

## Persistant

### Базы данных
- sql (SQLite, CoreData)
- NOsql (realm)

- Реляционные (сложная структура хранения, сущности разделены на детали)
- Не реляционные (все в одном месте)

По заверениям эпл не все классы CoreData thread safe
Нужно делать потокобезопасность

- Key-value Storage
- UserDefaults
- KeyChain
- FileManager

### UserDefaults - обычная обертка над .plist
Лежит в {applicationId}/Library/Preferences/{bundleid}.plist

- UserDefaults - openSource
- часть Foundation - framework
- полностью thread-safe api
- довольно быстрый, совмещает подходы URLCache, файлы кэшируются

Используем для хранения настроек
- хранение онбоардинга
- пользовательские действия
- Локальные бд объекты лежат в песочнице

после удаления приложения чистится
файл создается только при условии записи первого значения
можно создать свой .plist файл


### KeyChain
- зло в плане API
- ultra legacy
- API вокруг SQLite не зашифрована
- ее можно открыть напрямую

лежит Users/{username}/Library/Keychains/login.heychain-db
в симуляторе его нет
API для кей валюь хранения
шифруются отдельно записи

### плюсы
- безопасность
- Persistant + iCloud
- удалил приложения они остались
- хранение паролей токенов
- thread-safe

### минусы
- стремное API
- все ошибки представлены в виде системных статусов
- древняя штука
- есть расшифровки в интернете, специальные ресурсы

### FileManager

Нужен для того, чтобы хранить файлы URL(URI) локальные ресурсы

- ПРостое api
- thread safe
- похож на UserDefaults
- но чуть сложнее
- постоянно улучшается

используется если нужен кэш (постоянный)
кэш - кэширование разные ли вещи?
происходит в песочнице
подвержено удалению

## Временная память
Temporary

- NSCache API
- URLCache API

Хранилища могут вычищаться без удаления приложения

NS - табличный кэш
полностью в ОЗУ
простое API
legacy
NSCache
Работает с pointer объектами
ключ должен быть pointer (NSString)
протсой кэш где есть key value

был метод didRecievedMemoryWarning() {
  тут удалится этот кэш
}

не хранится в обычной памяти
узкоспециализированный API
пример - (кэш картинок)

URL очень похож на UserDefaults, коллаборация из RAM и ROM хранится и синхрониз
не всегда убивается когда приложение завершается
если системе нужна память то вычистится
простое api
тоже key value
responce data


CFDictionary
CFString - изучить!
Core Foundation
требуют pinter'ы

что такое OSStatus?
https://www.osstatus.com/
Apple API errors

Swift.Error - изучить!

Почитать про Pointer'ы

if case let .success() = result - разобраться
==
switch result {
  case .success():
}

ЧТо за символ &tokenResult? - KeyChain


DispatchQueue.main.asyncAfter(deadline: .now() + 2) - выполнить с задержкой

Кэширование запросов - если нужно зайти без интернета
есть инфа в кэше
или если интернет отваливается

didSet пересмотреть!
bad practice
сделать функцию configure(with model: SomeModel) например

## Домашнее задание на сегодня:

1. Создать сервис сохранения в "избранном" с логикой (встроить логику на экран)
2. Поюзать UserDefaults
3. Залить изменения в репозиторий
