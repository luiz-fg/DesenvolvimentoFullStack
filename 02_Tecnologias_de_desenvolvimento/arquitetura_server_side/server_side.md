
<h1 style="color: #E1BE5A;">ARQUITETURA  SERVER-SIDE</h1>

##### Professores: Adriana Cássia Reis dos Santos e Miguel Gomes Xavier.


>"Qualidade **não é opcional,** temos que saber. <br>
>tratá-la dentro do nosso desenvolvimento de sistemas <br>
>**<i>Daniel Wildt</i>**

<br>

## Ementa da disciplina

- Estudo sobre Arquitetura cliente-servidor para aplicações web.

- Introdução aos frameworks MVC server-side:
- Node.js,
- Express,
- Nestjs.
- Estudo de programação assíncrona e programação reativa.
- Desenvolvimento de aplicações web com o conceito de uso de serviços.

------------
<br>

#### Arquitetura cliente-Servidor

A arquitetura cliente / servidor é uma arquitetura de aplicação distribuída, ou seja, na rede existem os frnecedores de recursos ou serviços a rede, que são chamados de servidores, e existem aqueles que requerem serviços e recursos, chamados clientes.
Clientes não compartilham nenhum dos seus recursos com o servidor, no entanto soclicita algumas funções do servidor, sendo ele, o cliente, responsável por iniciar a comunicação com o servidor, enquanto o mesmo aguarda requisições de entrada.

<br>

#### Problemas Cliente-Servidor
Visto que fica centralizada no servidor a capacidade de oferecer serviços e recursos, surge um problema.
O que fazer quando a capacidade de atender requisiçõs dos clientes é ultrapassada ?
Sobrecarga é um problema real apesar da capacidade dos servidores ter aumentado consideravalmente.

Além de requisições não atendidas devido a sobrecarga do servidor, no modelo cliente / servidor, ainda há o fato de que o modelo não é robusto, ou seja, se um servior crítico falha, as requisições já feitas pelas clientes poderão não ser atendidas.
Esses motivos são a base das redes peer-to-peer(par-a-par / P2P).

##### Redes P2P ( peer-to-peer)
Redes peer-to-peer surgem como uma proposta de descentralizar o monopólio de processamento funcional. Fazendo sistemas servirem a outros sistemas, dando a cada estação as mesmas capacidades e responsabilidades dentro da rede.

**Dave Winer(UserLand Software)** sugere que sistemas P2P envolvam as seguintes características:
1.  Interface de troca de arquivos seja fora do navegador de internet.
<br>
2.  Computadores podem servir tanto como servidores como clientes.
<br>
1.  Sistemas fáceis de usar e bem integrados.
<br>
1.  O sistema deve incluir ferramentas que ajudam usuários que queiram criar ou adicionar alguma funcionalidade.
<br>
1.  Sistemas promovam conexão entre usuários
<br>
1.  Sistemas que façam algo novo ou excitante.

<br>

#### SOA - Service Oriented Architeture - Arquitetura Orientada a Serviços
Arquitetura Orietada a Serviços(Service-Oriented-Architeture - SOA) é um  método de desenvolvimento de software que usa componentes de software chamados de serviços para criar aplicações de negócios.
Cada serviço fornece um recurso do negócio, e todos podem se comunicar entre si independente da plataforma ou linguagem.
Desenvolvedores usam SOA para reutilizar serviços em sistemas diferentes ou combinar vários serviços independentes na realização de tarefas complexas.

**EX:** Se muitos serviços exigem autenticação de usuários. Ao invés de reescrever o código para todos os processos de negócios, pode-se criar um único serviço de autenticação e reutilizá-lo em todas as aplicações.
Da mesma maneira, sistemas de organizações de saúde, com sistemas para gerenciar pacientes, e prontuários enetrônico de saúde(EHR), precisam registrar pacientes.
Podem chamar um único serviço.


##### Vantagens do SOA:
Soa possuí várias vantagens em relação a arquiteturas monolíticas, onde todos os processos são executados como uma única unidade.

-   Mais rapidez para entrada no mercado
    -   Reutilizam serviços para poupar tempo e economizar custos
-   Manutenção eficiente
    -   Mais fácil criar, atualizar e deputrar pequenos serviços de grandes blocos de código.
-   Maior adaptabilidade
    -   Mais adaptável aos avanços da tecnologia. Pode-se modernizar a aplicação de maneira eficiente e econômica.

##### Principíos básicos do SOA
Não existem diretrizes padrões para implementar a arquitetura orientada a serviços(SOA).
Porém, alguns princípios básicos são comuns em todas as implementações da SOA.

-   Interoperabilidade
    Cada serviço SOA inclui documentos de descrição que especificam a funcionalidade do serviço, termos e condições relacionados.
    Qualquer sistema cliente pode executar um serviço independente de linguagem de programação ou plataforma.
    COmo não existe interação diretas, as alterações em um serviço não afetam outros componentes que usam esse serviço.

-   Acomplamento fraco
    Serviços SOA devem ter acoplamento fraco, possuindo menos dependência possível de recursos externos, como sistemas de informações ou modelos de dados.
    Devem ser stateless, sem reter informações de sessões ou transações anteriores.
    Assim, ao modificar um serviço, ele não afetará as aplicações cliente e outros serviços que o utilizam.

-   Abstração
-   Clientes ou usuários SOA não precisam conhecer a lógica do código ou detalhes do serviço.
-   Os serviços devem parecer uma caixa preta. CLientes obtêm informações necessárias sobre o serviço e como utilizá-lo por meio
-   de contratos de serviço e outros documentos de descrição de serviços.
  
-   Granularidade
    Serviços SOA devem ter tamanhos e escopos apropriados, empacotando uma única função de negócios por serviço.
    Para realizar operações complexas pode-se usar vários serviços a fim de criar um serviço composto.


##### C0mponentes da Arquetetura Orientada a Serviços:
Existem quatro componentes principais na SOA.
1.  **Serviço**
   Serviços são os alicerces básicos da SOA.
   Eles podem ser privados (apenas para usuários internos da organização), públicos (acessíveis a todos pela internet).
   Individualmente cada serviço possui 3 caracteristicas:

    1.  Implementação do serviço
        É o código com a lógica para realaizar a função do serviço.
        Como por exemplo autenticação de um usuário ou calcular uma fatura.

    2.  Contrato do serviço
        Define a natureza do serviço, seus termos e condições associadas, pré-requisitos para usar o serviço, custo do serviço e qualidade do serviço prestado.

    3.  Interface do serviço
        Na SOA, outros serviços ou sistemas se comunicam por meio de sua interface de serviço.
        A interface define como chamar o serviço para trocar dados ou realizar atividades.
        <br>

2.  **Provedor de serviços**
    Cria, mantém e fornece um ou mais serviços que outros usuários podem usar.
    Organizações podem criar seus serviços ou comprar de provedores de serviços terceirizados.
    <br>

    
3.  **Consumidor de serviços**
    Ele solicita que o provedor de serviços execute um serviço específico, podendo ser um sistema inteiro, uma aplicação ou outro serviço.
    O contrato especifica as regras que o provedor e o consumidor de serviços devem seguir para interagir entre si.
    Provedores e consumidores de serviços podem pertencer a diferentes departamentos, organizações ou até mesmo setores.
    <br>

4.  **Registro de serviços** 
   Um registro ou repositório de serviços, é um diretório de serviços disponíveis acessível pela rede.
   Ele armazena documentos de descrição de serviço de provedores de serviços.
   DOcumentos de descrição contêm informações sobre o serviço e como se comunicar com ele.
   Consumidores de serviços podem descobrir facilmente os serviços de que precisam usando o registro de serviços.
   <br>


#### Funcionamento da arquitetura orientada a serviços
Na SOA , os serviços funcionam de forma independente e fornecem funcionalidades ou troca de dados aos seus consumidores.

-   O consumidor solicita informações e envia dados de entrada ao serviço.
-   O serviço processa os dados, realiza a tarefa e retorna uma resposta.

EX: se uma aplicação utiliza um serviço de autorização, ela fornece usuário e senha, o serviço verifica esses dados e retorna uma resposta apropriada.

##### Limitações na implementação da SOA:

**Escalabilidade limitada**
A escalabilidade do sistema é afetata quando serviços compartilham muitos recursos e precisam ser coordenados para executar sua funcionalidade.

**Aumento das interdependências**
Os sistemas podem se tornar complexos ao longo do tempo e desenvolver várias interdependências entre serviços.
Eles podem acabar sendo difíceis de modificar ou depurar quando vários serviços estão chamando uns aos outros em loop.
Recursos compartilhados como banco de dados centralizados podem tornar o sistema lento.

**Ponto único de falha**
Implementações da SOA com um ESB, este último cria um ponto único de falta.
Trata-se de um serviço centralizado o que vai contra a ideia de descentralização que a SOA defende.
Clientes e serviços não poderão se comunicar uns com os outros se o ESB se tornar inoperante.


#### Microserviços
A arquitetura de microserviços é formada por componentes de software pequenos e independentes, chamados de microserviços.
Especializados e concentrados numa única tarefa.
Microserviços se comunicam por meio de APIs qeu são regras criadas para permittir que outros serviços se comuniquem com seus microserviços.
O estilo de microserviços é mais adequado para ambientes modernos de computação em nuvem, geralmente operam em containers.

**Benefícios dos microserviços**
-   Escalaveis de maneira independente
-   Rápidos
-   Portáteis
-   Independentes de plataformas
-   Desacoplados

Microserviços são uma evolução da SOA.
Os microserviços abordam as deficiências da SOa para tornar o software mais compatível com ambientes corporativos modernos baseados em nuvem.
Microserviços são refinados, favorecem a duplicação de dados em oposição ao compartilhamento de dados. Tornando-os independentes, com seus próprios protocolos de comunicação que são expostos por meio de APIs leves.


#### Web Service
Funcionam com qualquer sistema, plataforma de hardware ou linguagem de programação de suporte web. Estes transmitem apenas informações, ou seja, não suportam páginas que podem ser acessados por utilizadores através de navwgadores web.
Web services permitem reutilizar sistemas já existentes e acrescentar novas funcionalidades sem a necessidade de criar um sistema do zero, é posspivel melhorar sistemas existentes.

##### Como funciona
Considerando as operações disponíveis no web service, a aplicação solicita uma operação, o web service efetua o processamento e envia os dados para a aplicação.
A aplicação recebe os dados e interpreta, convertendo elas para sua própria linguagem.
Sendo linguagens diferentes é necessário uma linguagem intermediária para garantir a comunicação entre o web service e o sistema que fez o pedido. 
Para tal existem protocolos de comunicação como o SOAP(Simple Object Access Protocol) e o REST(Representational State Transfer).

SOAP utiliza XML para enviar mensagens que geralmente utiliza o protocolo HTTP para transportar dados.
REST é um protocolo mais recente e permite usars várias representaçoes de dados como JSON, XML, RSS e outros.

##### Beneficios do web service

1.  **Integração de informação e sistemas**
    o web service necessita apenas de XML/JSON e protocolos HTTP, a comunicação entre sistemas é bastante simplificada.
    <br>

2.  **Reutilização de código**
    Um web service pode ser utilizado por várias plataformas com diferentes objetivos de negócios.
    O código é feito uma vez e pode ser reutilizado por diferentes aplicações.
    <br>

3.  **Redução do tempo de desenvolvimento**
   Desenvolver com web services é mais rápido porque sistemas não são construidos totalmente do zero e novas funcionalidades são facilmente incluídas.
    <br>

4.  **Maior Segurança**
    O Web service evita que a comunicação seja feita diretamente com a base de dados.
    Assim a segurança do sistema que fornece os dados está salvaguardada.
    <br>

5.  **Redução de custos**
    COm web services não é necessário criar aplicações à medida para a integração de dados, algo que pode ser bastante caro.
    Web services tiram partido de protocolos e da infraestrutura web que já existem na organização, demandando pouco investimento.
    <br>


#### MVC
É um padrão de arquitetura de software, ele sugere uma maneira para dividir responsábilidades, principalmente dentro de um software web.
O princípio básico do MVP divide a aplicação em 3 camadas:
<br>
-   Model
    -   Camada de manipulação de dados
-   View
    -   Camada de interação do usuário
-   Controller
    -   Camada de controle.


quando falamos de MVC cada camada geralmente apresenta geralmente as seguintes responsábilidades:

**Model**
A responsábilidade dos models é representar o negócio, é responsável também pelo acesso e manipulação dos dados da aplicação.

**View**
A View é responsável pela interface que será apresentada, mnostrando as informações do model para o usuário.

**Controller**
É a camada de controle, responsável por ligar o model e a view, fazendo com que os models possam ser repassados para as views e vice-versa.


#### Frameworks
Framework nada mais é do que uma ferramenta que vai ajudar a ter como unico objetivo focar em desenvolver o projeto, não detalhes de configuração.
O framework evita que tenhamos tarefas repetitivas, automatizando parte do trabalho. Numa situação de desenvolvimento, se precisarmos criar um formulário de cadastro de usuários,
ele sempre vai requerer algum tipo de validação como por ex: email e senha. O framework já terá essa validação pronta para uso.

Agilidade com certeza é uma vantagem do uso de frameworks, já que os esforços são voltados ao desenvolvimento ao invés de nos preocuparmos tanto com configurações.
Com o uso de frameworks temos um padrão de código mais limpo, garantindo maior clareza de entendimento em tudo o que  é implementado pela ferramenta.


#### Javascript
é uma linguagem de programação que desenvolvida para trazer maior interatividade aos websites através da manipulação do DOM (Document Object Model).
pensado para ser rápido, dinâmico e acessível.
A linguagem possibilita subir ou trabalhar em aplicações sem precisar configurar todo um ambiente complexo.


#### Node.js
O Javascript surgiu para antender demandas relacionadas ao frontend e como as necessidades aumentam de acordo com o crescimento tecnológico, surgiu a ideia de usar a mesma linguagem
no lado do cliente e servidor para otimizar processos e serviços.
Surgindo assim o Node.js como uma alternativa viável para o backend.
Conforme a definição oficial, o node é um runtime, que não é nada mais do que um conjunto de códigos, APIs, bibliotecas responsáveis pelo tempo de execução(que faz o programa rodar).
É importante pontuar que o node é um ambiente assíncrono, ele trabalha de modo a não bloquear no momento de execução da tarefa delegando os processos a um segundo plano.

**Caracteristicas do node:**
-   multiplataforma
-   Multi-paradigma
-   Open Source
-   Escalável

#### Express.js
é um framework rápido e um dos mais utilizados em conjunto com o Node.js, facilitando no desenvolvimento de aplicações backend.
Escrito em JS é utilizado por inumeras empresas ao redor do mundo, entre elas:
-   Fox sports
-   Paypal
-   IBM
-   Uber

Bastante popular tanto nas grandes empresas como na comunidade, o express facilita o desenvolvimento de aplicações usando node.js em conjunto com javascript.


#### Nest.js
Framework progressivo para desenvolvimento em TypeScript.
ele é um framework backend feito em node que utiliza o padrão typescript. Usado no lado do servidor.


#### Next.js
Tanto Nest.js quanto Next.js são frameworks para desenvolvedores fullstack.
Next,js é uma pequena estrutura para aplicativos JS que são renderizados pelo servidor.

#### Frameworks opinativos e não opinativos.
Quem trabalha com frameworks precisa saber que existem dois tipos: Opinativos e não opinativos.

**Opinativos**
Como o nome diz, são frameworks que fazem sugestões para o desenvolvedor escolher o melhor caminho em algumas tarefas.
Isso ocorre porque algumas açoes dentro do código já são bem compreendidas, o que facilita na hora do desenvolvimento. Todavia a flexibilidade é menor.

**Não opinativo**
Conta com restrições menores na hora de indicar a mlhor forma de utilização do mesmo.
Express.js por ex é um framework não opinativo.


##### programação assincrona
É uma maneira de evitar delays ou tempos de espera na execução de algum programa.
Quando executamos sincronamento podemos ter bloqueios no processo pela necessidade em esperar alguma execução de código.
Isso pode bloquear o programa até que termina a execução da tarefa.

Podemos usar programação assíncrona sempre que tivermos alguma tarefa que pode ser independente tal como:

-   Leitura e escrita de algum arquivo.
-   Chamada de recursos 3rd party
-   lógicas independentes que podem ser separadas da thread principal.


##### Programação reativa
É programar por meio de fluo de dados assíncronos, que não são realizados simultaneamente ou seguindo o mesmo ritmo de desenvolvimento em relação a outro sistema.


#### SEO - Search Engine Optimization
É uma série de aprimoramento no código e conteúdo de um site com o objetivo de que ele seja encontrado mais facilmente e melhor avaliado por mecanismos de busca.
Um uso eficiente posiciona indexa melhor o site em páginas de resultados, podendo chegar até na primeira colocação.
De forma geral, sempre que precisar tornar o conteúdo mais visível em mecanismos de busca aposte no SEO.


#### Single Page Appications - SPA
Aplicação de página única.
Não há necessidade de fazer requisiços para carregar novas páginas, a aplicação é carregada por inteiro na primeira requisição, onde todo o HTML, CSS e Javascript são carregados de uma vez.
Quando novas páginas precisarem ser carregadas, elas serão carregadas através de rotinas, retirando a necessidade de requisições para o servidor.
De maneira geral podemos obter algumas vantagens tais como a possibilidade de otimização de performance.
Uma outra vantagem é o reaproveitamento de código através de tecnologias como React / React Native e Angular / Ionic, possibilitando desenvolvimento com menos esforço e mais padronizado até mesmo de aplicações mobile.

aplicações SPA conhecidas:
-   Spotify
-   Google Planilhas
-   Youtube

Atualmente aplicações SPA podem ser usadas em praticamente qualquer situação, o que explica bastante a popularidade dos frameworks SPA como Angular, React, Vue.js e Ember.

Aplicações que necessitam de SEO podem ter problemas ao serem desenvolvidas com frameworks SPA.
Esse "problema" acontece justamente porque o conteúdo não é renderizado no lado do servidor, por isso mecanismos de busca podem ter dificuldade para indexar o conteúdo das páginas.
Isso explica porque a maioria dos frameworks SPA contam com soluções SSR.

**SSR**
Significa Server Side Rendering, ele vem para solucionar parte dos problemas das aplicações SPA, tentando manter suas principais vantagens.
O SSR inverte o processo de renderização, levando parte do esforço de renderização das aplicações SPA para o servidor, de maneira semelhante ao carregamento tradicional.
Já que parte da renderização é feita no servidor pode fornecer um carregamente mais eficiente da aplicação.
Alem dá melhoria da performance, o SSR ajuda a lidar com problemas de SEO.

Aplicações SSR também são chamadas de universal apps.


#### React
É um framework Javascript criado pelo Facebook que é usado para criar interfaces de usuários em aplicativos web.
Ele é popular devido sua fácil utilização, flexibilidade e escalabilidade.
Usado por empresas como: - Facebook - Instagram - Airbnb e outras...

Um dos principais casos de uso na criação de aplicações que precisam ser atualizadas em tempo real, outro caso de uso comum são aplicações qer que precisam ser escaláveis e mantidas por equipes grandes.

##### React Router
Por padrão o react vem sem roteamento porque foi pensado no modelo de SPA. Porém para tornar isso possível em nosso projeto precisamos adicionar uma biblioteca chamada react-router.

##### DOM e Virtual Dom

O virtual DOm é uma representação em memória do DOM, que é atualizada muito mais rapidamente que o DOM real.
Quando um componente React é atualizado o virtual DOM é atualizado primeiro e após são sincronizadas com o DOM real, tornando a atualização da interface de usuário mais rápida e eficiente.

##### Componente React
Componente funcional é um tipo de componente no React definido como função javascript.
Ao invés de usar uma classe, um componente funcional é apenas uma função que recebe as propriedades como argumento e retorno o elemento React que deseja renderizar.
Isso torna os componentes mais leves, faceis de entender e manter diferentemente dos componentes de classe.

EX:

```javascript
function Titulo(props)
{
    return <h1>{props.texto}</h1>;
}
```

##### React Props
No React, componentes são como pequenas "peças de lego" que podem ser combinadas para criar a interface de usuario de uma aplicação.
Cada componente é um trecho de código que segue um determinado padrão e pode ser reutilizado várias vezes ao longo da aplicação.
Props(propriedades), são um tipo de dado que podem ser passados para um componente React. Esses dados podem incluir texto, números, imagens ou até mesmo outros componentes.


##### JSX
É uma extensão javascript usada pelo React para criar intercaces de usuários.
Permite usar código JS com sintaxe HTML, o que torna mais fácil escrever componentes de interface de usuário em um único arquivo de código.

##### Redux
É uma biblioteca para armazenar estados de aplicações JS.
Utiliza o conceito de dados unidirecional.
Quando se desenvolvem aplicações JS, deve-se lidar com gerenciamento de estado. O Redux supre essa necessidade de simplificar o controle dos estados de uma aplicação.
Compartilhar estados entre componentes se torna uma tarefa fácil quando utilizado o Redux.

Basicamente ele centraliza a responsábilidade de armazenar os estados dos componentes, sendo usado ao mesmo tempo por todos os componentes de maneira compartilhada.
Roda em diferentes ambientes como servidor, cliente e nativo.

##### React hook Form
É uma biblioteca que auxilia na criação e validação dos formulários.
Reduz a quantidade de código desenvolvido, fazendo a captura de ações de formulario de forma objetiva.
Outra facilidade é a melhora significativa de desempenho, já que a renderização também pode ser controlada. Dessa forma somente alterações de entrada são rerenderizadas, não o formulario todo.

#### Testes Unitários
São testes que verificam se parte do código está funcionando corretamente. Costumeiramente a nível de função.
Em Orientação a Objetos é usualmente a nível de classes e a mínima unidade de testes inclui construtores e destrutores.


##### Jest
É um framework de testes unitários de código aberto em javascript a partir do framework jasmine.
Jest é uma das ferramentas de testes mais difundidas dentro da comunidade javascript


#### TDD - Test Driven Developement
É uma metodologia muito adotada nos times de desenvolvimento.
Pode parecer que o TDD inverte a ordem das etapas, mas faz muito sentido.
Existem 3 fases principais no ciclo de desenvolvimento Orientado a Testes

1.  **RED**
    Escrevemos um teste que irá falhar( o código ainda não existe).

2.  **Green**
    Fazem-se os ajustes necessários, conforme o resultado esperado, até que o teste passe.

3.  **Refactor**
    Refatora-se o código, retirando duplicidades, renomeando variáveis, usando padrões conhecidos entre outras acçoes.

##### Ciclo de desenvolvimento do TDD.
Para cada funcionalidade do programa, o ciclo acima é repetido.
Por isso a técnica se encaixa perfeitamente na metodologia XP.
Para cada funcionalidade do sisdtema cria-se um teste que prepete a sequência Red, Green, Refactor.

**Vantagens**
-   Código mais limpo
-   Segurança na correção de bugs
-   Segurança no refactoring
-   Maior produtividade para o desenvolvedor
-   Feedback mais rápido sobre a funcionalidade

##### Diferenças entre TDD, BDD e DDD

**TDD**
Desenvolvimento orientado a testes. Cria-se primeiro o teste conforme o resultado que se deseja atingir para determianda funcionalidade.
Depois disso, aprimoramos o código.

**BDD**
Behavior Driven Development ( Desenvolvimento Orientado ao Comportamento)
Os testes são baseados no comportamento do software ao longo da sua vida útil, sendo um complemento ou evolução do TDD.

**DDD**
Domain-Driven Design (Design Orientado pelo Domínio).
O problema que ele se propõe a resolver(a regra de negócio) é a parte principal do software.

