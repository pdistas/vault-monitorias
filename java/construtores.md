# Construtores

O construtor é um método especial responsável por gerar e retornar uma *instância* de uma classe.

Diversos construtores diferentes podem ser declarados, de forma semelhante a um método, no entanto, o construtor não possui um tipo de retorno em sua declaração.
Quase sempre, o construtor é usado para definir valores a serem definidos nos atributos de uma classe, recebidos como argumentos na chamada do construtor.

*Arquivo carro.java*
```java
public class Carro {
	double quilometragem;
	String modelo;
	String marca;
	String cor;
	int ano;

	public Carro(String modelo, String marca) {
		this.modelo = modelo;
		this.marca = marca;
		this.quilometragem = 0;

		System.out.println("Carro zero!");
		// Construtores podem executar qualquer código, normalmente.
	}
	
	public Carro(String modelo, String marca, double quilometragem) {
		this.modelo = modelo;
		this.marca = marca;
		this.quilometragem = quilometragem;
	}
}
```

*Arquivo program.java*
```java
public class Program {
	public static void main(String[] args) {
		Carro carroZero = new Carro("Fit", "Honda");
		Carro carroUsado = new Carro("Saveiro", "Fiat", 250081);
	
		// Dependendo dos argumentos usados no construtor, um construtor diferente será usado.
		
		System.out.println(carroUsado.modelo);
	}
}
```

> O construtor é chamado usando a palavra-chave `new`.

Resultado:
```
Carro zero!
Saveiro
```