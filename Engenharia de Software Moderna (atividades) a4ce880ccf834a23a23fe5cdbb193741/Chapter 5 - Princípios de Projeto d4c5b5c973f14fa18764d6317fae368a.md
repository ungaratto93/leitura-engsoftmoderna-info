# Chapter 5 - Princípios de Projeto

Interessante guardar isso em mente 

![Untitled](Chapter%205%20-%20Princi%CC%81pios%20de%20Projeto%20d4c5b5c973f14fa18764d6317fae368a/Untitled.png)

mais uma coisa interessante

COESAO, FAZ APENAS UMA MERDA DIREITO, SEU CAVALO
COESAO = Responsabilidade Única
COESAO = Segregação de Interfaces

ACOPLAMENTO, NAO MANTEM TUDO GRUDADO, SENAO DEPOIS DA TRABALHO DOBRADO, DOENTE!
ACOPLAMENTO = Inversão de Dependências
ACOPLAMENTO = Prefira Composição a Herança
ACOPLAMENTO = Ocultamento de Informação

DEMETER, A LEI QUE VAI TE SALVAR DE REVELAR O OURO PRO BANDIDO FACISTA DO BOIOLOSAURO
Ocultamento de Informação

Extensibilidade, VAMOS EVOLUIR AS COISAS DA FORMA CERTA
Aberto/Fechado

Extensibilidade, SE NOS TROCAR AS PECINHA, TUDO CONTINUA GIRANDO
Substituição de Liskov

principios solid

Single Responsibility Principle
Open Closed/Principle
Liskov Substitution Principle
Interface Segregation Principle
Dependency Inversion Principle

comentario do exemplo do jornaleiro em  demeter

nao faz sentido o jornaleiro chamar um metodo pagar de cliente
faz sentido jornaleiro ter um metodo cobrar assim:

j = New Jornaleiro(id)

j.cobrar(CLiente cliente)

ai o cliente seria avisado sei la

ai la no cliente poderia ter algo como

c = New Cliente(id)
c.pagar(Jornaleiro jornaleiro)

e que pensando na logica,  um jornaleiro nao acessa cliente invocar algum pagamento

"o cliente oferece um método pagar, que deve ser chamado pelo jornaleiro."

isso ao meu ver nao faz sentido

eu acho que seria melhor no fim, algo assim em historia de usuario

- jornaleiro pode cobrar um cliente
- cliente pode pagar um jornaleiro

eu to tratando como um cliente do jornaleiro, e nao um cliente de aplicacao em tempo de execucao

tipo acho que o autor deve estar tratando cliente nesse contexto como um cliente de aplicacao

tipo o jornaleiro abre um sistema que vai ter uma area com botao pagar, ai ele mostraria para o comprador clicar e efetuar o pagamento

porem mesmo assim acharia mais facil ter um metodo cobrar em jornaleiro, onde receberia algum ID do comprador a ser cobrado pela compra

ou relendo ali

seja o cenario do jornaleiro invocar cliente.pagar() por meio de cobrar , deve ser isso

so se for algo assim....

class Jornaleiro() {

```
private Cliente cliente

void cobrar(Cliente cliente, float preco) {
    try {
        cliente.pagar(preco);
    }
    catch (ExcecaoValorInsuficiente e) {
        // volto amanhã, para cobrar o valor do jornal
    }
}

```

}

—————————————————————————————————————

## **Exercícios de Fixação [🔗](https://engsoftmoderna.info/cap5.html#exerc%C3%ADcios-de-fixa%C3%A7%C3%A3o)**

1. Descreva três benefícios da propriedade de projeto chamada ocultamento de informação (*information hiding*)?

1. Desenvolvimento em paralelo,  classes que escondam suas informações, sao mais faceis de serem implementadas em paralelo por desenvolvedores diferente, e por consequencia se reduz o tempo de implementacao.
2. Flexibilidade a mudancas, clases que isolam os detalhes de sua implementacao, sao mais faceis de serem substituidas.
3. Facilidade de entendimento, novos desenvolvedores precisam enteder apenas as classes que iram trabalhar,  e isso e possivel com o ocultamento da implementacao das classes entre si.

2. Suponha que um programador adote a seguinte estratégia: ao implementar qualquer nova funcionalidade ou corrigir um bug que implique na modificação de duas classes A e B localizadas em arquivos diferentes, ele conclui a tarefa movendo as classes para o mesmo arquivo. Explicando melhor: após terminar a tarefa de programação que ficou sob sua responsabilidade, ele escolhe uma das classes, digamos a classe B, e a move para o mesmo arquivo da classe A. Agindo dessa maneira, ele estará melhorando qual propriedade de projeto? Por outro lado, qual propriedade de projeto estará sendo afetada de modo negativo? Justifique.

De modo negativo irá perder a modularização e o desenvolvimento em paralelo, e do ponto de vista estaria melhorando a facilidade de entendimento pois o desenvolvedor teria as duas classes no mesmo arquivo para leitura sem precisar navegar entre modulos.

3. **Classitis** é o nome dado por John Ousterhout à proliferação de pequenas classes em um sistema. Segundo ele, *classitis* pode resultar em classes que individualmente são simples, mas que aumentam a complexidade total de um sistema. Usando os conceitos de acoplamento e coesão, como podemos explicar o problema causado por essa doença?

Classes muito simplistas e interdependentes entre sí, ou seja uma baixa coesao por serem muito pequenas e simples e nao fazerem nada sozinhas, e um acoplamento alto pois precisam de outras para realizar suas atividades de forma completa.

4. Defina: 

(a) acoplamento aceitável; 

- Quando uma classe usa apenas metodos publicos de outra classe
- A interface provida pela classe é estavel semanticamente (sentido ) e sintaticamente (escrita correta)

(b) acoplamento ruim; 

- Quando uma classe A acessa diretamente arquivos ou banco de dados da classe B
- Quando as classes compartilham o uso de uma variavel ou estrutura de dados global.

(c) acoplamento estrutural; 

- Ocorre  quando uma classe A possui uma referencia explicita para B

(d) acoplamento evolutivo (ou lógico).

- Ocorre quando mudancas na classe B tendem a se propagar para classe A

5. Dê um exemplo de:

 (1) acoplamento estrutural e aceitável; 

- Quando o acoplamento é direto, e explicito.

(2) acoplamento estrutural e ruim.

- Quando o acoplamento é indireto e implicito, no caso na dependencia de lib em 3 nível.

6. É possível que uma classe A esteja acoplada a uma classe B sem ter uma referência para B em seu código? Se sim, esse acoplamento será aceitável ou será um acoplamento ruim?

Sim, será um acoplamento ruim e dificil de manter, pois os desenvolvedores nao terao ciencia do impacto que o arquivo compartilhado causa nas classes.

7. Suponha um programa em que todo o código está implementado no método `main`. Ele tem um problema de coesão ou acoplamento? Justifique.

Teremos um problema de acoplamento, pois todo nosso codigo estará implementado apenas em uma classe, tornando-o com o passar do tempo  mais complexo de manter e dar suporte, sem falar no fato de toda regra de negocio estar misturada.

8. Qual princípio de projeto é violado pelo seguinte código?

```
void onclick() {
  num1 = textfield1.value();
  c1 = BD.getConta(num1)
  num2 = textfield2.value();
  c2 = BD.getConta(num2)
  valor = textfield3.value();
  beginTransaction();
  try {
    c1.retira(valor);
    c2.deposita(valor);
    commit();
  }
  catch() {
    rollback();
  }
}
```

- Responsabilidade Única
    - Afinal a função onclick faz muito mais que apenas capturar o valor no momento do click,
        
        ocorre operacao em banco de dados para recuperar contas, abre uma transaction, efetua operacoes de retirada e depositos nessas contas, por fim o commit e em caso de erro um rollback
        

9. Costuma-se afirmar que existem três conceitos chaves em orientação a objetos: encapsulamento, polimorfismo e herança. Suponha que você tenha sido encarregado de projetar uma nova linguagem de programação. Suponha ainda que você poderá escolher apenas dois dos três conceitos que mencionamos. Qual dos conceitos eliminaria então da sua nova linguagem? Justifique sua resposta.

Removeria a heranca, por causar muito acoplamento  e  classes menos flexiveis.

Por exemplo, uma classe A que implemente um metodo X de uma forma m, caso efetue uma alteracao nesse metodo m, todos clientes que herdam, sofreriam o impacto da mudanca. 

No caso, poderia se usar composicao, com classe A e B com metodos m distintos, e clientes interessados iriam compor conforme sua necessidade

10. Qual princípio de projeto é violado pelo seguinte código? Como você poderia alterar o código do método para atender a esse princípio?

```
void sendMail(ContaBancaria conta, String msg) {
  Cliente cliente = conta.getCliente();
  String mail = cliente.getMailAddress();
  "Envia mail"
}
```

- Inversao de dependencia, pois estamos dependendo de uma classe concreta para executar tal metodo, o mesmo torna-se inutil para outros tipos de conta.

11. Qual princípio de projeto é violado pelo seguinte código? Como você poderia alterar o código do método para atender a esse princípio?

```
void imprimeDataContratacao(Funcionario func) {
  Date data = func.getDataContratacao();
  String msg = data.format();
  System.out.println(msg);
}
```

- Responsabilidade unica, pois a funcao faz alem de imprimir a data, ela recupera a data, formata e entao imprimi.

```java
Data data = func.getDataContracao();

private Date formataData(Date data) {
	return data.format()
}

void imprimiDataContratacao(Data data) {
	System.out.println(data);
}
```

12. As pré-condições de um método são expressões booleanas envolvendo seus parâmetros (e, possivelmente, o estado de sua classe) que devem ser verdadeiras antes da sua execução. De forma semelhante, as pós-condições são expressões booleanas envolvendo o resultado do método. Considerando essas definições, qual princípio de projeto é violado pelo código abaixo?

```
class A {
  int f(int x) { // pre: x > 0
    ...
    return exp;
  }              // pos: exp > 0
  ...
}
```

```
class B extends A {
  int f(int x) { // pre: x > 10
  ...
  return exp;
  }              // pos: exp > -50
  ...
}
```

- Prefira composicao a heranca,  e o retorno em pre e pos:estao diferentes, violando o contrato estabelicido na classe pai

13. Calcule o CBO e LCOM da seguinte classe:

```
class A extends B {

  C f1, f2, f3;

  void m1(D p) {
    "usa f1 e f2"
  }
  void m2(E p) {
    "usa f2 e f3"
  }
  void m3(F p) {
    "usa f3"
  }
}
```

CBO: 4

LCOM: 2

14. Qual das seguintes classes é mais coesa? Justifique computando os valores de LCOM de cada uma delas.

```
class A {

  X x = new X();

  void f() {
    x.m1();
  }
  void g() {
    x.m2();
  }
  void h() {
    x.m3();
  }
}
LCOM 1
```

```
class B {

  X x = new X();
  Y y = new Y();
  Z z = new Z();

  void f() {
    x.m();
  }

  void g() {
    y.m();
  }

  void h() {
    z.m();
  }
}
LCOM 3
```

- A e mais coesa que B, por usar um unico atributo em todos metodos da classe

15. Por que a métrica LCOM mede a ausência e não a presença de coesão? Justifique.

- A metrica foi projetada para mensurar a ausencia de coesao na classe, conforme o seu nome lack of cohesion, entao quanto maior a pontuacao pior sera a coesao da sua classe.
    
    Entao ela foi projetada para medir a falta, pois quanto mais coesao a classe possuir, melhor será.
    

16. Todos os métodos de uma classe devem ser considerados no cálculo de LCOM? Sim ou não? Justifique.

- Não, metodos acessores e escritores nao devem ser considerados, getters e setters

17. A definição de complexidade ciclomática é independente de linguagem de programação. Sim ou não? Justifique.

- Sim, pois a analise e dada conforme a quantiade de diretivas de controle de fluxo. somando-se 1

18. Dê um exemplo de código com complexidade ciclomática mínima. Qual é essa complexidade?

- Codigos com a complexidade ciclomatica com valor 1, codigo qual nao possui nenhum comando condicional.

19. Cristina Lopes — professora da Universidade da Califórnia, em Irvine, nos EUA — é autora de um livro sobre estilos de programação ([link](https://dl.acm.org/citation.cfm?id=2648631)). Ela discute no livro diversos estilos para implementação de um mesmo problema, chamado frequência de termos. Dado um arquivo texto, deve-se listar as *n*-palavras mais frequentes em ordem decrescente de frequência e ignorando *stop words*, isto é, artigos, preposições, etc. O código fonte em Python de todas as versões analisadas no livro está publicamente disponível no GitHub (e, para esse exercício, fizemos um fork do repositório original). Faça uma análise de duas dessas versões:

- Monolítica, disponível neste [link](https://github.com/mtov/exercises-in-programming-style/tree/master/04-monolith).
- Orientada a objetos, disponível neste [link](https://github.com/mtov/exercises-in-programming-style/tree/master/11-things).

Primeiro, revise e estude o código das duas versões (cada versão tem menos de 100 linhas). Em seguida, argumente sobre as vantagens da solução OO sobre a versão monolítica. Para isso, tente extrapolar o tamanho do sistema. Suponha que ele será implementado por desenvolvedores diferentes e que cada um ficará responsável por uma parte do projeto.

- Vantagens da versao OO sobre a versao monolitica
    - modularizada
    - limites entre classes (capsula)
    - legivel
    - facil de enteder o dominio
    - encapsulamento dos dados
    - dados expostos por intermedio de procedimentos
    - procedimentos reusaveis entre classes

- a solucao oo e mais facil de dar manutencao, pois nao acoplamento entre as funcionalidades, e a logica imposta na solutiva do escopo deste problema.