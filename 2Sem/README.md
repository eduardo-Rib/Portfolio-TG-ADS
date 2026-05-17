# IDScan - 2º Semestre

<p align="center">
  <strong>API 2</strong> • <strong>2º Semestre</strong> • <strong>2024-2</strong> • 
  <a href="https://fatecsjc-prd.azurewebsites.net/">
    FATEC São José dos Campos - Prof. Jessen Vidal
  </a>
</p>

<p align="center">
  <img 
    src="./images/logo-idscan.png" 
    alt="Logo do Projeto IDScan" 
    width="300"
  >
</p>

<p align="center">
  <a href="https://github.com/Titus-System/2semestre-ADS">
    Repositório do Projeto
  </a>
</p>

<p align="center">
  <strong>Papel exercido no projeto:</strong> Desenvolvedor
</p>

---

## Parceiro acadêmico

| Item | Descrição |
|---|---|
| Parceiro acadêmico | [FATEC São José dos Campos - Prof. Jessen Vidal](https://fatecsjc-prd.azurewebsites.net/) |
| Contexto | Projeto acadêmico desenvolvido no 2º semestre do curso de Análise e Desenvolvimento de Sistemas |
| Equipe | Titus Systems |
| Produto | IDScan |

---

## Sumário

- [Identificação do projeto](#identificação-do-projeto)
- [Parceiro acadêmico](#parceiro-acadêmico)
- [Problema proposto](#problema-proposto)
- [Solução desenvolvida](#solução-desenvolvida)
- [Tecnologias utilizadas](#tecnologias-utilizadas)
- [Minhas contribuições](#minhas-contribuições)
- [Hard skills](#hard-skills)
- [Soft skills](#soft-skills)
- [Navegação do portfólio](#navegação-do-portfólio)

---

## Problema proposto

Documentos físicos de identidade, como o RG, possuem informações importantes que frequentemente precisam ser digitalizadas, organizadas e armazenadas.
Fazer a leitura e o cadastro manual desses dados é um processo demorado, repetitivo e sujeito a erros de digitação ou interpretação.
Depender de APIs externas para extrair essas informações poderia gerar custos, exigir conexão com a internet e criar riscos de privacidade no envio de documentos pessoais.
Por isso, havia a necessidade de processar a imagem localmente, identificar os dados relevantes e organizá-los em um banco relacional.

---

## Solução desenvolvida

A equipe desenvolveu o IDScan, uma aplicação desktop em Java voltada ao processamento de imagens de RG.
O sistema permite importar e processar a imagem do documento para extrair o texto por meio do Tesseract OCR.
Após a extração, a aplicação utiliza apoio de IA local com Ollama para identificar os dados relevantes dentro do texto obtido.
As informações localizadas são organizadas para armazenamento em um banco MySQL local.
O sistema também permite a consulta e edição dos dados persistidos, mantendo o processamento sem dependência de APIs externas.

---

## Tecnologias utilizadas

| Tecnologia | Aplicação no projeto |
|---|---|
| Java | Linguagem utilizada para desenvolvimento da aplicação desktop |
| MySQL | Banco de dados relacional utilizado para armazenamento local das informações |
| Ollama | Execução local de modelos de linguagem e apoio à interpretação dos dados extraídos |
| Tesseract OCR | Reconhecimento óptico de caracteres para leitura do texto presente nos documentos |
| Git e GitHub | Versionamento do código e organização do repositório |
| Jira | Gerenciamento das tarefas e acompanhamento das sprints |
| VS Code | Ambiente utilizado como apoio ao desenvolvimento |
| Figma | Criação e visualização prévia do design das telas |

---

## Minhas contribuições

Neste projeto, atuei como Desenvolvedor, contribuindo principalmente com pesquisas, testes de modelos de inteligência artificial e construção de consultas para o banco de dados MySQL.
Na primeira sprint, testei modelos visuais de IA executados com Ollama, incluindo `MiniCPM-V` e `LLaVA`, para avaliar a precisão na extração de informações de documentos.
Durante esses testes, aprendi sobre integração com Ollama e construção de prompts voltados à extração de dados.
A equipe decidiu usar Tesseract OCR para extrair o texto bruto e um modelo de linguagem para localizar os dados nesse texto, por ser uma abordagem mais rápida e precisa em hardwares mais fracos.
Na segunda e terceira sprint, contribuí com queries SQL para MySQL, apoiando o armazenamento, a consulta e a manipulação dos dados extraídos.
Também participei das decisões técnicas sobre a abordagem de extração e persistência da aplicação.

### Testes com modelos de inteligência artificial

Durante a primeira sprint, fiquei responsável por testar modelos de inteligência artificial visuais que pudessem auxiliar na extração de informações a partir das imagens dos documentos. Entre os modelos avaliados estavam o `MiniCPM-V` e o `LLaVA`, ambos executados localmente com o apoio do Ollama.

Essa etapa foi importante para entender as limitações e possibilidades do uso de modelos visuais no projeto. Durante os testes, adquiri maior conhecimento sobre integração com o Ollama, execução local de modelos de IA e construção de prompts voltados à extração de informações estruturadas.

Ao longo da sprint, a equipe identificou que utilizar apenas modelos visuais poderia gerar respostas menos previsíveis e exigir mais desempenho da máquina. Por isso, o grupo decidiu adotar uma abordagem híbrida, utilizando o Tesseract OCR para extrair o texto bruto da imagem e um modelo de linguagem para localizar, interpretar e estruturar os dados necessários dentro desse texto.

Essa decisão tornou o processo mais rápido, mais preciso e mais viável para execução em hardwares mais simples, mantendo a proposta de realizar todas as operações localmente.

### Contribuições no banco de dados

Na segunda e terceira sprint, minha participação foi mais direcionada à criação de queries SQL para o banco de dados MySQL. Contribuí na construção de comandos voltados ao armazenamento, consulta e manipulação dos dados extraídos dos documentos.

Essa atuação ajudou na organização das informações dentro do banco relacional, permitindo que os dados processados pela aplicação fossem persistidos e posteriormente consultados ou editados pelo usuário.

### Contribuições gerais no desenvolvimento

Além das atividades específicas com IA e banco de dados, também acompanhei o desenvolvimento da aplicação desktop, colaborando com decisões técnicas da equipe e com a adaptação da solução conforme os testes realizados durante as sprints.

O projeto foi importante para ampliar meu contato com aplicações Java Desktop, integração com ferramentas locais de inteligência artificial, OCR e persistência de dados em banco relacional.

---

## Hard skills

| Hard skill | Nível de proficiência | Evidência no projeto |
|---|---|---|
| Java | Faço/uso com ajuda | Participação no desenvolvimento da aplicação desktop |
| MySQL | Faço/uso com autonomia | Criação de queries para armazenamento, consulta e manipulação dos dados |
| SQL | Faço/uso com autonomia | Apoio na organização e persistência das informações extraídas dos documentos |
| Ollama | Faço/uso com ajuda | Testes e execução local de modelos de inteligência artificial |
| Prompt Engineering | Faço/uso com ajuda | Criação de prompts para orientar modelos na extração de informações estruturadas |
| Modelos de IA visuais | Faço/uso com ajuda | Testes com modelos como MiniCPM-V e LLaVA durante a primeira sprint |
| Tesseract OCR | Faço/uso com ajuda | Compreensão do fluxo de extração de texto bruto a partir das imagens dos documentos |
| Git e GitHub | Faço/uso com autonomia | Versionamento do código e colaboração no repositório |
| Jira | Faço/uso com autonomia | Acompanhamento de tarefas e organização do desenvolvimento por sprint |
| Figma | Faço/uso com ajuda | Consulta e apoio na visualização do design planejado para as telas |

---

## Soft skills

| Soft skill | Situação em que foi exercitada |
|---|---|
| Investigação técnica | Comparei modelos visuais como MiniCPM-V e LLaVA para avaliar a precisão na extração de informações de documentos |
| Pensamento crítico | Participei da análise que levou à troca do modelo visual puro por uma abordagem com Tesseract OCR e modelo de linguagem |
| Colaboração | Trabalhei com a equipe nas decisões técnicas sobre extração local, persistência dos dados e viabilidade da solução |
| Adaptabilidade | Adaptei-me ao desenvolvimento desktop com Java e MySQL e à mudança de estratégia para OCR + IA local |
| Organização | Criei queries SQL para apoiar o armazenamento, a consulta e a manipulação dos dados extraídos no MySQL |
| Aprendizado contínuo | Aprendi sobre Ollama, construção de prompts, OCR e integração dessas ferramentas em uma aplicação desktop |

---

<div align="center">

## Navegação do portfólio

| 🏠 Página inicial | ⬅️ Projeto anterior | ➡️ Próximo projeto |
|---|---|---|
| [README](../README.md) | [API 1](../1Sem/README.md) | [API 3](../3Sem/README.md) |

</div>
