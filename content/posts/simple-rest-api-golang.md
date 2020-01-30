---
title: "Building a Simple Rest API with Go"
date: 2020-01-30T15:39:38+07:00
tags:
  - go
  - api
categories:
  - Web Development
---

## Basics

Before writing the actual functions to execute, we first need to define our program and import the necessary packages

```go
package main

import (
    "log"
    "net/http"
)
```

Breaking the above code down:

### Packages

[Packages](https://golang.org/pkg/) are the Go's source code, organized into system directories. They enable code reusability across Go applications. The main file for each application will use the package `main` for making the package into an executable. The `package main` tells the Go compiler that the package should compile as an executable program instead of a library.

### Imports

The keyword 'import' is used for importing packages into our program or another package. When importing packages, the Go compiler will look on the locations specified by the two environment variables:

- `$GOROOT` where packages from the [standard library](https://golang.org/pkg/) shipped with Go are stored and
- `$GOPATH` for fetched third-party or self-made packages.

>**Note**: Go by design does not allow declaration of unused import and will adamantly complain about it during compile time if any is found

In our case, both packages comes from the standard library:

- `log` allows us to log errors and other issues.
- `net/htpp` gives us HTTP client and server implementation for building the actual API

After declaring the packages, we can get to defining and serving our API. Without using third party libraries and routers, there are two main 'approaches' to this. 

If we implement our handler as a function, we'd use `http.HandleFunc`. Otherwise, if we'd implemented our handler as a type with a `ServeHTTP` method, we'd use `http.Handle`.

For simple implementation like ours, the first option is much easier and clearer to read and understand. But using a struct type allows storing of useful information in it, an example of which is the [file server](https://golang.org/src/net/http/fs.go?s=12662:12702#L418) from the standard library. The struct contains the root directory for file service. See this [Stack Overflow post](https://stackoverflow.com/questions/21957455/difference-between-http-handle-and-http-handlefunc) for a more detailed explanation

>**Note**: HTTP handlers are processes that runs in response to a request made to a web application. For more information, see its [Wikipedia page](https://en.wikipedia.org/wiki/HTTP_handler)

## Approach 1 (Handler function with http.HandleFunc)

```go

func apiResponse(w http.ResponseWriter, r *http.Request) { 
  w.WriteHeader(http.StatusOK)
  w.Header().Set("Content-Type", "application/json")
  w.Write([]byte(`{"message":"hello world!"}`))
}

func main() {
  http.HandleFunc("/",apiResponse)
  log.Fatal(http.ListenAndServe(":8080",nil))
}
```

Let's run through the code again.

### apiResponse

The function apiResponse is responsible for writing the response code and JSON. The function itself takes two arguments: `w` of type `http.ResponseWriter` assembles our HTTP server's responses, while `r` reads and parse the requests. Now to go through each line of the function:

- `w.WriteHeaer(http.StatusOK)` writes the HTTP [response code](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status) 200, indicating that the requested resource (the JSON response in our case) has been successfully fetched and is transmitted in the message body.
- `w.Header().Set("Content-Type", "application/json")` indicates the return type of the requested resource.
- `w.Write([]byte('{"message":"hello world!"}'))` finally writes our response in the message body.

### main

In our main function, the `HandleFunc` call tells the HTTP package to handle all requests to the web root ("/") with our apiResponse function. It then calls `http.ListenAndServe`, specifying that it should listen on port `8080` on any interface.
