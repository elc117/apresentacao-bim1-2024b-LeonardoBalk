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
itemize list = map htmlItem list
```
A implementação da função `itemize` foi a mais tranquila.
A função recebe uma lista de strings e aplica a função `htmlItem` em cada uma delas.
Usei a função `map`, que percorre a lista e aplica `htmlItem` em cada elemento, retornando uma nova lista com os itens html.<br><br>

#### 2. Crie uma função `onlyVowels :: String -> String` que receba uma string e retorne outra contendo somente suas vogais. Por exemplo: `onlyVowels "abracadabra"` vai retornar `"aaaaa"`.

```haskell
onlyVowels :: String -> String
onlyVowels = filter (`elem` "aeiouAEIOU")
```

A função `onlyVowels` recebe uma string e filtra só as vogais.
Usei `filter`, que percorrer a string e mantem só os caracteres que são vogais.
Pra isso, o operador `elem` verifica se o caractere está entre "aeiouAEIOU" (tanto maiúsculas, quanto minúsculas).<br><br>
*Função feita com auxílio do ChatGPT*

#### 3. Escreva uma função `onlyElderly :: [Int] -> [Int]` que, dada uma lista de idades, selecione somente as que forem maiores que 65 anos.

```haskell
onlyElderly :: [Int] -> [Int]
onlyElderly ages = filter (> 65) ages
```

 A função `onlyElderly` recebe uma lista de idades e retorna uma lista só com as idades acima de 65.
 Novamente, usei `filter`, que percorre a lista e mantém só os números maiores que 65.<br><br>

#### 4. Crie uma função `onlyLongWords :: [String] -> [String]` que receba uma lista de strings e retorne somente as strings longas. Você deverá usar a função `isLongWord` definida no código de exemplo no início da prática (copie-a para cá).

```haskell
isLongWord :: String -> Bool
isLongWord word = if length word > 10 then True else False

onlyLongWords :: [String] -> [String]
onlyLongWords list = filter isLongWord list
```

A função `onlyLongWords` começou a ser mais díficil, nela eu criei uma função que filtra palavras longas (com mais de 10 letras).
Primeiro, defini a função `isLongWord`, que verifica se o comprimento de uma palavra é maior que 10.
Depois, usei `filter` pra aplicar essa função em cada elemento da lista de strings. <br><br>
*Função feita com auxílio do ChatGPT*

#### 5. Escreva uma função `onlyEven` que receba uma lista de números inteiros e retorne somente aqueles que forem pares. Você deverá usar a função `isEven` definida no código de exemplo no início da prática (copie-a para cá). Agora é com você a definição da tipagem da função!

```haskell
isEven :: Int -> Bool
isEven n = if mod n 2 == 0 then True else False

onlyEven :: [Int] -> [Int]
onlyEven list = filter isEven list
```

A função `onlyEven` segue uma lógica parecida e filtra os números pares de uma lista.
A função auxiliar `isEven` verifica se o número é par.
O `filter` usa essa condição para filtrar os pares.<br><br>

#### 6. Escreva uma função `onlyBetween60and80` que receba uma lista de números e retorne somente os que estiverem entre 60 e 80, inclusive. Você deverá criar uma função auxiliar `between60and80` e usar `&&` para expressar o operador "E" lógico em Haskell.

```haskell
between60and80 :: Int -> Bool
between60and80 x = if x >= 60 && x <= 80 then True else False

onlyBetween60and80 :: [Int] -> [Int]
onlyBetween60and80 list = filter between60and80 list
```

A função onlyBetween60and80 também segue a lógica igual às anteriores, sendo criada uma condição between60and80a para filtrar números que estão entre 60 e 80.
Criei uma função `between60and80` que retorna verdadeiro se o número estiver nesse intervalo.
Em seguida, o `filter` usa essa condição para filtrar os números entre 60 e 80.<br><br>

#### 7. Crie uma função `countSpaces` que receba uma string e retorne o número de espaços nela contidos. Dica 1: você vai precisar de uma função que identifica espaços. Dica 2: aplique funções consecutivamente, isto é, use o resultado de uma função como argumento para outra. 

```haskell
countSpaces :: String -> Int
countSpaces = length . filter (== ' ')
```
A função `countSpaces` foi a que mais tive dificuldade, a função conta quantos espaços existem numa string.
Usei `filter` pra pegar só os espaços, e depois `length` pra contar quantos existem. <br><br>
*Função feita com auxílio do ChatGPT*

#### 8. Escreva uma função `calcAreas` que, dada uma lista de valores de raios de círculos, retorne uma lista com a área correspondente a cada raio.

```haskell
calcArea :: Float -> Float
calcArea r = pi * r^2

calcAreas :: [Float] -> [Float]
calcAreas list = map calcArea list

```
A função `calcAreas` calcula a área de vários círculos dado uma lista de raios.
Criei a função `calcArea` que calcula a área de um círculo (pi * raio^2).
Depois, apliquei essa função em cada raio da lista usando `map`, pra retornar uma lista com as áreas.br><br>

## Conclusão

A maior dificuldade para criar as funções foi se adaptar à sintaxe e à lógica do Haskell. Entender como funcionavam as funções próprias da linguagem também foi um desafio, assim como não estar familiarizado com o uso de listas.

## Fontes

https://haskell.tailorfontela.com.br/starting-out
ChatGPT
