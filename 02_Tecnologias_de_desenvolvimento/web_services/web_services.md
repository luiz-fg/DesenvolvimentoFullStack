
<h1 style="color: #E1BE5A;">WEB SERVIÇES</h1>

##### Professores: Cássio Trindade e Miguel Gomes Xavier.


>"Das ideias que ue conheço de TI, a mais fácil de<br>
>vender até hoje foi a <i>**computação em nuvem"**</i><br>
>**<i>Aod Cunha de Moraes Jr.</i>**

<br>

## Ementa da disciplina

- Estudo sobre conceitos de arquitetura monolítica
- Revisão dos conceitos sobre:
  - SOAP
  - REST
  - Descritores de serviços
- Estudo sobre soluçoes serveless
- Construção de soluções com:
  - Framework REST
  - Framework GraphQL.
------------
<br>

#### WEB Service
-   **Web Service** são componentes de aplicativos
-   **Web Service** se comunicam usando protocolos abertos
-   **Web Service** são autocontidos e autodestrutivos
-   **Web Service** podem ser descobertos usando UDDI
-   **Web Service** podem ser usados por outros aplicativos
-   HTTP e XML são a base para **Web Service**.

 **XML - Extensible Markup Language**
É uma recomendação da W3C para gerar linguagens de marcação para necessidades especiais.


#### SOAP
**Simple Object Access Protocol - Protocolo Simples de Acesso a Objetos**
Protocolo para troca de informações estruturadas em uma plataforma descentralizada e distribuída. Ele se baseia na linguagem de marcação Extensível (XML).

-   Um mecanismo para a definição de unidades de comunicação
-   Um modelo de processamento
-   Um mecanismo para a manipulação de erros
-   Um modelo de extensibilidade
-   Um mecanismo flexível para a representação de dados
-   Uma conversa para a representação de chamadas remotas de procedimentos e respostas
-   Uma estrutura para um protocolo de vinculação

**WSDL - Web Service Description Language**
É uma notação XML para descrever um serviço da web.
Indica a um cliente como compor uma colicitação de serviço da web e descreve a interface que é fornecido pelo provedor de serviços da web.

**Exemplo de Envelope SOAP**

```XML
<?xml version="1.0"?>

<soap:Envelope
xmlns:soap="http://www.w3.org/2003/05/soap-envelope/"
soap:encodingStyle="http://www.w3.org/2003/05/soap-encoding">

<!-- Elemento raiz do SOAP que define que essa é uma mensagem SOAP -->
<soap:Header> <!-- Informações específicas como autenticação (opcional)-->
...
</soap:Header>

<soap:Body> <!-- Elemento que contém o corpo da mensagem -->
...
  <soap:Fault> <!-- Elemento que contém os erros que podem ocorrer -->
  ...
  </soap:Fault>
</soap:Body>

</soap:Envelope>
```

**Exemplo WSDL**
```XML

<?xml version="1.0" encoding="UTF-8"?>

<message name="getTermRequest">
  <part name="term" type="xs:string"/>
</message>

<message name="getTermResponse">
  <part name="value" type="xs:string"/>
</message>

<portType name="glossaryTerms">
  <operation name="getTerm">
    <input message="getTermRequest"/>
    <output message="getTermResponse"/>
  </operation>
</portType>
```

**REST**
**Representational State Transfer - Transferência Representacional de Estado**
Um estilo de arquitetura de software que define um conjunto de restriçoes a serem usadas pra a criação de web services.


<table>
  <thead>
  </thead>
  <tbody>
  <tr>
      <td> </td>
      <td> </td>
      <td>HTTP Verbs</td>
      <td> </td>
      <td> </td>
    </tr>
    <tr>
      <td>Client send<br> as request</td>
      <td>< JSON ></td>
      <td>GET<br>POST<br>DELETE<br>PUT<br>PATH<br>.<br>.<br>.</td>
      <td>< HTTP ></td>
      <td>Server send<br>as response</td>
    </tr>
    
  </tbody>
</table>

#### Uso de WebService na Nuvem

**Cluod computing - Computação em nuvem**
-   Disponibilidade sob demanda de recursos do sistema de computador
-   Armazenamento de dados e capacidade de compuitção, sem o gerenciamento ativo direto do utilizador.
-   Centros de dados disponíveis para muitos utilizadores pela internet
-   Nuvens em grande escala, prodominantes hojem em dia, geralmente têm funções distribuídas em vários locais dos servidores centrais.

**Principais players do mercado**
-   Microsoft Azure
-   Google Cloud
-   Oracle Cloud
-   AWS

**Serviços - siglas**
-   **IaaS**
    -   Infrastructure as a Service
-   **PaaS**
    -   Plataform as a Service
-   **SaaS**
    -   Software as a Service
-   **DBaaS**
    -   Data Base as a Service
-   **CaaS**
    -   Communication as a Service
-   **DRaaS**
    -   Disaster Recovery as a Service

##FaaS - Function as a Service - Função como Serviço##
Um tipo de serviço de cloud computing que permite que os desenvolvedores criem, executem e gerenciem pacotes de aplicações como funções, sem a necessidade de se preocupar com a manutenção da infraestrutura.

##AWS Lamba##
É um serviço de computação sem servidor e orientado a eventos que permite executar código para praticamente qualquer tipo de aplicação ou serviço de backend sem provisionar ou gerenciar servidores.


