---
title: Sintaxe Básica
permalink: /c/sintaxe/
layout: page
---

# Sobre a linguagem

C é uma linguagem estruturada procedural, o que significa que seus algoritmos são escritos como uma série de instruções, executadas uma a uma, permitindo o uso de estruturas semelhantes a blocos para alterar a ordem.

Um programa em C executa a partir de sua main().
O comando printf() te permite inserir uma mensagem entre aspas para ser mostrada no console.

Não se esqueça de terminar todo comando com `;`, ok?

```c
int main() {
    printf("Hello world!");
}
```

Simples, não?
O programa começa na linha que conter a main, e dali, executa tudo o que estiver dentro daqueles colchetes, linha por linha.

---

## Operações matemáticas

Vamos fazer uns testes!

```c
int main() {
    printf(1 + 1);
}
```

Podemos inserir operações matemáticas e escrever os valores delas. Os operadores são:

| Operação      | Operador |
| ------------- | :------: |
| soma          | `+`        |
| subtração     | `-`        |
| multiplicação | `*`        |
| divisão       | `/`        |
| resto da div. | `%`        |

Não se esqueça de que a linguagem obedece a ordem de operações, e parênteses podem ser utilizados para definir novas ordens.

Como por exemplo, `1 + 2 * 2` resulta em 5
E `(1 + 2) * 2` resulta em 6.

---

##### Variáveis

Mas, para escrever um bom programa, você vai precisar armazenar valores numéricos para fazer várias operações com eles. Valores, de qualquer tipo, são armazenados em **variáveis**. 

Variáveis são declaradas com seu tipo, seguido de um nome, e opcionalmente de um valor.

```c
int main() {
    int numero;      // Um 'int' é um número inteiro
    float y;         // Um 'float' é um número decimal
    char[] mensagem; // Um 'char[]' é uma sequência de letras
}
```

> *Qualquer texto precedido por `//` é ignorado, formando um* ***comentário***.

E agora, vamos fazer algo com esses valores.

```c
int main() {
    int numero = 4 * 2; // 8 
    float y;
    char[] mensagem = "Hello world!";
	
	y = 1.5 / 3; // 0.5
	
    printf(numero + 3);
    printf(mensagem);
}
```

---

## Formatadores de string

Se você executou o código acima, percebeu que ele resultou em "11Hello World!".
Isso aconteceu pois em momento nenhum pedimos para o código dar enter antes de escrever a mensagem. Vamos adicionar um enter em nossa mensagem!

```c
int main() {
    int numero = 4 * 2; // 8 
    float y = 1.5 / 3;  // 0.5
    char[] mensagem = "\nHello world!";
    /*
        um \n é interpretado como uma nova linha, um enter.
        um \t é interpretado como um tab.
        
        nesse caso, estamos pedindo para o programa dar um enter antes de exibir
        a mensagem.
    */
    
    printf(numero + 3);
    printf(mensagem);
}
```

E funciona!
Temos:

```
11
Hello world!
```

Mas e para os ints? Como eu coloco uma nova linha num número?
Para isso, usaremos formatadores!

Um formatador é uma forma de criar um texto usando valores presentes no código e caracteres especiais, como o `\n`.

```c
int main() {
    int numero = 4 * 2;
    float y = 1.5 / 3;
    char[] mensagem = "Hello world!";
    
    printf("Número: %d\nMensagem: %s", numero, mensagem);
}
```

Resulta em:

```
Número: 8
Mensagem: Hello world!
```

Strings formatadas são muito úteis para obter informações do seu programa de uma forma concisa e legível. 
Para usá-las, basta criar uma string normal dentro de um comando `printf()` e colocar os formatadores na posição em que você quiser as informações. Cada tipo tem seu formatador, todos começados com %. O formatador é substituído pela informação desejada quando o programa roda.

| Nome do tipo | Tipo   | Formatador |
| ------------ | ------ | :--------: |
| Inteiro      | `int`   | `%d`         |
| Decimal      | `float`  | `%f`         |
| Letra        | `char`   | `%c`         |
| Palavra      | `char[]` | `%s`         |

E se você quiser mostrar realmente um %, use `%%`, como em:
`printf("Você precisa de 50%% para ganhar!");`

---

## Input do usuário

De que serve um programa que sempre roda usando os mesmos valores? Vamos dar ao nosso usuário a capacidade de interagir com o programa.

Isso será feito através de duas funções novas: `scanf()` e `gets()`.

A primeira será mais utilizada, por ser mais versátil. Vamos a sintaxe!

```c
#include <stdio.h>

int main() {
	char[] nome;
	printf("Por favor, digite seu nome:  ");
	nome = gets();
	
	printf("Olá, %s!", nome);
}
```

Caso o usuário digite "Mariana" resultado será:

```
Por favor, digite seu nome:  Mariana
Olá, Mariana!
```


E, para demonstrar a funcionalidade do scanf, uma calculadora de adição!

```c
#include <stdio.h>

int main() {
	int x;
	int y;
	
	printf("Insira o primeiro número:  ");
	scanf("%d", &x);
	
	printf("Insira o segundo número:  ");
	scanf("%d", &y);
	
	printf("A soma será:  %d", x + y); 
	/* Você não precisa definir uma nova variável, expressões matemáticas
	 podem ser colocadas diretamente no printf */
}
```

O `scanf()` é um pouco mais complicado que o `gets()`. Ele recebe dois *argumentos*, isto é, informações no parênteses. O primeiro, uma string com os formatadores correspondentes a entrada esperada, e o segundo, o endereço da variável para onde o valor será escrito. No código, isso corresponde a colocar um `&` (pronuncia-se "E comercial") antes do nome da variável.
Sabendo disso, podemos alterar esse código:

```c
#include <stdio.h>

int main() {
	int x;
	int y;
	
	printf("Insira dois números:  ");
	scanf("%d %d", &x, &y);
	
	printf("A soma será:  %d", x + y); 
}
```

No primeiro caso, queríamos apenas um número isolado. Agora, pedimos dois números, separados por um espaço, tal como os formatadores representam.

Output para `8 4`:

```
Insira dois números:  8 4
A soma será:  12
```

Dois números, separados por um espaço. O comando entendeu isso perfeitamente. Qualquer combinação de formatadores pode ser usada no scanf: `%f` para decimais, por exemplo, ou `%c` para uma única letra.