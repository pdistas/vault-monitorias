# Classes e objetos

Classes são estruturas de dados complexas que permitem o modelamento de informações e comportamentos conforme o mundo real.

Um carro pode ser definido pela sua cor, marca, modelo, quilometragem e ano.
Uma classe te permite expressar essas características como código.

Para declarar uma classe, a palavra-chave `class` deve ser usada, seguida do nome da classe.
Dentro da classe, estarão os *atributos*, ou seja, valores relacionados com essa classe.

*Arquivo carro.java*
```java
public class Carro {
	double quilometragem;
	String modelo;
	String marca;
	String cor;
	int ano;
}
```

*Arquivo program.java*
```java
public class Program {
	public static void main(String[] args) {
		Carro car1 = new Carro();
		
		car1.modelo = "Ônix";
		car1.cor = "Prata";
		car1.ano = 2019;
		car1.marca = "Chevrolet";
		car1.quilometragem = 41300.4;
		
		System.out.println("Modelo do carro:  " + car1.modelo);
		System.out.println("Marca do carro:  " + car1.marca);
		System.out.println("Ano do carro:  " + car1.ano);
	}
}
```

Resultado:
```
Modelo do carro:  Ônix
Marca do carro:  Chevrolet
Ano do carro:  2019
```

Nesse modelo, possuímos uma classe carro, e toda **instância** de carro possui seu próprio modelo, marca, quilometragem, cor e ano.

Usando classes, podemos modelar as características de qualquer objeto, conceito ou sistema do mundo real como linhas de código.


