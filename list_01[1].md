# Respostas Lista 1 de exercícios

# Instruções
- Faça uma cópia deste arquivo .md para um repositório próprio
- Resolva as 8 questões objetivas assinalando a alternativa correta e **justificando sua resposta.**
- Resolva as 2 questões dissertativas escrevendo no próprio arquivo .md
- Lembre-se de utilizar as estruturas de código como ``esta aqui com ` `` ou
```javascript
//esta aqui com ```
let a = "olá"
let b = 10
print(a)
```
- Resolva as questões com uso do Visual Studio Code ou ambiente similar.
- Teste seus códigos antes de trazer a resposta para cá.
- Cuidado com o uso de ChatGPT (e similares), pois entregar algo só para ganhar nota não fará você aprender. Não seja dependente da máquina!
- Ao final, publique seu arquivo lista_01.md com as respostas em seu repositório, e envie o link pela Adalove. 

# Questões objetivas
**1) Considerando a execução do código abaixo, indique a alternativa correta e justifique sua resposta.**
```javascript
console.log(x);
var x = 5;
console.log(y);
let y = 10;
```
**a) A saída será undefined seguido de erro**

b) A saída será 5 seguido de 10

c) A saída será undefined seguido de undefined

d) A saída será erro em ambas as linhas que utilizam console.log

### **Resposta:**

Alternativa **A**.  

O código imprimirá `undefined` seguido de um erro.  
- O `console.log(x)` retorna `undefined`, pois `x` foi declarada com `var`, mas ainda não inicializada.  
- O `console.log(y)` gera um erro porque `y` foi declarada com `let` e ainda não foi inicializada antes de ser chamada.


**2) O seguinte código JavaScript tem um erro que impede sua execução correta. Analise e indique a opção que melhor corrige o problema. Justifique sua resposta.**

```javascript
function soma(a, b) {
    if (a || b === 0) {
        return "Erro: número inválido";
    }
    return a + b;
}
console.log(soma(2, 0));
```

a) Substituir if (a || b === 0) por if (a === 0 || b === 0)

**b) Substituir if (a || b === 0) por if (a === 0 && b === 0)**

c) Substituir if (a || b === 0) por if (a && b === 0)

d) Remover completamente a verificação if (a || b === 0)

### **Resposta**

Alternativa **B**

Deve-se substituir por if (a === 0 || b === 0).

(i) O objetivo da verificação é impedir que qualquer um dos valores seja 0. No entanto, a forma atual ⁠ a || b === 0 ⁠ está incorreta, pois não está verificando se a é igual a 0, neste caso, está verificando se a variável a é diferente de undefined.

**3) Ao executar esse código, qual será a saída no console? Indique a alternativa correta e justifique sua resposta.**
```javascript
function calcularPreco(tipo) {
    let preco;

    switch(tipo) {
        case "eletrônico":
            preco = 1000;
        case "vestuário":
            preco = 200;
            break;
        case "alimento":
            preco = 50;
            break;
        default:
            preco = 0;
    }

    return preco;
}

console.log(calcularPreco("eletrônico"));
```

a) O código imprime 1000.

**b) O código imprime 200.**

c) O código imprime 50.

d) O código gera um erro.

### Resposta:

Alternativa **B**.  

O código imprime `200`, pois falta um `break` no primeiro `case`, fazendo com que a execução continue até o próximo `break`.  

**4) Ao executar esse código, qual será a saída no console? Indique a alternativa correta e justifique sua resposta.**
```javascript
let numeros = [1, 2, 3, 4, 5];

let resultado = numeros.map(x => x * 2).filter(x => x > 5).reduce((a, b) => a + b, 0);

console.log(resultado);
```
a) 0

b) 6

c) 18

**d) 24**
______

### Resposta:

Alternativa **D**

O código transforma a lista `[1,2,3,4,5]` para `[2,4,6,8,10]`, filtra `[6,8,10]` e soma os valores, resultando em **24**.  

**5) Qual será o conteúdo do array lista após a execução do código? Indique a alternativa correta e justifique sua resposta.**

```javascript
let lista = ["banana", "maçã", "uva", "laranja"];
lista.splice(1, 2, "abacaxi", "manga");
console.log(lista);
```

a) ["banana", "maçã", "uva", "abacaxi", "manga", "laranja"]

b) ["banana", "abacaxi", "manga"]

**c) ["banana", "abacaxi", "manga", "laranja"]**

d) ["banana", "maçã", "uva", "abacaxi", "manga"]
______

### Resposta:

Alternativa **C**.  

O código gera um erro, pois `let a` dentro da função não pode ser acessado antes de sua inicialização. 

**6) Abaixo há duas afirmações sobre herança em JavaScript. Indique a alternativa correta e justifique sua resposta**

I. A herança é utilizada para compartilhar métodos e propriedades entre classes em JavaScript, permitindo que uma classe herde os métodos de outra sem a necessidade de repetir código.  
II. Em JavaScript, a herança é implementada através da palavra-chave `extends`.


**a) As duas afirmações são verdadeiras, e a segunda justifica a primeira.**

b) As duas afirmações são verdadeiras, mas a segunda não justifica a primeira.

c) A primeira afirmação é verdadeira, e a segunda é falsa.

d) A primeira afirmação é falsa, e a segunda é verdadeira.
______

### Resposta:

Alternativa **A**

A herança facilita o compartilhamento de funcionalidades entre outras classes, evitando redundânias. E `extends` permite que uma classe tenha como herança os métodos e propriedades de outra.

**7) Dado o seguinte código. Indique a alternativa correta e justifique sua resposta.**

```javascript
class Pessoa {
  constructor(nome, idade) {
    this.nome = nome;
    this.idade = idade;
  }

  apresentar() {
    console.log(`Olá, meu nome é ${this.nome} e tenho ${this.idade} anos.`);
  }
}

class Funcionario extends Pessoa {
  constructor(nome, idade, salario) {
    super(nome, idade);
    this.salario = salario;
  }

  apresentar() {
    super.apresentar();
    console.log(`Meu salário é R$ ${this.salario}.`);
  }
}
```

I) A classe Funcionario herda de Pessoa e pode acessar os atributos nome e idade diretamente.  
II) O método `apresentar()` da classe Funcionario sobrepõe o método `apresentar()` da classe Pessoa, mas chama o método da classe pai usando `super`.  
III) O código não funciona corretamente, pois Funcionario não pode herdar de Pessoa como uma classe, já que o JavaScript não suporta herança de classes.

Quais das seguintes afirmações são verdadeiras sobre o código acima?

**a) I e II são verdadeiras.**

b) I, II e III são verdadeiras.

c) Apenas II é verdadeira.

d) Apenas I é verdadeira.

______

### Resposta:

Alternativa **A**

A primeira afirmativa está correta, pois a classe Funcionario herda os atributos e métodos da classe principal Pessoa por meio da palavra-chave extends.

A segunda também é verdadeira, já que a classe Funcionario redefine o método apresentar(), mas faz uso de super.apresentar() para invocar a implementação original da classe pai.

A terceira está incorreta, pois o JavaScript permite herança de classes utilizando extends.

**8) Analise as afirmações a seguir. Indique a alternativa correta e justifique sua resposta.**

**Asserção:** O conceito de polimorfismo em Programação Orientada a Objetos permite que objetos de diferentes tipos respondam à mesma mensagem de maneiras diferentes.  
**Razão:** Em JavaScript, o polimorfismo pode ser implementado utilizando o método de sobrecarga de métodos em uma classe.

a) A asserção é falsa e a razão é verdadeira.

**b) A asserção é verdadeira e a razão é falsa.**

c) A asserção é verdadeira e a razão é verdadeira, mas a razão não explica a asserção.

d) A asserção é verdadeira e a razão é verdadeira, e a razão explica a asserção.

______

### Resposta:

Alternativa **B**

A afirmação está certa, pois o polimorfismo permite que objetos distintos respondam a uma mesma chamada de maneira diferente.

No entanto, a justificativa está errada, já que o JavaScript não oferece suporte à sobrecarga de métodos. Caso existam múltiplos métodos com o mesmo nome em uma classe, apenas o último será considerado.

Exemplo:

```javascript
test(x) {
  console.log("Teste:", x);
}

test(x, y) {
  console.log("Sucesso:", x, y);
}

test(1);      // Resultado: "Sucesso: 1 undefined"
test(1, 2);   // Resultado: "Sucesso: 1 2"
```

As duas chamadas utilizam a segunda versão do método, demonstrando que não há suporte para sobrecarga.

# Questões dissertativas
9) O seguinte código deve retornar a soma do dobro dos números de um array, mas contém erros. Identifique os problema e corrija o código para que funcione corretamente. Adicione comentários ao código explicado sua solução para cada problema.

```javascript
function somaArray(numeros) {

    for (i = 0; i < numeros.size; i++) {
        soma = 2*numeros[i];
    }
    return soma;
}
console.log(somaArray([1, 2, 3, 4]));
```
______

### Resposta:
```javascript
function sum(numbers) {
    let total = 0; // Inicializa a variável "total" em 0

    for (let i = 0; i < numbers.length; i++) { 
        total += 2 * numbers[i]; // Incrementa na variável "total"
    }

    return total;
}

console.log(sum([2, 4, 6, 8])); // Saída esperada: 40
```

10) Crie um exemplo prático no qual você tenha duas classes:

- Uma classe `Produto` com atributos `nome` e `preco`, e um método `calcularDesconto()` que aplica um desconto fixo de 10% no preço do produto.
- Uma classe `Livro` que herda de `Produto` e modifica o método `calcularDesconto()`, aplicando um desconto de 20% no preço dos livros.

Explique como funciona a herança nesse contexto e como você implementaria a modificação do método na classe `Livro`.

```javascript
// Cria classe base Veiculo
class Veiculo {
  constructor(marca, preco) {
    this.marca = marca;
    this.preco = preco;
  }

  // Método para aplicar um desconto de 10%
  calcularDesconto() {
    return this.preco * 0.9;
  }
}

// Classe Carro que herda de Veiculo
class Carro extends Veiculo {
  constructor(marca, preco, modelo) {
    super(marca, preco);
    this.modelo = modelo;
  }

  // Sobrescreve o método para aplicar um desconto de 20%
  calcularDesconto() {
    return this.preco * 0.8;
  }
}

// Criando instâncias para teste
const veiculo1 = new Veiculo("Genérico", 50000);
console.log(`Preço com desconto (Veículo): R$ ${veiculo1.calcularDesconto()}`);

const carro1 = new Carro("Toyota", 100000, "Corolla");
console.log(`Preço com desconto (Carro): R$ ${carro1.calcularDesconto()}`);
```
**Explicação:**  
- A classe `Veiculo` define um método `calcularDesconto()` que aplica 15% de desconto.  
- A classe `Carro`, que herda de `Veiculo`, redefine esse método para aplicar 5% de desconto. 
```