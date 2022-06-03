# Chapter 6 - Padrões de Projeto

## **Exercícios de Fixação [🔗](https://engsoftmoderna.info/cap6.html#exerc%C3%ADcios-de-fixa%C3%A7%C3%A3o)**

1. (ENADE 2011, adaptado) Sobre padrões de projeto, assinale V ou F.

( F) Prototype é um tipo de padrão estrutural.

( V) Singleton tem por objetivo garantir que uma classe tenha ao menos uma instância e fornecer um ponto global de acesso para ela.

( V) Template Method tem por objetivo definir o esqueleto de um algoritmo em uma operação, postergando a definição de alguns passos para subclasses.

( V) Iterator fornece uma maneira de acessar sequencialmente os elementos de um objeto agregado sem expor sua representação subjacente.

2. Dê o nome dos seguintes padrões de projeto:

1. Oferece uma interface unificada e de alto nível que torna mais fácil o uso de um sistema. =  Fachada
2. Garante que uma classe possui, no máximo, uma instância e oferece um ponto único de acesso a ela. = Singleton
3. Facilita a construção de objetos complexos com vários atributos, sendo alguns deles opcionais. = Builder
4. Converte a interface de uma classe para outra interface esperada pelos clientes. Permite que classes trabalhem juntas, o que não seria possível devido à incompatibilidade de suas interfaces. =   Adaptador
5. Oferece uma interface ou classe abstrata para criação de uma família de objetos relacionados. = Abstract Factory
6. Oferece um método para centralizar a criação de um tipo de objeto. Method Factory
7. Funciona como um intermediário que controla o acesso a um objeto base. Proxy
8. Permite adicionar dinamicamente novas funcionalidades a uma classe. = Decorator
9. Oferece uma interface padronizada para caminhar em estruturas de dados. = Iterator
10. Permite parametrizar os algoritmos usados por uma classe. = Strategy
11. Torna uma estrutura de dados aberta a extensões, isto é, permite adicionar uma função em cada elemento de uma estrutura de dados, mas sem alterar o código de tais elementos. = Visitor
12. Permite que um objeto avise outros objetos de que seu estado mudou. = Observer
13. Define o esqueleto de um algoritmo em uma classe base e delega a implementação de alguns passos para subclasses. = Template Method

3. Dentre os padrões de projeto que respondeu na questão (2), quais são padrões criacionais?

- Factory
- Singleton
- Builder

4. Considerando as respostas da questão (2), liste padrões de projeto que:

1. Ajudam a tornar uma classe aberta a extensões, sem que seja preciso modificar o seu código fonte (isto é, padrões que colocam em prática o princípio Aberto/Fechado).
* Strategy
* Factory

2. Ajudam a desacoplar dois tipos de classes.
* Observer

3. Ajudam a incrementar a coesão de uma classe (isto é, fazem com que a classe tenha Responsabilidade Única).
* Proxy

4. Simplificam o uso de um sistema.
* Facade

5. Qual a semelhança entre Proxy, Decorador e Visitor? E qual a diferença entre esses padrões?  *
Semelhança

- Adiciona funcionalidades a objetos

Diferenca

- Decorador é um exemplo de aplicação do princípio de projeto Prefira Composição a Herança
- Proxy e um exemplo de aplicacao do principio de projeto Prefira Interfaces a Classes
- Visitor pode quebrar o encapsulamento das classes (coesao)

6. No exemplo de Adaptador, mostramos o código de uma única classe adaptadora (`AdaptadorProjetorSamsung`). Escreva o código de uma classe semelhante, mas que adapte a interface `Projetor` para a interface `ProjetorLG` (o código de ambas interfaces é mostrado na Seção 6.5). Chame essa classe de `AdaptadorProjetorLG`.

[https://github.com/ungaratto93/nedia/tree/main/adapterPatternExercise](https://github.com/ungaratto93/nedia/tree/main/adapterPatternExercise)

7. Suponha uma classe base A. Suponha que queremos adicionar quatro funcionalidades opcionais F1, F2, F3 e F4 em A. Essas funcionalidades podem ser adicionadas em qualquer ordem, isto é, a ordem não é importante. Se usarmos herança, quantas subclasses de A teremos que implementar? Se optarmos por uma solução por meio de decoradores, quantas classes teremos que implementar (sem contar a classe A). Justifique e explique sua resposta.

Usando heranca teremos uma quantidade combinatoria do numero de funcionalidades, ou seja quatro classes.

Entretanto ao usar composicao, teremos que adicionar a classe decoradora, e conforme o contexto quebrar a classe A em classes especializadas para compor as chamadas e repassar ao decorador e que por sua vez passará a chamada a classe base.

8. No exemplo de Decorador, mostramos o código de um único decorador (`ZipChannel`). Escreva o código de uma classe semelhante, mas que imprima a mensagem a ser transmitida ou recebida no console. Chame essa classe decoradora de `LogChannel`.

[https://github.com/ungaratto93/nedia/tree/main/decoratorPatternExercise](https://github.com/ungaratto93/nedia/tree/main/decoratorPatternExercise)

9. Dado o código abaixo de uma classe `Subject` (do padrão Observador):

```
interface Observer {
  public void update(Subject s);
}

class Subject {

  private List<Observer> observers=new ArrayList<Observer>();

  public void addObserver(Observer observer) {
    observers.add(observer);
  }

  public void notifyObservers() {
    (A)
  }

}
```

Implemente o código de `notifyObservers`, comentado com um (A) acima.

[https://github.com/ungaratto93/nedia/tree/main/observerPatternExercise](https://github.com/ungaratto93/nedia/tree/main/observerPatternExercise)

10. Suponha a API de Java para E/S. Suponha que para evitar o que chamamos de paternite, você fez a união das classes `FileInputStream` e `BufferedInputStream` em uma única classe. Como discutimos na Seção 6.13, o mecanismo de buffer será ativado por *default* na classe que você criou. Porém, como você tornaria possível desativar buffers nessa nova classe, caso isso fosse necessário? Usando o Strategy pattern

Passando como argumento  a estrategia do input na classe FIle
[https://github.com/ungaratto93/nedia/tree/main/strategyPatternExercise](https://github.com/ungaratto93/nedia/tree/main/strategyPatternExercise)

/*
* Interessante como o padrão strategy trouxe flexibilidade
* na escolha do modo de input streams
* */

11. Suponha o exemplo de Visitor que usamos na Seção 6.11. Especificamente, suponha o seguinte código, mostrado no final da seção.

```
PrintVisitor visitor = new PrintVisitor();

foreach(Veiculo veiculo: listaDeVeiculosEstacionados) {
  veiculo.accept(visitor);
}
```

Suponha que `listaDeVeiculosEstacionados` armazene três objetos: `umCarro`, `umOnibus` e `umOutroCarro`. 

Desenhe um diagrama de sequência UML que mostre os métodos executados por esse trecho de código (suponha que ele é executado por um objeto `main`).

[sequence_visitor_diagram.drawio](Chapter%206%20-%20Padro%CC%83es%20de%20Projeto%2051dcf38bef8d450eba2a0af6036e7cb9/sequence_visitor_diagram.drawio)

![sequence_visitor_diagram.jpg](Chapter%206%20-%20Padro%CC%83es%20de%20Projeto%2051dcf38bef8d450eba2a0af6036e7cb9/sequence_visitor_diagram.jpg)

12. Em uma entrevista dada ao site InformIT, em 2009, por ocasião dos 15 anos do lançamento da primeira edição do GoF, três dos autores do livro mencionaram que — se tivessem que lançar uma segunda edição do trabalho — provavelmente manteriam os padrões originais e incluiriam alguns novos, que se tornaram comuns desde o lançamento da primeira edição, em 1994. Um dos novos padrões que eles mencionaram na entrevista é chamado de **Null Object**. Estude e explique o funcionamento e os benefícios desse padrão de projeto. Para isso, você vai encontrar diversos artigos na Web. Mas se preferir consultar um livro, uma boa referência é o Capítulo 25 do livro *Agile Principles, Patterns, and Practices in C#*, de Robert C. Martin e Micah Martin. Ou então o refactoring chamado Introduce Null Object do livro de Refactoring de Martin Fowler.

Caracteristica

- Inves de perguntar pelo tipo null e depois agir conforme a resposta, com null object invoca o comportamento do objeto, se o mesmo for o correto, o comportamento será executado.

Comportamento

- O null Object é uma instancia unica da classe alvo, aplica-se singleton para nao termos uma imensidao de objetos nulos pelo sistema.

Beneficios

- Elimina a duplicidade de codigo
- Desacopla de outras dependencias externas como sessoes, conexoes com banco e etc
- Aplica o “tell, don’t ask”

[http://silab.fon.bg.ac.rs/wp-content/uploads/2016/10/Refactoring-Improving-the-Design-of-Existing-Code-Addison-Wesley-Professional-1999.pdf](http://silab.fon.bg.ac.rs/wp-content/uploads/2016/10/Refactoring-Improving-the-Design-of-Existing-Code-Addison-Wesley-Professional-1999.pdf)

[https://dev.to/omarkdev/design-patterns-null-object-4fk](https://dev.to/omarkdev/design-patterns-null-object-4fk)