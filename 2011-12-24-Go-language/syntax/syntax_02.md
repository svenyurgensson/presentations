!SLIDE smbullets incremental left small left
## Синтаксис: константы
    
    @@@ javascript
    const Pi = 3.14

!SLIDE smbullets incremental left small left
## Синтаксис: переменные

    @@@ javascript
    // Полная декларация с инициализацией
    var v int = 0

    // Полная декларация без инициализации
    var v int

    // Вывод типа при инициализации
    var v = 0

    // Тоже самое, но еще короче
    v := 0

!SLIDE smbullets incremental left small left
## Синтаксис: типы

    @@@ javascript
    type Vertex struct {
      Lat, Long float64
    }

    var m map[string]Vertex

!SLIDE smbullets incremental left small left
## Синтаксис: лямбды

    @@@ javascript
    package main

    import "fmt"

    func adder() func(int) int {
      sum := 0
      return func(x int) int {
        sum += x
        return sum }
    }

    func main() {
      pos, neg := adder(), adder()
      for i := 0; i < 10; i++ {
        fmt.Println(
          pos(i),
          neg(-2*i),
        )}
    }