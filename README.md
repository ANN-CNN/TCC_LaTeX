# TCC - Trabalho de Conclusão de Curso (LaTeX)

Este repositório contém os arquivos do meu TCC desenvolvidos em LaTeX, utilizando o ambiente local no Visual Studio Code com a extensão **LaTeX Workshop**.

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

## 📄 Saída

O arquivo final compilado é um PDF localizado na mesma pasta do `Principal.tex`.
