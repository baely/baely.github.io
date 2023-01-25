---
title: "Hello World in Go"
---

```go
package main

import "fmt"

func main() {
	c := make(chan bool)

	go func() {
		defer func() {
			c <- true
		}()

		fmt.Println("Hello, world!")
	}()

	<-c
}
```
