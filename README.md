## Overview

This is a gpt3-go client library. It allows you to interact with the OpenAI GPT-3 API.

## Installation

Install the library with:

```bash
go get github.com/lakshminarasimmanv/gpt3-go
```

## Usage

Create a new client:

```go
c := gpt3.NewClient(nil)
```

You can also use your own http client:

```go
httpClient := &http.Client{
    // Do stuff...
}
c := gpt3.NewClient(httpClient)
```

Set your API key:

```go
c.APIKey = "YOUR_API_KEY"
```

## Examples

Here are some example usage patterns for the library.

### Completions

```go
// Create a new completions service.
completions := c.Completions

// Create a new context with a timeout of 10 seconds.
ctx, cancel := context.WithTimeout(context.Background(), 10*time.Second)
defer cancel()

// Create a new completions request.
req := &gpt3.CompletionsRequest{
    Prompt: "The quick brown fox jumps over the lazy dog",
    MaxTokens: 100,
}

// Do the request.
resp, err := completions.Completions(ctx, req)
if err != nil {
    // handle error
}

// Print the response.
fmt.Println(resp.Completions)
```

## License

The library is released under the MIT License.
