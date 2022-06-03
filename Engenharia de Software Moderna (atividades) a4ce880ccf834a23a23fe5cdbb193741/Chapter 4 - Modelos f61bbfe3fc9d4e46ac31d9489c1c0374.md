# Chapter 4 - Modelos

## **Exercícios de Fixação [🔗](https://engsoftmoderna.info/cap4.html#exerc%C3%ADcios-de-fixa%C3%A7%C3%A3o)**

1. Explique e discuta os três usos possíveis de UML:

1. Como blueprint (ou plantas técnicas detalhadas)
Para documentar modelos, e tomadas de decisoes mais complexas

2. Como sketches (esboços)
Para elucidar e validar ideias, explicar codigos, design e arquiteturas para os demais

3. Como linguagem de programação.
Para construir software partir da uml, conforme modelado

2. Descreva cenários de uso de diagramas de classes UML como instrumento dos seguintes tipos de engenharia:

1. Engenharia Reversa
Para entendimento do codigo implementado

2. Engenharia Avante (*Forward Engineering*).
Para concepcao de novas features 

3. Modele os cenários descritos a seguir usando Diagramas de Classe UML.Veja que as classes são grafadas em uma fonte diferente.

1. `ContaBancaria` possui exatamente um `Cliente`. Um `Cliente`, por sua vez, pode ter várias `ContaBancaria`. Existe navegabilidade em ambos os sentidos.
2. `ContaPoupanca` e `ContaSalario` são subclasses de `ContaBancaria`.
3. No código de `ContaBancaria` declara-se uma variável local do tipo `BancoDados`.

![Untitled Diagram (1).jpg](Chapter%204%20-%20Modelos%20f61bbfe3fc9d4e46ac31d9489c1c0374/Untitled_Diagram_(1).jpg)

1. Um `ItemPedido` se refere a um único `Produto` (sem navegabilidade). Um `Produto` pode ter vários `ItemPedido` (com navegabilidade).

![Untitled Diagram (2).jpg](Chapter%204%20-%20Modelos%20f61bbfe3fc9d4e46ac31d9489c1c0374/Untitled_Diagram_(2).jpg)

1. A classe `Aluno` possui atributos `nome`, `matricula`, `curso` (todos privados); e métodos `getCurso()` e `cancelaMatricula()`, ambos públicos.

![Untitled Diagram (3).jpg](Chapter%204%20-%20Modelos%20f61bbfe3fc9d4e46ac31d9489c1c0374/Untitled_Diagram_(3).jpg)

4. (ENADE 2014, Tec. e Análise de Sistemas) Construa um diagrama de classes para representar as seguintes classes e associações:

- Uma revista científica possui título, ISSN e periodicidade;
- Essa revista publica diversas edições com os seguintes atributos: número da edição, volume da edição e data da edição. Importante destacar que cada instância da classe edição relaciona-se única e exclusivamente a uma instância da classe revista científica, não podendo relacionar-se com nenhuma outra;
- Um artigo possui título e nome do autor. Um artigo é um conteúdo exclusivo de uma edição. E uma edição obrigatoriamente tem que possuir no mínimo 10 e no máximo 15 artigos.

![Untitled Diagram.jpg](Chapter%204%20-%20Modelos%20f61bbfe3fc9d4e46ac31d9489c1c0374/Untitled_Diagram.jpg)

5. Crie diagramas de classes para os seguintes trechos de código:

(a)

```
public class HelloWorldSwing {

   public static void main(String[] args) {
     JFrame frame = new JFrame("Hello world!");
     frame.setVisible(true);
   }

}
```

(b)

```
class HelloWorldSwing extends JFrame {

   public HelloWorldSwing() {
     super("Hello world!");
   }

   public static void main(String[] args) {
     HelloWorldSwing frame = new HelloWorldSwing();
     frame.setVisible(true);
   }

}
```

![Untitled Diagram (1).jpg](Chapter%204%20-%20Modelos%20f61bbfe3fc9d4e46ac31d9489c1c0374/Untitled_Diagram_(1)%201.jpg)

6. Mostre o diagrama de sequência relativo ao seguinte código. O diagrama deve começar com a seguinte chamada *a*.*m5()*.

```
A a = new A(); // variáveis globais
B b = new B();
C c = new C();

class C {
   void m1() { ... }
}

class B {
   void m2() { ... c.m1(); ... this.m3(); ... }
   void m3() { ... c.m1(); ... }
   void m4() { ... }
}

class A {
   void m5() { ... b.m2(); ... b.m3(); ... b.m4(); ...  }
}
```

![Untitled Diagram (2).jpg](Chapter%204%20-%20Modelos%20f61bbfe3fc9d4e46ac31d9489c1c0374/Untitled_Diagram_(2)%201.jpg)

7. Em diagramas de atividades, explique a diferença entre um nodo de *merge* e um nodo de *join*.
Merge: quando uma ficha chega em um dos fluxos, ocorre o repasse para o fluxo de saída.

Join : esperam que fichas cheguem em todos fluxos , para entao efetuar o repasse para o fluxo de saída

8. Qual é o erro do seguinte diagrama de atividades? Refaça o diagrama de forma a refletir corretamente a intenção do projetista.

![https://engsoftmoderna.info/figs/cap4/activity-exercicio.svg](https://engsoftmoderna.info/figs/cap4/activity-exercicio.svg)

R

![Untitled Diagram (3).jpg](Chapter%204%20-%20Modelos%20f61bbfe3fc9d4e46ac31d9489c1c0374/Untitled_Diagram_(3)%201.jpg)