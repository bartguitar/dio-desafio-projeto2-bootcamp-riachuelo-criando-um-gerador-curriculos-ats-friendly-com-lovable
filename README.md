# JobMatch ATS 🎯

> Descubra o quanto seu currículo combina com uma vaga — e gere, na hora, uma versão ATS friendly para aumentar suas chances no processo seletivo.

**Desafio de Projeto 2** do Bootcamp **Riachuelo — Criando Produtos com IA** (DIO), construído 100% por meio de **prompts** dentro do [Lovable](https://lovable.dev).

🔗 **App publicado:** [matchoughost.lovable.app](https://matchoughost.lovable.app/)

---

## 📌 Sobre o projeto

O **JobMatch ATS** é uma ferramenta gratuita e sem cadastro que compara o currículo do usuário com a descrição de uma vaga, calcula um **score de match**, aponta **palavras-chave presentes e ausentes** e gera automaticamente uma **versão do currículo otimizada para sistemas ATS** (Applicant Tracking Systems).

O diferencial deste projeto está no **processo de criação**: o app inteiro — front-end, design system, funcionalidades e conteúdo — foi construído por meio de **engenharia de prompt**, sem escrever código manualmente linha a linha.

> ⚠️ **Uso ético:** a ferramenta ajuda a organizar, destacar e adaptar experiências **reais** do candidato para cada vaga. Ela **não inventa** competências, cargos ou resultados que a pessoa não possui.

## 🧠 Metodologia: do prompt ao produto

O desenvolvimento seguiu um fluxo de **Vibe Coding** em duas etapas, combinando um LLM de propósito geral para desenhar a arquitetura da solução e o Lovable para executá-la:

### 1. Ideação e prompt-mestre no ChatGPT
A concepção do app começou em uma conversa com o **ChatGPT**, descrevendo o produto desejado, as tecnologias e a identidade visual. O prompt inicial foi:

```
eu quero criar um app do zero no lovable e 100% lá para fazer matchmaking de vagas de
emprego e criar versões do currículo do usuário que sejam ATS friendly pra essa vaga.

quero que você use ShadCN como design system

quero nas cores, azul claro, branco e amarelo claro.

me mande o prompt ÚNICO em formato MarkDown.
```

A partir desse briefing, o ChatGPT estruturou um **prompt único, em Markdown**, consolidando escopo, stack, design system e paleta de cores em um documento pronto para ser colado diretamente no Lovable — evitando ambiguidade e retrabalho na primeira geração do app.

### 2. Construção e iteração no Lovable
O prompt-mestre foi colado no Lovable, que gerou a base do projeto (estrutura React + roteamento + componentes ShadCN). A partir daí, o produto evoluiu por **prompts sucessivos em linguagem natural**, no próprio chat do Lovable, entre eles:

| Prompt enviado | Resultado gerado |
|---|---|
| *"quero adicionar uma funcionalidade de exportação do currículo em formato pdf"* | Botão de exportação em PDF ATS friendly (texto real selecionável, fonte serifada, sem imagens/colunas) |
| *"exporta pra mim o design system da aplicação em pdf"* | Documento **"JobMatch ATS — Design System"** com tokens de cor (tema claro/escuro), tipografia, raios e boas práticas de uso |
| *"quero personalizar uma logo pro JobMatch, mais formal"* | Refação da logo com monograma "JM" e tipografia mais elegante |
| *"muda a fonte desse bloco selecionado pra gothic"* | Ajuste tipográfico via **Visual Edit**, migrado depois para **Jost** (alternativa open-source próxima à Century Gothic) |
| Revisão de CTA e SEO | Textos de botão e metadados da página ajustados para publicação (ex.: "Ver como funciona" → "Teste agora") |

Esse ciclo demonstra o uso combinado de:
- **Chat prompts**, para features e mudanças estruturais (ex.: exportação em PDF)
- **Visual Edits**, para ajustes finos de texto, cor e fonte sem consumir créditos de geração
- **Geração de documentação viva**, com o próprio design system exportado em PDF a partir de um prompt

### 3. Publicação
Com o app validado no preview do Lovable, o projeto foi publicado (**Publish**) e sincronizado com este repositório no GitHub.

## ✨ Funcionalidades

- **Análise de match** entre currículo e vaga, com score percentual geral (ex.: 78% — "Bom match")
- **Palavras-chave encontradas** e **palavras-chave ausentes** na vaga, extraídas automaticamente
- **Versão ATS friendly** do currículo, organizada em abas (ATS friendly / Palavras-chave / Por vaga), pronta para copiar ou baixar
- **Exportação em PDF** com texto real selecionável, fonte serifada e layout sem imagens/colunas — compatível com leitores de ATS
- **Histórico de análises**, salvo localmente no navegador, com filtros por cargo, empresa e resultado do match
- **Dashboard, Perfil e Configurações** para gerenciar as análises realizadas
- Fluxo **sem cadastro**: todos os dados ficam salvos apenas no navegador do usuário

## 🧭 Como funciona (jornada do usuário)

1. **Cole a vaga** e adicione seu currículo
2. A ferramenta **compara e analisa** palavras-chave e requisitos
3. Você recebe o **resultado do match** e uma **versão ATS friendly** para baixar

## 🎨 Design system

Gerado e documentado a partir de prompts, exportado como PDF diretamente do Lovable:

- Componentes baseados em **ShadCN/ui**
- Paleta principal: azul claro, branco e amarelo claro, com tokens semânticos de cor (`primary`, `success`, `warning`, `destructive`) para estados como "bom match" e "lacunas"
- Tipografia: **Space Grotesk** (títulos/display), **Inter** (corpo de texto) e **Jost** (botões secundários)
- Suporte a **tema claro e escuro**, com tokens sobrescritos via classe `.dark` mantendo a mesma semântica entre os dois temas
- Boas práticas documentadas: sempre usar tokens semânticos (`bg-primary`, `text-foreground`, `border-border`), nunca hardcodar cores (`text-white`, `bg-black`, hex fixo), raios via `rounded-md/lg/xl`

## 🛠️ Tecnologias

- **React** + **Vite** + **TypeScript**
- **TanStack Router** (roteamento)
- **ShadCN/ui** + **Tailwind CSS**
- **Bun** como runtime/gerenciador de pacotes
- Geração de PDF client-side
- Persistência local no navegador (sem backend/banco de dados)
- Construído, iterado e publicado via **Lovable**, a partir de prompts estruturados no **ChatGPT**

## 🚀 Rodando localmente

```bash
git clone https://github.com/bartguitar/dio-desafio-projeto2-bootcamp-riachuelo-criando-um-gerador-curriculos-ats-friendly-com-lovable.git
cd dio-desafio-projeto2-bootcamp-riachuelo-criando-um-gerador-curriculos-ats-friendly-com-lovable
bun install
bun run dev
```

Alternativamente, edite o projeto diretamente pelo [Lovable](https://lovable.dev), que sincroniza as alterações com este repositório.

## 🎓 Contexto do desafio

Este projeto foi desenvolvido como entrega do **Desafio de Projeto 2** do Bootcamp **Riachuelo — Criando Produtos com IA**, promovido pela **DIO** em parceria com a **Riachuelo**, com foco em transformar ideias em produtos reais usando **IA generativa**, **engenharia de prompt** e ferramentas *no-code/vibe coding* como o Lovable — indo do prompt inicial no ChatGPT até um produto publicado, sem escrever código manualmente.

## 👤 Autor

Desenvolvido por [Adriel](https://github.com/bartguitar) como parte do portfólio de projetos práticos da trilha DIO/Santander/Riachuelo.
