___
Условная конструкция if-else в Go отличается от Python. 
1. Область видимости внутри условных выражений if-else очень ограничена и приходится только на тело выражения {}. Т.е. за пределами тела выражения, например, после выхода из условной конструкции, созданные переменные будут недоступны!!! ![[Pasted image 20230108114258.png]]
2. Для инициализации переменных (или их перезаписи) с помощью условных конструкций if - else нужно использовать оператор инициализации. Обычно применяется для инициализации переменных, которые далее используются в условной конструкции.  ![[Pasted image 20230108114336.png]]
___
[[Code]]:
```
1. Область видимости условных выражений
func main() {
	const x int64 = 1

	if x == 1 {
		new := 1 // new only inside this {}
	} else {
		new := "2" // new only inside this {}
	}

	fmt.Println("New var is", new) // error
}

2. Инициализация в условном выражении
func main() {
	strPrice = "100"

	if price, err := strconv.Atoi(strPrice); err == nil {
		fmt.Println("Price:", price)
	} else {
		fmt.Println("Error:", err)
	}
}

```
___
Language: [[GoLang]] [[Undone]]
Key-words: [[Поток управления GoLang]] [[Область видимости GoLang]]
Question query?: 