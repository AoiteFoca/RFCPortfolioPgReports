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
  - Model: responsável pela leitura e organização dos dados dos logs.
  - View: camada de interface e dashboards web.
  - Controller: lógica intermediária de negócio.

- **Modelos C4**:
  1. Nível 1 (Contexto): O PGReports opera dentro da rede WEG, acessando instâncias PostgreSQL internas.
  2. Nível 2 (Container): Divide-se entre servidor web, parser de logs (pgBadger) e base PostgreSQL para armazenamento de relatórios.
  3. Nível 3 (Componentes): Inclui módulos de autenticação, parsing, visualização e agendamento.
  4. Nível 4 (Código): Implementações em Typescript, scripts Bash e Python.

- **Mockups das Telas Principais**: As telas principais incluem:
  - Dashboard inicial (Overview): visão geral das instâncias e métricas de desempenho.

  - Calendário de relatórios: seleção de data e navegação entre períodos.

  - Aba “Top Queries”: exibe consultas mais custosas.


- **Decisões e Alternativas Consideradas**: Justifique escolhas de design, documentando alternativas avaliadas.

- **Critérios de Escalabilidade, Resiliência e Segurança**: Descreva como a solução será projetada para suportar crescimento, lidar com falhas e manter segurança.

### 3.3. Stack Tecnológica
- **Linguagens de Programação**: Liste e justifique as escolhas.
- **Frameworks e Bibliotecas**: Detalhe e justifique a seleção.
- **Ferramentas de Desenvolvimento e Gestão**: Inclua IDEs, sistemas de versionamento, plataformas de integração contínua, monitoramento, entre outros.
- **Licenciamento**: Indique as licenças dos softwares e bibliotecas utilizados ([MIT](https://opensource.org/licenses/MIT), [GPL](https://www.gnu.org/licenses/gpl-3.0.html), [Apache](https://www.apache.org/licenses/), [Creative Commons](https://creativecommons.org/licenses/)).

### 3.4. Considerações de Segurança
- **Riscos Identificados**: Liste ameaças potenciais (ex.: injeção de código, vazamento de dados, falhas de autenticação).
- **Medidas de Mitigação**: Explique as ações planejadas para minimizar riscos (ex.: criptografia, controle de acesso, validação de entrada).
- **Normas e Boas Práticas Seguidas**: Cite padrões como [OWASP Top 10](https://owasp.org/www-project-top-ten/), [ISO/IEC 27001](https://www.iso.org/isoiec-27001-information-security.html), [LGPD](https://www.planalto.gov.br/ccivil_03/_ato2015-2018/2018/lei/L13709.htm) ou outros aplicáveis.
- **Responsabilidade Ética**: Para projetos de IA ou manipulação de dados sensíveis, descreva como serão tratados vieses, privacidade e uso responsável ([UNESCO – Ética em IA](https://unesdoc.unesco.org/ark:/48223/pf0000380455), [OECD AI Principles](https://oecd.ai/en/ai-principles)).

### 3.5. Conformidade e Normas Aplicáveis
- Relacione todas as legislações, regulamentações e normas técnicas aplicáveis ao projeto, descrevendo brevemente como serão atendidas.
- Exemplos:
  - [LGPD – Lei Geral de Proteção de Dados](https://www.planalto.gov.br/ccivil_03/_ato2015-2018/2018/lei/L13709.htm)
    - Coletar apenas dados necessários (nome, contato, dados do imóvel).
    - Evitar dados sensíveis desnecessários.
    - Solicitar consentimento explícito e exibir política de privacidade clara.
    - Permitir acesso, correção e exclusão de dados pelo usuário.
    -   ...
   
## 4. Próximos Passos
 - Descrição dos passos seguintes após a conclusão do documento, com uma visão geral do cronograma para Portfólio I e II.
 - Definição de Marcos: Estabelecer datas para entregas intermediárias e checkpoints.

## 5. Referências
Listagem de todas as fontes de pesquisa, frameworks, bibliotecas e ferramentas que serão utilizadas.

## 7. Avaliações de Professores
Adicionar três páginas no final do RFC para que os Professores escolhidos possam fazer suas considerações e assinatura:

- Considerações Professor/a:

- Considerações Professor/a:

- Considerações Professor/a:
