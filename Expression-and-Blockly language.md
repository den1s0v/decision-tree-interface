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
|![image](https://github.com/den1s0v/decision-tree-interface/assets/42928670/6320fe3c-cb87-45ff-81e6-20ea8f0b678a)|Enum|перечисление (enum)|
|![image](https://github.com/den1s0v/decision-tree-interface/assets/42928670/e58a5cb3-5ab4-4c5e-8efb-a6aa29dac46a)|Decision tree var|переменная из дерева рассуждения (модели предметной области)|
|![image](https://github.com/den1s0v/decision-tree-interface/assets/42928670/7e9e2588-e447-44e1-97a5-d24afd73df10)| — | [внутренняя] переменная выражения (рекомендация:  писать в нижнем регистре) |

