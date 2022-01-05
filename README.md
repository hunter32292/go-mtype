# Mtype = Media Type
List of const content types, because I keep forgetting them. Just use autocomplete with the package and you can stop dealing with missed chars in your content types or forgetting what content types you can use.

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
	"log"
	"net/http"

	"github.com/hunter32292/go-mtype"
)

func main() {
	http.HandleFunc("/health", Health)
	log.Fatal(http.ListenAndServe("localhost:8080", nil))
}

func Health(w http.ResponseWriter, r *http.Request) {
	w.Header().Set("Content-Type", mtype.ApplicationJson)
	io.WriteString(w, `{"alive":"true"}`)
}
```

Find From the Const List:
![image](https://user-images.githubusercontent.com/6210083/135304428-41619e2a-b18a-4edd-a857-57cb54b35f46.png)
