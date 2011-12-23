!SLIDE smbullets incremental left small left
## Синтаксис: общее

* С-подобный, меньше скобок
* почти нет ;
* комментарии все как в С
* комментарии doxygen-style

!SLIDE left small left
## Синтаксис: конструкции
  
    @@@ javascript
    if x > 0 {
       return y
    }

    sum := 0
    for i := 0; i < 10; i++ { sum += i }

    for { }


!SLIDE left small left
## Синтаксис: конструкции
## видим хеш, проход по хешу

    @@@ javascript
    var m map[string]int
    sum := 0
    for _, value := range m { 
      sum += value 
    }
    // Ключ из map-а игнорируется.


!SLIDE left small left
## Синтаксис: функции

Возвращаемым значениям можно присваивать имена:

    @@@ javascript
    func idiv(a, b int) (d, r int) {
      d = a / b
      r = a % b
      return
    }


!SLIDE left small left
## Синтаксис: пакеты
    
    @@@ javascript
    import (
         "fmt"
         "io/sockets"
         "io/sharedmemory/fast"
    )

    fmt.Fprintf(...)
    a := io.Open( ... )

явно указываем имя пакета fmt, io




