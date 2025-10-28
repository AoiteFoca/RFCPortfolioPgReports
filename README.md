<p align="center">
    <img loading="lazy" src="https://files.engaged.com.br/5db0810e95b4f900077e887e/account/5db0810e95b4f900077e887e/xMCS8NFKTMqwhefy8WLd_catolica-horizontal.png" width="300">
</p>

# Capa
- **Título do Projeto**: PGReports.
- **Nome do Estudante**: Nathan Cielusinski.
- **Curso**: Engenharia de Software.
- **Data de Entrega**: 29/10/2025.

# Resumo
O PGReports é uma aplicação web desenvolvida para auxiliar na análise de logs e métricas de desempenho de instâncias PostgreSQL dentro dos ambientes corporativos da WEG. O sistema centraliza e transforma dados complexos de logs em informações acessíveis, permitindo que DBAs e analistas identifiquem rapidamente gargalos, queries custosas e comportamentos anômalos. O projeto destaca-se por sua abordagem direta ao log cru (raw log), possibilitando avaliações profundas e diagnósticos mais precisos. A aplicação visa otimizar o tempo de análise e aumentar a eficiência das equipes técnicas, tornando o processo de identificação e resolução de problemas mais ágil, visual e confiável.

## 1. Introdução
- **Contexto**: A aplicação PGReports foi desenvolvida para suprir uma necessidade interna da empresa WEG nas áreas de BASIS, suporte de infraestrutura e para auxiliar os colaboradores responsáveis por _databases_ que estejam ligadas à aplicações.
  
- **Justificativa**: Com a alta demanda de instâncias e bancos de dados PostgreSQL surgindo, foi identificado o crescimento abundante destes ambientes gerenciados pela TI. Considerando problemas que se tornavam muito custosos e trabalhosos para identificar uma resolução cabível, o PGReports foi pensado e desenvolvido para auxiliar na avaliação final e, rapidamente, identificar os problemas destes _environments_.
  
- **Objetivos**: Facilitar a análise de DBAs, analistas e responsáveis por bancos de dados à identificar problemas em instâncias e bancos de dados Postgres internos da WEG.

## 2. Descrição do Projeto
* **Linha de Projeto**: O PGReports é uma aplicação web disponibilizada na rede interna da empresa WEG.
  
* **Tema do Projeto**: Uma aplicação que economiza tempo e facilita a visualização de dados e informações de nível mais profundo de um log PostgreSQL.
  
* **Propósito e Uso Prático**: Quando ferramentas básicas de visualização e análise de dados, como Grafana, se tornam superficiais para a resolução de um problema, analistas devem atuar para identificar o gargalo ou a falha que resultou no problema encontrado. O PGReports surge, nesses casos, como uma ótima opção de análise, uma vez que trabalha diretamente com o _raw log_ (log puro e sem tratamento algum).

* **Público-Alvo**: O público alvo dessa ferramente são DBAs, analistas BASIS e os próprios responsáveis por bancos de dados dentro dos ambientes gerenciados pela T.I da WEG.

* **Problemas a Resolver**: Desperdício de tempo para encontrar queries que estão sendo mais executadas, mais demoradas e mais custosas, no geral, para o servidos. Identificação da aplicação e client responsável pela execução dessas queries. De maneira abrangente, o PGReports facilita na resolução destes problemas agrupando essas informações de forma amigável ao usuário final.

* **Diferenciação/Ineditismo**: Trabalhar com o "log cru" de forma detalhada, profunda e direta para apresentar os dados em uma exibição prática e intuitiva.

* **Limitações**: Como o PGReports surgiu para suprir uma necessidade existente da empresa, seu foco está voltado para a instância geral, o que não abrange a avaliação individual dos bancos de dados presentes nela. Vale ressaltar que a aplicação pode gerar insights positivos quanto à melhorias de aplicações e databases individuais, mas os reports não são voltados às _databases_ individuais, e sim à instância em que estes se localizam.

* **Normas e Legislações Aplicáveis**: O desenvolvimento e a operação do PGReports seguem diretrizes de conformidade técnica e de proteção de dados, assegurando que informações corporativas sejam tratadas com segurança e responsabilidade.
  - LGPD (Lei Geral de Proteção de Dados – Lei nº 13.709/2018):
O PGReports não coleta dados pessoais de usuários finais. Todos os logs processados são provenientes de servidores internos e possuem natureza técnica, não identificando pessoas físicas. Caso haja necessidade futura de integração com dados sensíveis, será aplicado o princípio de minimização e anonimização conforme a LGPD.
  - ISO/IEC 27001 – Segurança da Informação: As práticas de controle de acesso, armazenamento seguro e versionamento seguem os princípios da norma ISO/IEC 27001, garantindo confidencialidade, integridade e disponibilidade das informações.
  - OWASP: O sistema foi projetado com base nas boas práticas de segurança de aplicações web, prevenindo riscos como injeção de código, falhas de autenticação e exposição indevida de dados.
  - Política Interna de Segurança WEG: O PGReports opera exclusivamente na rede corporativa, observando as políticas internas de TI e conformidade da WEG, com controle de acesso restrito a usuários autenticados e autorização hierárquica.

* **Métricas de Sucesso**: O sucesso do PGReports será avaliado pela eficiência e impacto direto nas operações de análise de dados da WEG. Entre os principais indicadores estão:
  - Redução do tempo de diagnóstico de falhas em bancos PostgreSQL.
  - Identificação proativa de gargalos e consultas ineficientes, prevenindo incidentes.
  - Aumento da produtividade das equipes técnicas, com centralização das informações.
  - Melhoria na performance das aplicações e no uso dos recursos do servidor.
  - Adoção interna crescente e feedback positivo dos usuários.

## 3. Especificação Técnica
Esta seção descreve os requisitos, arquitetura, design e considerações técnicas do PGReports, assegurando conformidade com boas práticas de desenvolvimento web e segurança corporativa.

### 3.1. Requisitos de Software
- **Requisitos Funcionais (RF)**:
  1. O sistema deve processar logs brutos (raw logs) do PostgreSQL e gerar relatórios incrementais.
  2. O usuário deve poder acessar relatórios diários, semanais e mensais por meio de um calendário interativo.
  3. O sistema deve permitir filtragem por banco de dados, usuário, query e tipo de evento (erro, checkpoint, vacuum, lock).
  4. O sistema deve exibir métricas de desempenho em dashboards visuais, incluindo tempo médio de execução, queries mais custosas e sessões ativas.
  5. O usuário deve poder exportar relatórios em formato HTML e PDF.
  6. O sistema deve permitir o controle de acesso autenticado (login interno via LDAP corporativo).
  7. O administrador deve poder configurar o ciclo de retenção dos relatórios (lifetime de 3 meses).

- **Requisitos Não-Funcionais (RNF)**:
  1. Desempenho: Os relatórios devem ser gerados de forma incremental, otimizando tempo e consumo de recursos.
  2. Usabilidade: Interface intuitiva, responsiva e visualmente clara, com navegação simplificada.
  3. Segurança: Acesso restrito à rede corporativa da WEG e autenticação via LDAP.
  4. Escalabilidade: Suporte à análise simultânea de múltiplas instâncias PostgreSQL.
  5. Disponibilidade: Operação contínua com logs processados em background via agendamentos (cron jobs).
  6. Manutenibilidade: Código modular em Python, organizado por camadas e integrado a sistemas de versionamento (Git).
  7. Compatibilidade: Integração com PostgreSQL 14+ e versões futuras.

- **Aderência aos Requisitos da Linha de Projeto**: O PGReports é uma aplicação Web que atende aos critérios obrigatórios desta linha de projeto:
  - Indexes do report desenvolvidos em HTML5, CSS3 e JavaScript (frontend).
  - Interface desenvolvida em Typescript.
  - Utilização de scripts Python durante o seu ciclo.
  - Integração com banco de dados PostgreSQL.
  - Geração de relatórios e visualizações dinâmicas (componentes web responsivos).
  - Comunicação via HTTP/HTTPS com controle de acesso.

### 3.2. Considerações de Design
- **Visão Inicial da Arquitetura**: A arquitetura do PGReports é dividida em quatro camadas principais:
  1. Coleta: Captura dos logs do PostgreSQL via pgBadger incremental.
  2. Processamento: Parser dos logs e estruturação dos dados em formato legível.
  3. Armazenamento: Organização dos relatórios em diretórios estruturados por data (ano/mês/semana).
  4. Apresentação: Exibição dos resultados em uma interface web responsiva com filtros dinâmicos e gráficos interativos.
    
- **Padrões de Arquitetura**: O projeto adota uma Arquitetura em Camadas combinada com o padrão MVC (Model–View–Controller):
  - Model: Responsável pela leitura e organização dos dados dos logs.
  - View: Camada de interface e dashboards web.
  - Controller: Lógica intermediária de negócio.

- **Modelos C4**:
  1. Nível 1 (Contexto): O PGReports opera dentro da rede WEG, acessando instâncias PostgreSQL internas.
  2. Nível 2 (Container): Divide-se entre servidor web, parser de logs (pgBadger) e base PostgreSQL para armazenamento de relatórios.
  3. Nível 3 (Componentes): Inclui módulos de autenticação, parsing, visualização e agendamento.
  4. Nível 4 (Código): Implementações em Typescript, scripts Bash e Python.

- **Mockups das Telas Principais**: As telas principais incluem:
  - Calendário de relatórios: Seleção de data e navegação entre períodos.
<COLOCAR IMAGEM CALENDARIO AQUI>
  - Dashboard inicial (Overview): Visão geral das instâncias e métricas de desempenho.
<COLOCAR IMAGEM OVERVIEW AQUI>
  - Aba “Top Queries”: Exibe consultas mais custosas.
<COLOCAR IMAGEM TOP AQUI>

- **Decisões e Alternativas Consideradas**:
    - Inicialmente foi considerado o uso direto de ferramentas já implementadas na WEG, como Grafana e Splunk, mas ambas se mostraram superficiais para logs PostgreSQL detalhados.
    - Optou-se, então, por desenvolver o PGReports, garantindo personalização e independência para a empresa.

- **Critérios de Escalabilidade, Resiliência e Segurança**:
    - Escalabilidade: Processamento incremental permite adicionar novas instâncias sem afetar o desempenho.
    - Resiliência: Logs corrompidos ou incompletos são ignorados automaticamente, mantendo a integridade dos relatórios.
    - Segurança:
        - Acesso restrito à rede corporativa (VPN interna).
        - Autenticação via LDAP.
        - Políticas de retenção e descarte automático após 90 dias.

### 3.3. Stack Tecnológica
- **Linguagens de Programação**:
    - Typescript e Python: núcleo da interface e orquestração do pipeline.
    - Bash/Shell: rotinas de agendamento (cron/systemd timer), integração com pgBadger e manutenção/rotação de relatórios.
    - SQL (PostgreSQL): consultas administrativas e eventual persistência de metadados.
    - HTML/CSS/JavaScript: reports/camada de visualização (dashboards responsivos, filtros e interação com gráficos).
      
- **Frameworks e Bibliotecas**:

  | **Biblioteca / Ferramenta**  | **Função / Descrição**                                               | **Categoria**              |
  | ---------------------------- | -------------------------------------------------------------------- | -------------------------- |
  | **Python 3.x**               | Linguagem utilizada para automação.       | Automação        |
  | **Typescript**                    | Linguagem base do projeto e interface da aplicação.             | Front / Web              |
  | **Jinja2**                   | Template engine para renderização dinâmica de relatórios.            | Frontend / Template        |
  | **pgBadger**                 | Parser de logs PostgreSQL e gerador de relatórios incrementais.      | Análise / Log              |
  | **PostgreSQL**               | Banco de dados utilizado como base e origem dos logs.                | Banco de Dados             |
  | **boto3 / botocore**         | Integração com AWS (S3), automação de backups e armazenamento.       | Cloud / Automação          |
  | **paramiko**                 | Conexões seguras SSH para execuções remotas e transferências.        | Rede / Automação           |
  | **airflow.providers.ssh**    | Hook de conexão do Airflow para tarefas programadas via SSH.         | Orquestração / DevOps      |
  | **datetime / timedelta**     | Manipulação e controle temporal em rotinas automáticas.              | Utilitário / Sistema       |
  | **re (Regex)**               | Filtragem de padrões e nomes de arquivos em logs.                    | Processamento / Parser     |
  | **stat**                     | Controle de permissões e atributos de arquivos no sistema.           | Sistema / Segurança        |
  | **os**                       | Manipulação de diretórios, variáveis de ambiente e automações.       | Sistema / Backend          |
  | **Shell Script / Bash**      | Execução automatizada de processos e manutenção de relatórios.       | Automação / Sistema        |
  | **VS Code**                  | IDE principal para desenvolvimento e integração com Git e extensões. | Desenvolvimento            |
  | **Git / GitLab / GitHub**    | Versionamento, CI/CD e colaboração de código.                        | DevOps / Versionamento     |
  | **Chart.js / Plotly**        | Visualização interativa de métricas e gráficos.                      | Frontend / Visualização    |
  | **Bootstrap / Tailwind CSS** | Criação de interfaces responsivas e consistentes.                    | Design / UI                |
  | **Nginx / Apache**           | Proxy reverso e camada de segurança HTTPS/TLS.                       | Infraestrutura / Segurança |
  | **Cron / Systemd**           | Agendamento e monitoramento de execuções automáticas.                | Sistema / Automação        |

- **Ferramentas de Desenvolvimento e Gestão**:
    - IDE/Editor: VS Code.
    - Controle de versão: GitLab, merge requests e code review.
    - CI/CD: GitLab CI.
    - Observabilidade: logs de aplicação/servidor/instância, métricas do host e integração com Grafana.
    - Gestão: Jira.
    
- **Licenciamento**:

  - Projeto PgReports: 
    - Caso o projeto fosse externo a WEG, encaixaria em MIT (permissiva) para reuso interno/acadêmico. Porém, como o caso do repositório é corporativo, o licenciamento é direcionado ao colaborador responsável e padronizado com a WEG.
  - Dependências:
      | **Dependência / Ferramenta**              | **Função no Projeto**                                             | **Licença**        |
      | ----------------------------------------- | ----------------------------------------------------------------- | ------------------ |
      | **Python 3.x**                            | Linguagem principal de automação.                               | PSF License        |
      | **Jinja2**                                | Template engine para renderização de relatórios.                  | BSD 3-Clause       |
      | **pgBadger**                              | Parser e gerador de relatórios de logs PostgreSQL.                | PostgreSQL License |
      | **PostgreSQL**                            | Banco de dados e origem dos logs analisados.                      | PostgreSQL License |
      | **boto3 / botocore**                      | SDK da AWS para automação e integração com S3.                    | Apache License 2.0 |
      | **paramiko**                              | Conexões seguras SSH entre servidores.                            | LGPL 2.1           |
      | **airflow.providers.ssh**                 | Execução remota de tarefas no Airflow.                            | Apache License 2.0 |
      | **re / os / stat / datetime / timedelta** | Módulos nativos do Python para manipulação de arquivos e sistema. | PSF License        |
      | **Chart.js / Plotly**                     | Visualização interativa de métricas e relatórios.                 | MIT License        |
      | **Bootstrap / Tailwind CSS**              | Frameworks CSS para design e responsividade.                      | MIT License        |
      | **Git / GitLab / GitHub**                 | Versionamento e integração contínua (CI/CD).                      | MIT License        |
      | **VS Code**                               | IDE de desenvolvimento e depuração.                               | MIT License        |
      | **Shell Script / Bash**                   | Automação de processos e execução periódica de relatórios.        | GNU GPL v3         |
      | **Nginx / Apache**                        | Proxy reverso e camada de segurança HTTPS.                        | BSD / Apache 2.0   |
      | **Cron / Systemd**                        | Agendamento e monitoramento de rotinas.                           | GPL v2             |


### 3.4. Considerações de Segurança
- **Riscos Identificados**: 
    - Exposição de informações sensíveis em logs (strings de conexão, IPs internos, mensagens de erro detalhadas).
    - Falhas de autenticação/autorização (acesso indevido a relatórios).
    - Injeção (HTML Injection) via campos de filtro/consulta exibidos na UI.
    - Command Injection em rotinas que manipulam caminhos/execuções de processos externos.
    - DoS por carga excessiva (picos de logs ou consultas pesadas).
    - Configuração insegura (TLS ausente, segredos em variáveis expostas, permissões amplas no host).
    
- **Medidas de Mitigação**:
    - **Controle de acesso:** autenticação corporativa (LDAP/SSO) e autorização por perfil (RBAC: DBA, leitura, admin).
    - **Segurança de transporte:** HTTPS/TLS término no reverse proxy (Nginx/Apache); HSTS e secure cookies.
    - **Validação e sanitização de entrada:** whitelists de parâmetros, escaping rigoroso em templates Jinja2, Content-Security-Policy (CSP) para mitigar XSS.
    - **Segregação de permissões:** usuário de sistema dedicado, least privilege, no-root containers (se Docker).
    - **Proteção contra CSRF:** tokens anti-CSRF em POSTs sensíveis.
    - **Proteção operacional:** rate limiting em endpoints críticos; timeouts e bulkheads para tarefas de parsing.
    - **Gestão de segredos:** variáveis de ambiente/secret manager; nunca versionar credenciais.
    - **Hardening & Logs:** cabeçalhos de segurança (X-Frame-Options, X-Content-Type-Options), auditoria de acessos, rotação/retenção (90 dias).
    - **Backups e recuperação:** snapshots dos artefatos de relatório/índices, testes periódicos de restauração.

- **Normas e Boas Práticas Seguidas**:
    - OWASP Top: diretrizes para prevenção de vulnerabilidades web (XSS, auth, exposição de dados).
    - ISO/IEC 27001: princípios de confidencialidade, integridade e disponibilidade (políticas, controle de acesso, trilhas de auditoria).
    - LGPD (Lei nº 13.709/2018): princípio da minimização; tratamento apenas de dados técnicos necessários; anonimização/pseudonimização quando aplicável; logging sem PII; política de privacidade interna.
    
- **Responsabilidade Ética**:
    - Privacidade por padrão: processar apenas o necessário para diagnóstico; mascarar ou suprimir PII acidental em logs.
    - Transparência: registrar quais dados são coletados e por quê; disponibilizar política interna clara aos usuários.
    - Uso responsável de dados e automações: auditoria de regras que destacam “gargalos” para evitar decisões enviesadas com supervisão humana sempre presente.
    - Futuras extensões com IA: caso sejam adicionados modelos para detecção de anomalias, seguiremos os princípios da UNESCO – *Ética em IA e OECD AI Principles*.

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
   
## 4. Próximos Passos
Após a conclusão deste documento, o projeto PgReports seguirá para as etapas de desenvolvimento, validação e aprimoramento contínuo, alinhadas às entregas previstas para Portfólio I e II.
1. Validação Técnica (Novembro/2025)
    - Testes internos de coleta e parsing incremental de logs.
    - Ajustes de desempenho e consistência no processamento via pgBadger.
    - Avaliação da interface inicial e revisão de usabilidade.

2. Desenvolvimento de Funcionalidades-Chave (Dezembro/2025 a Janeiro/2026)
    - Implementação dos módulos Overview, Top Queries, etc.
    - Integração com autenticação corporativa (LDAP) e controle de acesso.
    - Adição de exportação de relatórios em HTML.

3. Aprimoramento da Interface e Experiência do Usuário (Fevereiro/2026)
    - Aplicação de padrões visuais.
    - Criação de dashboards interativos e filtros dinâmicos.
    - Inclusão de indicadores de performance e métricas visuais.

4. Testes de Escalabilidade e Segurança (Março/2026)
    - Testes de carga em múltiplas instâncias PostgreSQL.
    - Validação de autenticação e comunicação segura.
    - Revisão de logs e políticas de retenção (lifetime de 3 meses).

5. Implantação Interna e Coleta de Feedback (Abril/2026)
    - Disponibilização do PGReports para equipes de Suporte, BASIS e DBAs da WEG.
    - Coleta de feedback e métricas de uso real.
    - Planejamento de melhorias e roadmap para nova versão.

| **Marco** | **Descrição**                                      | **Data Estimada** |
| --------- | -------------------------------------------------- | ----------------- |
| M1        | Documento de Especificação Técnica finalizado      | 29/10/2025        |
| M2        | Protótipo funcional do parser e dashboard básico   | 15/12/2025        |
| M3        | Integração completa com PostgreSQL e autenticação  | 30/01/2026        |
| M4        | Testes de desempenho e segurança                   | 15/03/2026        |
| M5        | Implantação interna e validação com usuários reais | 10/04/2026        |
| M6        | Entrega final Portfólio II                         | 30/04/2026        |

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
