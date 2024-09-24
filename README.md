# Resolução MyFunctions2

## Funções próprias do Haskell que foram utilizadas:
| Função         | Descrição                                                                                   |
|----------------|---------------------------------------------------------------------------------------------|
| `map`          | Aplica uma função a cada elemento de uma lista, retornando uma nova lista com os resultados.|
| `filter`       | Retorna uma nova lista contendo apenas os elementos que satisfazem uma condição específica. |
| `length`       | Retorna o número de elementos em uma lista.                                               |
| `elem`         | Verifica se um elemento pertence a uma lista, retornando `True` ou `False`.               |
| `(^)`          | Potência.                                             |

<br>

##  Resolução
#### 1. Crie uma função `itemize :: [String] -> [String]` que receba uma lista de nomes e aplique a função `htmlItem` em cada nome.

  ```haskell
itemize :: [String] -> [String]
itemize = map htmlItem
```
A implementação da função `itemize` foi a mais tranquila, pois utilizei apenas as funções prontas do haskell para implementar.<br><br>

#### 2. Crie uma função `onlyVowels :: String -> String` que receba uma string e retorne outra contendo somente suas vogais. Por exemplo: `onlyVowels "abracadabra"` vai retornar `"aaaaa"`.

```haskell
  onlyVowels :: String -> String
  onlyVowels = filter (`elem` "aeiouAEIOU")

```

Na função `onlyVowels` usei **filter** para filtrar apenas as vogais e **elem** para verificar se existe as vogais dentro da string.<br><br>

#### 3. Escreva uma função `onlyElderly :: [Int] -> [Int]` que, dada uma lista de idades, selecione somente as que forem maiores que 65 anos.

```haskell
onlyElderly :: [Int] -> [Int]
onlyElderly = filter (> 65)
```

Na função `onlyElderly` usei **filter** para filtrar apenas os números maiores que 65.<br><br>

#### 4. Crie uma função `onlyLongWords :: [String] -> [String]` que receba uma lista de strings e retorne somente as strings longas. Você deverá usar a função `isLongWord` definida no código de exemplo no início da prática (copie-a para cá).

```haskell
isLongWord :: String -> Bool
isLongWord word = length word > 10

onlyLongWords :: [String] -> [String]
onlyLongWords = filter isLongWord
```

A função `onlyLongWords` começou a ser mais díficil, tive que criar a condição **isLongWord** usando **lenght** (que retorna o tamanho da string).  Depois usei a condição criada no **filter** da função `OnlyLongWords`. <br><br>

#### 5. Escreva uma função `onlyEven` que receba uma lista de números inteiros e retorne somente aqueles que forem pares. Você deverá usar a função `isEven` definida no código de exemplo no início da prática (copie-a para cá). Agora é com você a definição da tipagem da função!

```haskell
isEven :: Int -> Bool
isEven n = if mod n 2 == 0 then True else False

onlyEven :: [Int] -> [Int]
onlyEven = filter isEven
```

A função `onlyEven` segue a lógica igual da anterior, porém foi mais tranquila pois já existia a função **isEven**.<br><br>

#### 6. Escreva uma função `onlyBetween60and80` que receba uma lista de números e retorne somente os que estiverem entre 60 e 80, inclusive. Você deverá criar uma função auxiliar `between60and80` e usar `&&` para expressar o operador "E" lógico em Haskell.

```haskell
between60and80 :: Int -> Bool
between60and80 x = x >= 60 && x <= 80

onlyBetween60and80 :: [Int] -> [Int]
onlyBetween60and80 = filter between60and80
```

A função onlyBetween60and80 também segue a lógica igual às anteriores, sendo criada uma condição between60and80 para depois ser usada no filter para manter apenas números entre 60 e 80.<br><br>

#### 7. Crie uma função `countSpaces` que receba uma string e retorne o número de espaços nela contidos. Dica 1: você vai precisar de uma função que identifica espaços. Dica 2: aplique funções consecutivamente, isto é, use o resultado de uma função como argumento para outra. 

```haskell
countSpaces :: String -> Int
countSpaces = length . filter (== ' ')
```
A função `countSpaces` foi a que mais tive dificuldade, utilizei **lenght** e **filter** e entender como funcionava (e saber que tinha como) usar duas funções do haskell ao mesmo tempo foi a dificuldade para realizar a função. <br><br>

#### 8. Escreva uma função `calcAreas` que, dada uma lista de valores de raios de círculos, retorne uma lista com a área correspondente a cada raio.

```haskell
calcArea :: Float -> Float
calcArea r = pi * r^2

calcAreas :: [Float] -> [Float]
calcAreas = map calcArea

```
Na função `calcAreas` primeiro fiz o cálculo para descobrir a área de cada círculo, depois usei **map** para aplicar o cálculo em cada elemento da lista.<br><br>

## Conclusão

A maior dificuldade para criar as funções foi se adaptar à sintaxe e à lógica do Haskell. Entender como funcionavam as funções próprias da linguagem também foi um desafio, assim como não estar familiarizado com o uso de listas.
