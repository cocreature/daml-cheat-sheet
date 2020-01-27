|                      |                                                       |
| -------------------- | ----------------------------------------------------- |
| Record | `data Record = Record { label1 : Int, label2 : Text}` |
| Product type | `data Product = Product Int Text` |
| Sum type | `data IntOrText = MyInt Int | MyText Text` |
| Data with type parameters | `data Record a b = Record {label1 : a, label2 : b}` |
| Deriving Show/Eq instances | `data Record = Record {label : Int} deriving (Show, Eq)` |
