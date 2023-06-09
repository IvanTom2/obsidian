___
Срезы позволяют хранить переменное количество значений. Срез это структура данных, которая содержит три значения: указатель на массив, длину среза и емкость среза. Длина среза - это количество элементов, которое он может хранить. Емкость среза - это количество элементов, которые могут быть сохранены в массиве. 

Массив расширяется с помощью функции append. Она создает массив, достаточно большой для размещения новых элементов, копирует существующий массив и добавляет новые значения. 

Создание срезов может быть неэффективным. Поэтому при создании среза можно закладывать дополнительную емкость. Т.е. задать длину среза 3 и емкость 6 - таким образом будет создан массив на 6 элементов, 3 из которых будут пустыми и иметь пространство для расширения без пересоздания. 

Срез является указателем на массив. Если был создан достаточно большой массив (емкость среза велика), то при вызове append он не будет пересоздан. Таким образом, могут получиться ситуации:
1. Был создан срез с маленькой емкостью. Новый срез был создан через расширение старого через append, вследствие чего был создан новый массив, т.к. в него не влезали элементы. Сейчас первый и второй срез указывают на разные массивы. Соответственно, если изменить значения у срезов, изменятся разные массивы и изменения одного не будут касаться другого.
2. Был создан срез с большой емкостью. Новый срез был создан через расширение старого через append, но емкости массива хватило для того, чтобы добавить новые элементы. Теперь оба среза указывают на одинаковый массив. Изменение одного среза приведет к изменениям другого. 
___
[[Code]]:
```
names := make([]string, 3) // срез начальной длинны 3
var names1 = []string {"A", "B", "C"}

names1 = append(names1, "D", "E")


```
___
Language: [[GoLang]]
Key-words:  [[Встроенные типы коллекций GoLang]]
Question query?: Как создать срез в GoLang