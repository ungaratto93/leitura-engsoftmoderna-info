# Chapter 9 - Refactoring

## **Exercícios de Fixação [🔗](https://engsoftmoderna.info/cap9.html#exerc%C3%ADcios-de-fixa%C3%A7%C3%A3o)**

1. Marque a alternativa FALSA:

(a) refactorings melhoram o projeto de um sistema de software.

(b) refactorings tornam o código de um sistema mais fácil de ser entendido.

(c) refactorings facilitam a localização e a correção de bugs futuros.

v (d) refactorings aceleram a implementação de novas funcionalidades.

(e) refactorings melhoram o desempenho de um sistema, em termos de tempo de execução.

2. O gráfico a seguir mostra o total acumulado de novas funcionalidades implementadas em dois sistemas (A e B), de domínios semelhantes, desenvolvidos por times semelhantes, usando as mesmas tecnologias. Em qual dos dois sistemas você acha que refactorings foram realizados de forma sistemática? Justifique a sua resposta.

![https://engsoftmoderna.info/figs/cap9/refactoring-exercicio.png](https://engsoftmoderna.info/figs/cap9/refactoring-exercicio.png)

O sistema A por apresentar uma linha de crescimento constante e progressivo, demonstra que o refactoring foi sendo aplicado de forma sistematica.

3. Descreva as diferenças entre refactorings oportunistas e refactorings planejados. Qual dessas formas de refactoring deve ser mais comum?

- refactoring oportunista refere-se ao programador observar uma oportunidade de refactoring e ja aplica-la durante a execuçao de uma tarefa
- refactorings planejados, refere-se a trecho de codigo com potencial de impacto maior, e de complexidade alta, sendo necessario um planejamento para execucao.
- os refactorings oportunistas devem ser encorajados.

4. Escreva o nome de refactorings A e B que se executados em sequência não produzem impacto no código de um sistema. Ou seja, o refactoring B reverte as transformações realizadas pelo refactoring A.

- Clone do Tipo 1: quando A e B têm o mesmo código, com diferenças apenas em comentários e espaços.
- Clone do Tipo 2: quando A e B são clones do Tipo 1, porém as variáveis usadas em A e B podem ter nomes diferentes.

5. Nos exemplos a seguir, extraia o código comentado com a palavra extrair para um método `ga`

1. 

```

class A {
  void f() {
    int x = 10
    x++;
    display(x);   // extrair
  }
	void display(x) {
		print(x);
	}
}
```

b. 

```
class A {
  void f() {
    int x = 10
    x = increments(x);    
    display(x);
  }
	void display(x) {
		print(x);
	}
	int increments(x) {
		return int x++;
	}
}
```

c.

```
class A {
  void f() {
    int x = 10
    increments(x);     // extrair
    display(x); // extrair
    int y = x+1;
    ...
  }

	void display(x) {
		print(x);
	}
	int increments(x) {
		return int x++;
	}
}
```

d.

```
class A {
  void f() {
    int x = 10
    int y = calc(); 
    display(y);
    int z = y+1;
    ...
  }
	void display(x) {
		print(x);
	}
	int calc() {
		return h()*2;
	}
 int h() {};
}
```

6. A seguinte função calcula o n-ésimo termo da sequência de Fibonacci. O primeiro termo dessa sequência é 0; o segundo termo é 1; e a partir daí o n-ésimo termo é a soma dos dois termos anteriores.

```
int fib(int n) {
   if (n == 1)
      return 0;
   if (n == 2)
      return 1;
   return fib(n-1) + fib(n-2);
}
```

Descreva clones dos Tipos 1, 2, 3 e 4 para essa função. Não precisa implementar o código do clone, mas seja bem preciso na sua resposta ao indicar as diferenças entre cada clone e o código acima.

- codigo cem comentarios e espacos
- codigo variaveis diferentes e estruturalmente semelhante
- codigo com comandos um pouco modificados
- codigo que faz a mesma coisa, porem com algoritmos diferentes

7. Seja o seguinte trecho de código de uma classe `Moeda`, que vai armazenar um determinado valor em reais.

```
class Moeda {
  ...
  private double valor = 0.0;
  void add(Moeda m) {
    this.valor = this.valor + m.getValor();
  }
  ...
}
```

(a) Descreva porque objetos da classe `Moeda` são mutáveis.

- classe pode ser herdada
- os atributos podem ser modificados

(b) Reimplemente esse trecho da classe `Moeda` de forma a assegurar que os seus objetos sejam imutáveis (como vimos no capítulo, objetos mutáveis tendem a ser um code smell, principalmente no caso de objetos pequenos e simples, como provavelmente é o caso de objetos da classe em questão).

```jsx
final class Moeda {
  ...
  final private double valor = 0.0;
  void add(Moeda m) {
    this.valor = this.valor + m.getValor();
  }
  ...
}
```

8. Como discutido no final da Seção 9.5, comentários que são usados para explicar código ruim são considerados um code smell. Nessas situações, o ideal é tornar o código mais claro e, então, remover os comentários. A seguir, mostramos mais um caso de comentário que pode ser deletado. Explique por que esses comentários são desnecessários.

```
// classe Aluno
class Aluno {

   // matrícula do aluno
   int matricula;

   // data de nascimento do aluno
   Date dataNascimento;

   // endereço do aluno
   Endereco endereco;

   // construtor default da classe Aluno
   Aluno() {
     ...
   }
   ...
}
```

- os nomes dos atributos, construtor e classe, ja revelam o que fazem

9. Use uma IDE, como o Eclipse ou IntelliJ para Java, para realizar um refactoring simples, em um de seus programas. Por exemplo, realize uma renomeação de método. Quais as vantagens de se realizar refactorings com o suporte de IDEs?

- produtividade e automacao

10. Use uma IDE para testar o exemplo de Movimentação de Classe discutido na Seção 9.4.1, isto é, o exemplo com classes `A` e `B` e pacotes `P1` e `P2`. Se realizar a Movimentação de Classe discutida nesse exemplo via IDE, ocorrerá algum erro? Se sim, descreva o erro detectado pela IDE.

- Vai ocorrer erro na compilacao por conta dos metodos acessores, se mover metodos entre pacotes distintos, deve-se corrigir os modificadores de acesso.
- No caso em questao altera o funcionamento do programa e executado metodos diferente caso nao ajuste o modificador de acesso da classe.