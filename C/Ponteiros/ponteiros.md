
# Ponteiros

---

## Endereços de memória

Toda informação armazenada durante a execução de um programa encontra-se em uma localização física no computador, que pode ser acessada, tanto para leitura quanto escrita, por meio de seu *endereço*.

O endereço de memória determina a localização de um dado, e é atribuido pelo sistema operacional no exato momento em que a memória é requisitada (como ao criar uma variável).
É um valor quase aleatório, indeterminável, que se altera a cada execução do programa.

```C
int main() {
	int numero = 5; // nesse momento, o sistema operacional reserva um
					// espaço de memória e ali armazena o número cinco.

	numero = 4;  // endereço de memória continua o mesmo, só mudamos o valor guardado.
}
```

Ao declarar uma variável, um espaço com o seu tamanho é reservado pelo sistema operacional, que garante seu acesso para o programa.
Mudar o valor de uma variável não altera o tamanho do espaço reservado, apenas o que está guardado nele.
Variáveis maiores, como `long` e `double`, necessitam de mais memória que suas contrapartes `int` e `float`.

Para ler o endereço de uma variável, utiliza-se o operador prefixado `&`.

```c
int main() {
	int numero = 5;

	printf("%d", numero); // 5
	printf("%d", &numero); // endereço de memória
	// muda a cada execução
}
```

> Não há uso prático para imprimir o endereço de uma variável durante a execução, não é uma informação útil para o usuário.

O endereço de memória da variável `numero` é onde está armazenado o valor `5`.


## Ponteiros

O ponteiro é uma variável que armazena um endereço de memória, ao invés de um valor em si. Dessa forma, é possível referenciar o valor de outra variável num ponto externo do programa.

```c
int main() {
	int numero = 5;
	int* ponteiro = &numero; // endereço de número

	printf("%d\n", &numero);
	printf("%d\n", ponteiro);
	// ambos os printfs irão imprimir a mesma coisa, o endereço de número
}
```

Para receber o valor que está guardado em um endereço de memória, utiliza-se o operador `*`.

```c
int main() {
	int numero = 5;
	int* ponteiro = &numero; 

	printf("%d", *&numero); // imprime 5
	printf("%d", *ponteiro); // imprime 5

	numero = 6;
	
	printf("%d", numero); // imprime 6
	printf("%d", *ponteiro); // imprime 6

	*ponteiro = 7; // altera o valor de outra variável através do ponteiro
	
	printf("%d", numero); // imprime 7
	printf("%d", *ponteiro); // imprime 7
}
```

É possível alterar o valor da variável para qual o ponteiro aponta com a sintaxe `*ponteiro = {valor}`.

