# Лекция 8 Многопоточность, асинхронные задачи

[Репо проекта из лекции](https://github.com/ilya-r-cherkasov/ConcurrencySummerSchool)

[Ссылка на презентацию](https://drive.google.com/file/d/1MkyK7bo9ME3AfBwiKQ6igTbkU0NG1mmJ/view?usp=sharing)

[Запись лекции](https://drive.google.com/file/d/1yqwgPcV5nD_MzxVnf2hwWxuj7V-tJdKp/view?usp=sharing)

> Сегодня мы поговорили о многопоточности, выяснили преимущества асинхронного программирования, и разобрали проблемы, которые могут проявляться в многопоточном коде.

## Полезные материалы

- [Немного о RunLoop](https://rderik.com/blog/understanding-the-runloop-model-by-creating-a-basic-shell/)
- [Swift: Mutex benchmark](https://medium.com/@sergebouts/swift-mutex-benchmark-b21ee293d9ad)
- [Параллелизм, многопоточность и асинхронное программирование](https://codewala.net/2015/07/29/concurrency-vs-multi-threading-vs-asynchronous-programming-explained/)
- [Multithreading в swift с нуля](https://www.youtube.com/watch?v=JtDf-S1uLLs&list=PLmTuDg46zmKCKjZqxXqJFjGXwzqGQi4D3&index=1)
- [Deadlocks, Livelocks и Starvation](https://medium.com/german-gorelkin/deadlocks-livelocks-starvation-ccd22d06f3ae)
- [Параллельное программирование на Swift](https://medium.com/@jan_olbrich/parallel-programming-with-swift-what-could-possibly-go-wrong-f5bcc38b1814)
- [Устройство многопоточности в iOS](https://sidorov.tech/all/ustroystvo-mnogopotochnosti-v-ios/)
- [Multithreading](https://habr.com/ru/company/otus/blog/549814/)

## Многопоточность

Процессор постоянно переключается между задачами

Задачи параллеллятся

Запуск - dispatch

**Вход - очередь - запуск - (пауза) - ЦП - выход**

## Конкурентность, параллелелизм, многопоточность

### Конкурентность - понятие, которое говорит о том, что ВУ может выполнять задачи одновременно

### Параллелелизм - компьютер имеет несколько вычислительных блоков (ядер) и они работают параллельно

### Многопоточность - один из способов реализации конкурентности путем выделения абстрацкии рабочего потока
ОС может делить программы на потоки

### Асинхронность - можно поставить задачу на исполнение и забыть про нее. Потом будет напоминание

## Проблемы 

- Race Condition
- Deadlock
- RunLoop
- Mutex

изучить термины

## Виды очередей

- serial
- cuncurency

main - serial
global - cuncurency

### На каждом потоке есть run loop

Если ничего нет он просто засыпает

thread после исполнения деинициализируется
если он не в свойстве класса

sync
async

атрибуты очереди

sync/async

DispatchWotkItem()
метод, который уведомляет очередь, что item выполнился
item.notify()

GCD - обстракция над NSThread
operationQueue слой абстракции над GCD

Как синхронизировать потоки?
можно с помощью DispatchGroup

item.cancel()
отменить задачу возможно

если задача в очереди, оттуда удалить ее невозможно??? изучить

В operation можно отменять запущенное
dispatchGroup нельзя если уже запустилась

можно удалить задачу из очереди если она не взялась в работу

## Семафоры

DispatchSemaphore()
изучить

- Потоки - бабушки, которые встают в очереди
- Семафор - служба охраны, которая может проверять только две бабушки

semaphore.signal()

DispatchGroup()
group.enter()
в кажду задачу
group.leave()
group.wait()

Барьерная таска
помогает решить проблему с deadlock
BarrierTask()
concQueu.async(flags: .barrirer) { }
заграждаем эти заданием выполнение следующих


OperationQUeue() изучить

Run loop
Race Condition


NSLock()

цикл while в функцию main ?
Паттерн EventLoop

## Домашнее задание на сегодня:

1. Реализовать верстку и логику экрана поиска. 
2. Залить изменения в репозиторий
