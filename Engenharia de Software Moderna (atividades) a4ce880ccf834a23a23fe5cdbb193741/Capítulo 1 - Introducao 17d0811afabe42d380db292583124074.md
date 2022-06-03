# Capítulo 1 - Introducao

Exercícios

1. Segundo Frederick Brooks, desenvolvimento de software enfrenta dificuldades essenciais (para as quais não há bala de prata) e acidentais (para as quais existe uma solução melhor). Dê um exemplo de dificuldade acidental que já tenha experimentado ao desenvolver programas, mesmo que pequenos. Sugestão: elas podem estar relacionadas a ferramentas que tenha usado, como compiladores, IDEs, bancos de dados, sistemas operacionais, etc.

R: Pacotes entre Linux e Windows usados com python pelo pip, quebravam constantemente. 

2. Diferencie requisitos funcionais de requisitos não-funcionais.

R: Requisitos funcionais definem o que um sistema deve fazer, enquanto que requisitos não-funcionais definem como um sistema deve operar, sob quais restrições e com qual qualidade de serviço.

3. Explique porque testes podem ser considerados tanto uma atividade de verificação como de validação de software. Qual tipo de teste é mais adequado se o objetivo for verificação? Qual tipo de teste é mais adequado se o objetivo for validar um sistema de software?

R: Testes podem ser usados tanto para verificação como para validação de sistemas. 

Verificação tem como o objetivo garantir que um sistema atende à sua especificação. 

Validação, o objetivo é garantir que um sistema atende às necessidades de seus clientes. A diferença entre os conceitos só faz sentido porque pode ocorrer de a especificação de um sistema não expressar as necessidades de seus clientes.

Quando se realiza um teste de um método, para verificar se ele retorna o resultado especificado, estamos realizando uma atividade de verificação. Por outro lado, quando realizamos um teste funcional e de aceitação, ao lado do cliente, isto é, mostrando para ele os resultados e funcionalidades do sistema, estamos realizando uma atividade de validação.

4. Por que testes não conseguem provar a ausência de bugs?

R: Por que segundo Dijkstra “Testes de Software são para mostrar a presença de bugs e não sua ausência”

5. Suponha um programa que tenha uma única entrada: um inteiro de 64 bits. Em um teste exaustivo, temos que testar esse programa com todos os possíveis inteiros (logo, 264). Se cada teste levar 1 nanossegundo (10-9 segundos), quanto tempo levará esse teste exaustivo? (Exercício baseado em um comentário do livro de Fox & Patterson, link)

R: 2^64 * 10^9 = 1,84467441e10

6. Se considerarmos seu contexto histórico, por que foi natural que os primeiros processos de desenvolvimento de software tivessem características sequenciais e que fossem baseados em planejamento e documentação detalhados?

R: Por terem se baseado no princípio em modelos de outras engenharias, como a civil, por exemplo veja o processo waterfall.

7. Alguns estudos mostram que os custos com manutenção e evolução podem alcançar 80% ou mais dos custos totais alocados a um sistema de software, durante todo o seu ciclo de vida. Explique porque esse valor é tão alto.

R: Com o passar do tempo a manutenção custosa e arriscada.

8. Refactoring é normalmente definido como uma transformação de código que preserva comportamento. Qual o significado da expressão preservar comportamento? Na prática, qual restrição ela impõe a uma operação de refactoring?

R: O significado refere-se ao fator de efetuar melhorias na leitura e organização do código sem impactar em sua funcionalidade.

9. Dê exemplos de sistemas A (Acute, ou críticos) e B (Business, ou comerciais) com os quais já tenha interagido

R: Acute : Sistemas de Instrumentação de aeronaves 

Business : Sistema de pagamento via maquina

10. Dê exemplos de sistemas C (casuais) que você já tenha desenvolvido.

R: Sistema para envio de emails 

11. Em 2015, descobriu-se que o software instalado em mais de 11 milhões de carros da Volkswagen detectava quando eles estavam sendo testados em um laboratório de certificação. Nessas situações, o carro emitia poluentes dentro das normas legais. Fora do laboratório, emitia-se mais poluentes, para melhorar o desempenho. Ou seja, o código provavelmente incluía uma estrutura de decisão como a seguinte (meramente ilustrativa, para fins deste exercício): if "Carro sendo testado em um laboratório" "Emita poluentes dentro das normas" else "Emita poluentes fora das normas" O que você faria se seu chefe pedisse para escrever um if como o acima? (para mais informações sobre esse episódio com automóveis Volkswagen, consulte essa página da Wikipedia).

R: Poderia até escrever, porém iria alertá-lo dos impactos e consequências.