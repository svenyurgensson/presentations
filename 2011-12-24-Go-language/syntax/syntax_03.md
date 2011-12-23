!SLIDE small

## Обработка ошибок через возврат  

    @@@ javascript

      src, err := os.Open(srcName, os.O_RDONLY, 0)
      if err != nil {
          return
      }
      defer src.Close()


!SLIDE small

## Как используется panic

    @@@ javascript
      func g(i int) {
        if i > 3 {
            fmt.Println("Panicking!")
            panic(fmt.Sprintf("%v", i))
        }
        defer fmt.Println("Defer in g", i)
        fmt.Println("Printing in g", i)
        g(i+1)
      }

## Все просто:

* panic - паникует (выбрасывает исключение)
* defer - отлавливает это исключение
