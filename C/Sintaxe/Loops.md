# Estruturas de repetição

Autoexplicativas: te permitem executar uma sequência de comandos várias vezes. 
Existem vários tipos de estrutura de repetição, e cada uma delas apresenta algumas variações no comportamento, mas todas tem uma característica em comum: fazem uma mesma coisa várias vezes.


## while

A estrutura de repetição mais básica. 
O while recebe entre parênteses uma [[Operadores#Operadores lógicos|condição]] e executa seu bloco de código **enquanto** essa condição for verdadeira. 

```C
while(1 == 1) {
	printf("oi\n");
}
```

Como 1 sempre será igual a 1, esse loop continuará executando infinitamente, escrevendo oi na tela. 
É chamado de *loop infinito*, e normalmente são criados por acidente.

> Para encerrar um programa de terminal forçadamente, use `ctrl`+`C`.

Loops infinitos não são muito úteis. 

```C
int numero_secreto = 20;
int numero;

while(numero != numero_secreto) {
	printf("Digite a senha:  ");
	scanf("%d", &numero);
}

printf("Parabéns, você acertou a senha!");
```

O programa acima requisitará um número, e, enquanto o usuário não acertar o número esperado, continuará requisitando, repetidamente. 
O loop termina no momento em que a condição se torna falsa, ou seja, nesse caso, quando o usuário digitar `20`.

E se quiséssemos contar quantas vezes o usuário errou a senha?

```c
int numero_secreto = 20;
int tentativas = 0;
int numero;

while(numero != numero_secreto) {
	tentativas = tentativas + 1;
	printf("Tentativa %d\n\n", tentativas);
	
	printf("Digite a senha:  ");
	scanf("%d", &numero);
}

printf("Parabéns, você acertou a senha!");
```

Resultado:
```
Tentativa 1
Digite a senha: 12

Tentativa 2
Digite a senha: 15

Tentativa 3
Digite a senha: 8

Tentativa 4
Digite a senha: 20

Parabéns, você acertou a senha!
```


Mas e se quiséssmos limitar o programa a somente três tentativas, por exemplo?

```C
int numero_secreto = 20;
int tentativas = 0;
int numero;

while((numero != numero_secreto) || (tentativas >= 3)) {
	tentativas = tentativas + 1;
	printf("Tentativa %d\n\n", tentativas);
	
	printf("Digite a senha:  ");
	scanf("%d", &numero);
}

if (tentativas > 3) {
	printf("Erro. Sistema bloqueado.");
} else {
	printf("Parabéns, você acertou a senha!");
}
```

Resultado:
```
Tentativa 1
Digite a senha: 12

Tentativa 2
Digite a senha: 15

Tentativa 3
Digite a senha: 8

Erro. Sistema bloqueado.
```

Nesse caso, a condição no while foi alterada. Agora, assim que o usuário exceder três tentativas, o loop será encerrado.


### Variável de controle

Um caso muito comum com estruturas de repetição é necessidade de realizar uma determinada tarefa uma certa quantidade de vezes. Isso pode ser feito com o auxílio de uma variável de controle. 

```C
int i = 0;  // Este é o controle. 
			// Pode receber qualquer nome, mas normalmente, i

while(i < 5) {
	printf("loop!\n");
	i++;
}
```

Resultado:
```
loop!
loop!
loop!
loop!
loop!
```

Exatamente cinco vezes.


#### Loops variáveis

Uma variável do usuário pode ser usada para determinar a quantidade de execuções de um loop. 

```C
int i = 0;
int quantidade_oi;

printf("Quantas vezes você quer receber oi?  ");
scanf("%d", &quantidade_oi);

while(i < quantidade_oi) {
	printf("Oi!\n");
}
```

Resultado:
```
Quantas vezes você quer receber oi?  4
Oi!
Oi!
Oi!
Oi!
```

> Note que, caso o usuário digite 0 ou um número negativo, ele não receberá nenhum oi.



## do while
Essa estrutura de controle é utilizada para garantir pelo menos uma repetição do escopo.

```C
do {
	printf("do while!\n");
} while (5 > 8);

while (5 > 8) {
	printf("while!\n");
}
```

Resultado:
```
do while!
```

A expressão `5 > 8` é falsa, portanto o `while` não é executado. O `do while`, por sua vez, sempre executa ao menos uma vez, e escreveu na tela. Entretanto, não continuou repetindo.

```c
int qntOi;

printf("Quantas vezes você quer dizer oi?  ");
scanf("%d", &qntOi);

do {
	printf("\n%d - Oi!", qntOi);
	qntOi--;
} while (qntOi > 0);
```

Resultado:
```
Quantas vezes você quer dizer oi?  4

4 - Oi!
3 = Oi!
2 - Oi!
1 - Oi!
```

Funciona como se esperaria de um `while`, executou o escopo até que a variável `qntOi` deixasse de ser maior que 0.

Entretanto, no caso de inserirmos um número menor ou igual a zero:

Resultado:
```
Quantas vezes você quer dizer oi? -2

-2 - Oi!
```

Independentemente do número inserido, o bloco `do while` sempre irá executar uma vez. 

> `do while` executa uma ou mais vezes
> `while` executa zero ou mais vezes


## for loop
O loop mais importante e o mais utilizado. Usa de sintaxe especial para trabalhar com o conceito de [[#Variável de controle|variável de controle]].
Te permite executar o escopo uma quantidade definida de vezes.

```c
for (int i = 0; i < 5; i++) {
	printf("Oi número %d\n", i);
}
```

Resultado:
```
Oi número 1
Oi número 2
Oi número 3
Oi número 4
Oi número 5
```


### A sintaxe do for loop
O parênteses da estrutura `for` possui três campos que facilitam o uso de uma variável de controle para executar o loop uma quantidade definida de vezes.

É o mesmo que usar uma variável de controle em um [[#while|while]] ou [[#do while]], porém mais conciso.

Os campos são:
- Atribuição
	- Define a variável de controle para o loop
- Condição
	- Condição de execução do loop, semelhante ao while
- Operação
	- Uma operação que deverá ser executada no final de cada loop, como aumentar 1 na variável de controle.

#### Atribuição
A primeira parte do `for`.
```C 
for (int i = 0; i < 5; i++) {
//   ^ essa parte
}
```

Serve para definir a variável de controle e atribuir um valor a ela.
Pode ser usada, por exemplo, nos seguintes casos:
- Definir uma variável
- Definir um novo valor para uma variável anterior
- Definir um valor inicial diferente para o loop
	- Ex.: Começar o loop em 2, ir de 5 até 0

```C
int i;

for (i = 0; i < 2; i++) {
	printf("Primeiro loop!\n");
}

for (i = 2; i < 4; i++) {
	printf("Segundo loop!\n");
}

for (; i < 6; i++) { // A atribuição não é necessária. Note o ;
	printf("Terceiro loop!\n");
}
```

Resultado:
```
Primeiro loop!
Primeiro loop!
Segundo loop!
Segundo loop!
Terceiro loop!
Terceiro loop!
```

A variável de controle `i` foi declarada no começo, definida como 0 no primeiro loop, que executou duas vezes.

No segundo loop, a variável foi definida para 2, e incrementada até 4, quando o loop parou. De 2 até 4, executou duas vezes.

Para o terceiro loop, o valor de `i` não foi redefinido, portanto *ainda é* 4. Foi incrementada duas vezes, até 6, e executou duas vezes.


#### Condição
Condição normal do loop. Como é um loop `for`, quase sempre envolve a variável de controle. 

> A condição aceita qualquer tipo de [[Operadores#Operadores lógicos|operador lógico]], inclusive condições complexas com `&&` e `||`, que podem ser úteis em certos casos.

```C
// Crie a variável i e atribua o valor 0 a ela
// Enquanto i for menor que 6, execute o seguinte bloco
// Ao final de cada execução do bloco, some 1 a i
for (int i = 0; i < 6; i++) {
	printf("%d ", i);
}
```

Resultado:
```
0 1 2 3 4 5
```

> Perceba que o loop executa 6 vezes, entre 0 e 5. O loop não executa em 6 pois 6 **não é** menor que 6.


#### Operação
Ao final de cada loop, execute alguma operação, quase sempre envolvendo a variável de controle.

```C
int i = 0; // Atribuição

while (i < 6) { // Condição
	printf("%d ", i);
	
	i++; // Operação
}
```

```C
for (int i = 0; i < 6; i++) {
	printf("%d ", i);
}
```

Resultado (igual para ambos):
```
0 1 2 3 4 5
```

Ambos os loops são equivalentes, mas o `for` lida com todas as operações envolvendo a variável de controle `i`.

> Um `for loop` é somente uma forma mais concisa de fazer um loop com uma variável de controle.

A parte de operação do loop `for` permite fazer mais que somente somar um.

```C
for (int i = 6; i > 0; i--) { // Note o maior que
	printf("%d ", i);
}
```

Resultado:
```
6 5 4 3 2 1
```



### Exemplos
O `for` é o loop mais usado na maioria das linguagens de programação.


- Mostrar o último número e começar em 1
> A maioria dos programadores iniciantes desgosta dos loops começados em 0, pois são contraintuitivos. Loops mais legíveis podem ser feitos com o `for`.

```C
// 6 não é menor que 6, mas é menor *ou* igual a 6
for (int i = 1; i <= 6; i++) {
	printf("%d ", i);
}
```

Uma outra prática comum é somar 1 em `i` dentro do `printf`. O valor real de `i` não muda, mas a visualização é melhor.

```C
for (int i = 0; i < 6; i++) {
	printf("%d ", i+1);
}
```

Resultado (para ambos):
```
1 2 3 4 5 6
```



- Escrever na tela todos os números pares até 20:

```C
for (int i = 0; i <= 20; i+=2) {
	printf("%d ", i);
}
```

Resultado:
```
0 2 4 6 8 10 12 14 16 18 20
```

> Note que somamos 2 a `i` em cada execução do loop, até 20, incluindo 20 por causa do `<=`.


- Quebrar o loop no primeiro múltiplo de 9 (excluindo 9):

```C
// Faça o loop enquanto i não for um múltiplo de 9 ou for 9
for (int i = 1; (i % 9 != 0) || i == 9; i++) {
	printf("%d ", i);
}
```

Resultado:
```
1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17
```

- `for` com quantidade de execuções variável

```C
int qntExec;

printf("Quantas vezes você quer executar o loop?  ");
scanf("%d", &qntExec);

for (int i = 0; i < qntExec; i++) {
	printf("\nExecução %d!", i+1);
}
```

Resultado:
```
Quantas vezes você quer executar o loop?  4

Execução 1!
Execução 2!
Execução 3!
Execução 4!
```

---

## Quando usar cada loop?

- O `while` deve ser usado quando você não sabe quantas vezes algo vai se repetir.
- `do while` deve ser usado quando você não sabe quantas vezes algo vai se repetir, mas deve acontecer ao menos uma vez.
- `for` deve ser usado para repetir uma ação por uma quantidade definida de vezes.

O `for` é o loop mais comum, especialmente quando se trabalha com listas de itens, mais conhecidas como [[Vetores|vetores]].