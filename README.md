# Capa
- **Título do Projeto**: PGReports.
- **Nome do Estudante**: Nathan Cielusinski.
- **Curso**: Engenharia de Software.
- **Data de Entrega**: [Data].

# Resumo
Breve descrição do conteúdo do documento, incluindo o propósito do projeto e os principais pontos de discussão.

## 1. Introdução (FEITO)
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
* **Normas e Legislações Aplicáveis**: Liste normas, leis e diretrizes relevantes ao contexto do projeto (ex.: LGPD, HIPAA, WCAG, ESRB/PEGI), indicando como serão observadas. <-- FAZER ESSE AQUI -->
>Fazer Normas e Legislação - Ainda pendente.
* **Métricas de Sucesso**: Pontos que apresentam o sucesso da implementação dessa aplicação na empresa podem ser, principalmente, a redução de tempo nas avaliações de problemas, identificação de gargalos que ainda não causaram problemas, identificação para melhorias em queries e diretamente nas aplicações. 

## 3. Especificação Técnica
Descrição detalhada da proposta, contemplando requisitos, arquitetura, tecnologias, segurança e aderência aos critérios obrigatórios da linha de projeto escolhida.

### 3.1. Requisitos de Software
- **Requisitos Funcionais (RF)**: Liste de forma clara as funcionalidades que o sistema deverá oferecer.
- **Requisitos Não-Funcionais (RNF)**: Inclua requisitos de desempenho, segurança, usabilidade, escalabilidade, disponibilidade, entre outros.
- **Representação dos Requisitos**: Inclua um Diagrama de Casos de Uso (UML) ou outra representação visual que facilite o entendimento.
- **Aderência aos Requisitos da Linha de Projeto**: Indique como cada requisito está alinhado aos itens “Obrigatório Atender” definidos para a linha de projeto (Web, Mobile, Jogos, IA ou IoT).

### 3.2. Considerações de Design
- **Visão Inicial da Arquitetura**: Apresente os principais componentes e suas interações.
- **Padrões de Arquitetura**: Informe padrões adotados (ex.: [MVC](https://en.wikipedia.org/wiki/Model–view–controller), [Microserviços](https://microservices.io/), [MVVM](https://en.wikipedia.org/wiki/Model–view–viewmodel), Arquitetura em Camadas).
- **Modelos C4**: Utilize os quatro níveis ([C4 Model](https://c4model.com/)) quando aplicável.
- **Mockups das Telas Principais**: Apresente protótipos visuais das telas mais relevantes, mostrando navegação, disposição de elementos e principais interações do usuário. Esses mockups podem ser feitos em ferramentas como Figma, Adobe XD ou similares, e devem refletir a identidade visual e usabilidade prevista para o produto.
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

## 6. Apêndices (Opcionais)
Informações complementares, dados de suporte ou discussões detalhadas fora do corpo principal.

## 7. Avaliações de Professores
Adicionar três páginas no final do RFC para que os Professores escolhidos possam fazer suas considerações e assinatura:

- Considerações Professor/a:

- Considerações Professor/a:

- Considerações Professor/a:
