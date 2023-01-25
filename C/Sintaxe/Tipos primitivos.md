A linguagem C contém alguns *tipos primitivos*, que permitem ao programador armazenar informações de diversos tipos, como caracteres, números inteiros e racionais e matrizes. 

## Tipos primitivos

### Principais

| Tipo    | Descrição                  | Placeholder |
| ------- |:-------------------------- |:-----------:|
| `int`   | Armazena números inteiros  |    `%d`     |
| `float` | Armazena números racionais |    `%f`     |
| `char`  | Armazena caracteres        |    `%c`     |

> O tipo `float` é frequentemente chamado de "ponto flutuante".

### Outros

Além dos tipos primitivos principais, alguns outros são mais específicos e úteis para certas aplicações. 

#### `short`
- Armazena números inteiros
- Possui metade do tamanho do int 
- Placeholder: `%hd`

#### `long`
- Armazena números inteiros
- Maior que um int
- Placeholder: `%ld`

#### `double`
- Armazena números racionais
- Maior que um float
- Chamado de "ponto flutuante de dupla precisão"
- Placeholder: `%lf`

---

## Modificadores
Modificadores são palavras reservadas que podem ser inseridas antes da definição de um tipo para modificá-lo.

### Para definição de conjuntos numéricos

#### `unsigned`
Em tipos numéricos inteiros, como `int`, `short` e `long`, esse modificador pode ser usado para criar um tipo que armazena somente números inteiros *positivos*.
**Conjunto:** N (naturais)
```C
int neg = -8;
unsigned int pos = 8;

neg = 8;  // Funciona
pos = -8; // Vai dar erro; 'pos' não pode armazenar números negativos.
```

#### `signed`
Por padrão, os tipos numéricos inteiros tem o modificador `signed`, que indica uma variável capaz de armazenar números inteiros, positivos ou negativos. 
**Conjunto:** Z (inteiros)
```C
signed int num = -10;
int val = -10;
// As duas variáveis são exatamente iguais, "signed" é considerado por padrão.
```


### Para tamanho

#### `long`
Em todos os tipos numéricos, esse modificador pode ser usado para aumentar a amplitude de números que podem ser armazenados por essa variável.

```C
long float renda;
unsigned long int milissegundos;
```

#### `short`
O exato oposto do long; diminui consideravelmente a quantidade de números que podem ser armazenados pela variável. Funciona apenas com o tipo "int".

```C
unsigned short int idade;
short int numero_favorito;
```

#### Trivia

Os tipos primitivos apresentados na sessão [[#Outros|outros]] são atalhos para o uso dos modificadores `long` e `short`.

| Tipo     | Correspondência |
| -------- | --------------- |
| `double` | `long float`    |
| `short`  | `short int`     |
| `long`   | `long int`      |



