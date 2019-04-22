**[back to table of contents](../README.md)**

---

# Meaningful Names

## Use meaningful and pronounceable variable names

**Bad:**

```go
yymmdd := time.Now().Format("2006-01-02")
```

**Good:**

```go
currentTime := time.Now().Format("2006-01-02")
```

[`open in playground`](https://play.golang.org/p/3RJt_QkclwO)

**[⬆ back to top](#meaningful-names)**

## Use the same vocabulary for the same type of variable

**Bad:**

```go
getUserInfo()
getClientData()
getCustomerRecord()
```

**Good:**

```go
userInfo()
```

Since Go doesn't provide automatic support for getters and setters, it's neither idiomatic nor necessary to put Get into the getter's name. [source](https://golang.org/doc/effective_go.html#Getters)

[`open in playground`](https://play.golang.org/p/kUAhNQdCx-j)

**[⬆ back to top](#meaningful-names)**


## Use searchable names

**Bad:**

```go
// what the heck is 86400 for?
time.Sleep(86400 * time.Second)
```

**Good:**

```go
secondsPerDay := 60 * 60 * 24
	
time.Sleep(secondsPerDay * time.Second)
```

[`open in playground`](https://play.golang.org/p/-wKeelxOt4s)

**[⬆ back to top](#meaningful-names)**

## Avoid mental mapping in a larger scope

**Bad:**

```go
func Read(buffer *Buffer, inBuffer []byte) (size int, err error){
    if buffer.empty(){
        buffer.Reset()
    }

    size = copy(
        inBuffer,
        buffer.buffer[buffer.offset:]
    )

    buffer.offset += size
    return size, nil
}
```

This is too verbose. That's okay in a larger scope, when functions are bigger (they shouldn't be, but that happens), but in a smaller scope it's a good practice to use a few words on naming variables.

**Good:**

```go
func Read(b *Buffer, p []byte) (n int, err error){
    if b.empty(){
        b.Reset()
    }

    n = copy(p, b.buf[b.off:])

    b.off += n

    return n, nil
}
```

[`open in playground`](https://play.golang.org/p/JE9hbt1h8k0)

**[⬆ back to top](#meaningful-names)**

## Struct names

**Bad:**

```go
```

**Good:**

```go
```

[`open in playground`](https://play.golang.org/)

**[⬆ back to top](#meaningful-names)**

## Interface names

**Bad:**

```go
```

**Good:**

```go
```

[`open in playground`](https://play.golang.org/)

**[⬆ back to top](#meaningful-names)**

## Method names

**Bad:**

```go
```

**Good:**

```go
```

[`open in playground`](https://play.golang.org/)

**[⬆ back to top](#meaningful-names)**

## Don't be cute

**Bad:**

```go
```

**Good:**

```go
```

[`open in playground`](https://play.golang.org/)

**[⬆ back to top](#meaningful-names)**

## Be consistent

**Bad:**

```go
```

**Good:**

```go
```

[`open in playground`](https://play.golang.org/)

**[⬆ back to top](#meaningful-names)**

## Avoid mental mapping

**Bad:**

```go
```

**Good:**

```go
```

[`open in playground`](https://play.golang.org/)

**[⬆ back to top](#meaningful-names)**

---

**[back to table of contents](../README.md)**
