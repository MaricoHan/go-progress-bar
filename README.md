# go-progress-bar
a progress-bar with golang


### install
```shell
go get -u github.com/MaricoHan/go-progress-bar
```
### how to use
```go
package main

import (
	"time"

	"MaricoHan/go-progress-bar"
)

func main() {
	opts := []progress.Option{
		progress.WithInterval(time.Second / 5),
		progress.WithETAFormat("2006-01-02 15:04:05"),
		progress.WithFillerLength(25),
	}
	bar := progress.New(100, append(opts, progress.WithFiller("⭐️"))...)
	for i := 0; i < 100; i++ {
		time.Sleep(time.Second / 50)
		bar.Done(1)
	}
	bar.Finish()
}
```

### result display
```text
[⭐️⭐️⭐️⭐️⭐️⭐️⭐️⭐️⭐️⭐️⭐️⭐️⭐️⭐️⭐️⭐️⭐️⭐️⭐️⭐️⭐️⭐️⭐️⭐️⭐️]100/100 [eta]2023-03-29 09:34:10 [qps]33 
```