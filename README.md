# mtnmomo-go

[![Build](https://github.com/NdoleStudio/mtnmomo-go/actions/workflows/main.yml/badge.svg)](https://github.com/NdoleStudio/mtnmomo-go/actions/workflows/main.yml)
[![codecov](https://codecov.io/gh/NdoleStudio/mtnmomo-go/branch/main/graph/badge.svg)](https://codecov.io/gh/NdoleStudio/mtnmomo-go)
[![Scrutinizer Code Quality](https://scrutinizer-ci.com/g/NdoleStudio/mtnmomo-go/badges/quality-score.png?b=main)](https://scrutinizer-ci.com/g/NdoleStudio/mtnmomo-go/?branch=main)
[![Go Report Card](https://goreportcard.com/badge/github.com/NdoleStudio/mtnmomo-go)](https://goreportcard.com/report/github.com/NdoleStudio/mtnmomo-go)
[![GitHub contributors](https://img.shields.io/github/contributors/NdoleStudio/mtnmomo-go)](https://github.com/NdoleStudio/mtnmomo-go/graphs/contributors)
[![GitHub license](https://img.shields.io/github/license/NdoleStudio/mtnmomo-go?color=brightgreen)](https://github.com/NdoleStudio/mtnmomo-go/blob/master/LICENSE)
[![PkgGoDev](https://pkg.go.dev/badge/github.com/NdoleStudio/mtnmomo-go)](https://pkg.go.dev/github.com/NdoleStudio/mtnmomo-go)


This package provides a generic `go` client template for the MTN Mobile Money API

## Installation

`mtnmomo-go` is compatible with modern Go releases in module mode, with Go installed:

```bash
go get github.com/NdoleStudio/mtnmomo-go
```

Alternatively the same can be achieved if you use `import` in a package:

```go
import "github.com/NdoleStudio/mtnmomo-go"
```


## Implemented

- [API User](#api-user)
    - `POST {baseURL}/apiuser`: Create API User

## Usage

### Initializing the Client

An instance of the client can be created using `New()`.

```go
package main

import (
	"github.com/NdoleStudio/mtnmomo-go"
)

func main()  {
	client := mtnmomo.New(
      mtnmomo.WithSubscriptionKey(""/* Subscription key */),
    )
}
```

### Error handling

All API calls return an `error` as the last return object. All successful calls will return a `nil` error.

```go
status, response, err := statusClient.Status.Ok(context.Background())
if err != nil {
    //handle error
}
```

### API User

#### `POST {baseURL}/apiuser`: Create API User

```go
response, err := client.APIUser.Create(context.Background())

if err != nil {
    log.Fatal(err)
}

log.Println(response.HTTPResponse.StatusCode) // 201
```

## Testing

You can run the unit tests for this client from the root directory using the command below:

```bash
go test -v
```

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details