This repo is a fork of original repo https://github.com/hidez8891/shm.

Just added versioning for beautiful look in go.mod file.
# shm

shm is Golang shared memory library.

## Example

```go
w, _ := shm.Create("shm_name", 256)
defer w.Close()

r, _ := shm.Open("shm_name", 256)
defer r.Close()

wbuf := []byte("Hello World")
w.Write(wbuf)

rbuf := make([]byte, len(wbuf))
r.Read(rbuf)
// rbuf == wbuf
```
