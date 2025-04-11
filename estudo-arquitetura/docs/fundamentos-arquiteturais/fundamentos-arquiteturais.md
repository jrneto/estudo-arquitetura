# Fundamentos Arquiteturais

## RAs - Requisitos Arquiteturais

Os Requisitos Arquiteturais (RAs) são as necessidades ou restrições que guiam o design e a implementação de uma arquitetura de software. Eles podem ser divididos em:

- **Requisitos Funcionais**: Definem o que o sistema deve fazer, como funcionalidades específicas.
- **Requisitos Não Funcionais**: Incluem aspectos como desempenho, escalabilidade, segurança e usabilidade.

## VAs - Variáveis Arquiteturais

As Variáveis Arquiteturais (VAs) representam as decisões ou escolhas que podem ser feitas durante o design da arquitetura. Elas são flexíveis e podem variar dependendo do contexto ou das necessidades do projeto. Exemplos incluem:

- Escolha de tecnologias (e.g., frameworks, linguagens de programação).
- Padrões arquiteturais (e.g., microsserviços, monolito).
- Estratégias de deploy (e.g., cloud, on-premises).

Esses conceitos ajudam a estruturar e organizar o processo de design arquitetural, garantindo que as decisões sejam bem fundamentadas e alinhadas aos objetivos do projeto.

## Stakeholders

Os stakeholders são todas as partes interessadas que possuem influência ou são impactadas pelo projeto de software. Eles podem incluir indivíduos, equipes ou organizações, e desempenham um papel fundamental na definição dos requisitos e no sucesso do projeto.

Exemplos de stakeholders no contexto da arquitetura de software:

- **Clientes/Usuários Finais**: Utilizam o sistema e fornecem feedback sobre suas necessidades e expectativas.
- **Equipe de Desenvolvimento**: Responsável por implementar a solução arquitetural.
- **Gerentes de Projeto**: Garantem que o projeto atenda aos prazos, orçamento e escopo.
- **Arquitetos de Software**: Definem e supervisionam a arquitetura do sistema.
- **Equipe de Operações**: Gerencia a infraestrutura e o deploy do sistema.
- **Investidores ou Patrocinadores**: Fornecem os recursos financeiros e esperam retorno sobre o investimento.

Entender as necessidades e expectativas dos stakeholders é essencial para criar uma arquitetura que atenda aos objetivos do projeto e agregue valor ao negócio.

## Custo | Prazo | Qualidade

Na arquitetura de software, é essencial considerar três pilares fundamentais: **Custo**, **Prazo** e **Qualidade**.

O arquiteto deve avaliar cuidadosamente esses aspectos ao iniciar o projeto, pois os requisitos arquiteturais serão definidos com base na prioridade estabelecida pela empresa. Por exemplo, a organização pode optar por priorizar a redução de custos, a entrega rápida ou a alta qualidade do produto final.

Essas decisões impactam diretamente as escolhas técnicas e estratégicas ao longo do desenvolvimento do projeto.

## Componentes Arquiteturais

Os componentes arquiteturais são elementos fundamentais de uma arquitetura de software, cada um com um propósito bem definido e responsável por executar tarefas específicas dentro do sistema. Eles colaboram para atender aos requisitos funcionais e não funcionais da aplicação, garantindo modularidade, escalabilidade e manutenibilidade.

### Exemplos de Componentes Arquiteturais:

- **Cache**: Armazena dados temporariamente para melhorar o desempenho e reduzir a latência de acesso.
- **Fila (Message Queue)**: Gerencia a comunicação assíncrona entre serviços, garantindo resiliência e desacoplamento.
- **API Gateway**: Atua como ponto de entrada único para APIs, gerenciando autenticação, roteamento e limitação de taxa (rate limiting).
- **Log**: Registra eventos e informações do sistema para auditoria, depuração e análise.
- **Monitoramento**: Coleta métricas e dados de desempenho para identificar problemas e garantir a saúde do sistema.
- **NoSQL**: Banco de dados não relacional, ideal para armazenar grandes volumes de dados não estruturados ou semi-estruturados.
- **RDBMS (Relational Database Management System)**: Banco de dados relacional, utilizado para armazenar dados estruturados com suporte a transações e consultas complexas.
- **Orquestrador de Containers**: Gerencia a implantação, escalabilidade e operação de contêineres (e.g., Kubernetes).
- **Identity Provider (IdP)**: Gerencia autenticação e autorização, permitindo Single Sign-On (SSO) e integração com provedores externos.

Esses componentes são escolhidos e configurados de acordo com as necessidades do projeto, garantindo que a arquitetura seja robusta, eficiente e alinhada aos objetivos do negócio.

## ACID

O acrônimo **ACID** representa os quatro pilares fundamentais que garantem a confiabilidade e integridade das transações em sistemas de banco de dados: **Atomicidade**, **Consistência**, **Isolamento** e **Durabilidade**.

- **Atomicidade**: Garante que todas as operações de uma transação sejam concluídas com sucesso ou, em caso de falha, nenhuma delas seja aplicada. É o princípio do "tudo ou nada".
- **Consistência**: Assegura que o banco de dados permaneça em um estado válido antes e depois da transação, respeitando todas as regras de integridade e restrições definidas.
- **Isolamento**: Garante que as transações sejam executadas de forma independente, sem interferir umas nas outras, mesmo quando ocorrem simultaneamente. Isso evita problemas como leituras sujas, leituras não repetíveis e leituras fantasmas.
- **Durabilidade**: Uma vez que uma transação é confirmada (commit), suas alterações são permanentemente gravadas no banco de dados, mesmo em caso de falhas no sistema.

Esses princípios são essenciais para garantir a integridade e a confiabilidade dos dados em sistemas transacionais.

## Camada de Integração

A camada de integração conecta diferentes sistemas ou serviços, permitindo a troca de informações de forma eficiente e confiável. Exemplos de abordagens comuns:

- **Arquivos**: Compartilhamento de arquivos via pastas compartilhadas ou FTP.
- **Filas**: Enfileiramento de mensagens para comunicação assíncrona (e.g., RabbitMQ, Kafka).
- **APIs**: Exposição de endpoints para comunicação síncrona ou assíncrona.
- **Banco de Dados**: Integração direta em nível de banco de dados, como consultas ou replicação.
- **Outros**: Webhooks para notificações em tempo real, gRPC para comunicação de alto desempenho e barramentos como ESB (Enterprise Service Bus).

Essas abordagens são escolhidas com base nos requisitos de desempenho, escalabilidade e desacoplamento do sistema.

## Consumer-Driven Contracts (CDC)

O padrão **Consumer-Driven Contracts** é uma abordagem para garantir que os contratos de comunicação entre microserviços sejam mantidos e testados de forma eficiente. Ele foca em validar que os serviços (producers) atendem às expectativas dos consumidores (consumers) em termos de APIs ou mensagens.

### Como funciona:
1. **Contrato Definido pelo Consumidor**:
   - O consumidor define um contrato que especifica como ele espera que o serviço produtor se comporte (e.g., formato de dados, endpoints, respostas esperadas).
   - Esse contrato é compartilhado com o produtor.

2. **Testes Baseados no Contrato**:
   - O consumidor testa localmente o contrato para garantir que ele está correto.
   - O produtor utiliza o contrato para validar que sua implementação atende às expectativas do consumidor.

3. **Automação**:
   - Ferramentas como **Pact** ou **Spring Cloud Contract** são usadas para automatizar a criação, validação e verificação dos contratos.

### Benefícios:
- **Desacoplamento**: Consumidores e produtores podem evoluir de forma independente, desde que respeitem os contratos.
- **Confiabilidade**: Reduz o risco de falhas na integração entre microserviços.
- **Feedback Rápido**: Problemas de compatibilidade são detectados cedo no ciclo de desenvolvimento.

### Exemplo:
Imagine um microserviço de pagamento (produtor) e um microserviço de pedidos (consumidor). O consumidor define um contrato que especifica:
- Endpoint: `POST /payments`
- Request body: 
  ```json
  {
    "orderId": "123",
    "amount": 100.0
  }
- Response body: 
```json
{
  "status": "success",
  "transactionId": "abc123"
}
```

Essa abordagem é amplamente utilizada em arquiteturas de microserviços para garantir a compatibilidade e a comunicação confiável entre serviços.

## Escalabilidade

A escalabilidade é a capacidade de uma aplicação ou sistema de lidar com um aumento na demanda de forma eficiente, mantendo o desempenho e a disponibilidade. Ela pode ser alcançada de duas formas principais:

1. **Escalabilidade Vertical**: Aumentar os recursos de um único servidor, como adicionar mais memória, CPU ou armazenamento.
2. **Escalabilidade Horizontal**: Adicionar mais instâncias ou servidores para distribuir a carga de trabalho.

Um sistema escalável é projetado para crescer de acordo com as necessidades do negócio, garantindo que ele continue a atender aos usuários mesmo em cenários de alta demanda.