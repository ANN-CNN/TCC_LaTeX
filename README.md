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

### 🚀 Compilação Automática (Recomendado)

Abra a pasta do projeto no VS Code e pressione `Ctrl+Alt+B` para compilar com `latexmk` (atalho padrão da extensão LaTeX Workshop).

**Ou via terminal:**
```bash
latexmk -pdf Principal.tex
```

### 🔧 Compilação Manual com Bibliografia

Para casos específicos onde seja necessário controle total do processo:

```bash
pdflatex Principal.tex && bibtex Principal && pdflatex Principal.tex && pdflatex Principal.tex
```

#### 🔍 Por que 4 etapas?

| Etapa | Comando | Função |
|-------|---------|--------|
| 1️⃣ | `pdflatex` | Gera arquivos auxiliares (.aux) e identifica citações |
| 2️⃣ | `bibtex` | Processa a bibliografia do arquivo `Referencias.bib` |
| 3️⃣ | `pdflatex` | Incorpora a bibliografia e resolve citações |
| 4️⃣ | `pdflatex` | Finaliza referências cruzadas e numeração de páginas |

## 📄 Saída

O arquivo final compilado é um PDF localizado na mesma pasta do `Principal.tex`.
