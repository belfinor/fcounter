# fcounter

Work with counter in a text file

# Install

```
go get github.com/belfinor/fcounter
```

# Usage

```go
package main

import (
  "fmt"
  "time"

  "github.com/belfinor/fcounter"
)

func main() {

  // 0 if no file or last value
  // val = val % 100000000
  cnt := fcounter.New("counter.txt", 100000000)

  cnt.Set(0)

  fmt.Println(cnt.Get()) // 0

  for i := 0 ; i < 10 ; i++ {
    // inc = ( inc + 1 ) % 100000000
    fmt.Println( cnt.Inc() ) // i + 1
  }

  cnt.SetDate(time.Now()) // val = YYYYMMDD
}
```
