
<h1 style="color: #E1BE5A;">QUALIDADE E TESTE<br> DE SOFTWARE</h1>

##### Professores: Ricardo Beck e Daniel Callegari.


>"A tecnologia não faz nada. <i>**Ela faz aquilo que**</i><br>
>"<i>**nós fizermos com ela"**</i><br>
>**<i>Gabriela Cardozo Ferreira</i>**

<br>

## Ementa da disciplina

- Introdução aos conceitos de testes unitário
- Teste de integração
- teste de UI
- Introdução aos conceitos de garantia e qualidade de software
- Estudo de métricas voltadas ao controle de qualidade no desenvolvimento de software
------------
<br>

**O que é qualidade ?**
Segundo um QA, é a sensação de que um produto ou serviço atende a necessidade do cliente, segundo o IEEE é o grau de conformidade de um sistema, componentes ou processo com seus respectivos requisitos.

#### Ciclo de vida de projetos de software

**waterfall - cascata**
Projetos regulares com etapas definidas para:
-   Investigação
-   Prototipação
-   Desenvolvimento
-   Testes
-   Liberação em produção

**Ciclo de vida ágil**
Projetos interativos onde a cada etapa de tempo(sprint) ocorre uma entrega de valor.

#### Tipos de testes e suas características
Para que exista qualidade é necessário que exista repetibilidade no processo e consistência nos fluxos.
A qualidade é caracterizada como uma "sensação" pelo Quality Assurance Institute, o usuário ou cliente sabe que um produto tem "qualidade" se esse produto, serviço ou artefato serve ao seu propósito.


**Caixa transparente**
O conceito advem da possibilidade de conhecermos partes "internas" do artefato a ser testado.
Essas estratégias aproveitam o conhecimento de como o código foi criado, sua tecnologia e seu acomplamento.
Também existem expressões como "caixa branca", "caixa preta" e "caixa cinza".

#### Conceito de unidade para teste
-   Uma unidade pode ser a menor parte indivisível do código.
-   Em geral temos:
    -   DD path - Caminho decisão à decisão
    -   DU path - Declaração e Uso das variáveis.

```javascript
...
if(a == b)
{
    b = b + 1;
}
if(b > a)
{
    b = b - 1;
}
```

```javascript

var a = 0;
let b = 0;
...
if(a == b)
{
    b = b + 1;
}
if(b > a)
{
    b = b + 1;
}
```

#### Necessidade de isolamento entre componentes
Unidades devem ser isoladas entre si, de maneira a garantir o minímo de interferencia externa quando os estímulos forem recebidos.
Para criar os níveis de isolamento é necessário criar stubs, chamados de esqueletos que sempre respondem a um valor conhecido quando a classe ou métodod depende de algum agente externo.
Os estímulos gerados devem ser rastreáveis e repetitivos.

##### Exmplo de níveis

**Nivel de método:**
Método soma(inteiro a, inteiro b)
{
    retorna a+b
}

**Nível de método (testes):**
Esperando = [2, 1.0, -1, erro]
Esperado[0] = soma(1,1)
Esperado[1] = soma(0,1)
Esperado[2] = soma(0,0)
Esperado[3] = soma(1,-2)
Esperado[4] = soma(A,1)

**Nível de classe:**

Classe instalacao(caminho)

Metodo publico instalar(caminho){
validaRegistroApp()
copiaArquuvos(caminho)
verifica instalacao()

Metodo privado
validaRegistroApp()
...

Metodo privado
copiaArquivos(caminho)
...

Metodo privado
verificaInstalação()
...

}

**Nível de classe (testes):**

Esperado = [Pass, Pass, Fail]
Esperado[0] = Instalacao.instalar("C:\temp")
Esperado[1] = Instalacao.instalar("./temp")
Esperado[2] = Instalacao.instalar("@#$%")

Critérios ambientais:
-   HD cheio
-   Usuário sem direitos de instalação
-   Direitório protegido
-   Diretório Inexistente
-   Arquivos somente para leitura

#### Estratégias de teste unitário

**TDD - Test Driven Developement**
Cria-se o teste unitário antes de começar a codificação.
Nessa estratégia os testes devem sempre falhar inicial,ente, após a falha se escreve o código para que o teste passe.

**BDD - Behavior Driven Development**
Entende-se a demanda da unidade para que sejam criados os testes.
Podem ser baseados em "promessas" ou requisitos funcionais / não-funcionais.

Como um (pessoa ou perfil)
Eu gostaria de (funcionalidade)
Para que (objetivo ou benefício)

Critérios de aceitção:
-   Dado que (critério inicial)
-   Quando (evento que inicia a ação)
-   Então (resultados esperados)

#### Diferenças entre teoria e prática.
No dia-a-dia cria-se o código e depois testa-se.
Poucos times conseguem ter a disciplina de criar os testes primeiro para verificar a "falha" para depois implementar o código.
Ferramentas de verificação de código são boas referências para a saúde do código, assim como o entendimento do esforço faltante para complementação de testes.

A regra de ouro é 80% ou mais de cobertura de código.


#### Integração dos testes unitários no dia-a-dia
A integraço dos testes unitários deve iniciar logo uqe o projeto comece, pois muitas vezes o código para investigação e pesquisa é mantido para o produto final.
Sistemas de build devem concentrar a execução dos testes unitários de forma a prover a execução automática em diferentes níveis.
A cobertura de código deve ser analisada para fins de aprovação ou rejeição do PR(pull-request), no caso de uso do git-hub.


##### Processo de build
Processos de build devem ter a capacidade de validar branches progressivamente bem como executar testes unitários de acordo com regime requisitado.

**Estratégia 1:**
Executar todos testes unitários após cada commit.
Essa forma proporciona uma grande confiabilidade no código a ser integrado, porém causa filas para validação.

**Estratégia 2:**
Executar os testes no código a ser inserido na branch principal.
Proporciona uma maior velocidade e pontualidade dos processos, entretanto cria-se uma demanda de executar os testes completos ao final de um período de tempo ( dia - semana ou sprint).

##### Processo de review e merge

O processo de revisão voltado à qualidade devem se ater aos padrões de código definidos pelo time e também a cobertura de testes unitários provida.
Quando postergados os testes acabam por promover novas atividades futuras e retrabalho, conhecidas como dívidas técnicas.

A integração do código gerado com a branch principal só deve ser feita(aprovada) após verificações de padronagem de código, testes unitários e avaliações estáticas de código.
EX: - [Lint](https://en.wikipedia.org/wiki/Lint_(software))

#### Testes de integração
Avaliam o ecossistema no qual os diferentes métodos ou classes se integram compondo a solução.
As estratégias de testes de integração tendem a exercitar incrementalmente a união parte a parte das unidades.

EX: Testes unitários para uma calculadora, seriam feitos testes para cada método (soma, subtração, divisão e multiplicação). A+B, A-B, A/B e A*B
No caso de integralção, os testes devem exeritar o conjunto incremental dos mótodos soma seguida de subtração e divisão. A+(B-A)*B+B/A

##### Estratégias de intregração de componentes

**Top-down**
Cria-se testes para a camada mais superior da solução. O grande problema dessa abordagem é a grande quantidade de variáveis para diagnóstico da causa raiz.
Mas a complexidade dos testes é mais baixa

**Bottom-up**
Onde os métodos e calsses vão sendo testados aos poucos mantendo partes isoladas. A desvantagem dessa abordagem é o consumo de tempo para execução e manutenção dos testes a cada interação de software.

**Sanduiche**
Um misto das abordagens anteriores, onde partes mais críticas do sistema são testadas individualmente e partes estáveis são testadas em alto nível pela integração.

##### Frontend /backend
O backend é testado atráves de um conjunto de Rest Apis, e outras estruturas mantidas sem interface com o usuário, o Frontend é xercitado manipulando-se os componentes e controles visuais disponíbilizados pela aplicação/solução ou serviço.

##### Testes de interface com o usuário
São testes realizados manipulando-se os controles disponíveis visualmente.
Principais pontos:
-   Verificação do alinhamento dos componentes visuais.
-   Verificação dos padrões de ancoragem, padronização das cores, fontes e espaçamentos.
-   Verificação do vocabulário usado.

##### Teste de performance
São avaliações/inspeçoes periódicas que devem ser feitas visando un cenário de uso específico.

As seguintes perguntas devem ser feitas:
-   Quantos usuários devem acessar ( em média) a solução por minuto?
-   Quais os limites de escalonamento(máquinas, memória, HD)?
-   Quais são os SLAs definidos (prazos e limites)?

**Definição de testes de perfonmance**
Baseados nos parâmetros anteiores, devemos:

-   Estabelecer cenários incremantais de carga(100 usuários por minuto).
    -   100 usuários por minuto => 100 / 60 = 1.7 usuarios por segundo => 2 usuários por segundo.

1.  Carga inicial de 10 usuários por minuto por 5 minutos, adicionando-se 10 ao final do tempo.
2.  Carga inicial de 100 usuarios por minuto por 20 minutos, adicionando-se 10 ao final do tempo.
3.  Carga inicial de 200 usuários por minuto por 1 hora.

**Definição de baseline**
É definida como o padrão atual ou padrão definido.
Atráves dos testes anteiores pode ser definida uma baseline atual.
No caso, por exemplo, digamos que com carga de 100 usuários por minuto o sistema se manteve em 20% de alicação(geral) com tempos de resposta inferior a 1 segundo.
Na próxima liberação caso o tempo de resposta dobre e a alocação de infra seguir igual, podemos indentificar uma quebra de baseline causada por código, que deve ser avaliada.

##### Definição de ROI
O retorno de investimento é um calculo que auxilia o entendimento dos gastos comprometidos com a qualidade e o que poderia ter sido o prejuizo por não aplicar.
De maneira geral:
-   Quantidade de pessoas do desenvolvimento
-   Quantidade de pessoas na qualificação
-   Número de defeitos achados
-   Etapa em que foram achados defeitos

#### Key Performance indicator
-   Satisfação do cliente
-   Processo interno de qualidade
-   Satisfação do funcionário
-   ìndice de performance financeira

##### Quais KPI escolher?
-   Custo do trabalho
-   Percentual de entregas perdidas
-   Estimativas de artefatos entregues (no tempo)
-   Custo da gerência de processos
-   Ordem completada por ciclo de tempo
-   Throughput
-   Crescimento do mercado
-   Satisfação do consumidor
-   Variância entre falhas
-   Média de tempo para resposta inicial.

**Mais métricas, mais complicado de veririficar**
Quanto mais métricas existirem no processo que qualidade e verificação do projeto, mais completo e complexo serão as análises providas pela mesma.

**Como correlacionar níveis de qualidade com métricas?**
-   Nível de teste unitário:
    -   Em geral são vistos correlações entre quanidade de linhas de código adicionadas/modificadas por periodo de tempo.
    -   Número de defeitos a cada mil linhas de código(KLoC)
    -   % de cobertura de código
-   Nível de teste de integração:
    -   Defeitos por componentes
    -   Componente mais alterado x defeitos achados(efetividade do teste)
-   Nível de sistema:
    -  Quantidade de defeitos achados por tempo(por prioridade)
    -  Quantidade de defeitos resolvido por tempo
    -  Idade dos defeitos por prioridade.

**Como saber qual abordagem usar?**
-   Começar sempre pelo mais simples
-   Conforme mais perguntas aparecem, pode-se aumentar o nível de detalhamento
-   Controle nos logs da aplicação sempre ajudam.


#### Testes A / B
São testes que comparam duas versões de conteúdo para identificar qual versão tem maior atratividade aos clientes.
Sempre se verifica a versão A contra a versão B como parâmetro de medida, baseado nas métricas atribuídas.
-   Trafego gerado
-   Quantos usuários completaram a ação
-   Quantos usuários responderam dentro do tempo esperado
-   Qual foi o potencial para engajamento.

**Quando e porque?**
Testes A / B proveem maior benefício quando ocorrem continuamente.
Com a cedencia correta, pode-se gerar um conjunto de recomendações e melhorias de performance atrelada ao serviço ou produto.
Canais de contato com cliente podem se aproveitar deste tipo de validação para verificar a eficácia de comunicação através de:
-   Email
-   Newsletter
-   Propaganda
-   SMS
-   Páginas de anúncio de website
-   Aplicativos em Smartphones

**Beneficios para websites**
-   Aliando-se ao uso de ferramentas analiticas, pode-se definir qual formato é mais eficiente para atingir o público alvo.
-   Ao mesmo tempo possibilitando uma "falha" controlada e rápida adaptação, pois nem todos os clientes serão afetados pelo teste. E um conceito testado que se prove incorreto ou aplicado de forma errônea não acarretará necessariamente np impacto direto de todos usuários.

**Como aplicar**
1.  Entendimento e revisão da Baseline
2.  Determinação de um objetivo baseado no Baseline(aumento de 10% na velicidade de aquisição de passagens aéreas)
3.  Desenvolvimento de uma hipótese que irá alavancar a performance(criação de atalho para os destinos mais pesquisados)
4.  Identificação dos alvos para teste e localização(clientes logados que fazem compras no site)
5.  CRiação de versões A e B(A - sem atalhos e B - com atalhos)
6.  Utilização de ferramentas de automação de testes
7.  Execução e validação dos resultados do teste com uso de ferramentas analíticas
8.  Aplicar o conhecimento na melhoria dos processos e experiência

