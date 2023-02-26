# Conceitos básicos

## Variáveis

JavaScript não possui tipos fortemente tipados, e variáveis podem receber qualquer valor.

Para criar uma variável, use `let`. 
`const` também pode ser usado, e cria uma variável cujo valor não pode ser alterado.

```js
let value = "Hello world"
console.log(value + "!"); // Hello world!

value = 3;
console.log(3 - 2); // 1

const num = 3;
console.log(value == num); // true
```

> A palavra-chave `var` funciona de forma semelhante ao `let`, criando uma variável que pode ser alterada. No entanto, possui problemas de escopo e **não deve** ser usada.


### Tipos primitivos

Por mais que não hajam tipos explícitos e uma variável possa ser modificada para um tipo diferente do original, a linguagem usa de alguns tipos primitivos.

| Tipo        | Informação                                      |
| :---------: | ----------------------------------------------- |
| `number`    | Armazena números racionais                      |
| `string`    | Armazena cadeias de caracteres                  |
| `boolean`   | Armazena um valor lógico (verdadeiro ou falso)  |
| `undefined` | Valor padrão de uma variável ainda não definida |
| `null`      | Valor vazio                                     |

> Note que não há distinção entre inteiros e racionais, como acontece em outras linguagens com `int` e `float`. A primitiva `number` é usada tanto para números inteiros quanto para racionais.
> Também não há um tipo que represente um caractere, somente cadeias.


### Operadores

A linguagem disponibiliza alguns operadores matemáticos que podem ser usados nos tipos primitivos.


#### Operadores aritméticos

São usados com o tipo `number`, e são todos operadores binários, ou seja, que atuam em dois números.

| Operador | Função                    |
|:--------:| ------------------------- |
|   `+`    | Soma                      |
|   `-`    | Subtração                 |
|   `*`    | Multiplicação             |
|   `/`    | Divisão                   |
|   `%`    | Resto da divisão (módulo) |
|   `**`   | Potenciação               |

> O operador `-` pode ser usado de forma unária (ou seja, somente com um valor) para inverter o sinal de um número.

Exemplo:

```js
let x = 4;
let y = 3;

let z = (x + y) * 2; // z == 14

let numero = 2;
numero = numero ** 3; // 2 elevado a três, numero = 8

let numeroNegativo = -8;
let numeroPositivo = -numeroNegativo; // operador - unário inverte o sinal
```


#### Operadores bitwise

São raramente usados, e atuam na representação binária de um número.

| Operador | Função                   |
| -------- | ------------------------ |
| `>>`     | Bitshift para a direita  |
| `<<`     | Bitshift para a esquerda |
| `&&`     | "and" lógico             |
| `ǀǀ`     | "or" lógico              |
| `^`      | "xor" lógico             |

Exemplos:
```js
let x = 4;
x = x << 3; // x = 32
x = x >> 2; // x = 8

let y = 38 | 10; // y = 46
y = y & 1; // y = 0
```

---

## Estruturas de controle

Funcionam de forma semelhante ou idêntica a suas contrapartes em C.

### `if`, `else if` e `if`

Funcionam de forma idêntica.
```js
let val = 4;

if (val > 3) {
	console.log("Maior que três!");
} else if (val == 3) {
	console.log("Igual a três!");
} else {
	console.log("Menor que três!");
}
```

Resultado:
```
Maior que três!
```


### Operadores lógicos

| Operador | Função             |
|:--------:|:------------------ |
|   `==`   | Igual a            |
|   `!=`   | Diferente de       |
|   `>`    | Maior que          |
|   `>=`   | Maior ou igual que |
|   `<`    | Menor que          |
|   `<=`   | Menor ou igual que |

