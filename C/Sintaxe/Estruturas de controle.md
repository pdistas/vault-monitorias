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

