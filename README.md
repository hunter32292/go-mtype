# Netcontent
List of const content types, because I keep forgetting them

## Notes

This is a subset of all content types, only some of the more common ones.

Complete list here:
https://www.iana.org/assignments/media-types/media-types.xhtml

## To Use:

import module:

`go get -u github.com/hunter32292/go-mtype`

Include in application like so:

```go 
package main

import (
 "io"
 "net/http"
 "fmt"
 
 "github.com/hunter32292/go-mtype"
)

func main() {
	fmt.Println(netcontent.ApplicationJson)
	http.HandleFunc("/health", Health)
	log.Fatal(http.ListenAndServe("localhost:8080", nil))
}


func Health(w http.ResponseWriter, r *http.Request) {
	w.Header().Set("Content-Type", netcontent.ApplicationJson)
	io.WriteString(w, `{"alive":"true"}`)
}


```
