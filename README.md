# TCC - Trabalho de Conclusão de Curso (LaTeX)

<div align="center">
  <img src="media/logo.png" alt="Logo do TCC" width="800">
</div>

Este repositório contém os arquivos do meu TCC desenvolvidos em LaTeX, utilizando o ambiente local no Visual Studio Code com a extensão **LaTeX Workshop**.

## 📋 Índice

- [🛠 Ambiente de Desenvolvimento](#-ambiente-de-desenvolvimento)
  - [1. Atualize o sistema](#1-atualize-o-sistema)
  - [2. Instale os pacotes LaTeX essenciais](#2-instale-os-pacotes-latex-essenciais)
  - [3. Extensões recomendadas no VS Code](#3-extensões-recomendadas-no-vs-code)
- [▶️ Como Compilar](#️-como-compilar)
  - [🔧 Compilação Manual com Bibliografia](#-compilação-manual-com-bibliografia)
  - [🔍 Por que 4 etapas?](#-por-que-4-etapas)
- [🧹 Limpeza de Arquivos Auxiliares](#-limpeza-de-arquivos-auxiliares)
- [🔧 Troubleshooting](#-troubleshooting)
  - [Erros de Registros de Compilações Anteriores](#erros-de-registros-de-compilações-anteriores)
- [📄 Arquivo de Saída](#-arquivo-de-saída)
  - [✅ Verificação da Compilação](#-verificação-da-compilação)
  - [🔍 Localização dos Arquivos](#-localização-dos-arquivos)

## 🛠 Ambiente de Desenvolvimento

O projeto foi configurado e compilado localmente no Linux com o **Visual Studio Code**. Para garantir o funcionamento adequado, siga os passos abaixo para instalar os pacotes necessários:

### 1. Atualize o sistema:

```bash
sudo apt update
```

### 2. Instale os pacotes LaTeX essenciais:

```bash
sudo apt install latexmk texlive-full
```

> ⚠️ A instalação do `texlive-full` pode ocupar bastante espaço em disco (mais de 2GB), pois inclui todos os pacotes LaTeX disponíveis.

### 3. Extensões recomendadas no VS Code:

- [LaTeX Workshop](https://marketplace.visualstudio.com/items?itemName=James-Yu.latex-workshop)
- [LaTeX Utilities](https://marketplace.visualstudio.com/items?itemName=tecosaur.latex-utilities)

Essas extensões permitem:

- Compilação automática (`latexmk`)
- Visualização em PDF integrada
- Destaque de sintaxe e snippets
- Navegação entre seções, figuras, referências, etc.

## ▶️ Como Compilar

### 🔧 Compilação Manual com Bibliografia

Para controle total do processo:

```bash
pdflatex Principal.tex && bibtex Principal && pdflatex Principal.tex && pdflatex Principal.tex
```

#### 🔍 Por que 4 etapas?

| Etapa | Comando    | Função                                                |
| ----- | ---------- | ----------------------------------------------------- |
| 1️⃣    | `pdflatex` | Gera arquivos auxiliares (.aux) e identifica citações |
| 2️⃣    | `bibtex`   | Processa a bibliografia do arquivo `Referencias.bib`  |
| 3️⃣    | `pdflatex` | Incorpora a bibliografia e resolve citações           |
| 4️⃣    | `pdflatex` | Finaliza referências cruzadas e numeração de páginas  |

## 🧹 Limpeza de Arquivos Auxiliares

Para remover os arquivos temporários gerados durante a compilação, use:

```bash
rm -f Principal.{aux,bbl,blg,brf,idx,lof,log,toc}
```

Este comando remove os seguintes arquivos auxiliares:
- `.aux` - Informações auxiliares
- `.bbl` - Bibliografia processada
- `.blg` - Log do bibtex
- `.brf` - Arquivo de brief
- `.idx` - Índice
- `.lof` - Lista de figuras
- `.log` - Log de compilação
- `.toc` - Sumário

## 🔧 Troubleshooting

### Erros de Registros de Compilações Anteriores

Erros do tipo "manter registros de compilações anteriores" (que acontece muito com o `configuracao.tex`) podem ser corrigidos no VS Code usando:

1. **Ctrl+Shift+P** (ou **Cmd+Shift+P** no macOS)
2. Digite: `Developer: Reload Window`
3. Pressione **Enter**

Isso recarrega a janela do VS Code e limpa o cache interno da extensão LaTeX Workshop, resolvendo conflitos com compilações anteriores.

## 📄 Arquivo de Saída

Após a compilação bem-sucedida, o arquivo final **`Principal.pdf`** será gerado na raiz do projeto (mesma pasta do `Principal.tex`).

### ✅ Verificação da Compilação

Para confirmar que a compilação foi realizada corretamente:

- **Arquivo gerado**: `Principal.pdf` na pasta raiz
- **Tamanho**: Deve ter um tamanho apropriado (não 0 bytes)
- **Conteúdo**: Abra o PDF para verificar se todas as seções, figuras, tabelas e referências estão presentes
- **Bibliografia**: Confirme se as citações e referências bibliográficas aparecem corretamente

### 🔍 Localização dos Arquivos

```
TCC_LaTeX/
├── Principal.tex      # Arquivo principal (fonte)
├── Principal.pdf      # Arquivo compilado (saída)
├── Referencias.bib    # Bibliografia
└── ...outros arquivos
```
