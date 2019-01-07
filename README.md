# go-freeocr
Libreria de Golang para usar la OCR API de OCR.Space como servicio.

## Instalacion
```sh
go get github.com/arthurnavah/go-freeocr
```

## Ejemplo de uso
```go
package main

import (
	"fmt"
	"log"

	gofreeocr "github.com/arthurnavah/go-freeocr"
)

func main() {
    client := gofreeocr.NewClient("apikey", "true")    // API Key

    img := gofreeocr.NewImage(
        "https://host.com/url/de/la/imagen",    // URL de la imagen

        "spa",                                  // Lenguaje de la imagen

        gofreeocr.UNDEFINED,                    // Tipo de archivo de la imagen
    )

    response, err := client.SendImage(img, gofreeocr.POST)    // Se envia la imagen, Declarando el metodo a utilizar
    if err != nil {
        log.Println(err)
    }

    fmt.Println(response.Text())
}
```
