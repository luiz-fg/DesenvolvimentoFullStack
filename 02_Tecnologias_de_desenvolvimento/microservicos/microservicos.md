
<h1 style="color: #E1BE5A;">MICROSERVIÇOS</h1>

##### Professores: Vinicius Soares e Luis Fernando Planella Gonzalez.


>"Hoje <i>**dados e informações**</i> são as coisas <br>
>mais valiosas que tem." <br>
>**<i>Eugenio Facchini Neto</i>**

<br>

## Ementa da disciplina

- Estudo sobre a arquitetura de microserviços.
- Estudo sobre conceitos de particionamento de serviços, replicação e distribuição.
- Comunicação assincrona via filas
- Soluções serveless.
------------
<br>

#### SOA - Service Oriented Architecture

-   NÃO é uma tecnologia
-   NÃO é um produto
-   NÃO é um webservice
-   NÃO é um software
-   NÃO é um framework
-   NÃO é uma metodologia
-   NÃO é uma solução de negócio.

SOA é uma abordagem arquitetural corporativa que permite a criação de serviços de negócio interoperáveis que podem ser facilmente reutilizados e compartilhados entre aplicações e empresas.

**Visão geral**
SOA é uma arquitetura baseada em reusabilidade com serviços bem definidos e providos de componentes de ti, seus componentes possuem baixo acomplamento.
Ela provê plataforma, tecnologia e linguagens independentes.

**Benefícios**
-   Desacoplamento
    -   Integrações inteligentes, flexibilidade, alinhamento com negócio.
-   Reutilização de serviços
    -   Produtividade, manutenibilidade
-   Infraestrutura de plataforma
    -   Padronização corporativa (log, Governança, etc...)

#### Monolito X Microserviços

##### Monolito
Em uma arquitetura monolitica típica de um sistema complexo todas as funções do negócio estão implementadas em um unico processo.

**Vantagens**
-   Fácil de desenvolver
-   Fácil manutenção
-   Apenas um deploy
-   Tráfego de rede baixo.


**Problemas**
-   Aumento da complexidade e tamanho ao longo do tempo
-   Alta dependência de componentes de código
-   Escalabilidade do sistema é limitada
-   Falta de flexibilidade
-   Dificuldade para colocar alterações em produção.

O monolito possui vantagens e desvantagens.
Uma das grandes desvantagens é que a dificuldade em escalar o sistema. Muito comum que cada cliente que você tiver, terá que replicar/duplicar o servidor, duplicando o custo.

<i>Quanto mais clientes houverem, mais servidores serão necessários, mais caro irá se tornar.</i>

#####Microserviços
>"Um serviço com um único propósito e que execute bem a sua tarefa dentro de un nível de granularidade e suporte as mudanças dos sistemas que são considerados
<br>
>imporatntes tanto em tempo de projeto quanto em tempo de execução.
<br>
>O foco principal é tentar construir software que pode se adaptar e isto só é possível de ser feito se as partes forem pequenas suficientes para
<br>
>se ajustar às diferenças nas mudanças de sua arquitetura."
<br>
><i>Russ Mile</i>

**Vantagens**
-   Manutenção e evolução dos serviços mais estáveis
-   Serviços com baixo nível de acoplamento e interdependência
-   Escalabilidade do sistema
-   Redução de custos
-   Flexibilidade de tecnologia
-   Facilidade de colocar alterações em produção
-   Resiliencia
-   Aumento da produtividade
-   Implementação de entrega contínua
-   Monitoramento e automação de processos
-   Foco na entrega de valor ao cliente

**Riscos**
-   Aumento da complexidade de coordenação
-   Comunicação entre os microsserviços
-   Governança

**Caracteristicas**
-   Software modularizado em pequenos serviços que comunicam atra´ves de uma forma padronizada.
-   Se cominicam através de uma API Restfull(HTTP / json)

**Características técnicas**
-   Out-of-process
    -   Possibilidade de execução fora dos processos
-   Chamadas remotidas
    -   Microsserviços são acessados por chamadas remotas
-   Independente de linguagem de programação
    -   São agnósticos a linguagem de progrmação, você pode ter serviços escritos em node, java, python, etc...

**Características organizacionais**
-   Agilidade
    -   Trabalhando em conjuntos de negócio menores você garante agilidade no desenvolvimento de software
-   Equipe pequena e focada
    -   Utilizando o conceito de two-pizzas team você garante foco e produtividade do time de desenvolvimento.
-   Entregas rápidas
    -   Por ser altamente testável, um microserviço pode estar disponível rapidamente em produção com garantias de segurança e qualidade.
-   Combinação de tecnologias
    -   Times podem ser multidisciplinares em tecnologias para desenvolver microsserviços.

**Praticas recomendadas**
-   Modele o serviço em torno do domínio da empresa.
-   Descentralize tudo.
    -   Equipes individuais são responsáveis por projetar e criar serviços.
    -   Evite compartilhar esquema de dados ou códigos.
-   O armazenamento de dados deve ser privado para o serviço que é o proprietário dos dados.
    -   Use o melhor armazenamento para cada serviço e tipo de dados.
-   Os serviços comunicam-se por meio de APIs bem projetadas.
    -   Evite o vazamento de detalhes da implementação.
    -   As APIs devem modelar o domínio, não a implementação interna do serviço.
-   Evite acomplamento entre serviços.
    -   Causas de acoplamento incluem protocolos de comunicação rígidos e esquemas de banco de dados compartilhados.
-   Descarregue preocupações abrangentes, como autenticação e terminação SSL, para o gateway.
-   Mantenha o conhecimento do domínio fora do gateway.
-   Os serviços devem ter um acoplamento flexível e alta coesão funcional.
-   Isole falhas
    -   Use estratégias de resiliência para impedir que falhas em um serviço distribuam-se em cascata.

>"Everything fails<br>
>all the time"<br>
><i>Werner Vogels</i>


**Falácias**
-   A rede é confiável
-   Latência é zero
-   A banda de internet é infinita
-   A rede é segura
-   A topologia de rede não muda
-   Existe somente UM administrador
-   Custo de transporte é zero
-   A rede é homogênea

#### IaaS - Infrastucture as a Service - Infraestrutura como Serviço
Iaas significa entregar computação de infraestrutura sob demanda.
É um dos 3 modelos de serviços da computação em nuvem.

**IaaS provê:**
-   Servidores
    -   Computação e máquinas
-   Storage
-   Rede
-   Sistemas Operacionais

O usuário ao invés de adquirir softwares ou máquinas, espaço em data centers ou equipamentos de rede ele praticamente aluga espaços para estes recursos em uma infraestrutura externa.

**IaaS pode ser obtido em:**
-   Nuvem píblica
    -   É considerada nuvem pública uma infraestrutura que consistem de recursos compartilhados, liberados sob demanda na internet.
-   Nuvem privada
    -   Incorpora a maioria das features de uma nuvem pública como virtualização porém fica dentro de uma rede privada.
-   Nuvem híbrida
    -   Mistura de ambas as anteriores, geralmente conectada atráves de uma VPN.

**Quando utilizar**
-   Empresas sem capacidade de investimento em hardware
-   Quando a demanda for volátil
    -   Você tem a possibilidade de aumentar ou diminuir sua capacidade computacional de acordo com a necessidade.
-   Empresas com crescimento rápido e necessidade de escala rápida de sua infraestrutura
-   Por estratégias de negócios rápidas

**Quando não utilizar**
-   Quando a legislação não permitir guardar os dados fora da infraestrutura interna da empresa, ou a terceirização do armazenamento não é permitida.
-   Não é recomendado quando os níveis de desempenho necessários para aplicação tenham limite de acesso ao provedor da cloud.

#### Paas - plataform as a Service - Plataforma como Serviço
Pode ser considerada Iaas adicionada de uma camada de middleware e/ou componentes prontos, é um ambiente de execução escalável e com alta disponibilidade para aplicações customizadas.

Paas, é uma categoria de computação em nuvem que fornece uma plataforma e um ambiente para permitir que os desenvolvedores criem apicativos e serviços pela internet, fornece fundamentalmente escala elástica do seu aplicativo.

**Benefícios**
-   Infraestrutura na nuvem, escalável e com alta disponibilidade nativa.
-   Alta produtividade no desenvolvimento e manutenção de aplicações sob demanda.
-   Resumindo
    -   Baixo custo
    -   Confiabilidade
    -   Diminuição do tempo de entrega

**Vantagens**
-   Desenvolvimento 100% focado no negócio
    -   Por direcionar a arquitetura lógica e administrar a arquitetura física de forma transparente, é possível desenvolver aplicações que irão demandar uma requisição por minuto ou 10 mil requisições por segundo da mesma forma, com o mesmo nível de preocupação do ponto de vista técnico.
-   Produtividade
    -   Por não gerenciar balanceamento de carga, replicação, cluster, instalar e configurar middlewares já é um ganho. Além disso, os grandes fornecedores estão criando camadas de componentes prontos para uso, APIs e aceleradores de desenvolvimento nessas plataformas.

**Decisões**
-   A plataforma por trás do PaaS foi criada para trazer benefícios e acelerar o desenvolvimento. Existe um esforço por parte dos fornecedores para deixar essa camada o mais padrão possível, mas ainda existe uma boa parte que é proprietária.
<br>
-   Ao adotarmos PaaS, é natural se adotar também essa camada proprietária, caso contrário, poderia se trabalhar direto na infraestrutura.
<br>
-   É esta camada que permite dar um salto de produtividade e lidar com escalabilidade e disponibilidade de forma transparente.
<br>
-   A decisão a ser tomada é:
    -   Menos custo e mais entregas contra o efeito "lock-in" das aplicações construídas nessa abordagem!


**Restrições**
-   Plataformas são muito eficientes para construção de novas aplicações.
-   A migração de aplicações já existentes para elas é um processo custosos ou mesmo inviável(dependendo da tecnologia e plataforma almejada).


#### The twelve factor apps

1.  ##### Base de código
    1.  Somente uma base de código por aplicação
    2.  Vários deploys por aplicação
    3.  Desenvolvedor possui uma cópia local do repositório
2.  ##### Dependências
    1.  Descubra e isole explicitamente as dependências
    2.  Uma aplicação Twelve Factor nunca confia na existência implícita de pacotes em todo o sistema
    3.  Uma declaração de dependência explícita é que simplifica a configuração da aplicação para novos desenvolvedores
    4.  Na prática:
        1.  Tenha sempre um gerenciador de dependências configurado para seu projeto(maven, gradle, npm, pip, etc...)
3.  ##### Configurações
    1.  A configuração de uma aplicação é tudo que é provável variar entre deploys(homologação, desenvolvimento, produção, etc...)
    2.  Uma aplicação Twelve Factor armazena a configuração em variáveis de ambiente ou algum recurso de configuração distribuída
    3.  Necessitamos de facilidade na troca de ambientes sem ter a necessidade de alterar o codebase.
4.  ##### Serviço de apoio
    1.  Trate serviços de apoio como recursos anexados
    2.  Serviço de apoio é quqlquer seviço que a aplicação consuma via rede como parte da sua operação normal
        1.  Banco de dados
        2.  Mensageria
        3.  Cache
    3.  Não deve fazer distinção entre serviços terceiros ou locais.
5.  ##### Construa, lance, execute
    1.  Uma base de código é transformada em deploy atráves de 3 estágios:
        1.  Construção:
            1.  Converte o repositório em pacote executável
        2.  Lançamento:
            1.  Combina o artefato construído com a configuração do deploy
        3.  Execução:
            1.  Roda a aplicação no ambiente de execução através dos processos especificos da aplicação.
    2.  A aplicação Twelve Factor utiliza separação estrita entre os estagios de construção, lançamento e execução
6.  ##### Processos
    1.  Você não deve introduzir estado em seus serviços
        1.  Os aplicativos devem ser executados como um processo único e sem estado.
    2.  Os processos do Twelve Factor são stateless e não compartilhham nada
        1.  Esse fator está no núcleo da arquitetura de microsserviços.
7.  ##### Vínculo de porta
    1.  Seu serviço deve estar visível para outras pessoas via ligação de alguma porta.
        1.  Se criou um serviço, verifique se outros serviços podem tratar ele como um recurso, se assim desejarem.
        2.  Aplicações Twelve Factor são totalmente independente de outros recursos.
8.  ##### Concorrência
    1.  Divida sua aplicação em pequenos pedaços, ao invés de tentar aumentar (executando uma única instância na máquina mais poderosa disponível).
    2.  Aplicativos pequenos e definidos permitem a expansão conforme necessário para lidar com cargas variadas
    3.  O processo deve ser dimensionado individualmente, com o fator 6(sem estado), torna-se transparente este tipo de abordagem.
9.  ##### Descartabilidade
    1.  Processos devem consumir menos tempo
        1.  Certifique-se de poder correr e parar rapidamente e poder lidar com falhas.
            1.  Sem isso o dimensionamento automático e a facilidade de implantação e desenvolvimento estão sendo diminuídos
            2.  Pode conseguir isso com containers
10. ##### Paridade entre desenvolvimento e produção
    1.  Mantenha o desenvolvimento, homologação e prdução o mais semelhante possível.
        1.  Para que qualquer pessoa possa usar da mesma forma.
        2.  Inplantação continua precisa de integração continua com base em ambientes correspondentes para limitar desvios de erros.
        3.  Incentiva uma cultura DevOps onde desenvolvimento e operações de software são unificados.
        4.  CONTEINERIZAÇÃO É UMA GRANDE AJUDA
11. ##### Logs
    1.  Trate os logs como fluxos de eventos.
        1.  O registro é importante para validar erros e verificar a integridade geral do sistema.
            1.  Ao mesmo tempo a aplicação não deve se preocupar com o armazenamento dessa informação
        2.  Os logs devem ser tratados como fluo contínuo capturado e armazenada por serviço separado.
12. ##### Processos administrativos
    1.  Execute tarefas administrativas / gerenciamento como processos pontuais - tarefas como migração de banco de dados ou execução de scripts pontuais no ambiente.
        1.  Para evitar mexer com banco de dados, use ferramentas criadas ao lado do aplicativo e isole completamente sua aplicação por exemplo.


##### Apesar de algums pontos parecerem triviais, ao executarmos inumeros serviços em poucos ambientes os twelve factor podem ser de grande importância.

#### Aplicações Cloud Native

##### Definição - CNCF
-   Containerizado
-   Gerenciado dinamicamente
-   Orientado a microsserviços
    -   Automação
    -   Registro e Descoberta
    -   Rastreamento distribuído / observabilidade
-   Cloud
    -   Elasticidade
    -   Modelo on-demand

##### Definição - Pivotal
-   DevOps
    -   Processos
    -   Ferramentas
    -   Cultura
-   Entrega continua
    -   Automação
-   Microsserviços
    -   Automação
    -   Registro e Descoberta
    -   Rastreamento distribuído / Observabilidade
    -   Anti-fragilidade / Engenharia de caos;
-   BOSH
    -   Suporte a múltiplas clouds(evita ficar preso a um único provider)
    -   Seperação clara entre sistemas
    -   Provisionamento rápidp
    -   Escalabilidade
    -   Monitoramento de saúde
    -   Controle de falhas
    -   Deploy canário

##### AO FALAR DE CLOUD NATIVE FALAMOS SOBRE ABSTRAÇÕES.

#### Particionamento de serviços

##### Domain Driven Design - DDD
É uma abordagem que reúne um conjunto de boas práticas, padrões, ferramentas e recursos da orientação a objetos que têm como objetivo a construção e desenvolvimento de sistemas de acordo com o domínio e regras de negócio do cliente.

Como principais componentes do DDD, podemos listar:
-    Linguagem onipresente
-    Arquitetura em camadas
-    Padrões


##### DDD - Camadas
-   Interface
    -   Aceita comandos e apresenta informações de volta ao usuário
-   Aplicação
    -   Gerencia trasações
    -   traduz TDOs
    -   Coordenad atividades de aplicativos
    -   Cria e acessa objetos de domínio
-   Domínio
    -   Conteêm o estado e comportamento do domínio.
-   Instraestrutura
    -   Suporta todas as outras camadas
    -   Inclui repositórios
    -   Adaptadores
    -   frameworks...

##### DDD - Modelo
O modelo é evolutivo: cada interação entre especialistas de domínio e a equipe técnica, o modelo se torna mais profundo e expressivo, mais rico e os desenvolvedores transportam essa fonte de valor para o software.

Quando novas regras de negócio são adicionadas e/ou regras existentes são alteratas ou removida, a implementação é refatorada para refletir essas alterações do modelo no código. no final, o código vai expressas com riqueza de conhecimento o negócio.

##### DDD e Event Storming
Event storming é uma técnica de design rápido que engaja especialistas do domínio de negócios com desenvolvedores para que alcancem um ciclo rápido de aprendizagem.

Aprender o máximo possível no menor tempo possível.
-   mapeando Eventos
-   Identificando comandos
-   Associando Aggregates
-   Delimitando fronteiras do modelo de negócio
-   Identificando domínios de negócio

