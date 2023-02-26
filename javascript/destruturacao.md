# Destruturação

Destruturação é o processo de associar um tipo complexo (como um array, tupla ou objeto) a diversas variáveis mais simples. Ou seja, a destruturação *quebra* um tipo complexo em seus componentes.

Exemplos:
```js
const numbers = [1, 3, 5, 6]; // array com 4 números
const [x, y] = numbers;
console.log("x = " + x); // x = 1
console.log("y = " + y); // y = 3

// Os valores dos dois primeiros elementos serão copiados para x e y, em respectiva ordem.
```

```js
const person = {
	name: "Mariana",
	age: 21,
	favColor: "roxo"
}

const { name, age } = person;
console.log(name + ", " + age); // Mariana, 21
```