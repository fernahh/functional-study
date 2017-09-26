# Introdução

- Uma função é um mapeamento de um item de um conjunto à um item de outro conjunto.
- A entrada é chamado de domínio, e segundo conjunto é chamdo de co-domínio (como tudo na matemática).
  - Nem sempre um item em um co-domínio, vai ter um correspondente. (ex: função de dobro)
- Imagem é o termo pra dizer todos os itens que estão em co-domínio mas não estão no domínio.

## Lambda Calculus

- A máquina de Turing é bem procedural, ou seja, **como fazer**.
- Alonzo Church (criador do Lambda calculus), ele via que conduzia vários hábitos da computação de maneira simples.
- Só existem 4 termos em expressão lambdas:
  - Identificador de lambda
  - Head (binding de uma variável)
  - Separador `.`, que separa o *body* de uma expressão lambda;
  - Body (pode ser outra expressão lambda)
- Se eu fizer `λxy`, estou aplicando `y` a `x`.
- `λx.x` é igual a `λy.y`, ou seja, uma equivalência.
- Em lambdas calculus, tudo é representado com funções lambdas.
- Uma “free variable”, é uma função que não está no head.
- Uma variável que está no head, é chamada cordinator.
- Se eu escrever uma função com mais argumentos, preciso escrever uma função dentro de outra. `λ Yx.Yy`. Ou seja, todas as função são curryed.

## Sobre programação funcional

- Programação funcional nada mais é do que programar uma função no sentido matemático.
- A maioria das função que programamos, não são funcionais porque a função não opera em todos os tipos.
- Tudo que você pode representar com tipos, pode ser representados com tipos. Ex: tudo que é um tipo inteiro, faz parte do conjunto de inteiros.
- Para uma função ser matemática, ela precisa ser total.
- Função parciais são as que não cobrem todos os itens do conjunto domínio.

> Por que eu vou codar em um ambiente mais restritivo (funções matemáticas)?

O maior ganho é o ferramental que você vai ganhar.

```javascript
const even = (x) => {
  let result

  if (x % 2 === 0) // esse if não gera nenhum valor
    result = true
  else
    result false

  return result
}
```

O `if`, dentro de algumas linguagens funcionais, é uma função, porque não existe *statements*. Não existe atribuição em linguagens funcionais. O próprio `if` retorna um valor.

```haskell
even x = if y % 2 == 0 -- return a value
  then true -- return a value
  else false -- return a value
```

Quando as pessoas falam que Haskell é fortemente tipado, todo mundo acha que precisa anotar o tipo, mas você quase nunca vai fazer isso. Isso acontece porque você não pode chamar nenhum operador sobre um item se você não sabe o tipo dele. Notações de tipo são usadas basicamente pra **documentação**.

```haskell
let sum x y = x + y
-- :t sum
-- sum :: Num a => a -> a -> a
-- sum has type of a function a, that return a
```

Documentada (com tipos):

```haskell
let sum :: Int -> Int -> Int; let sum x y = x + y
```
