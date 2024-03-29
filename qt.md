1. [Оглавление](README.md)
1. [Общее](#1)
    1. [Приведение типов d Qt](#1.2)
    1. [QVariant](#1.2)
    1. [Макрос Q_OBJECT](#1.3)
    1. [Класс QObject](#1.4)
    1. [MOC compiler](#1.5)
1. [Многопоточность в qt/события, сигналы, слоты](#2)
    1. [Event loop](#2.1)
    1. [Delete later](#2.2)
    1. [Сигналы/слоты](2.3)
1. [Модели в qt](#3)
1. [QWidget](#4)
1. [QML](#5)
1. []()

* **Общее**: <a name=""></a>
    * **Приведение типов в Qt**: <a name="4"></a>
        * qvariant_cast - приводит объект класса QVariant к нужному классу.
        * qobject_cast - аналог dinamic_cast, но без использования RTTI. Класс должен быть наследником QObject и содержать в себе макрос Q_OBJECT.
    * **QVariant**: <a name="5"></a> 
    * **Макрос Q_OBJECT**: <a name="6"></a> Макрос, который раскрывается с помощью MOC компилятора, генерируя код позволяющий работать QT фичам.
    * **Класс QObject**: <a name="7"></a> Хранит ссылку на объект и информацию о типе объекта? #TODO
    * **MOC compiler**: <a name="8"></a>
* **Многопоточность в qt/события, сигналы, слоты**: <a name=""></a> https://habr.com/ru/post/467261/
    * **QtConcurrent**: <a name="1"></a> #TODO
    * **QThread**: <a name="1"></a> это Qt обертка для потока конкретной ОС, которая позволяет взаимодействовать с потоком из Qt проекта, в первую очередь через Qt signals/slots.
        * Неправильный способ, это отнаследоваться от QThread и переопределить метод run(), но добавлять туда какую-то бизнес логику - противоречит идее заложенной самими qt разработчиками. Прибегать к этому способу стоит только тогда, когда нужно кастомизировать стандартные потоки.
        * Правильный способ работы с тредом, это реализовать класс в котором выполняется некая бизнес логика и сигналы/слоты для начала и конца работы этого класса, затем через moveToThread (метод QObject), переместить экземпляр класса в отдельный тред и связать его с методами started() и quit(). 
    * **Event loop**: <a name="1"></a> #TODO
    * **Delete later**: <a name="2"></a> #TODO
    * **Сигналы/слоты**: <a name=""></a>
        * 5 параметр функции connect:
            * Auto Connection (default) - если источник сигнала и слот находятся в одном потоке, то поведение как у Direct Connection, если источник сигнала и слот находятся в разных потоках, то поведение как у Queued Connection.
            * Direct Connection - слот вызывается немедленно при отправке сигнала. Слот выполняется в потоке отправителя, который не обязательно является потоком-получателем.
            * Queued Connection - слот вызывается, когда управление возвращается в Event Loop в потоке получателя. Слот выполняется в потоке получателя.
            * Blocking Queued Connection - слот вызывается так же, как и при соединении через очередь, за исключением того, что текущий поток блокируется до тех пор, пока слот не возвратит управление. 
                * Использование этого типа подключения объектов в одном потоке приведет к дедлоку
            * Unique Connection - поведение такое же, что и при автоматическом соединении, но соединение устанавливается только если оно не дублирует уже существующее соединение. т.е., если тот же сигнал уже соединён с тем же самым слотом для той же пары объектов, то соединение не будет установлено и connect() вернет false.
* **Модели в qt**: <a name=""></a>   
* **QWidget**: <a name=""></a>
* **QML**: <a name=""></a>
