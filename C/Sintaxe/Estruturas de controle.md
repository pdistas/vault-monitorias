# O que são estruturas de controle?
C é conhecido por ser uma linguagem declarativa, onde o programador usa [[palavras reservadas]] para dizer ao código não só o que deve ser feito, mas quando. 

> Um "escopo" diz respeito ao conteúdo presente dentro de um conjunto de chaves - `{ }` 

Essas estruturas de comando permitem ações como repetição, execução condicional de pedaços do código e declaração de subrotinas.

---
## Estruturas de decisão

Estruturas de decisão te permitem escolher qual código será executado conforme a situação do programa. Por exemplo, o que uma calculadora da fórmula de bháskara deverá fazer caso o delta seja negativo? 

Estruturas de decisão te permitem definir "caminhos" alternativos para seus programas, tomando ações diferentes em situações diferentes.

### if
O `if` é a mais básica e mais importante de todas as estruturas de comando. Você declara ele, e o conteúdo de seu escopo só será executado caso a [[Operadores#Operadores lógicos|condição]] fornecida for verdadeira.

```c
if (1 == 1) {
	printf("Verdadeiro!");
}
```

> *Se x for verdade, faça isso.*

#### else
O `else` é um bloco de código executado caso a condição presente no `if` não seja verdadeira. 
Caso a condição presente no `if` seja verdadeira, o `else` não será executado.

```C
if ('a' != 'a') {
	printf("'a' não é 'a'.\n");
} else {
	printf("'a' é 'a'!\n");
}

if (5 > 2) {
	printf("5 é maior que 2!\n");
} else {
	printf("5 não é maior que 2.\n")
}
```

Resultado:
```
'a' é 'a'!
5 é maior que 2!
```

> *Se x for verdade, faça isso. Senão, faça essa outra coisa.*


#### if else
Múltiplas condições poderão ser checadas encadeando blocos if-else. 
Caso o primeiro if seja falso, o programa segue para o bloco if-else, que, caso verdadeiro, é executado.

Caso o primeiro if seja verdadeiro, o if-else é ignorado.

```C
char[] pet = "gato";

if (pet == "cachorro") {
	printf("auau");
} else if (pet == "gato") {
	printf("miau");
} else if (pet == "girafa") {
	printf("???");
}
```

Resultado:
```
miau
```

> *Se x for verdadeiro, faça isso. Senão, veja se y é verdadeiro, e se for, faça essa outra coisa.*

##### if else else

Um `else` pode ser colocado ao final de uma cadeia de if-else.

```C
char melhor_letra = 'l';
char pior_letra   = 'j';
char letra_quatro = 'e';

char inicial = 'c';

if (inicial == melhor_letra) {
	printf("Ótima inicial!");
} else if (inicial == pior_letra) {
	printf("Inicial horrível!");
} else if (inicial == letra_quatro) {
	printf("Sua inicial é a quarta letra do alfabeto.");
} else {
	printf("Inicial mediana.");
}
```

Resultado:
```
Inicial mediana.
```


### switch case
Sequências muito longas de if-else são visualmente desagradáveis e difíceis de entender. Pegando o exemplo do [[#if else else]], quanto mais letras quisermos testar, mais difícil será de entender o código. 

Sequências longas de if else poluem o código, e para isso, o `switch` é uma alternativa.

O switch permite ao programador comparar uma variável a diversos "casos" diferentes e executar um código específico para aquele que corresponder.

> Não se esqueça de terminar cada "case" com o comando `break`.

```C
char letra = 'b';

switch(letra) {
	case 'a':
		printf("Primeira letra do alfabeto!");
		break;

	case 'b':
		printf("Segunda letra do alfabeto!");
		break;

	default:
		printf("Não reconheço essa letra...");
}
```

Resultado:
```
Segunda letra do alfabeto!
```

O switch pode ser usado para determinar letras, números ou até palavras inteiras. A expressão `default` é opcional, e pode ser colocada ao final do `switch`. Se nenhum dos casos corresponder a variável fornecida, o bloco default será executado.

> Pegue x. Caso x for isso, faça isso. Caso x for isso, faça isso. Se nenhum dos casos corresponder, faça isso.

---

## Estruturas de repetição

Autoexplicativas: te permitem executar uma sequência de comandos várias vezes. 
Existem vários tipos de estrutura de repetição, e cada uma delas apresenta algumas variações no comportamento, mas todas tem uma característica em comum: fazem uma mesma coisa várias vezes.


### while

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


#### Variável de controle

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


##### Loops variáveis

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



### do while
Essa estrutura de controle é utilizada quando o 
