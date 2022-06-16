# Chapter 10 - DevOps

## **Exercícios de Fixação [🔗](https://engsoftmoderna.info/cap10.html#exerc%C3%ADcios-de-fixa%C3%A7%C3%A3o)**

1. Defina e descreva os objetivos de DevOps.

- aproximar o time de operacoes do time de desenvolvimento, visando antecipar problemas de implantacao de sistemas, para que ocorram entregas mais ageis e em curto espaco de tempo, e que essas implantacoes sejam em dias uteis com todos na empresas

2. Em sites de oferta de empregos na área de TI, é comum encontrar vagas para Engenheiro DevOps, requerendo habilidades como as seguintes:

- Ferramentas de controle de versão (Git, Bitbucket, SVN, etc.)
- Gerenciadores de dependência e build (Maven, Gradle, etc.)
- Ferramentas de integração contínua (Jenkins, Bamboo, VSTS)
- Administração de servidores em Cloud (AWS e Azure)
- Sistemas Operacionais (Ubuntu, CentOS e Red Hat)
- Banco de dados (DynamoDB, Aurora Mysql)
- Docker e orquestração de Docker (Kubernetes, Mesos, Swarm)
- Desenvolvimento com APIs REST, Java

Considerando a definição de DevOps que usou como resposta no exercício anterior, você considera adequado que a função de um funcionário seja Engenheiro DevOps? Justifique a sua resposta.

- Nao necessariamente, afinal a cultura devops nao advoga a criacao de um novo perfil de trabalho, mas sim a aproximacao do profissional de operacoes e do profissional de desenvolvimento

3. Descreva duas vantagens de um Sistema de Controle de Versões Distribuído (DVCS), como o git.

- serem distribuidos e permitirem aos desenvolvedores possuirem um sistema completo de versionamento em sua maquina
- permite que desenvolvedores trabalhem de forma independente

4. Descreva uma desvantagem relacionada com o uso de mono-repositórios.

- dificulta o trabalho do desenvolvedor em base de codigo gigantescas

5. Defina (e diferencie) os seguintes termos: integração contínua (*continuous integration*); entrega contínua (*continuous delivery*) e deployment contínuo (*continuous deployment*).

- CI
    - codigo local deve sempre ser integrado a branch master em menos tempo
- CDelivery
    - entrega continua aos clientes finais
- CDeploy
    - codigo é testado e buildado com sucesso sem erros

6. Por que integração contínua, entrega contínua e deployment contínuo são práticas importantes em DevOps? Na sua resposta, considere a definição de DevOps que usou no primeiro exercício desta lista.

- acelera o fluxo de entrega de features ou bugfixes para o cliente final, e remove o trauma de implantacao longas e dolorosas

7. Pesquise o significado da expressão Teatro de CI (*CI Theater*) e então descreva-o com suas próprias palavras.

- que por usar uma ferramenta de CI, as pessoas acreditam estarem praticando a cultura, enquanto seguem trabalhando isoladas a fio por semanas, e quando surgem para um code review, o mesmo e gigantesco e com varios arquivos e linhas de codigo.

8. Suponha que você foi contratado por uma empresa que fabrica impressoras. E que você ficou responsável por definir as práticas de DevOps que serão adotadas no desenvolvimento dos *drivers* (software) dessas impressoras. Qual das seguintes práticas você adotaria nesse desenvolvimento: deployment contínuo ou delivery contínuo? Justifique sua resposta.

- o deployment continuo, pois a questao do delivery deve ser feita por managers, por que o evento de update do driver nao e transparente para o usuario como sistemas web.

9. Descreva um problema (ou dificuldade) que surge quando decide-se usar feature flags para delimitar código que ainda não está pronto para entrar em produção.

- codigo duplicado

10. Linguagens como C possuem suporte a diretivas de compilação condicional do tipo `#ifdef` e `#endif`. Pesquise o funcionamento e o uso dessas diretivas. Qual a diferença entre elas e feature flags?

- sao blocos condicionados a sua execucao somente se o nome da macro for definida

11. Qual tipo de feature flags possui maior tempo de vida (isto é, permanece no código por mais tempo): *release flags* ou *business flags*? Justifique sua resposta.

- business flags, por se tratarem de regras de negocio, enquanto que release  flags sao referentes a funcionalidades parcialmente prontas que pode estar desabilitadas temporariamente, que apos concluidas a flag pode ser removida.

12. Quando uma empresa migra para CI, normalmente ela não usa mais branches de funcionalidades (*feature branches*). Em vez disso, ela tem um único branch, que é compartilhado por todos os desenvolvedores. Essa prática é chamada Desenvolvimento Baseado no Trunk (ou TBD), conforme estudamos neste capítulo. No entanto, TBD não significa que branches não são mais usados nessas empresas. Descreva então um outro uso para branches, que não seja como *feature branches*.

- branch master, onde todo trabalho é concentrado, auxiliando a identificar problemas de integração mais cedo.

13. Leia o seguinte [artigo](https://gmail.googleblog.com/2011/12/developing-gmails-new-look.html) do blog oficial do GMail, que descreve uma grande atualização realizada na interface do sistema, em 2011. O artigo chega a comparar os desafios dessa migração com aqueles de trocar os pneus de um carro com ele em movimento. Sobre esse artigo, responda então:

1. Qual tecnologia — que estudamos neste capítulo — foi fundamental para viabilizar essa atualização na interface do GMail? Qual nome o artigo dá para essa tecnologia?
    - conditional features
2. E qual nome usamos no capítulo para referenciá-la?
    - feature flag