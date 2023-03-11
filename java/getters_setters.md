# Métodos get e set

Um dos conceitos mais importantes da orientação a objeto é o **encapsulamento**, que permite esconder detalhes sobre sua classe para que só sejam acessados via métodos com regras definidas pelo programador.

Usando as palavras-chave `public` e `private` é possível restringir o acesso a certos métodos e atributos de uma classe.

É recomendável que **todos** os atributos de uma classe sejam privados.

```java
public class Carro {
	private double quilometragem;
	private String modelo;
	private String marca;
	
	public Carro(String modelo, String marca) {
		this.modelo = modelo;
		this.marca = marca;
		this.quilometragem = 0;
	}
	
	public Carro(String modelo, String marca, double quilometragem) {
		this.modelo = modelo;
		this.marca = marca;
		this.quilometragem = quilometragem;
	}

	public void viajar(double quilometros) {
		System.out.println("Viajando " + quilometros);
		this.quilometragem += quilometros;
	}
	
	public void informarQuilometragem() {
		System.out.println(this.quilometragem);
	}
}
```

Nesse exemplo, por mais que o usuário não possa interagir diretamente com os atributos, pode definir um valor para eles usando os construtores e interagir com a quilometragem de forma *limitada* usando os métodos públicos definidos.

Essa limitação no uso te permite definir regras, como por exemplo, permitir somente números positivos, emails válidos e CPFs verificados.

No entanto, no exemplo acima, não temos uma forma de acessar os valores dos outros campos. Isso pode ser feito através de métodos que retornem esses valores.

```java
public class Carro {
	private double quilometragem;
	private String modelo;
	private String marca;
	
	public Carro(String modelo, String marca) {
		this.modelo = modelo;
		this.marca = marca;
		this.quilometragem = 0;
	}
	
	public Carro(String modelo, String marca, double quilometragem) {
		this.modelo = modelo;
		this.marca = marca;
		this.quilometragem = quilometragem;
	}

	public void viajar(double quilometros) {
		System.out.println("Viajando " + quilometros);
		this.quilometragem += quilometros;
	}
	
	public double getQuilometragem() {
		return this.quilometragem;
	}
	
	public String getModelo() {
		return this.modelo;
	}
	
	public String getMarca() {
		return this.marca;
	}
}
```

A partir desses métodos, é possível receber as informações do veículo, mas não alterar elas.
O nome padrão para esses métodos de controle de acesso é ***get***, que não recebe nada e retorna o tipo do campo em questão.

Sua contra parte é o método ***set***, para controlar a definição de atributos.

```java
public class Carro {
	private double quilometragem;
	private String modelo;
	private String marca;
	
	public Carro(String modelo, String marca) {
		this.modelo = modelo;
		this.marca = marca;
		this.quilometragem = 0;
	}
	
	public Carro(String modelo, String marca, double quilometragem) {
		this.modelo = modelo;
		this.marca = marca;
		this.quilometragem = quilometragem;
	}

	public void viajar(double quilometros) {
		System.out.println("Viajando " + quilometros);
		this.quilometragem += quilometros;
	}
	
	public double getQuilometragem() {
		return this.quilometragem;
	}
	
	public void setQuilometragem(double quilometragem) {
		if (quilometragem > this.quilometragem)
			this.quilometragem = quilometragem;
	}
	
	public String getModelo() {
		return this.modelo;
	}
	
	public void setModelo(String modelo) {
		this.modelo = modelo;
	}
	
	public String getMarca() {
		return this.marca;
	}
}
```

O método set permite definir regras para os possíveis valores de um atributo, servindo como uma garantia de que o valor será válido.

No exemplo acima, o campo quilometragem jamais poderá ser redefinido para um valor menor que o anterior, somente maior.
Enquanto isso, o campo modelo pode ser recebido e definido pelos métodos get e set respectivos, sem limitações.
E o campo marca só pode ser lido, já que é atribuído na criação do objeto pelo construtor, e jamais será alterado posteriormente.
