# Métodos

Um método é, em sua essência, uma função ligada a uma classe.
E assim como uma função, possui um nome, parâmetros e retorno.

*Arquivo carro.java*
```java
public class Carro {
	double quilometragem;
	String modelo;
	String marca;
	String cor;
	int ano;
	
	public void parar() {
		System.out.println("Carro parado!");
	}
	
	public void viajar(int quilometros) {
		System.out.println("Viajando " + quilometros + " quilômetros");
		this.quilometragem += quilometros;
	}
	
	public void informarModelo() {
		System.out.println("Modelo do veículo:  " + this.modelo);
	}
}
```

> A palavra-chave *this* é usada para referenciar o objeto que está chamando o método, ou seja, o objeto atual.

*Arquivo program.java*
```java
public class Program {
	public static void main(String[] args) {
		Carro onix = new Carro();
		onix.modelo = "Ônix";
		onix.marca = "Chevrolet";
		onix.cor = "Prata";
		onix.quilometragem = 20500;
		
		Carro hb20 = new Carro();
		hb20.modelo = "HB20";
		hb20.marca = "Hyundai";
		hb20.cor = "Branco";
		hb20.quilometragem = 0;
		
		System.out.println("Quilometragem:  " + onix.quilometragem);
		onix.parar();
		onix.viajar(50);
		System.out.println("Quilometragem:  " + onix.quilometragem);

		System.out.println(); // só para dar um espaço extra

		onix.informarModelo();
		hb20.informarModelo();		
	}
}
```

Resultado:
```
Quilometragem:  20500
Carro parado!
Viajando 50 quilômetros

Modelo do veículo: Ônix
Modelo do veículo: HB20
```

Ambos os carros, como são da classe carro, compartilham dos mesmos campos e métodos. 

No entanto, os valores armazenados são diferentes, e os carros apresentam comportamentos diferentes.
