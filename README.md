<p align="center">
    <img loading="lazy" src="https://files.engaged.com.br/5db0810e95b4f900077e887e/account/5db0810e95b4f900077e887e/xMCS8NFKTMqwhefy8WLd_catolica-horizontal.png" width="300">
</p>

# Capa
- **Título do Projeto**: PGReports.
- **Nome do Estudante**: Nathan Cielusinski.
- **Curso**: Engenharia de Software.
- **Data de Entrega Inicial**: 30/11/2025.
- **Data de Entrega Final:** 24/06/2026.

# Resumo
O PGReports é uma aplicação web desenvolvida para auxiliar na análise de logs e métricas de desempenho de instâncias PostgreSQL dentro dos ambientes corporativos da WEG. O sistema centraliza e transforma dados complexos de logs em informações acessíveis, permitindo que DBAs e analistas identifiquem rapidamente gargalos, queries custosas e comportamentos atípicos. O projeto destaca-se por sua abordagem direta ao log cru *(raw log)*, possibilitando avaliações profundas e diagnósticos mais precisos. A aplicação visa otimizar o tempo de análise e aumentar a eficiência das equipes técnicas, tornando o processo de identificação e resolução de problemas mais ágil, visual e confiável.

## 1. Introdução
- **Contexto**: A aplicação PGReports foi desenvolvida para suprir uma necessidade interna da empresa WEG nas áreas de SAP BASIS (SAP Business Application Software Integrated Solution), suporte de infraestrutura e para auxiliar os colaboradores responsáveis por _bancos de dados_ que estejam ligadas à aplicações.
  
- **Justificativa**: Com a alta demanda de instâncias PostgreSQL surgindo, foi identificado o crescimento abundante destes ambientes gerenciados pela TI. Considerando problemas que se tornavam muito custosos e trabalhosos para identificar uma resolução cabível, o PGReports foi pensado e desenvolvido para auxiliar na avaliação final e, rapidamente, identificar os problemas destes _bancos de dados_.
  
- **Objetivos**: Facilitar a análise de DBAs, analistas e responsáveis por *databases* para identificar problemas em instâncias e bancos de dados Postgres internos da WEG.

## 2. Descrição do Projeto
* **Linha de Projeto**: O PGReports é uma aplicação web disponibilizada na rede interna da empresa WEG.
  
* **Tema do Projeto**: Uma aplicação que economiza tempo e facilita a visualização de dados e informações de nível mais profundo dos logs PostgreSQL.
  
* **Propósito e Uso Prático**: Quando ferramentas básicas de visualização e análise de dados, como Grafana, se tornam superficiais para a resolução de um problema, analistas devem atuar para identificar o gargalo ou a falha que resultou no problema encontrado. O PGReports surge, nesses casos, como uma ótima opção de análise, uma vez que trabalha diretamente com o _raw log_ (log puro e sem tratamento algum).

* **Público-Alvo**: O público alvo dessa ferramente são DBAs, analistas BASIS e os próprios responsáveis por bancos de dados dentro dos ambientes gerenciados pela T.I da WEG.

* **Problemas a Resolver**: Desperdício de tempo para encontrar situações atípicas, queries que estão sendo mais executadas, mais demoradas e mais custosas, no geral, para o servidor, assim como a identificação da aplicação e client responsável pela execução dessas queries. De maneira abrangente, o PGReports facilita na resolução destes problemas agrupando essas informações de forma prática com uma interface amigável ao usuário final.

* **Diferenciação/Ineditismo**: Trabalhar com o "log cru" de forma detalhada, profunda e direta para apresentar os dados em uma exibição prática e intuitiva.

* **Limitações**: Como o PGReports surgiu para suprir uma necessidade existente da empresa, abrangendo apenas ambientes gerenciados pela T.I. WEG, seu foco está voltado para a instância geral, o que não abrange a avaliação individual dos bancos de dados presentes nela. Vale ressaltar que a aplicação pode gerar insights positivos quanto à melhorias de aplicações e databases individuais, mas os reports não são voltados às _databases_, e sim à instância em que estes se localizam.

* **Normas e Legislações Aplicáveis**: O desenvolvimento e a operação do PGReports seguem diretrizes de conformidade técnica e de proteção de dados, assegurando que informações corporativas sejam tratadas com segurança e responsabilidade.
  - LGPD (Lei Geral de Proteção de Dados – Lei nº 13.709/2018):
O PGReports não coleta dados pessoais de usuários finais. Todos os logs processados são provenientes de servidores internos e possuem natureza técnica, não identificando pessoas físicas. Caso haja necessidade futura de integração com dados sensíveis.
  - ISO/IEC 27001 – Segurança da Informação: As práticas de controle de acesso, armazenamento seguro e versionamento seguem os princípios da norma ISO/IEC 27001, garantindo confidencialidade, integridade e disponibilidade das informações.
  - OWASP: O sistema foi projetado com base nas boas práticas de segurança de aplicações web, prevenindo riscos como injeção de código, falhas de autenticação e exposição indevida de dados.
  - Política Interna de Segurança WEG: O PGReports opera exclusivamente na rede corporativa, observando as políticas internas de TI e conformidade da WEG, com controle de acesso restrito a usuários autenticados e autorização hierárquica.

* **Métricas de Sucesso**: O sucesso do PGReports será avaliado pela eficiência e impacto direto nas operações de análise de dados da WEG. Entre os principais indicadores estão:
  - Redução do tempo de diagnóstico de falhas em bancos PostgreSQL.
  - Identificação de gargalos e queries ineficientes, prevenindo incidentes.
  - Aumento da produtividade das equipes técnicas, com centralização das informações.
  - Melhoria na performance das aplicações e no uso dos recursos do servidor.
  - Maior rastreabilidade em ações de usuários dos bancos de dados PostgreSQL.
  - Adoção interna crescente e feedback positivo dos usuários.

## 3. Especificação Técnica
Considerando e assegurando a conformidade com boas práticas de desenvolvimento web e segurança corporativa, os requisitos, arquitetura, design e considerações técnicas do PGReports foram pensados da seguinte forma:

### 3.1. Requisitos de Software
- **Requisitos Funcionais (RF)**:
  1. RF-001 — Geração de relatórios D-1:
      - O sistema deve gerar e disponibilizar os relatórios no modelo D-1, permitindo que os dados de um determinado dia sejam consultados a partir do dia seguinte.
  2. RF-002 — Processamento incremental:
      - O sistema deve processar os logs brutos gerados pelas instâncias PostgreSQL e produzir relatórios incrementais, evitando o reprocessamento desnecessário de dados já analisados.
  3. RF-003 — Consulta por calendário:
      - O usuário deve poder acessar relatórios diários e semanais por meio de um calendário interativo.
      - O calendário deve apresentar somente datas e períodos que possuam relatórios disponíveis.
  4. RF-004 — Classificação de eventos:
      - O sistema deve organizar e exibir os dados de acordo com categorias de eventos, incluindo:
        - erros;
        - checkpoints;
        - vacuums;
        - locks;
        - sessões;
        - tipos de queries;
        - demais eventos identificados nos logs.
  5. RF-005 — Dashboards e métricas:
      - O sistema deve exibir métricas e informações de desempenho em dashboards visuais.Entre as informações apresentadas devem estar:
        - tempo de execução das queries;
        - quantidade de execuções;
        - queries mais demoradas;
        - queries que mais consumiram tempo;
        - sessões identificadas;
        - eventos e períodos de maior atividade.
  6. RF-006 — Exportação de gráficos:
      - O usuário deve poder exportar ou baixar os gráficos disponibilizados nos relatórios em formato PNG.
  7. RF-007 — Controle de acesso:
      - O sistema deve restringir o acesso a usuários internos autenticados.
A autenticação deve utilizar o serviço corporativo definido para o projeto, como LDAP, Active Directory ou Keycloak.
      - As funcionalidades administrativas devem ser disponibilizadas somente para usuários autorizados.
  8. RF-008 — Retenção de relatórios:
      - O sistema deve permitir a configuração do período de retenção dos relatórios.
      - O período padrão deve ser de 90 dias, após o qual os relatórios e índices relacionados poderão ser removidos automaticamente.

- **Requisitos Não-Funcionais (RNF)**:
  1. RNF-001 — Desempenho:
      - O processamento dos logs deve ocorrer de forma incremental, reduzindo o tempo de execução e o consumo de recursos.
      - A aplicação deve evitar o reprocessamento completo dos arquivos sempre que houver apenas novos registros.
  2. RNF-002 — Usabilidade:
      - A interface deve ser intuitiva, responsiva e visualmente clara.
      - A navegação deve permitir que o usuário localize ambientes, servidores, períodos e relatórios sem precisar acessar diretamente os arquivos de log.
  3. RNF-003 — Segurança:
      - O acesso deve ser restrito à rede corporativa da WEG ou aos meios de conexão autorizados pela organização.
      - O sistema deve exigir autenticação para acesso aos relatórios.
      - Informações sensíveis presentes nos logs devem ser mascaradas sempre que aplicável.
      - Credenciais e segredos não devem ser armazenados diretamente no código-fonte.
  4. RNF-004 — Escalabilidade:
      - O sistema deve permitir a inclusão de novas instâncias PostgreSQL sem exigir alterações significativas na arquitetura.
      - O processamento de uma instância não deve impedir a geração de relatórios das demais.
  5. RNF-005 — Disponibilidade:
      - As rotinas de coleta, processamento e transferência devem ser executadas automaticamente em segundo plano.
      - Falhas de processamento devem ser registradas para permitir diagnóstico e reexecução.
      - As rotinas podem ser controladas por ferramentas de agendamento e orquestração, como Airflow, cron ou systemd, conforme a arquitetura adotada.
  6. RNF-006 — Compatibilidade
      - O sistema deve ser compatível com instâncias PostgreSQL 14 ou superiores, considerando as versões homologadas e testadas durante o projeto.
      - A compatibilidade deve considerar também o formato e as configurações dos logs utilizados pelo pgBadger.
  7. RNF-007 — Manutenibilidade:
      - Os scripts, configurações e componentes da aplicação devem ser versionados.
      - O código deve ser organizado de forma modular, facilitando correções e inclusão de novas funcionalidades.
      - As configurações específicas de cada ambiente devem ser mantidas separadas da lógica principal da aplicação.
  8. RNF-008 — Rastreabilidade:
      - As rotinas automatizadas devem registrar informações sobre início, término, duração, sucesso e falha das execuções.
      - Os registros devem permitir a identificação da instância, do período e do relatório processado.

- **Aderência aos Requisitos da Linha de Projeto**: O PGReports é uma aplicação Web que atende aos critérios obrigatórios desta linha de projeto:
  - Indexes dos reports desenvolvidos em HTML5, CSS3 e JavaScript (frontend).
  - Interface da aplicação desenvolvida em Typescript.
  - Utilização de scripts Python durante o seu ciclo.
  - Geração de relatórios e visualizações dinâmicas (componentes web responsivos).

### 3.2. Considerações de Design
- **Visão Inicial da Arquitetura**: A arquitetura do PGReports é dividida em quatro camadas principais:
  1. Coleta: As instâncias PostgreSQL geram os logs técnicos, atuando com os scripts e rotinas automatizadas que transferem os arquivos para o processamento. 
  2. Processamento: Parser dos logs (pgBadger) e estruturação dos dados em formato legível.
  3. Armazenamento: Organização dos relatórios em diretórios estruturados por data (ano/mês/semana/dia).
  4. Apresentação: Exibição dos resultados em uma interface web responsiva com gráficos dinâmicos e interativos.
    
- **Padrões de Arquitetura**: O projeto adota uma Arquitetura em Camadas combinada com o padrão MVC (Model–View–Controller):
  - Model: Responsável pela leitura e organização dos dados dos logs.
  - View: Camada de interface e dashboards web.
  - Controller: Lógica intermediária de negócio.


- **Modelos C4**:
  1. Nível 1 — Diagrama de Contexto do Sistema:
    - Objetivo:
      - Mostrar o PGReports de forma geral, sem entrar nos detalhes internos da aplicação, focando nos usuários e sistemas externos que se comunicam com a aplicação.

    - Sistema principal:
      - PGReports:
        - Aplicação web usada para transformar logs e métricas do PostgreSQL em relatórios mais fáceis de consultar.
        - Ajuda DBAs, analistas BASIS e responsáveis por databases a identificar gargalos, queries demoradas, eventos, locks e outros problemas.

    - Usuários:
      - DBA:
        - Consulta relatórios, dashboards e informações de desempenho das instâncias PostgreSQL.
      - Analista BASIS:
        - Usa os dados do PGReports para apoiar análises e chamados relacionados às aplicações.
      - Responsável por Databases:
        - Acompanha os ambientes e verifica queries, eventos e indicadores relacionados aos bancos sob sua responsabilidade.

    - Sistemas externos:
      - Instâncias PostgreSQL:
        - Geram os logs e métricas usados pelo PGReports.
      - Autenticação Corporativa:
        - Valida o acesso dos usuários internos por LDAP, AD ou Keycloak.
      - MinIO S3:
        - Armazena os relatórios, índices e demais arquivos gerados.

  ![Diagrama de Nível 1 - Modelo C4](images/c4model/ModelC4Nivel1.png)

  2. Nível 2 — Diagrama de Contêineres:
    - Objetivo:
      - Mostrar as principais partes que formam o PGReports e a responsabilidade de cada uma.

    - Contêineres:
      - Interface Web / Dashboard:
        - Exibe calendário, overview, top queries, events, sessions, locks e outros relatórios visuais.
        - Desenvolvida com TypeScript, HTML, CSS e JavaScript.

      - Serviço de Aplicação:
        - Recebe as solicitações da interface, aplica filtros, valida acessos e entrega os dados para o frontend.
        - Desenvolvido principalmente em Python.

      - Processador de Logs:
        - Usa pgBadger, Python e Bash para transformar logs brutos do PostgreSQL em relatórios estruturados.

      - Agendador / Automação:
        - Usa Cron, Airflow, GitLab CI/CD e scripts para disparar geração, atualização, transferência e limpeza dos relatórios.

    - Armazenamento:
      - Bucket MinIO S3:
        - Guarda os relatórios processados, índices, gráficos e artefatos organizados por ambiente, servidor e data.

    - Sistemas externos:
      - Instâncias PostgreSQL:
        - Fornecem os logs que serão processados.

      - Autenticação Corporativa:
        - Valida os usuários que acessam a aplicação.

  ![Diagrama de Nível 2 - Modelo C4](images/c4model/ModelC4Nivel2.png)

  3. Nível 3 — Diagrama de Componentes:
    - Objetivo:
      - Mostrar os principais módulos internos do PGReports, principalmente dentro do Serviço de Aplicação.

    - Componentes:
      - Módulo de Autenticação:
        - Valida login, perfil e permissão dos usuários.

      - Módulo de Filtros e Consulta:
        - Aplica filtros por ambiente, servidor, período, database, usuário, evento e tipo de query.

      - Módulo de Leitura de Relatórios:
        - Localiza e lê os relatórios armazenados no MinIO S3.

      - Módulo de Parsing e Análise:
        - Interpreta os arquivos processados e organiza os dados de overview, top queries, events, sessions, locks, checkpoints e vacuums.

      - Módulo de Visualização:
        - Prepara gráficos, tabelas, indicadores e demais informações que serão exibidas na interface.

      - Módulo de Agendamento:
        - Controla as rotinas automáticas de geração, atualização e limpeza dos relatórios.

      - Módulo de Auditoria e Erros:
        - Registra acessos, falhas de leitura, erros de processamento e ações importantes do sistema.

  ![Diagrama de Nível 3 - Modelo C4](images/c4model/ModelC4Nivel3.png)

  4. Nível 4 — Diagrama de Código:
    - Objetivo:
      - Mostrar os detalhes de implementação de um componente específico do PGReports.

    - Implementações:
      - TypeScript:
        - Usado na interface, navegação, filtros, componentes visuais e comunicação com o backend.

      - Python:
        - Usado no serviço de aplicação, leitura de relatórios, automações e integração com o MinIO.

      - Bash / Shell Script:
        - Usado nas rotinas de coleta, execução do pgBadger, transferência e limpeza de arquivos.

      - SQL:
        - Usado em consultas administrativas e na integração com ambientes PostgreSQL.

    - Exemplos de classes ou módulos:
      - ReportController:
        - Recebe as solicitações relacionadas aos relatórios.
      - ReportQueryService:
        - Coordena as consultas e os filtros aplicados.
      - MinioReportRepository:
        - Acessa os relatórios armazenados no MinIO S3.
      - ReportParser:
        - Interpreta o conteúdo dos relatórios.
      - ReportMapper:
        - Organiza os dados no formato usado pela interface.
      - AuthorizationService:
        - Valida o usuário e suas permissões.
      - AuditLogger:
        - Registra acessos, erros e downloads.

  ![Diagrama de Nível 4 - Modelo C4](images/c4model/ModelC4Nivel4.png)

- **Mockups das Telas Principais**: As telas principais incluem:
  - Calendário de relatórios: Seleção de data e navegação entre períodos.
![Calendário de Relatórios](./images/mock/reportscalendar.png)
  - Dashboard inicial (Overview): Visão geral das instâncias e métricas de desempenho.
![Dashboard Overview](./images/mock/reportsoverview.png)
  - Aba “Top": Na área de queries, exibe as consultas mais custosas.
![Dashboard Top Queries](./images/mock/reportslongquery.png)

- **Decisões e Alternativas Consideradas**:
  - Inicialmente, foi avaliada a utilização exclusiva de ferramentas já disponíveis na WEG, como Grafana e Splunk. Essas soluções continuam sendo importantes para monitoramento, observabilidade e centralização de informações. Entretanto, para o caso de uso do projeto, foi identificada a necessidade de uma visualização mais específica dos logs PostgreSQL, com relatórios organizados por ambiente, servidor e período.
  - Também foi considerada a utilização isolada do pgBadger. Apesar de a ferramenta gerar relatórios detalhados a partir dos logs PostgreSQL, ainda seria necessário acessar e organizar manualmente os arquivos produzidos.
  - Diante dessas limitações, optou-se pelo desenvolvimento do PGReports como uma solução complementar, capaz de centralizar os relatórios, aplicar uma organização adequada ao ambiente interno e disponibilizar uma interface adaptada à rotina de DBAs, analistas BASIS e responsáveis por bancos de dados.
  - A escolha pelo desenvolvimento de uma solução própria também permite maior controle sobre os filtros, a retenção dos relatórios, a inclusão de novas instâncias e a evolução das funcionalidades conforme as necessidades internas.

- **Critérios de Escalabilidade, Resiliência e Segurança**:

  - Escalabilidade:
    - O processamento incremental reduz a necessidade de reprocessar completamente os logs já analisados;
    - A inclusão de novas instâncias deve ocorrer por meio de configurações padronizadas, evitando alterações significativas no código principal;
    - As rotinas devem permitir que os ambientes sejam processados de forma independente, reduzindo o impacto de uma instância sobre as demais;
    - A capacidade máxima de processamento deverá ser validada por meio de testes de carga e acompanhamento do tempo de execução das rotinas.
  - Resiliência:
    - Uma falha no processamento de determinada instância não deve interromper a geração dos relatórios das demais;
    - Arquivos ausentes, incompletos ou incompatíveis devem ser registrados e tratados de forma controlada;
    - As rotinas automatizadas devem registrar informações de início, término, sucesso e falha;
    - O sistema deve permitir a reexecução de uma rotina quando ocorrer uma falha durante a coleta, o processamento ou a transferência;
    - Relatórios inválidos ou incompletos não devem substituir arquivos anteriormente gerados e considerados válidos.
  - Segurança:
    - O acesso ao PGReports deve permanecer restrito à rede corporativa da WEG ou aos meios de conexão autorizados, como a VPN interna;
    - A aplicação deve exigir autenticação corporativa e verificar as permissões de acesso de cada usuário;
    - As credenciais, chaves e demais segredos utilizados pela aplicação não devem ser armazenados diretamente no código-fonte;
    - Informações sensíveis encontradas nos logs devem ser mascaradas ou removidas sempre que aplicável;
    - Os usuários e processos do sistema devem possuir somente as permissões necessárias para executar suas funções;
    - Os relatórios e índices devem ser removidos automaticamente após o período de retenção definido, atualmente estabelecido em 90 dias;
    - Os acessos, erros e operações relevantes devem ser registrados para possibilitar auditoria e rastreabilidade.

### 3.3. Stack Tecnológica
- **Linguagens de Programação e Marcações**:
  - **TypeScript**: Utilizado no desenvolvimento da interface web do PGReports, sendo responsável pela navegação, filtros, componentes visuais e interação do usuário com os relatórios;
  - **Python**: Utilizado nas rotinas de automação, transferência, processamento e integração, é responsável por tarefas relacionadas ao Airflow, MinIO e manipulação dos arquivos de relatório;
  - **Bash / Shell Script**: Utilizado na execução de comandos do sistema operacional, gerencia as rotinas de processamento, manutenção, limpeza e execução do pgBadger;
  - **SQL**: Utilizado em consultas administrativas e na obtenção de informações técnicas das instâncias PostgreSQL, quando necessário.
  - **HTML5, CSS3 e JavaScript**: Utilizados na estrutura e apresentação dos relatórios, são os responsáveis pelos dashboards, filtros, gráficos e componentes visuais exibidos ao usuário.

- **Bibliotecas e Componentes de Software**:

| **Tecnologia**                   | **Função no PGReports**                                                                                              | **Categoria**            |
| -------------------------------- | -------------------------------------------------------------------------------------------------------------------- | ------------------------ |
| **Jinja2**                       | Renderização de templates e geração dinâmica de conteúdo HTML, quando aplicável.                                     | Templates                |
| **pgBadger**                     | Processamento dos logs PostgreSQL e geração incremental de relatórios HTML.                                          | Análise de logs          |
| **boto3 / botocore**             | Comunicação com o MinIO por meio da API compatível com S3, realizando leitura, envio e gerenciamento dos relatórios. | Armazenamento            |
| **Paramiko**                     | Realização de conexões SSH e transferências seguras entre servidores.                                                | Comunicação remota       |
| **apache-airflow-providers-ssh** | Disponibilização de hooks e operadores SSH para tarefas executadas pelo Apache Airflow.                              | Orquestração             |
| **Chart.js / Plotly**            | Geração de gráficos e visualizações interativas na interface web.                                                    | Visualização             |
| **datetime / timedelta**         | Manipulação de datas e períodos utilizados nas rotinas automáticas.                                                  | Biblioteca padrão Python |
| **re**                           | Aplicação de expressões regulares para filtragem, validação e mascaramento de informações.                           | Biblioteca padrão Python |
| **os**                           | Manipulação de diretórios, arquivos, variáveis de ambiente e operações do sistema.                                   | Biblioteca padrão Python |
| **stat**                         | Controle e consulta de permissões e atributos de arquivos.                                                           | Biblioteca padrão Python |

- **Plataformas e Infraestrutura**:

| **Tecnologia**                         | **Função no PGReports**                                                                            |
| -------------------------------------- | -------------------------------------------------------------------------------------------------- |
| **PostgreSQL**                         | Origem dos logs e das informações técnicas processadas pelo PGReports.                             |
| **MinIO S3**                           | Armazenamento dos relatórios, índices, gráficos e demais arquivos gerados.                         |
| **Apache Airflow**                     | Orquestração e acompanhamento das rotinas de coleta, transferência, processamento e armazenamento. |
| **Cron / systemd**                     | Execução de rotinas locais e tarefas periódicas no sistema operacional, quando aplicável.          |
| **GitLab CI/CD**                       | Automação dos processos de integração, validação e implantação do projeto.                         |
| **LDAP / Active Directory / Keycloak** | Autenticação e controle de acesso dos usuários internos, conforme a arquitetura adotada.           |

- **Ferramentas de Desenvolvimento e Gestão**:

| **Ferramenta**         | **Utilização**                                                                        |
| ---------------------- | ------------------------------------------------------------------------------------- |
| **Visual Studio Code** | Ambiente principal utilizado para desenvolvimento e manutenção do código.             |
| **Git**                | Controle de versão do código-fonte.                                                   |
| **GitLab**             | Hospedagem do repositório, colaboração e execução dos pipelines de CI/CD.             |
| **Jira**               | Organização das atividades, tarefas, melhorias e correções do projeto.                |
| **Grafana**            | Apoio à observabilidade dos servidores, serviços e rotinas relacionadas ao PGReports. |
    

- **Licenciamento**:
  - Caso o projeto fosse externo a WEG, encaixaria em MIT (permissiva) para reuso interno/acadêmico. Porém, como o repositório é corporativo, o licenciamento é direcionado ao colaborador responsável e padronizado com a WEG.

- **Dependências**:
    | **Dependência / Ferramenta**              | **Licença**        |
    | ----------------------------------------- | -------------------|
    | **Python 3**                              | PSF License        |
    | **Jinja2**                                | BSD 3-Clause       |
    | **pgBadger**                              | PostgreSQL License |
    | **PostgreSQL**                            | PostgreSQL License |
    | **boto3 / botocore**                      | Apache License 2.0 |
    | **paramiko**                              | LGPL 2.1           |
    | **airflow.providers.ssh**                 | Apache License 2.0 |
    | **re / os / stat / datetime / timedelta** | PSF License        |
    | **Chart.js / Plotly**                     | MIT License        |
    | **Git / GitLab / GitHub**                 | MIT License        |
    | **VS Code**                               | MIT License        |
    | **Shell Script / Bash**                   | GNU GPL v3         |
    | **Cron / Systemd**                        | GPL v2             |

### 3.4. Considerações de Segurança
- **Riscos Identificados**: 
    - Exposição de informações sensíveis em logs (strings de conexão, IPs internos, mensagens de erro detalhadas).
    - Falhas de autenticação/autorização (acesso indevido a relatórios).
    - Injeção (HTML Injection) via campos de filtro/consulta exibidos na UI.
    - Command Injection em rotinas que manipulam caminhos/execuções de processos externos.
    - DoS por carga excessiva (picos de logs ou consultas pesadas).
    - Configuração insegura (TLS ausente, segredos em variáveis expostas, permissões amplas no host).
    
- **Medidas de Mitigação**:
    - **Masks:** Informações sensíveis serão tratadas com exibição mascarada.
    - **Controle de acesso:** Autenticação corporativa (keycloak) e autorização por perfil (access e admin).
    - **Validação e sanitização de entrada:** Whitelists de parâmetros, escaping rigoroso em templates Jinja2, Content-Security-Policy (CSP).
    - **Segregação de permissões:** Usuário de sistema dedicado, least privilege.
    - **Proteção contra CSRF:** Tokens anti-CSRF em POSTs sensíveis.
    - **Proteção operacional:** Rate limiting em endpoints críticos, timeouts e bulkheads para tarefas de parsing.
    - **Gestão de segredos:** Variáveis de ambiente/secret manager, nunca versionar credenciais.
    - **Hardening & Logs:** Auditoria de acessos, rotação/retenção (90 dias).
    - **Backups e recuperação:** Snapshots dos artefatos de relatório, indexes, servidores, instâncias e *databases*.

- **Normas e Boas Práticas Seguidas**:
    - OWASP: Diretrizes para prevenção de vulnerabilidades web (XSS, auth, exposição de dados).
    - ISO/IEC 27001: Princípios de confidencialidade, integridade e disponibilidade (políticas, controle de acesso, trilhas de auditoria).
    - LGPD (Lei nº 13.709/2018): Princípio da minimização, tratamento apenas de dados técnicos necessários, anonimização quando aplicável e política de privacidade interna.
    
- **Responsabilidade Ética**:
    - Privacidade por padrão: Processar apenas o necessário para diagnóstico, mascarando ou suprimindo PIIs acidentais em logs.
    - Transparência: Seguir a mesma configuração de exibição de dados que a WEG disponibiliza, sem alterações ou variações, puxando diretamente do arquivo postgresql.conf.
    - Uso responsável de dados e automações: Auditoria de regras que destacam “gargalos” para evitar decisões errôneas e sempre com supervisão humana presente.
    - Futuras extensões com IA: Caso sejam adicionados modelos para detecção de anomalias, seguiremos os princípios da UNESCO – *Ética em IA e OECD AI Principles*.

### 3.5. Conformidade e Normas Aplicáveis
O desenvolvimento e a operação do PGReports seguem rigorosamente as normas e legislações aplicáveis ao contexto de sistemas corporativos, com foco em segurança da informação, privacidade de dados e boas práticas de desenvolvimento de software.
- LGPD – Lei Geral de Proteção de Dados (Lei nº 13.709/2018):
    - O PGReports não coleta dados pessoais de usuários externos.
    - Todos os dados processados são logs técnicos provenientes de servidores PostgreSQL corporativos, sem identificação de pessoas físicas.
    - Caso haja necessidade futura de integração com dados sensíveis, o sistema seguirá os princípios da minimização, anonimização e finalidade legítima.
    - O projeto mantém aderência à política interna de privacidade da WEG e à gestão de dados corporativos.
      
- ISO/IEC 27001 – Segurança da Informação:
    - A arquitetura segue os pilares de confidencialidade, integridade e disponibilidade das informações.
    - São aplicados controles de acesso restrito, auditoria de uso e segregação de funções.
    - Logs e relatórios são armazenados em diretórios protegidos e com tempo de retenção definido (90 dias).
    - Backups e procedimentos de recuperação de falhas seguem as diretrizes internas de segurança e continuidade de negócios.

- OWASP - Segurança de Aplicações Web:
    - O sistema é projetado com base nas boas práticas de segurança definidas pela OWASP Foundation, mitigando riscos como:
        - Injeção de código (SQL/Command Injection).
        - Quebra de autenticação e gerenciamento de sessão.
        - Exposição de dados sensíveis.
        - Falhas de configuração de segurança.
    - Implementações incluem sanitização de entradas, escape em templates, controle de sessão seguro e criptografia de comunicações (HTTPS/TLS).

- Política Interna de Segurança WEG:
    - O PGReports opera exclusivamente dentro da rede corporativa da WEG.
    - O acesso é controlado via autenticação corporativa (LDAP/AD).
    - Todas as comunicações e permissões são auditáveis e alinhadas com as diretrizes de conformidade interna da empresa.
   
## 4. Evolução do Projeto e Próximos Passos

O desenvolvimento do PGReports foi realizado de forma incremental, passando pelas etapas de validação técnica, implementação das funcionalidades principais, aprimoramento da interface, automação das rotinas, integração com os serviços utilizados e validação do funcionamento da solução.

As atividades previstas no planejamento inicial foram concluídas, resultando em uma aplicação funcional para geração, armazenamento e visualização de relatórios de ambientes PostgreSQL.

### 4.1. Entregas Concluídas

As seguintes atividades foram implementadas durante o desenvolvimento do projeto:

- Processamento incremental dos logs PostgreSQL com o pgBadger;
- Geração e disponibilização dos relatórios no modelo D-1;
- Organização dos relatórios por ambiente, servidor e período;
- Implementação da navegação por calendário;
- Desenvolvimento dos módulos de visualização, incluindo:
  - Overview;
  - Top Queries;
  - Events;
  - Sessions;
  - Locks;
  - Checkpoints;
  - Vacuums;
- Exibição de queries mais executadas, mais demoradas e com maior consumo de recursos;
- Implementação de dashboards, gráficos, tabelas e filtros dinâmicos;
- Desenvolvimento da interface web com TypeScript;
- Utilização de scripts Python e Bash nas rotinas de processamento e automação;
- Integração das rotinas com o Apache Airflow;
- Transferência e armazenamento dos relatórios no MinIO S3;
- Implementação de conexões e transferências seguras por SSH;
- Organização dos arquivos e índices no bucket por ambiente, servidor e data;
- Implementação das rotinas de limpeza no servidor Linux;
- Aplicação da política de retenção e descarte dos relatórios;
- Tratamento de arquivos ausentes, incompletos ou inválidos;
- Registro das execuções, sucessos e falhas das rotinas automatizadas;
- Ajustes no horário de execução e no tempo de transferência dos arquivos;
- Aplicação de mascaramento em informações sensíveis encontradas nos logs;
- Implementação do controle de acesso corporativo;
- Validação da aplicação com os usuários envolvidos;
- Ajustes de usabilidade e padronização visual;
- Elaboração da documentação técnica e dos diagramas do Modelo C4;
- Revisão dos requisitos funcionais e não funcionais;
- Preparação da aplicação e da documentação para a entrega final do projeto.

### 4.2. Marcos Concluídos

| **Marco** | **Descrição**                                           | **Data Planejada** | **Status** |
| --------- | ------------------------------------------------------- | -----------------: | ---------- |
| **M1**    | Documento inicial de especificação técnica              |         30/11/2025 | Concluído  |
| **M2**    | Protótipo funcional do parser e dashboard básico        |         15/12/2025 | Concluído  |
| **M3**    | Integração com PostgreSQL, armazenamento e autenticação |         30/01/2026 | Concluído  |
| **M4**    | Testes de desempenho, resiliência e segurança           |         15/03/2026 | Concluído  |
| **M5**    | Implantação interna e validação com usuários            |         10/04/2026 | Concluído  |
| **M6**    | Automação das rotinas de limpeza e manutenção           |         10/05/2026 | Concluído  |
| **M7**    | Consolidação da documentação e entrega do Portfólio II  |         24/06/2026 | Pendente  |

### 4.3. Estado Atual da Solução

O PGReports encontra-se em estado funcional, com as principais rotinas de coleta, processamento, armazenamento e apresentação dos relatórios implementadas, já obtendo resultados positivos em avaliações internas da empresa.

Atualmente, o sistema permite que os usuários consultem informações técnicas dos ambientes PostgreSQL sem precisar analisar diretamente arquivos extensos de log. A aplicação centraliza os relatórios, organiza os dados por período e apresenta informações relevantes por meio de dashboards e visualizações específicas.

O projeto atende ao objetivo inicial de reduzir o esforço necessário para análise dos ambientes e facilitar a identificação de queries custosas, eventos, bloqueios, sessões e comportamentos atípicos.

### 4.4. Planos para o futuro — Integração com um Agente de Inteligência Artificial

Como evolução futura do PGReports, propõe-se a integração de um agente de inteligência artificial capaz de analisar automaticamente os relatórios gerados pela aplicação.

O agente atuaria como uma camada adicional de apoio à análise técnica, utilizando as informações já processadas pelo PGReports para identificar comportamentos relevantes e apresentar conclusões de forma mais direta aos usuários.

#### Objetivos do Agente de Inteligência Artificial

- Analisar automaticamente os relatórios gerados pelo PGReports;
- Identificar padrões de comportamento nas instâncias PostgreSQL;
- Detectar possíveis anomalias e situações atípicas;
- Apontar queries com alto custo, longa duração ou grande quantidade de execuções;
- Identificar aumento incomum de erros, locks, vacuums ou checkpoints;
- Comparar o comportamento atual com períodos anteriores;
- Gerar resumos técnicos sobre o estado das instâncias;
- Destacar possíveis gargalos de desempenho;
- Sugerir pontos que devem ser investigados pelos responsáveis;
- Gerar alertas quando determinados limites ou comportamentos forem identificados.

#### Possíveis Funcionalidades

O agente poderá oferecer funcionalidades como:

- **Resumo diário do ambiente**:
  - Apresentação dos principais eventos encontrados no relatório D-1;
  - Destaque das queries mais impactantes;
  - Identificação de horários de maior atividade;
  - Resumo de erros, locks e eventos relevantes.

- **Detecção de anomalias**:
  - Identificação de variações fora do padrão histórico;
  - Comparação com dias ou semanas anteriores;
  - Detecção de crescimento inesperado no tempo de execução das queries;
  - Identificação de aumento no número de erros ou bloqueios.

- **Classificação de criticidade**:
  - Classificação dos eventos em níveis como:
    - Informativo;
    - Atenção;
    - Alerta;
    - Crítico.

- **Geração de alertas**:
  - Envio de notificações para os responsáveis;
  - Alertas sobre queries com comportamento anormal;
  - Alertas sobre falhas no processamento dos relatórios;
  - Alertas sobre indisponibilidade ou ausência de dados;
  - Alertas sobre crescimento inesperado do consumo de recursos.

- **Explicação dos resultados**:
  - Tradução de informações técnicas para uma linguagem mais clara;
  - Explicação do motivo pelo qual determinada query ou evento foi destacado;
  - Apresentação dos dados utilizados para gerar cada alerta;
  - Indicação de quais informações devem ser verificadas pelo analista.

- **Assistente de consulta**:
  - Permitir que o usuário faça perguntas sobre os relatórios;
  - Responder questões como:
    - “Quais foram as queries mais custosas desta semana?”;
    - “Houve aumento no número de locks?”;
    - “Qual ambiente apresentou mais erros?”;
    - “Quais eventos devem ser investigados primeiro?”;
    - “O comportamento atual está diferente da semana anterior?”.

### 4.5. Fluxo Proposto para o Agente de IA

O fluxo de funcionamento poderá seguir a seguinte estrutura:

```text
Instâncias PostgreSQL
        ↓
Logs técnicos
        ↓
Processamento com pgBadger
        ↓
Relatórios e índices
        ↓
Armazenamento no MinIO S3
        ↓
PGReports
        ↓
Agente de Inteligência Artificial
        ↓
Resumos, alertas e possíveis gargalos
        ↓
DBAs, analistas BASIS e responsáveis pelos ambientes
```

### 4.6. Arquitetura Inicial Proposta

A integração poderá ser dividida nos seguintes componentes:

| **Componente**                   | **Responsabilidade**                                               |
| -------------------------------- | ------------------------------------------------------------------ |
| **Coletor de Dados**             | Obtém do PGReports os dados necessários para análise.              |
| **Normalizador**                 | Converte os relatórios em uma estrutura padronizada para o agente. |
| **Motor de Regras**              | Valida limites e condições previamente definidos pelos DBAs.       |
| **Detector de Anomalias**        | Compara métricas atuais com o histórico do ambiente.               |
| **Agente de IA**                 | Interpreta os resultados e gera resumos técnicos.                  |
| **Classificador de Criticidade** | Define a prioridade dos eventos identificados.                     |
| **Gerenciador de Alertas**       | Envia as notificações aos responsáveis.                            |
| **Interface de Consulta**        | Permite perguntas em linguagem natural sobre os relatórios.        |
| **Módulo de Auditoria**          | Registra as análises, respostas e alertas gerados.                 |

### 4.7. Etapas Futuras de Implementação

#### Etapa 1 — Preparação dos Dados

- Definir quais informações dos relatórios serão enviadas ao agente;
- Criar uma estrutura padronizada de dados;
- Remover ou mascarar informações sensíveis;
- Selecionar as métricas mais relevantes;
- Organizar uma base histórica por ambiente e período.

#### Etapa 2 — Regras e Limites

- Definir limites de duração, quantidade de execuções e criticidade;
- Criar regras iniciais para identificação de possíveis gargalos;
- Definir quais eventos devem gerar alertas;
- Validar as regras com DBAs e analistas;
- Permitir configurações diferentes para cada ambiente.

#### Etapa 3 — Resumos Automáticos

- Gerar resumos diários e semanais;
- Apresentar os principais eventos identificados;
- Destacar diferenças em relação aos períodos anteriores;
- Exibir os dados que fundamentaram cada conclusão;
- Permitir que o usuário acesse o relatório original.

#### Etapa 4 — Detecção de Anomalias

- Criar uma linha de base histórica para cada ambiente;
- Comparar o comportamento atual com o histórico;
- Identificar variações estatisticamente relevantes;
- Reduzir alertas falsos;
- Ajustar os critérios com base no feedback dos usuários.

#### Etapa 5 — Alertas

- Definir os canais de notificação;
- Criar níveis de criticidade;
- Evitar alertas repetitivos;
- Registrar o envio e o recebimento das notificações;
- Permitir que o analista confirme ou descarte um alerta.

#### Etapa 6 — Assistente de Consulta

- Permitir perguntas em linguagem natural;
- Limitar as respostas aos dados autorizados;
- Exibir as fontes utilizadas na resposta;
- Registrar as consultas realizadas;
- Aplicar controle de acesso conforme o ambiente consultado.

### 4.8. Segurança e Governança do Agente

A integração com inteligência artificial deverá respeitar os mesmos princípios de segurança aplicados ao PGReports.

Entre os principais cuidados estão:

- Não enviar logs brutos ou informações corporativas para serviços externos sem autorização;
- Mascarar informações sensíveis dos bancos e sessões;
- Aplicar controle de acesso aos resumos e alertas;
- Restringir cada usuário aos ambientes para os quais possui permissão;
- Registrar as análises e respostas produzidas;
- Informar quando uma conclusão foi gerada pela inteligência artificial;
- Manter os dados utilizados como evidência da análise;
- Evitar que o agente execute alterações diretamente nas instâncias PostgreSQL;
- Exigir validação humana antes de qualquer ação operacional;
- Aplicar políticas de retenção para prompts, respostas e dados processados;
- Avaliar o uso de modelos executados em ambiente interno ou corporativo.

### 4.9. Supervisão Humana

O agente de inteligência artificial deverá atuar como uma ferramenta de apoio, e não como substituto do DBA ou do analista responsável.

As conclusões apresentadas deverão ser interpretadas como recomendações ou pontos de investigação. A decisão final sobre ajustes, correções, encerramento de sessões ou alterações nos ambientes continuará sendo responsabilidade dos profissionais autorizados.

O agente não deverá:

- Executar queries administrativas;
- Alterar configurações do PostgreSQL;
- Encerrar sessões automaticamente;
- Aplicar recomendações sem aprovação;
- Expor informações de ambientes não autorizados;
- Apresentar uma hipótese como causa confirmada sem evidências suficientes.

### 4.10. Resultados Esperados da Evolução

Com a integração do agente de inteligência artificial, espera-se:

- Reduzir ainda mais o tempo necessário para interpretar os relatórios;
- Facilitar a priorização dos eventos mais importantes;
- Identificar comportamentos atípicos de forma antecipada;
- Diminuir o esforço manual de comparação entre períodos;
- Gerar resumos técnicos de forma automática;
- Melhorar a comunicação entre DBAs, analistas e responsáveis pelas aplicações;
- Aumentar a capacidade preventiva da solução;
- Apoiar a tomada de decisão com informações organizadas e contextualizadas;
- Manter histórico dos alertas e comportamentos identificados;
- Evoluir o PGReports de uma ferramenta de visualização para uma plataforma de apoio inteligente ao diagnóstico.

### 4.11. Roadmap Futuro

| **Marco Futuro** | **Descrição**                                       | **Prioridade** | **Status** |
| ---------------- | --------------------------------------------------- | -------------: | -------------- |
| **F1**           | Padronização dos dados para análise do agente       |           Alta | Para Planejar  |
| **F2**           | Implementação do motor inicial de regras            |           Alta | Para Planejar  |
| **F3**           | Geração automática de resumos diários               |           Alta | Para Planejar  |
| **F4**           | Classificação de eventos por criticidade            |           Alta | Para Planejar  |
| **F5**           | Detecção de anomalias com base no histórico         |          Média | Para Planejar  |
| **F6**           | Envio de alertas para os responsáveis               |          Média | Para Planejar  |
| **F7**           | Assistente de consulta em linguagem natural         |          Média | Para Planejar  |
| **F8**           | Avaliação de modelos executados em ambiente interno |           Alta | Para Planejar  |
| **F9**           | Validação do agente com DBAs e analistas            |           Alta | Para Planejar  |
| **F10**          | Auditoria e acompanhamento da precisão das análises |           Alta | Para Planejar  |

## 5. Referências
POSTGRESQL GLOBAL DEVELOPMENT GROUP. PostgreSQL Documentation (v14–17).
Disponível em: https://www.postgresql.org/docs/


AYYALUSAMY, B. pgBadger: PostgreSQL Log Analyzer and Report Generator.
Disponível em: https://github.com/dalibo/pgbadger


PYTHON SOFTWARE FOUNDATION. Python 3 Documentation.
Disponível em: https://docs.python.org/3/


GNU PROJECT. Bash Reference Manual.
Disponível em: https://www.gnu.org/software/bash/manual/bash.html


MICROSOFT. Visual Studio Code Documentation.
Disponível em: https://code.visualstudio.com/docs


OWASP FOUNDATION. OWASP Top 10 – Web Application Security Risks.
Disponível em: https://owasp.org/www-project-top-ten/


BRASIL. Lei nº 13.709, de 14 de agosto de 2018 – Lei Geral de Proteção de Dados Pessoais (LGPD).
Disponível em: https://www.planalto.gov.br/ccivil_03/_ato2015-2018/2018/lei/L13709.htm


ISO. ISO/IEC 27001 – Information Security Management Systems.
Disponível em: https://www.iso.org/isoiec-27001-information-security.html

## 6. Avaliações de Professores
Adicionar três páginas no final do RFC para que os Professores escolhidos possam fazer suas considerações e assinatura:

- Considerações Professor/a:

- Considerações Professor/a:

- Considerações Professor/a:
