# Колесо сетевой сансары

- у нас новая задача, надо отправить вот это вот туда
- не вопрос, просто пишем в сокет, у нас ти.си.пи. ноу проблем
..спустя год
- у нас проблема, в определенных кейсах данные не пролазят и пухнут буфера на отправку
- о да.. оказывается это называется backpressure, теперь мы смотрим скока отправилось и можем разрядить\компресснуть перед отправкой
- чудесно, всё оке.
..спустя год
- блин, расширили топологию сети, выяснили, что при перестроениях путей мы теряем данные, кааак?
- черт, оказыватся backpressure он только про скорость, но из за буферов на отправке: в нашей мегалибе, в ОС, в сетевой карте, свитчах и на принимающей стороне мы незнаем скока точно приняли и обработали
- оказывается есть паттерн на все случаи жизни: req\rep и вроде пока лучше ничего не придумали.
- чудесно, всё оке.
..спустя год
- блин, выяснили, что мы опять теряем данные, выяснилось что влияет увеличенная нагрузка на принимающей стороне, кааак?
- черт, оказывается всё из-за отложенной записи на приемнике, если ждать честно(из за дисков и хранилищ), то куча req\rep у нас должны выполняться параллельно чтобы успеть отправить, но тогда теряем последовательность операций, можем усложнить протокол так как простым счетчиком запросов как выяснилось не обойтись, но.. оказывается есть семантика pull, прикиньте принимающая сторона должена слать запросы а писатель отвечать, так и сделаем
- чудесно, всё оке.
..спустя год
- у нас новая задача, надо отправить вот это вот туда
- не вопрос, просто пишем в сокет, у нас ти.си.пи. ноу проблем

*to be continued*
