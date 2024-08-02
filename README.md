<img width="976" alt="image" src="https://github.com/user-attachments/assets/ef9304fa-164d-4820-b525-54cf0937c84f"># priorityQueue
## Priority queue with Generics support

* Supports only cmp.Ordered types

usage 
```go
var pq priorityqueue.Queue[int]

pq.Push(2)
pq.Push(3)
pq.Push(1)

for len(pq) != 0 {
    e = pq.Pop()
    fmt.Println(e)
}
```

```go
type pair struct {
	x, y int
}

pq := priorityqueue.New[pair](func(i, j pair) bool {
	return i.x < j.x
})

pq.Push(pair{2, 1})
pq.Push(pair{3, -1})
pq.Push(pair{1, 10})

for pq.Len() != 0 {
	e, _ := pq.Pop()
	fmt.Println(e)
}
```
