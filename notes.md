# Introdução

- Uma função é um mapeamento de um item de um conjunto à um item de outro conjunto.
- A entrada é chamado de domínio, e segundo conjunto é chamado de co-domínio (como tudo na matemática).
  - Nem sempre um item em um co-domínio, vai ter um correspondente. (ex: função de dobro)
- Imagem é o termo pra dizer todos os itens do co-domínio que têm um correspondente no domínio.

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
- Se eu escrever uma função com mais argumentos, preciso escrever uma função dentro de outra. `λx.λy.xy`. Ou seja, todas as função são curried.

## Sobre programação funcional

- Programação funcional nada mais é do que programar uma função no sentido matemático.
- A maioria das função que programamos em linguagens imperativas não são funcionais
porque a função não opera em todos os habitantes de um tipo (conjunto).
- Tipos são conjuntos; Um número 1 é um habitante do tipo Inteiro.
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

O `if`, dentro de algumas linguagens funcionais, é uma função, porque não existe *statements*. Não existe atribuição em linguagens funcionais. *Statements* como o `if` em linguagens funcionais
normalmente são expressões como quaiquer outras.

```haskell
even x =
  if y % 2 == 0 -- return a value
    then true
    else false
```

Quando as pessoas falam que Haskell é fortemente tipado, todo mundo acha que precisa anotar o tipo, mas você quase nunca vai fazer isso. Isso acontece porque você não pode chamar nenhum operador sobre um item se você não sabe o tipo dele. Notações de tipo são usadas basicamente pra **documentação**.

```haskell
sum x y = x + y
-- :t sum
-- sum :: Num a => a -> a -> a
-- sum has type of a function a, that return a
```

Documentada (com tipos):

```haskell
sum :: Int -> Int -> Int
sum x y = x + y
```
