
<h1 style="color: #E1BE5A;">PROGRAMAÇÃO PARA WEB</h1>

#####Professores: Andrea Konzen e Luis Fernando Gonzalez.


>"Todo mundo surfa na onda da tecnologia,
>**<i>todo mundo ganha com isso na tecnologia.</i>**
>**<i>Cassio Trindade</i>**

<br>
##Ementa da disciplina

- Estudo do desenvolvimento de aplicações com HTML, CSS e JavaScript.

- Estudo sobre Document Object Model (DOM).

- Utiização de forms em aplicações WEB.

- Desenvolvimento de aplicações responsivas e acessíveis.

------------

##Breve História

-   1960 - É criada a ARPANET
    -   Departamento de defesa dos EUA criou para conectar computadores de diferentes universidades e centros de pesquisa do país.
-   1970 - A ARPANET se expande
    -   Para países como Reino Unido e Noruega e é dividida em redes menores.
-   1983 - A ARPANET adota protocolo TCP/IP
    -   Que se torna o padrão para comunicação entre computadores na internet
-   1990 - A internet se torna mais acessível ao público em geral.
-   1991 - Tim Berners-Lee criou a linguagem HTML.
    -  entre 1990 e 2000 também surgiram salas de bate-papo, provedores de email, hospedagens de sites...
-   2000 - A internet continua a crescer em popularidade e importância.
  
##Arquitetura web e caracteristicas das Aplicações web
É um conjunto de padrões, princípios, técnicas e boas praticas utilizadas para projetar e desenvolver sistemas e aplicações web.
ela é responsável pordefinir:
-   A estrutura
-   Os componentes da aplicação
-   As regras
-   Os protocolos de comunicação entre componentes.

####Caracteristicas importantes:
-   Escalabilidade
    -   lidar com grande volume de tráfego
-  Flexibilidade
   -  ser possível acomudar mudanças e atualizações futuras
-  Segurança
   -  ser capaz de proteger dados de usuários e a integridade das aplicações
-  Performance
   -  ter desempenho rápido e eficiente

####Arquiteturas mais comuns:
-   Arquitetura de 3 camadas(cliente-Servidor)
    -   divide a aplicação em: Front-end / back-end e banco de dados
-   Arquitetura orientada a serviços(SOA)
    -   divide em serviços independentes, cada serviço é responsável por uma tarefa especifica
-   Arquetetura baseada em microsserviços
    -   divide em microsserviços independentes que se comunicam entre si por meio de APIs.


##Protocolos
toas as atividades de comunicação na internet são governadas por protocolos.
Um protocolo controla e possibilita conexão, comunicação, tranferência de dados entre sistemas computacionais.

###protocolos de internet:

####TCP/IP
Transmission  Control Protocol / Internet Protocol.
Protocolo padrão da Internet, usado para transmitir dados entre dispositivos em redes de computadores.

####HTTP / HTTPS
HyperText Transfer Protocol / HyperText Transfer Protocol Secure
usado para transferir dados da web entre servidor e navegador, também usado para solicitar páginas web e outros recursos.

####FTP
File Transfer Protocol
Protocolo de tranferência de arquivos entre dispositivos, amplamente usado para transferir arquivos grandes, como imagens, vídeos e arquivos de áudio.

####DNS
Domain Name System
Usado para traduzir nomes de domínio em endereços IP.
Permite acessar sites e recursos web usando nomes de domínios em vez de endereços ip numéricos.

####SMTP / POP3 / IMAP
Simple Mail Transfer Protocol / Post Office Protocol / Internet Message Acesso Protocol
SMTP - protocolo para envio de e-mails
POP3 / IMAP - protocolos para recebimento de emails.

####ICMP
Internet Control Message Protocol
Conjunto de regras de comunicação usados para informar erros de transmissão de dados em uma rede.

###Protocolos de rede:

####Aplicação
Responsável pela comunicação entre aplicativos entre diferentes dispositivos de rede.
Define formatos de mensagens e regras de comunicação para dispositivos se comunicarem. Estabelece uma comunicação confiável entre origem e destino.

####Transporte
Responsável por fornecer comunicação confiável e eficiente entre aplicativos de diferentes dispositivos.
Garanteq que os dados sejam transmitidos sem erros, na ordem correta e com velocidade adequeada.

####Rede
####enlace
####Física


##Front End & Back End

###Front end
 É a parte do sistema web ou aplicativo que o usuário interage.
É responsável pela parte visual. O front end é o processo de desenvolvimento da interface do usuário, incluindo o design, a codificação e a integração de todos os elementos que fazem parte dessa interface.

o Frontend envolve várias tecnologias e ferramentas:
-   **HTML**
-   **CSS**
-   **Javascript**
-   **Frameworks frontend**

###Back end
É a parte do sistema que fica no servidor e cuida da lógica do negócio, o armazenamento de dados e a segurançaa.
A implementação do backend envolve várias tecnologias e ferramentas, incluindo frameworks, bancos de dados e linguagens de programação.

Várias linguagens de programação podem ser usadas para criar o backend incluindo:
-   PHP
-   Python
-   Ruby
-   Node.js
-   java


Cada linguagem possuí seus prós e contras, a escolha da linguagem dependerá das necessecidades do projeto.

####Banco de dados
São usados para armazenar e gerenciar dados dos aplicativos e sistemas.
Existem vários tipos de banco de dados, incluindo bancos relacionais, e banco de dados noSQL.
É importante escolher o tipo de banco de dados adequado para cada projeto e criar um estrutura eficiente e escalável.

####Frameworks backend
Os frameworks backend são ferramentas que ajudam a desenvolver mais rapidamente aplicavos robustos e escaláveis.
Existem diversos frameworks backend populares:
-   Laravel - para php
-   Djando - Para Python
-   Ruby on Ralis - para Ruby
-   Express.js - Para node.js

Cada framework tem suas próprias convenções e recursos, sendo importante escolher de maneira correta o que se adequa melhor ao projeto.

####Segurança
Medidas de segurança são importantes de serem implementadas, como **autenticação e autorização de usuários, criptografia de dados e prevenção de ataques**.


####APIs e Backend

Quando o assunto é backend precisamos relacionarmos com as APIs.
APIs são usadas para conectar diferentes sistemas e permitir a troca de informações entre os mesmos de maneira facilitada e eficiente.
No contexto de backend, as APIs são usadas para expor funcionalidades e dados de um sistema para o uso externo. Elas fornecem uma maneira padronizada para que os desenvolvedores possam acessar as informações e funções do sistema semp precisar conhecer a fundo os detalhes do sistema.

####Tipos de APIs

-   API da web:
    -   Usadas para acessar informações e serviços da web
-   API de serviço:
    -   usada para acessar informações e funcionalidades de sistemas específicos como bancos de dados e sistema de gerenciamento de conteúdo.
-   API de plataforma:
    -   usadas para acessar funcionalidades de uma plataforma específica como por ex: API do Facebook ou API do Twitter.

Cada tipo de API tem suas especificidades e requisitos.

####Segurança nas APIs

**- APIs** devem ser projetadas com autenticação e autorizações adequadas para proteger os dados e as funcionalidades do sistema.

-   É importante limitar o número de requisições feitas para evitar sobrecargas do servidor da API e proteger contra ataques de negação de serviço (DDoS).
  

  ##Tipos de sistemas para WEB: SPA, MPA e PWA.

- **SPA** - Single Page Application
  - Consiste em uma única página web que atualiza dinamicamente, permitindo construção de interfaces de usuários ricas e responsivas
  - Carrega todo o conteúdo necessário em uma única página.
  - Experiência mais rápida e fluída.
  -  O carregamento é assincrono, através de chamadas AJAX, o que evita a necessidade de recarregar a página inteira a cada interação.

    **Benefícios:**
    Velocidade - Melhor Experiência - Desenvolvimento mais fácil - Arquitetura Modular - Acesso offline - Maior Segurança - Facilidade de Manutenção


- **MPA** - Multi Page Application
 - Cada página é carregada como uma página separada.
 - São páginas independentes, cada uma com sua própria estrutura e conteúdo

    **Vantagens:**
    SEO-friendly - Manutenção mais fácil - Rápido tempo de carregamento - boa usabilidade.

    **Desvantagens:**
    transições mais lentas - Experiência de usuário inconsistente - Requisições de servidor - dificuldade em gerenciar o estado do aplicativo.
    
  - **PWA** - Progressive WebApps
    - Oferecem experiência de usuário semelhante Á um app móvel nativo
    - Combinam a facilidade de desenvolvimento de sistemas web com funcionalidade e capacidade de engajamento de app móvel.
  
  Requisitos para aplicação ser considerada PWA:
  - Possibilidade de ser indexada por mecanismos de busca
  - Ser instalável
  - Compartilhavel via URL
  - Funcionar offline ou com conexão instável.
  

**Características**

Confiabilidade - Engajamento - Navegação Suave - Instalação Fácil - Compatibilidade - Métricas de desempenho.


**Benefícios**
-   Desenvolvimento mais rápido e fácil
-   Custos reduzidos
-   Fácil Manutenção
-   Multiplataforma
-   Melhor Experiência do usuário
-   Fácil distribuição


##DOM
É uma estrutura em árvore cujos nodos são cada elemento do documento HTML. os atributos também são modos na árvore DOM.
é a base de uma SPA


##Layout responsivo vs Layout adaptativo

####Responsivo
Mesmo conteúdo, é definido através de CSS.

####Adaptativo
Conteúdo distinto, é gerado no servidor para o layout.

##Web Design responsivo
Seu conteúdo é como água.
Numa xicará, ele se torna a xicará
Numa garrafa, ele se torna a garrafa.
Num bule, se ele se torna o bule.
Josh Clark - Bruce Lee.

####Mobile-first
-   Abordagem adotada por Luke Wroblewski em 2009
-   Amplamente adotada nos dias atuais
-   O Design é projetado inicialmente para dispositivos móveis
-   Há pouco espaço na tela
-   Foco no conteúdo

####Media queries
-   São declarações CSS condicionais
-   permitem aplicar estilos de acordo com o dispositivo / ambiente
-   Podem ser usadas de duas formas:
    -   Em um elemento <link>
    -   Dentro de uma declaração CSS

EX:
```HTML
<link rel="stylesheet" media="print" href="estilos-impressao.css">
```

**OU**

```CSS
<style>
    @media print {
        .menu  {
            display: none;
        }
    }
</style>
```

####Media queries - largura de tela

-   width: Largura exata do viewport(pouco usado)
-   min-width: Largura mínima do viewport
-   max-width: Largura máxima do viewport

Sempre usar entre parêntesis
EX:
```CSS
button{ width: 100%}

@media( min-width: 600px )
{
button{ width: auto; }
}
```

####Media brakepoints
- Utiliza larguras para diferenciar os tipos de dispositivos
- cada "quebra" é chamada de media brakepoints
- não existe consenso nos tamanhos
  

brakepoints bootstrap:
- Extra pequena - celulares (retrato): < 576px
- Pequena - celulares(paisagem): => 576px, < 768px
- Média - tablets(retrato), desktops: => 768px, < 992px
- Grande 0 tablets(paisagem, desktops): => 992px, < 1200px
- Extra Grande - desktops, tvs: => 1200px, < 1400px
- Extra extra Grande - desktops, tvs: => 1400px

brakepoints material design
- Extra pequena - celulares: < 600px
- Pequena - tablets: => 600px, < 1240px
- Média - laptops: => 1240px, < 1440px
- Grande - desktops / tvs: => 1440px

