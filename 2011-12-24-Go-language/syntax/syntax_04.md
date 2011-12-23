!SLIDE smbullets incremental left small left
## Goroutines

* запуск функции в отдельной нити
* отображаются на потоки ОС
* создание дешевое
* общение через каналы


!SLIDE left small left
## Запуск goroutine

    @@@ javascript
    func Announce(message string, delay int64) {
       go func() {
            time.Sleep(delay);
            fmt.Println(message);
          }() 
          // Круглые скобки здесь важны -
          // делается вызов функции
    }


!SLIDE smbullets incremental left small left
## Goroutines+Channals

* типобезопасные unix-pipes
* синхронизация goroutines
* блокирующие/неблокирующие

!SLIDE left small left
## Синхронизация через каналы

    @@@ javascript
    // Создание канала.
    c := make(chan int)

    // Сортировка запускается в отдельном потоке
    // Когда она завершается
    // в канал записывается сигнал
    go func() {
       list.Sort()
       // Отсылка сигнала.
       // Не важно, какое это будет значение
       c <- 1 
    }()

    doSomethingForAWhile()
    <-c 
    // Ожидание завершения сортировки. 
    // Прочитанное из канала значение
    // просто выбрасывается


!SLIDE left small left
## Utilize all CPU Cores

    @@@ javascript
    // Количество доступных CPU
    const NCPU = 4

    func (v Vector) DoAll(u Vector) {

      // Буферизация не обязательна,
      // но может иметь смысл
      c := make(chan int, NCPU)
      for i := 0; i < NCPU; i++ {
        go v.DoSome(i*len(v)/NCPU, 
                    (i+1)*len(v)/NCPU, u, c)
      }

      // Вычитываем все из канала
      for i := 0; i < NCPU; i++ {
        // Ждем, пока завершиться 
        // очередная операция
        <-c 
      }
      // Все действия завершены
    }
