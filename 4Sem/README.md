# Nexa - 4º Semestre

<p align="center">
  <strong>2º semestre de 2025</strong> • 
  <a href="https://www.tecsysbrasil.com.br/">
    TecSys Brasil
  </a>
</p>

<p align="center">
  <img 
    src="./images/logo-nexa.png" 
    alt="Logo do Projeto Nexa" 
    width="300"
  >
</p>

<p align="center">
  <a href="https://github.com/Titus-System/Nexa">
    Repositório do Projeto
  </a>
</p>

<p align="center">
  <strong>Papel exercido no projeto:</strong> Desenvolvedor Backend
</p>

---

## Sumário

- [Problema proposto](#problema-proposto)
- [Solução desenvolvida](#solução-desenvolvida)
- [Tecnologias utilizadas](#tecnologias-utilizadas)
- [Minhas contribuições](#minhas-contribuições)
- [Hard skills](#hard-skills)
- [Soft skills](#soft-skills)
- [Navegação do portfólio](#navegação-do-portfólio)

---

## Problema proposto

A elaboração da instrução de registro aduaneiro é um processo manual que exige atenção a informações como Part Number, classificação fiscal, fabricante, origem e endereço do fabricante. Quando esses dados são tratados manualmente, podem ocorrer erros de interpretação, descrições ambíguas, retrabalho e riscos de questionamentos, penalidades ou multas.

O desafio proposto pela empresa parceira foi criar uma solução capaz de automatizar esse processo de forma inteligente, gerando descrições claras, precisas e compatíveis com exigências legais. A ferramenta precisava apoiar a equipe responsável, reduzir o esforço manual e aumentar a segurança das informações geradas para submissão à Receita Federal.

---

## Solução desenvolvida

A solução desenvolvida foi o Nexa, uma aplicação baseada em arquitetura orientada a eventos, com foco em automação, integração com inteligência artificial e comunicação em tempo real. O projeto foi dividido em três componentes principais: `Nexa-frontend`, `Nexa-api` e `Nexa-AI-Agents`.

A aplicação permite o envio de documentos, a extração de Part Numbers, o processamento das informações com agentes de IA e a geração de descrições técnicas para apoiar a elaboração da instrução de registro aduaneiro. A comunicação entre os serviços ocorre por meio de APIs REST, WebSockets e Redis, garantindo maior desacoplamento entre os componentes.

<p align="center">
  <img 
    src="./images/arquitetura-nexa.svg" 
    alt="Logo do Projeto Nexa" 
  >
</p>

### Nexa API

O `Nexa-api` é o orquestrador central da aplicação. Desenvolvido em Python com Flask, ele atua como API Gateway, gerenciando as requisições do frontend, a lógica de negócio principal, a persistência dos dados e a comunicação assíncrona com os demais serviços.

Entre suas responsabilidades estão:

- Exposição de endpoints REST para upload de documentos e classificação de Part Numbers;
- Orquestração assíncrona de tarefas com Celery e Redis;
- Comunicação em tempo real com o frontend utilizando WebSocket;
- Persistência dos resultados em PostgreSQL;
- Validação de dados e controle de autenticação e autorização.

### Nexa AI Agents

O `Nexa-AI-Agents` é o serviço responsável pelas tarefas de inteligência artificial. Ele executa os agentes que buscam informações técnicas, geram descrições humanizadas e apoiam a classificação dos produtos.

Entre suas responsabilidades estão:

- Execução de modelos de linguagem locais;
- Geração de descrições técnicas dos produtos;
- Apoio à classificação de NCMs;
- Uso de RAG com ChromaDB para recuperação de informações contextuais;
- Publicação de atualizações de progresso via Redis Pub/Sub.

<p align="center">
  <img 
    src="./images/diagrama-agents.png" 
    alt="Logo do Projeto Nexa" 
  >
</p>

### Nexa Frontend

O `Nexa-frontend` é a interface web da aplicação. Desenvolvido com React e TypeScript, ele permite que o usuário envie documentos, insira Part Numbers manualmente, acompanhe o progresso das tarefas em tempo real e visualize os resultados gerados pelo sistema.

Entre suas responsabilidades estão:

- Upload de documentos;
- Entrada manual de Part Numbers;
- Exibição dos resultados de classificação;
- Comunicação com a API via HTTP REST;
- Atualização em tempo real por WebSocket.

---

## Tecnologias utilizadas

| Tecnologia | Aplicação no projeto |
|---|---|
| Python | Linguagem utilizada no backend e nos agentes de IA |
| Flask | Framework utilizado na construção da API e dos serviços |
| Pytest | Criação e execução de testes automatizados |
| PostgreSQL | Banco de dados relacional utilizado para persistência dos dados |
| SQLAlchemy | ORM utilizado para comunicação com o banco de dados |
| Redis | Broker de mensagens e apoio à comunicação assíncrona |
| Celery | Execução de tarefas assíncronas |
| Socket.IO | Comunicação em tempo real entre backend e frontend |
| Smolagents | Construção e organização dos agentes de IA |
| Ollama | Execução local de modelos de linguagem |
| ChromaDB | Banco vetorial utilizado para RAG |
| Node.js | Ambiente utilizado no frontend |
| TypeScript | Linguagem utilizada no desenvolvimento do frontend |
| React | Construção da interface web |
| Vite | Ferramenta de build e execução do frontend |
| HTML | Estruturação das páginas da aplicação |
| Tailwind CSS | Estilização da interface |
| Docker | Conteinerização dos serviços da aplicação |
| Git e GitHub | Versionamento e colaboração no código |
| Figma | Apoio na prototipação das interfaces |
| Jira | Organização das tarefas e acompanhamento das sprints |
| Scrum | Organização do trabalho em equipe durante o desenvolvimento |

---

## Minhas contribuições

Neste projeto, atuei como integrante do time de desenvolvimento, com foco principal no backend e nos serviços relacionados à inteligência artificial. Minha participação envolveu o desenvolvimento de agentes, criação de rotas, extração de dados em documentos e pesquisa de alternativas para obtenção de informações técnicas de produtos.

### Desenvolvimento do agente de descrição

Na primeira sprint, fiquei responsável pelo desenvolvimento do `description_writer_agent`, agente responsável por gerar uma descrição humanizada do produto a partir das informações técnicas disponíveis.

Essa funcionalidade tinha como objetivo transformar dados técnicos em uma descrição mais clara e adequada ao contexto da instrução de registro aduaneiro. A implementação exigiu atenção à forma como as informações eram organizadas e repassadas ao modelo, buscando gerar respostas coerentes, úteis e compatíveis com a proposta do sistema.

Essa etapa contribuiu para meu aprendizado sobre agentes de IA, estruturação de prompts, integração com modelos locais e organização de respostas geradas automaticamente.

### Extração de Part Numbers em PDFs

Na segunda sprint, fiquei responsável por desenvolver a lógica de extração dos Part Numbers a partir de pedidos de compra em PDF. Para isso, desenvolvi uma rota de upload de arquivos PDF e implementei a lógica de identificação dos códigos utilizando expressões regulares.

Essa funcionalidade foi importante para automatizar a primeira etapa do fluxo da aplicação, evitando que o usuário precisasse digitar manualmente todos os Part Numbers presentes no documento. A extração por REGEX também ajudou a tornar o processo mais objetivo e rápido, principalmente em documentos com padrões identificáveis.

### Pesquisa de dados técnicos de produtos

Na terceira sprint, fiquei responsável por pesquisar e testar alternativas para consulta de dados técnicos de produtos a partir dos Part Numbers. Inicialmente, tentei desenvolver soluções de web scraping em sites especializados, como Mouser, Findchips e Digikey.

Durante essa etapa, encontrei dificuldades relacionadas às verificações de segurança e bloqueios desses sites, o que limitou a viabilidade do scraping. Também testei alternativas por meio de APIs, como a API da LCSC/JLCPCB e a API da Mouser.

Apesar de conseguir acesso ao plano estudantil da API da Mouser, os dados retornados eram majoritariamente comerciais, não técnicos, o que não atendia completamente às necessidades do projeto. Além disso, algumas soluções pagas não eram viáveis para o contexto acadêmico, pois o limite gratuito seria consumido rapidamente.

Essa investigação foi importante porque os agentes de IA locais estavam apresentando alto tempo de resposta na busca de dados técnicos pela web, chegando a demorar muito tempo para retornar informações de um único Part Number e, em alguns casos, não retornando dados úteis. A pesquisa por alternativas ajudou a equipe a avaliar os limites técnicos e práticos das abordagens disponíveis.

### Contribuições gerais no desenvolvimento

Além das entregas específicas de cada sprint, participei de discussões técnicas sobre a arquitetura do sistema, integração entre serviços e alternativas para melhorar o desempenho do fluxo com inteligência artificial.

O projeto foi importante para aprofundar meus conhecimentos em backend, processamento assíncrono, integração com IA, extração de dados em documentos, comunicação entre serviços e arquitetura desacoplada.

---

## Hard skills

| Hard skill | Nível de proficiência | Evidência no projeto |
|---|---|---|
| Python | Sei fazer com autonomia | Desenvolvimento de funcionalidades backend e agentes de IA |
| Flask | Sei fazer com autonomia | Criação de rotas e serviços da aplicação |
| APIs REST | Sei fazer com autonomia | Desenvolvimento de endpoints para upload de PDF e processamento de dados |
| REGEX | Sei fazer com autonomia | Extração de Part Numbers a partir de documentos PDF |
| Ollama | Sei fazer com apoio | Integração com modelos de linguagem executados localmente |
| Agentes de IA | Sei fazer com apoio | Desenvolvimento do `description_writer_agent` |
| Prompt Engineering | Sei fazer com apoio | Estruturação de instruções para geração de descrições humanizadas |
| Redis | Sei fazer com apoio | Compreensão da comunicação assíncrona entre serviços |
| Celery | Sei fazer com apoio | Contato com processamento assíncrono de tarefas |
| PostgreSQL | Sei fazer com apoio | Compreensão da persistência dos resultados da aplicação |
| SQLAlchemy | Sei fazer com apoio | Contato com ORM para manipulação dos dados |
| Socket.IO | Sei fazer com apoio | Compreensão do fluxo de atualização em tempo real |
| Web Scraping | Sei fazer com apoio | Testes de extração de dados em sites de consulta de Part Numbers |
| Integração com APIs externas | Sei fazer com apoio | Testes com APIs como Mouser e LCSC/JLCPCB |
| Docker | Sei fazer com apoio | Execução da aplicação em ambiente conteinerizado |
| Git e GitHub | Sei fazer com autonomia | Versionamento e colaboração no repositório |
| Jira | Sei fazer com autonomia | Acompanhamento de tarefas e entregas durante as sprints |
| Scrum | Sei fazer com autonomia | Participação no desenvolvimento incremental do projeto |

---

## Soft skills

| Soft skill | Situação em que foi exercitada |
|---|---|
| Investigação técnica | Pesquisei alternativas para obtenção de dados técnicos por scraping e APIs externas |
| Resolução de problemas | Busquei soluções para reduzir o tempo de resposta dos agentes de IA locais |
| Persistência | Mesmo com bloqueios em sites e limitações de APIs, continuei testando abordagens alternativas para o problema |
| Pensamento crítico | Avaliei a viabilidade técnica e econômica das soluções encontradas, considerando limites gratuitos e qualidade dos dados retornados |
| Colaboração | Trabalhei em conjunto com a equipe para integrar minhas entregas ao fluxo geral da aplicação |
| Adaptabilidade | Precisei ajustar as abordagens conforme as limitações técnicas surgiram durante as sprints |
| Aprendizado contínuo | Aprofundei conhecimentos em IA local, agentes, scraping, APIs externas e arquitetura orientada a eventos |
| Comunicação técnica | Compartilhei com a equipe os resultados dos testes, limitações encontradas e alternativas analisadas |

---

<div align="center">

## Navegação do portfólio

| 🏠 Página inicial | ⬅️ Projeto anterior | ➡️ Próximo projeto |
|---|---|---|
| [README](../README.md) | [API 3](../3Sem/README.md) | [API 5](../5Sem/README.md) |

</div>