# Chapter 7 - Arquitetura

## **Exercícios de Fixação [🔗](https://engsoftmoderna.info/cap7.html#exerc%C3%ADcios-de-fixa%C3%A7%C3%A3o)**

1. Dada a sua complexidade, sistemas de bancos de dados são componentes relevantes na arquitetura de qualquer tipo de sistema. Verdadeiro ou falso? Justifique a sua resposta.

- Em sistemas monolitos sim, pois a mudança na definição de estrutura dos dados podem impactar diferentes modulos do sistemas.
    
    Entretanto em sistemas baseados em microservico, cada parte do sistema é um pequeno servico com sua propria base de dados.
    

2. Descreva três vantagens de arquiteturas MVC.

- Favorece o trabalho especializado, podemos alocar desenvolvedores somente na front end (views), e desenvolvedores no backend, ou seja models, controllers, e etc
- Reuso de classes modelo (models) em diferentes views.
- MVC favorece a testabilidade, pois e mais facil testar objetos nao visuais.

3. Qual a diferença entre classes Controladoras em uma Arquitetura MVC tradicional e classes Controladoras de um sistema Web implementado usando um framework MVC como Ruby on Rails?

No modelo tradicional, classes controladoras atuam juntamente com a camada de visão

- Ou seja temos 3 camadas

No modelo web, classes controladores atuam como controladores de requisições e gerando novas visoes conforme a requisição.

- Esse modelo lembra bastante arquitetura 3 camadas

Imagem de arquitetura 3 camadas 

![Untitled](Chapter%207%20-%20Arquitetura%20f52bb1645ab24b39b44c58fbce4ddedd/Untitled.png)

Imagem MVC CLASSICO (smaltalk80)

![Untitled](Chapter%207%20-%20Arquitetura%20f52bb1645ab24b39b44c58fbce4ddedd/Untitled%201.png)

Imagem de MVC WEB

![Untitled](Chapter%207%20-%20Arquitetura%20f52bb1645ab24b39b44c58fbce4ddedd/Untitled%202.png)

4. Descreva resumidamente quatro vantagens de microsserviços.

- Microservicos autonomos e independentes
- Microservicos possuem falhas parciais
- Microservicos escalam horizontalmente (cloud e virtual machines)
- Times distribuidos globalmente

5. Por que microsserviços não são uma bala de prata? Isto é, descreva pelo menos três desvantagens do uso de microsserviços.

- Complexidade: entendimento de comunicação em redes (HTTP/REST)
    - Exemplo
        - quando dois módulos executam em um mesmo processo, a comunicação entre eles é por meio de chamadas de métodos. Quando esses módulos estão em máquinas diferentes, a comunicação entre eles deve usar algum protocolo de comunicação, como **HTTP/REST**
    
    Ilustração de como ocorre a comuniçao em maquinas separadas vs em uma maquina.
    
    ![processos_rest_micro.jpg](Chapter%207%20-%20Arquitetura%20f52bb1645ab24b39b44c58fbce4ddedd/processos_rest_micro.jpg)
    

6. Explique a relação entre a Lei de Conway e microsserviços.

- Conway explica que um sistema será o reflexo da estrutura organizacional da empresa, ou seja empresas gigantes de tecnologia de forma global, seus times sao distribuidos geograficamente e autonomos, alem de pequenos, isso reflete na organização dos sistemas.

7. Explique o que significa desacoplamento no espaço e desacoplamento no tempo. Por que arquiteturas baseadas em filas de mensagens e arquiteturas Publish/Subscribe oferecem essas formas de desacoplamento?

- Desacoplamento no espaço significa que cliente e servidor nao precisam se conhecer  para que o servidor consuma a informação produzida pelo cliente.
    - Filas de mensagens fornecem um desacoplamente no espaco, permitindo que times que desenvolvam a solução cliente e times que desenvolvam a solução do servidor nao fiquem travados, pois a fila fornece esse desacoplamento, a regra é que o formato das mensagens seja estavel ao longo do tempo evolutivo das soluções.
    
- Desacoplamento no tempo significa que cliente e servidor nao precisam estar constantemente disponíveis para consumir a informação produzida.
    - O desacoplamento torna a solução robusta a falhas, pois o sistema servidor pode ficar indisponiveis e as mensagens serão consumidas posteriormente quando o mesmo ficar disponiveis, entretanto a regra neste cenário é que o broker de mensagens seja robusto o suficiente para armenzar um grande numero de mensagens,.

8. Quando uma empresa deve considerar o uso de uma arquitetura baseada em filas de mensagens ou uma arquitetura publish/subscribe?

- Quando a comunição for de 1:1 e nao necessita ser em tempo real, o emprego de uma fila atenderá, pois esse tipo arquitetura é ponto a ponto onde o sistema cliente produz msgs que serão consumidas pelo sistema cliente.
    - Essa arquitetura fornece desacoplamente entre os sistemas
    - O sistema servidor precisa sempre consultar a fila por novas msgs a serem consumidas

- Quando se necessita de uma comunicação em grupo, com multiplos sistemas servidores interessados em uma msg produzida por um cliente, entao devemos implementar uma arquitetura pub\sub pois o cliente produzira uma msg que sera armazenada no broker, onde que os assinantes daquele topico que a msg produzida foi gerada, serão notificados que há novas msgs a serem puxadas (pull), esse tipo arquitetura é assincrona.
    - produtores e consumidores sao processos separados e na maioria das vezes distribuidos..

9. Explique o objetivo do conceito de tópicos em uma arquitetura publish/subscribe.

Um cliente assina um tópico ao invés de todas mensagens que tenha interesse 

10. (POSCOMP, 2019, adaptado) Marque V ou F.

(v ) O padrão MVC é uma adaptação do padrão arquitetural Camadas. A Camada Visão lida com a apresentação e a manipulação da interface, a Camada Modelo organiza os objetos específicos da aplicação, e a Camada Controle posiciona-se entre estas duas com as regras do negócio.

(v ) O padrão Broker é voltado a problemas de ambientes distribuídos. Sugere uma arquitetura na qual um componente (broker) estabelece uma mediação que permite um desacoplamento entre clientes e servidores.

(v ) Mesmo que um dado padrão arquitetural ofereça uma solução para o problema sendo resolvido, nem sempre ele é adequado. Fatores como contexto e o sistema de forças que afeta a solução fazem também parte do processo de avaliação e da escolha de padrões adequados.