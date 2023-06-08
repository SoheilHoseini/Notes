#### Concurrency vs Parallelism
Concurrency is about multiple tasks which start, run, and complete in overlapping time periods, in no specific order. Parallelism is about multiple tasks or subtasks of the same task that literally run at the same time on a hardware with multiple computing resources like multi-core processor.
Concurrency is two lines of customers ordering from a single cashier (lines take turns ordering); Parallelism is two lines of customers ordering from two cashiers (each line gets its own cashier).


#### Goroutines



#### Channels
Channels are a means through which different goroutines communicate. Think of them as pipes through which you can connect with different concurrent goroutines. The communication is bidirectional by default, meaning that you can send and receive values from the same channel. Moreover, by default, channels send and receive until the other side is ready. This allows goroutines to synchronize without explicit locks or condition variables.

.... To be continued ....






### References
[Stackoverflow-Concurreny-vs-Parallelism](https://stackoverflow.com/questions/1050222/what-is-the-difference-between-concurrency-and-parallelism)
[Educative.io-Channels](https://www.educative.io/answers/what-are-channels-in-golang)
[JakeWright-YouTube-Concurrency in Go](https://www.youtube.com/watch?v=LvgVSSpwND8)
