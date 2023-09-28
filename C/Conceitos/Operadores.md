# Operadores
Um *operador* é um caractere especial que desempenha algum papel transformando informações.

---

## Operadores matemáticos

| Operador | Operação      |
|:--------:| ------------- |
|   `+`    | soma          |
|   `-`    | subtração     |
|   `*`    | multiplicação |
|   `/`    | divisão       |
|   `%`    | resto da div. |

Os operadores mais comuns são os operadores matemáticos, que realizam alguma das quatro operações entre dois valores.

**Exemplo:**
```C
int x = 4;
int y = 8;
int xy;
int z;

xy = x * y;
z = xy + x;
```

### `-` (menos)
Esse operador desempenha dois papéis distintos na maioria das linguagens de operação: subtrair dois valores e inverter o sinal de um número.

```C
int pos = 5;
int neg = -pos;      // -5
int num = pos - neg; // 10
```

---

## Operadores lógicos

Operadores lógicos são utilizados para criar *condições*, e são capazes de avaliar e comparar diferentes informações ou variáveis. Sempre vão resultar em "verdadeiro" ou "falso".

| Operador | Operação         |
|:--------:| ---------------- |
|   `>`    | Maior que        |
|   `<`    | Menor que        |
|   `<=`   | Menor ou igual a |
|   `>=`   | Maior ou igual a |
|   `==`   | Igual a          |
|   `!=`   | Diferente de     |

**Exemplos:**
|      Expressão       | Resultado  |
|:--------------------:|:----------:|
|       `5 < 6`        | Verdadeiro |
|       `5 < 5`        |   Falso    |
|       `9 > 9`        |   Falso    |
|      `10 >= 10`      | Verdadeiro |
|     `'a' != 'a'`     |   Falso    |

> Na linguagem C, um único símbolo de igual, como `=`, é usado para dar um valor a uma variável. Dois, como em `==`, representam o operador lógico de igualdade.


### Lógica composta

| Operador | Operação |
|:--------:|:--------:|
|   `&&`   | and (e)  |
| `&pipe`  | or (ou)  |
|   `!`    |   not    |

Esses operadores são usados para criar condições envolvendo vários operadores lógicos.

#### `||` (ou)

```C
int nivel = 50;
int nivel_minimo = 20;
int nivel_maximo = 45;

if ((nivel > nivel_maximo) || (nivel < nivel_minimo)) {
	printf("Alerta!");
}
// O alerta será emitido.
```

Neste programa, se o nível estiver abaixo de 20 **ou** acima de 45, um alerta é emitido.

> Para esse operador, somente uma das condições precisa ser verdadeira.


#### `&&` (e)

```c
int nivel = 50;
int nivel_minimo = 20;
int nivel_maximo = 45;

float risco = 1.4;

if ((nivel > nivel_maximo) && (risco > 2)) {
	printf("Alerta máximo!");
}
// O alerta não será emitido
```

Nesse exemplo, o alerta só será emitido no caso do nível exceder o nível máximo **e** o risco estiver acima de 1. 
Portanto, mesmo que o nível suba para muito além do nível máximo, desde que o risco esteja baixo, o alerta não será emitido.

> Para este operador, **ambas** as condições precisam ser verdadeiras.


#### "e" ou "ou"?
Trocar os operadores `&&` e `||` é  erro muito comum na programação, e que certamente vai acontecer com você.

Se somente um dos dois casos precisar ser verdadeiro, é um "ou".
Se ambos os casos precisarem ser verdadeiros, é um "e".

---

## Operadores binários

você não precisa de operadores binários, confia em mim.