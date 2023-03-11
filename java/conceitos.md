# Sintaxe básica

Java é uma linguagem orientada a objeto inspirada em C++, com coletor de lixo para alocação dinâmica e compilada para um formato intermediário *bytecode*, que pode ser executado em qualquer plataforma pela JVM (Java Virtual Machine).

Um programa em Java começa a executar a partir do método **main**.

```java
public class Program {
	public static void main(String[] args) {
		System.out.println("Hello world!");
	}
}
```

A classe que contiver o método main será considerada a classe principal, e o programa começará a executar a partir dela.

> Somente uma classe pode conter um método main

`System.out.println` é o comando responsável por escrever strings, semelhante ao `console.log` de JavaScript e `printf` de C.

---

## Sintaxe básica

As estruturas básicas de controle de fluxo, `if` / `else if` / `else` e `switch`, além das estruturas de repetição `while`, `do { ... } while`, `for`.

Os operadores matemáticos básicos funcionam de forma exatamente igual.
Os operadores lógicos `&&` (and), `||` (or), `==` (igual a) e `!=` (diferente de) funcionam da mesma forma.

---

## Variáveis

A declaração de variáveis em Java é similar a declaração de C; o tipo da variável, seguido de um nome, e opcionalmente, um valor.

```java
int inteiro = 10;
float racional = 8.5;
char letra = 'L';

int soma;

if (inteiro % 2 == 0) {
	soma = 10 / 2;
} else {
	soma = 10 * 2;
}
```

No entanto, a classe `String` age como um tipo e simplifica consideravelmente o uso de cadeias de caracteres.

```Java
String nome = "Mariana";
String sobrenome = "Alves";

String nomeCompleto = nome + " " + sobrenome;

System.out.println("Meu nome é:  " + nomeCompleto);
```

> O operador de soma ` + ` pode ser usado para concatenar strings, resultando numa nova sequência de caracteres.
