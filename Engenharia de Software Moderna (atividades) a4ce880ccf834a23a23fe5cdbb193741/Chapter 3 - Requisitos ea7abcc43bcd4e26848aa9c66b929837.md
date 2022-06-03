# Chapter 3 - Requisitos

## **Exercícios de Fixação [🔗](https://engsoftmoderna.info/cap3.html#exerc%C3%ADcios-de-fixa%C3%A7%C3%A3o)**

1. [POSCOMP 2010, adaptado] Sobre Engenharia de Requisitos, marque Verdadeiro (V) ou Falso (F).

(v) A Engenharia de Requisitos, como todas as outras atividades de Engenharia de Software, precisa ser adaptada às necessidades do processo, do projeto, do produto e do pessoal que está fazendo o trabalho.

(f) No estágio de levantamento e análise dos requisitos, os membros da equipe técnica de desenvolvimento do software trabalham com o cliente e os usuários finais do sistema para descobrir mais informações sobre o domínio da aplicação, que serviços o sistema deve oferecer, o desempenho exigido do sistema, as restrições de hardware, dentre outras informações.

(f) Na medida em que a informação de vários pontos de vista é coletada, os requisitos emergentes são consistentes.

(v) A validação de requisitos se ocupa de mostrar que estes realmente definem o sistema que o cliente deseja. Ela é importante porque a ocorrência de erros em um documento de requisitos pode levar a grandes custos relacionados ao retrabalho.

2. Cite o nome de pelo menos cinco técnicas para elicitação de requisitos.

- entrevistas com stakeholders
- aplicacao de questionarios
- leitura de documentos e formularios da contratante
- implementacao de prototipos
- analise de cenarios de uso

3. Quais são as três partes de uma história de usuário? Responda usando o acrônimo 3C's.

Historia de usuario = Cartao + Conversas + Confirmacao

4. Suponha uma rede social como o Facebook. 

(1) Escreva um conjunto de cinco histórias para essa rede, assumindo o papel de um usuário típico; 

Como um usuário típico eu gostaria de adicionar amigos

Como um usuário típico eu gostaria de remover amigos

Como um usuário típico eu gostaria de bloquear contato de outros usuários comigo

Como um usuário típico eu gostaria de publicar conteudo multimida para todos da rede social

Como um usuário típico eu gostaria de publicar conteudo multimidia para apenas meus amigos

(2) Pense agora em mais um papel de usuário e escreva pelo menos duas histórias para ele.

Como um administrador de grupo eu gostaria de excluir postagens de membros do grupo

Como um administrador de grupo eu gostaria de promover outros membros a administradores

Como um administrador de grupo eu gostaria de criar filtros para monitorar postagens que violem um conjunto de regras pre-definidas

5. Em Engenharia de Software, *anti-patterns* são soluções não recomendadas para um certo problema. Escreva pelo menos cinco *anti-patterns* para histórias de usuários. Em outras palavras, descreva formatos de histórias que não são recomendados ou que não possuem propriedades recomendáveis.

- historias dependentes
- historias fechadas para negociacao
- historias que nao agregam valor
- historias que nao sao viaveis de implementar
- historias longas
- historias que nao sao possiveis de testar

Ou seja as historias devem seguir a sigla INVEST

6. Pense em um sistema e escreva uma história épica para o mesmo.

Como um usuário eu gostaria de retirar meu produto em qualquer agencia com estoque disponível

7. No contexto de requisitos, o que significa a expressão *gold plating*?

Quando os desenvolvedores decidem, por contra própria sofisticar a implementacao de alguma historias

8. Escreva um caso de uso para um Sistema de Controle de Bibliotecas (similar ao que usamos para ilustrar a escrita de histórias na Seção 3.3.1).

Gerar boleto para pagamento de multa de atraso na entrega do livro

***Ator:** Cliente da Biblioteca*

***Fluxo normal:***

*1 - Autenticar Cliente (sublinhado)*

*2 - Cliente informa cpf no modal de aviso da multa por atraso na entrega*

3 *- Sistema envia o boleto para email do cliente*

***Extensões:***

*2a - Se cpf incorreto, solicitar novamente*

9. O seguinte caso de uso possui apenas o fluxo normal. Escreva então algumas extensões para ele.

Comprar Livro

Ator:  Usuário da loja virtual

     Fluxo normal:

            Usuário pesquisa catálogo de livros

      Usuário seleciona livros e coloca no carrinho de compra

Usuário decide fechar a compra

Usuário seleciona endereço de entrega

Usuário seleciona tipo de entrega

Usuário seleciona modo de pagamento

Usuário confirma pedido

Extensoes

2a. Se usuario pesquisa por livro inexistente, entao retorna nao encontrado

2b. Se usuario seleciona um cep invalido, entao retorna cep invalido

2.c Se usuario informa o modo de pagamento com cartao vencido, entao retorna cartao invalido

10. Para cada técnica de especificação e/ou validação de requisitos a seguir, descreva um sistema no qual o seu uso seria mais recomendado: 

(1) Histórias de Usuários; 
       Sistemas com regras de negocios complexas e fazendo uso de metologias ageis com a presenca do dono do produto

(2) Casos de Uso; 
       Sistemas com requisitos estaveis

(3) MVPs.

Sistemas que precisem estar logo no mercado para validar ideias

11. Qual a diferença entre um Produto Mínimo Viável (MVP) e o produto obtido na primeira iteração de um método ágil, como XP ou Scrum?
        O mvp terá o minimo para ser utilizavel, sem necessáriamente atender as metricas de qualidade, enquanto que em metodologias ageis sera entregue o priorizado pelo cliente.

12. O artigo *Failures to be celebrated: an analysis of major pivots of software startups* ([link](https://arxiv.org/abs/1710.04037)) apresenta uma discussão sobre quase 50 casos reais de pivôs em startups da área de software. Na Seção 2.3, o artigo apresenta uma classificação de dez tipos de pivô comuns nessas startups. Leia essa parte do artigo, liste pelo menos cinco tipos de pivôs e faça uma breve descrição de cada um deles.

       1. Zoom In Pivot
       Uma unica funcionalidade se torna o produto principal

2. Zoom Out Pivot 

Uma unica funcionalidade se torna parte de um grande produto

3. Customer Segment Pivot
Quando o segmento do produto muda

4. Customer Need Pivot
Quando a tentativa de resolucao do problema central nao interessa ao cliente, porem durante essa tentativa se descobre necessidades mais urgentes

5. Platform Pivot
Mudar de contexto de simples aplicacao para uma plataforma que suporte aplicacoes

13. Quando começou, a EasyTaxi — a empresa brasileira de aplicativos para solicitação de táxis — construiu um MVP que usava um software muito simples e uma parte operacional realizada de forma manual. Pesquise na Internet sobre esse MVP (basta usar as palavras EasyTaxi e MVP) e faça uma descrição do mesmo.

O EasyTaxi começou com um MVP "Concierge". A equipe de fundadores disponibilizava uma página web para que usuários entrassem manualmente o endereço onde estavam - e um *Submit* gerava um e-mail para os sócios. Estes, assim que recebiam uma mensagem, ligavam eles mesmos para as cooperativas pedindo um táxi para o endereço.

Bingo! Com isso, tudo começou. Os fundadores haviam validado uma hipótese básica: muitas pessoas estavam dispostas a usar um serviço que chamaria táxis para elas

14. Suponha que estamos em 2008, quando ainda não existia Spotify, e você decidiu criar uma startup para oferecer um serviço de streaming de músicas na Internet. Então, como primeiro passo, você implementou um MVP.

1. Quais seriam as principais funcionalidades desse MVP?
Um player de musica que pudesse reproduzir arquivos de audios recebidos via link compartilhavel
2. Ele seria desenvolvido para qual hardware e sistema operacional?
Servidor linux hospedado em algum provedor que tivesse escalabilidade
3. Elabore um rascunho rápido da sua interface com o usuário.
Um player de musica que reproduziria uma musica ou conjunto de musicas oriundos de links compartilhaveis.
4. Quais métricas você usaria para medir o sucesso/fracasso do MVP?
Quantiade de links compartilhados entre usuarios e plays por links

15. Suponha que você seja responsável por um sistema de comércio eletrônico. Suponha que na versão atual desse sistema (versão A) a mensagem do carrinho de compra seja Adicionar ao Carrinho. Suponha que você pretenda fazer um teste A/B testando a mensagem alternativa Compre Já, a qual vai corresponder à versão B do teste.

1. Qual seria a métrica usada como taxa de conversão nesse teste?
quantiade de compras efetivadas
2. Supondo que no sistema original a taxa de conversão seja de 5% e que você deseja avaliar um ganho de 1% com a mensagem da versão B, qual seria o tamanho da amostra que deveria testar em cada uma das versões? Para responder, use uma calculadora de tamanho de amostras de testes A/B, como aquela que citamos na Seção 3.6.
Teria que ser o valor equivalente a parte dessa populacao e avaliar o risco de rejeicao

Ou por exemplo 
Se após 200K acessos, a versão B aumentar a taxa de conversão em pelo menos 1% podemos ter certeza estatística de que esse ganho é causado pelo tratamento B 
E assim dividiriamos entre grupo A e B, e nos primeiros 100k usariam a versao original, apos isso usariam a versao com a msg adicionada, assim mensurando o impacto da msg.