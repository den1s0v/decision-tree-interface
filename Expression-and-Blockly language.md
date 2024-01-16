# Комментарии к языку выражений для узлов дерева решений

Источник: ТЗ бакалаврской работы "_Компиляция логических формул в правила Jena Rules_".



## Перечень литералов языка
Компилируемый язык оперирует следующими типами данных:

|Вид|Название|Описание|
|:----:|----|----|
|![image](https://github.com/den1s0v/decision-tree-interface/assets/42928670/852af515-8d68-4fa4-b979-ad769c5369d8)|Object|объект – индивид в RDF|
|![image](https://github.com/den1s0v/decision-tree-interface/assets/42928670/8a9b5a27-c50f-439b-a38e-40a82a9aeb7a)|Class|класс в RDF|
|![image](https://github.com/den1s0v/decision-tree-interface/assets/42928670/439363d5-5757-42ad-bcc7-e01570f81dfe)|Property|свойство – связь между индивидом и литералом в RDF|
|![image](https://github.com/den1s0v/decision-tree-interface/assets/42928670/fd3f8f23-eba2-4976-90f3-67d28c2d51c7)|Relationship|отношение – связь между индивидами в RDF|
|![image](https://github.com/den1s0v/decision-tree-interface/assets/42928670/ff84783e-649c-4ba7-9123-63cc6188d75d)|String|строка|
|![image](https://github.com/den1s0v/decision-tree-interface/assets/42928670/55bddd62-e70d-4445-baf3-111d0a09482b)|Boolean|булево значение|
|![image](https://github.com/den1s0v/decision-tree-interface/assets/42928670/2be484ce-2116-4b80-af76-2d84ab0c5cab)|Integer|целое число|
|![image](https://github.com/den1s0v/decision-tree-interface/assets/42928670/64a8ce1c-1d37-45f4-a7e7-8dbc8e069c7e)|Double|дробное число|
|![image](https://github.com/den1s0v/decision-tree-interface/assets/42928670/6320fe3c-cb87-45ff-81e6-20ea8f0b678a)|Enum|перечисление (enum) — `owner::value`|
|![image](https://github.com/den1s0v/decision-tree-interface/assets/42928670/e58a5cb3-5ab4-4c5e-8efb-a6aa29dac46a)|Decision tree var|переменная из дерева рассуждения (модели предметной области) — `var:X`|
|![image](https://github.com/den1s0v/decision-tree-interface/assets/42928670/7e9e2588-e447-44e1-97a5-d24afd73df10)| — | локальная переменная выражения (рекомендация:  писать в нижнем регистре) — `$x`|


# Существенные замечания


### _Find extreme_

Задача: найти оператор **Y**, ближайший слева к **A**. Смысл "ближайшести" в том, что между **Y** и **A** не должно быть ни одного другого такого **Y**.

![изображение](https://github.com/den1s0v/decision-tree-interface/assets/42928670/70f4b554-aa29-4c9f-a05f-c9e51b6993f4)  
Например:  
``` 
findExtreme Y_ex [ 
  not exist Z [ true ] { Z->isBetween(Y_ex, A) }   # extreme condition
]  
where Y {
 Y is operator and Y.state == state::unevaluated and Y->leftOf(A)   # general condition
}
```

1) Сначала выполняется **_general condition_**, чтобы найти все возможные **`Y`**. 
2) Затем проверяется условие **_extreme condition_** с целевым экстремальным **`Y_ex`** (одним из объектов, вычисленных на предыдущем этапе) — это условие должно быть истинным только для одного объекта из множества.

В результате должен остаться один **`Y`**, ведь переменные дерева никогда не могут содержать множества, — только конкретные объекты/экземпляры.


---------

# Архив (неактуальное)

### _Get relationship object_ имело устаревшие поля (слоты), которые были удалены
![изображение](https://github.com/den1s0v/decision-tree-interface/assets/42928670/769c01c2-8c53-4996-bc04-2f4ceb2218ef)  
Переменная не используется, а  
условие _boolean_ (которое предназначалось для выбора одного объекта из нескольких возможных) нужно всегда устанавливать в **true**.

