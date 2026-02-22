# 🦎 Catálogo Taxonômico da Fauna do Brasil

[![Site ao vivo](https://img.shields.io/badge/Site-faunadobrasilctfb.online-00e5a0?style=flat-square&logo=netlify)](https://faunadobrasilctfb.online)
[![Hospedagem](https://img.shields.io/badge/Hospedagem-Netlify-00AD9F?style=flat-square&logo=netlify)](https://netlify.com)
[![Licença](https://img.shields.io/badge/Licença-CC%20BY%204.0-lightgrey?style=flat-square)](https://creativecommons.org/licenses/by/4.0/)
[![Espécies](https://img.shields.io/badge/Espécies%20válidas-125.138-00e5a0?style=flat-square)](https://fauna.jbrj.gov.br/fauna)
[![Especialistas](https://img.shields.io/badge/Especialistas-800%2B-00e5a0?style=flat-square)](https://faunadobrasilctfb.online)

> Site institucional do Catálogo Taxonômico da Fauna do Brasil (CTFB), o inventário mais completo da megadiversidade animal brasileira. Hospedado via Netlify com deploy automático a partir deste repositório.

**🌐 URL pública:** https://faunadobrasilctfb.online  
**🔬 Sistema de busca:** https://fauna.jbrj.gov.br/fauna  
**📦 Dados (IPT/DwC-A):** https://ipt.jbrj.gov.br/jbrj/resource?r=catalogo_taxonomico_da_fauna_do_brasil  
**📧 Contato:** faunadobrasilctfb@gmail.com

---

## 📋 Conteúdo

- [Estrutura do site](#-estrutura-do-site)
- [Como editar uma página](#-como-editar-uma-página)
- [Tarefas de manutenção comuns](#-tarefas-de-manutenção-comuns)
- [Elementos HTML reutilizáveis](#-elementos-html-reutilizáveis)
- [Fluxo de publicação](#-fluxo-de-publicação)
- [Sobre o projeto](#-sobre-o-projeto)

---

## 📁 Estrutura do site

Cada página é um arquivo `.html` **autocontido** — CSS e JavaScript estão embutidos diretamente, sem dependências externas além das fontes do Google Fonts.

```
ctfb-site/
│
├── index.html               → Página inicial · O Catálogo
│
├── — SOBRE —
├── como-citar.html          → Como citar o Catálogo
├── normas.html              → Normas do CTFB
├── fontes-de-dados.html     → Fontes de dados
│
├── — DADOS —
├── download.html            → Download de grupos específicos
├── scripts-r.html           → Scripts do R · Pacote faunabr
├── links-externos.html      → Links externos
├── arquivos.html            → Arquivos e documentos oficiais
│
├── — PUBLICAÇÕES —
├── publicacoes.html         → Artigos publicados sobre o CTFB
├── citacoes.html            → Citações do CTFB na literatura
│
├── — NOTÍCIAS —
├── noticias.html            → Notícias recentes
├── boletim.html             → Boletim Informativo CTFB
├── noticias-arquivadas.html → Histórico de notícias
│
├── — COMUNIDADE —
├── reunioes.html            → Reuniões do CTFB
├── reunioes-online.html     → Reuniões online
├── oficinas.html            → Oficinas de capacitação
├── congresso-zoo.html       → 34° Congresso Brasileiro de Zoologia
├── bzg2023.html             → Brazilian Zoology Group 2023
├── palestras.html           → Palestras em eventos científicos
├── material-divulgacao.html → Material de divulgação
│
├── — CURADORIA —
├── tutoriais.html           → Tutoriais para curadores
├── demandas.html            → Demandas / Controle do sistema
│
├── netlify.toml             → Configuração de deploy (não editar)
└── README.md                → Este arquivo
```

---

## ✏️ Como editar uma página

### Opção A — Direto no GitHub (recomendada · sem instalar nada)

Ideal para pequenas correções de texto, adição de notícias, novos artigos, etc.

1. Acesse o repositório em **github.com/[seu-usuario]/ctfb-site**
2. Clique no arquivo que deseja editar (ex: `noticias.html`)
3. Clique no ícone de lápis **✏️** no canto superior direito do arquivo
4. Faça a edição diretamente no navegador
5. No final da página, em **"Commit changes"**, descreva o que foi alterado
   (ex: *"Adiciona notícia sobre aprovação do financiamento MMA"*)
6. Clique em **"Commit changes"** — o site atualiza em **~30 segundos** automaticamente

### Opção B — Localmente com VS Code (para mudanças maiores)

Ideal para redesign de páginas, adição de novas seções, alterações em múltiplos arquivos.

1. Instale o [VS Code](https://code.visualstudio.com/) — gratuito
2. Clone o repositório:
   ```bash
   git clone https://github.com/[seu-usuario]/ctfb-site.git
   cd ctfb-site
   ```
3. Abra a pasta no VS Code: `File → Open Folder`
4. Edite os arquivos `.html`
5. Use `Ctrl+Shift+H` para busca e substituição global em todos os arquivos
6. Envie as mudanças:
   ```bash
   git add .
   git commit -m "Descrição clara da mudança"
   git push
   ```
7. Netlify publica automaticamente em ~30 segundos

---

## 🔧 Tarefas de manutenção comuns

### Atualizar número de espécies válidas

Nos arquivos `index.html` e `o-catalogo.html`, localize e substitua:
```html
<span class="stat-num">125.138</span>
```

Em **todas as páginas** (sidebar), localize e substitua:
```html
<span class="vv">125.138</span>
```
> 💡 Use `Ctrl+Shift+H` no VS Code para substituição em todos os arquivos de uma vez.

---

### Adicionar nova notícia

Abra `noticias.html`, localize a seção de notícias e **adicione no início** (para aparecer primeiro):

```html
<div style="border:1px solid var(--border);padding:1.5rem;background:var(--canopy)">
  <div style="font-family:'JetBrains Mono',monospace;font-size:0.58rem;
       letter-spacing:0.15em;color:var(--teal);text-transform:uppercase;
       margin-bottom:0.5rem">2025 · Categoria da notícia</div>
  <h3>Título da notícia</h3>
  <p>Texto explicativo da notícia aqui.</p>
</div>
```

---

### Adicionar novo artigo em Publicações

Abra `publicacoes.html`, localize a `<tbody>` da tabela e adicione uma nova linha:

```html
<tr>
  <td>7</td>
  <td>
    <strong>Sobrenome A, Sobrenome B</strong> (2025) Título completo do artigo.
    <em>Nome da Revista</em> 42: e12345.
  </td>
  <td>
    <a href="https://doi.org/10.xxxx/xxxxx" target="_blank">10.xxxx/xxxxx</a>
  </td>
</tr>
```

---

### Atualizar versão do catálogo

Em **todas as páginas**, na sidebar, localize e substitua:
```
BZG2024-2034  →  nova versão
```
> 💡 Use `Ctrl+Shift+H` no VS Code para fazer isso em todos os arquivos de uma vez.

---

### Adicionar novo link externo

Abra `links-externos.html` e duplique um bloco `card` existente:

```html
<a class="card" href="https://nova-url.com" target="_blank">
  <div class="card-tag">Categoria</div>
  <div class="card-title">Nome do recurso</div>
  <div class="card-desc">Descrição breve do que é este recurso.</div>
  <div class="card-url">nova-url.com</div>
</a>
```

---

## 🧩 Elementos HTML reutilizáveis

Cole estes blocos onde necessário em qualquer página.

**Parágrafo:**
```html
<p>Texto aqui.</p>
```

**Título com destaque em verde:**
```html
<h2>Texto normal com <em>destaque verde</em></h2>
```

**Citação em destaque (pull quote):**
```html
<div class="pull-quote">
  <p>Texto de destaque em itálico aqui.</p>
</div>
```

**Caixa de referência bibliográfica:**
```html
<div class="citation-box">
  <div class="citation-label">Referência</div>
  <div class="citation-text">
    Autor, A. (2024). <em>Título do trabalho</em>. Revista, volume.
    <a href="https://doi.org/..." target="_blank">https://doi.org/...</a>
  </div>
  <button class="copy-btn" onclick="copyText('texto a copiar', this)">Copiar</button>
</div>
```

**Card clicável (link):**
```html
<a class="card" href="https://url.com" target="_blank">
  <div class="card-tag">Tipo</div>
  <div class="card-title">Título</div>
  <div class="card-desc">Descrição.</div>
  <div class="card-url">url.com</div>
</a>
```

**Grade de 2 cards lado a lado:**
```html
<div class="card-grid cols-2">
  <a class="card" href="#">...</a>
  <a class="card" href="#">...</a>
</div>
```

**Bloco de licença CC BY:**
```html
<div class="license-block">
  <span class="license-icon">CC BY 4.0</span>
  <p class="license-text">Descrição dos termos de uso aqui.</p>
</div>
```

---

## 🚀 Fluxo de publicação

```
Você edita arquivo no GitHub
        ↓
GitHub notifica o Netlify  (~instantâneo)
        ↓
Netlify faz o build e deploy  (~10–30 segundos)
        ↓
faunadobrasilctfb.online atualizado ✓
```

Todo commit fica registrado no histórico com **data, autor e descrição** — rastreabilidade completa, ideal para um projeto científico colaborativo com 800+ especialistas.

---

## 🔬 Sobre o projeto

O **Catálogo Taxonômico da Fauna do Brasil (CTFB)** é o inventário taxonômico mais completo da megadiversidade animal brasileira, desenvolvido desde abril de 2015 por mais de 800 zoólogos especialistas. O projeto é financiado pelo Ministério do Meio Ambiente (MMA) e pelo Ministério da Ciência, Tecnologia e Inovação (MCTi).

| | |
|---|---|
| **Versão atual** | BZG2024-2034 |
| **Espécies válidas** | 125.138 |
| **Espécies nominais** | 133.691 |
| **Especialistas** | 800+ |
| **Licença** | CC BY 4.0 |
| **Formato de dados** | Darwin Core Archive (DwC-A) |
| **Início do projeto** | Abril de 2015 |
| **Instituição** | JBRJ — Instituto de Pesquisas Jardim Botânico do Rio de Janeiro |

### Citação recomendada

```
Brazilian Zoology Group (2024). Catálogo Taxonômico da Fauna do Brasil.
Available at http://fauna.jbrj.gov.br/fauna
```

---

*Repositório mantido pelo Grupo Gestor do CTFB · JBRJ / MMA / MCTi*  
*Licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)*
