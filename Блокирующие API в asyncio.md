___
Можно применять блокирующие API, такие как requests, вместе с asyncio, если запускать их в потоках threading. 

Казалось бы, в Python существует GIL - глобальная блокировка интерпретатора, которая не позволяет использовать многопоточность. Но GIL отключена, например, в операциях ввода-вывода - это выполнено потому что во время операций ввода-вывода действуют низкоуровневые функции операционной системы. Эти функции работают за пределами интерпретатора, следовательно, никак не могут повредить его внутренние структуры. 
___
[[Code]]:
```
print('hello world')
```
___
Language: [[Python]] [[Undone]]
Key-words:  [[asyncio python]]
Question query?: 