# 🎓 Parecer do Orientador: Guia Geral de Validação do TCC

**Avaliador:** Prof. Dr. Virtual (Especialista em Ciência da Computação e Visão Computacional)
**Objetivo deste documento:** Servir como um *checklist* implacável de autoavaliação para garantir o rigor científico, a coerência estrutural e a excelência acadêmica em todas as fases da sua monografia.

---

## 1. O Fio Condutor (Coerência Global)
*Um bom TCC conta uma história lógica do início ao fim. Nada deve aparecer "do nada" e nenhuma promessa deve ser esquecida.*

- [ ] **Alinhamento Introdução-Conclusão:** O objetivo geral prometido na Introdução (Ex: Comparar arquiteturas X e Y sob o aspecto de precisão e tempo) foi inequivocamente respondido na Conclusão?
- [ ] **Justificativa Sustentada:** O problema de pesquisa apresentado na Introdução justifica o esforço computacional gasto na Metodologia?
- [ ] **Progressão Lógica:** O leitor consegue entender exatamente *por que* você escolheu essa metodologia após ler a sua Fundamentação Teórica? A teoria preparou o terreno?
- [ ] **Antecipação dos Modelos:** Cada modelo comparado (YOLOv5, YOLOv8, YOLO11, SSD, Faster R-CNN) foi apresentado e contextualizado na Fundamentação antes de aparecer na Metodologia?
- [ ] **Desfecho das Promessas:** Toda métrica apresentada no Capítulo 2 (mAP@0.5, mAP@0.5:0.95, F1-Score, tempo de inferência) é de fato reportada nos Resultados?

## 2. Rigor Científico e Metodológico
*Em Ciência da Computação, a reprodutibilidade é a regra de ouro. Se outro pesquisador ler seu texto, ele consegue refazer seu experimento?*

- [ ] **A Regra dos "Por quês":** Para cada escolha feita (arquitetura, *dataset*, *framework*, métrica, hiperparâmetro, variante do modelo), existe uma justificativa técnica ou citação bibliográfica que a embase? (Nunca diga apenas "escolhi X"; diga "optou-se por X devido à sua vantagem em Y [AUTOR, Ano]").
- [ ] **Parâmetros declarados:** Os valores exatos dos hiperparâmetros utilizados (número de épocas, *batch size*, *patience*, *confidence threshold*, limiar de IoU do NMS) estão registrados na Metodologia?
- [ ] **Versões declaradas:** As versões exatas do *software* utilizado (Python, TensorFlow, Ultralytics, CUDA) estão declaradas?
- [ ] **Divisão do Dataset:** As proporções treino/validação/teste estão explicitadas? A estratégia de divisão (aleatória, estratificada) está descrita?
- [ ] **Limitações Declaradas:** Você foi transparente sobre as limitações do seu hardware, da qualidade do *dataset* ou das escolhas de *software*? (A ciência verdadeira não esconde os problemas, ela os documenta).
- [ ] **Reprodutibilidade:** *Seeds* aleatórias e o ambiente de execução (Google Colab, GPU T4, etc.) estão claros para permitir replicação?
- [ ] **Tabela de Parâmetros dos Modelos:** Uma tabela com o número aproximado de parâmetros de cada variante usada (ex: YOLOv5s ~7M, YOLOv8s ~11M) foi incluída para justificar quantitativamente a comparação justa?

## 3. Análise Crítica (Não seja um "Leitor de Tabelas")
*A banca sabe ler tabelas e gráficos. O seu papel não é narrar os números, mas sim interpretar os fenômenos computacionais por trás deles.*

- [ ] **Correlação de Fatores:** Você está cruzando informações? (Ex: em vez de dizer "O modelo A teve mAP de 80% e tempo de 10ms", diga "Apesar de o modelo A atingir o maior mAP, seu tempo de inferência inviabiliza o uso em tempo real, evidenciando o *trade-off*...").
- [ ] **Investigação de Anomalias:** Se um resultado fugiu do esperado pela literatura (ex: um modelo grande perdendo para um pequeno, um sobreajuste prematuro), você criou um parágrafo formulando uma hipótese técnica para explicar isso?
- [ ] **Análise Qualitativa vs. Quantitativa:** Você confrontou as métricas frias com inspeções visuais (*bounding boxes* erradas, oclusões, problemas de iluminação)?
- [ ] **Comparação com a Literatura:** Seus resultados de mAP são compatíveis com os benchmarks publicados pelos autores originais? Se divergirem, você explica o motivo (dataset diferente, menor número de épocas, etc.)?

## 4. Escrita Acadêmica e Estilo (O "Padrão TCC")
*A linguagem deve ser formal, impessoal, direta e inequívoca.*

- [ ] **Impessoalidade (3ª Pessoa):** 
  - ❌ *Incorreto:* "Nós usamos o modelo", "No meu trabalho", "Eu observei".
  - ✅ *Correto:* "Utilizou-se o modelo", "Neste trabalho", "Observou-se".
- [ ] **Gestão do Tempo Verbal:**
  - **Fundamentação Teórica:** Presente (A teoria *é* uma verdade atual).
  - **Trabalhos Relacionados:** Passado (O autor X *desenvolveu*).
  - **Metodologia:** Passado (O ambiente *foi configurado*, o modelo *foi treinado*).
  - **Resultados:** Passado (O modelo *obteve* X% de mAP).
  - **Conclusão:** Passado e Presente (O estudo *concluiu* que o modelo A *é* o melhor).
- [ ] **Estrangeirismos:** Todos os jargões em inglês obrigatórios na computação (*framework, dataset, batch size, overfitting, ground truth, early stopping, backbone, trade-off, pipeline*) estão rigorosamente em **itálico**?
- [ ] **Concisão:** Elimine pleonasmos e floreios. (Ex: "Há anos atrás", "Conclusão final", "Resultados obtidos" — se é resultado, obviamente foi obtido).
- [ ] **Termos técnicos consistentes:** "caixa delimitadora" vs. "*bounding box*", "*ground truth*" vs. "gabarito" — escolha um padrão e mantenha-o em todo o texto.

## 5. Referencial Teórico e Citações (Blindagem Anti-Plágio)
*Cada afirmação técnica forte que não é fruto direto do seu experimento precisa de um "padrinho" bibliográfico.*

- [ ] **Cruzamento Texto-Referências:** Todos os autores citados no corpo do texto estão na lista final (e vice-versa)?
- [ ] **Relevância Semântica das Citações:** A referência citada realmente embasa o que está sendo afirmado? (Ex: citar um paper que você não usa no estudo — como EfficientDet — para justificar um *trade-off* é questionável. Prefira citar o paper do modelo que você de fato usa ou um survey da área).
- [ ] **Paráfrase vs. Citação Direta:** Evite ao máximo copiar e colar trechos de autores entre aspas (citação direta). Na área de Exatas/Computação, prefere-se a ideia do autor reescrita com as suas próprias palavras (paráfrase), com a devida citação ao final.
- [ ] **Formatação ABNT Controlada:**
  - Segundo Autor (Ano), a rede neural... (Citação indireta na narrativa).
  - A rede neural aprende feições (AUTOR, Ano). (Citação indireta no final da frase).
- [ ] **URLs e @misc:** Entradas `@misc` com URLs possuem data de acesso *exata* (dia, mês e ano), não apenas o ano?
- [ ] **Subseções sem citação:** Nenhuma subseção com afirmação técnica ficou sem ao menos uma referência bibliográfica?

## 6. Formatação LaTeX e ABNT
*Detalhes técnicos de formatação impactam diretamente a nota final.*

- [ ] **Figuras referenciadas:** Toda figura possui `\label{}` e é mencionada no texto com `\autoref{}` antes de aparecer?
- [ ] **Fonte das figuras:** Toda figura possui `\source{}` (ex: "Autoria própria (2025)" ou "Adaptado de AUTOR (Ano)")?
- [ ] **Equações numeradas:** Todas as equações relevantes estão em ambiente `equation` com numeração automática?
- [ ] **Siglas introduzidas:** Toda sigla é escrita por extenso na primeira ocorrência seguida da sigla entre parênteses (ex: "Rede Neural Convolucional (CNN)")? Após isso, usa-se apenas a sigla?
- [ ] **Seções sem texto introdutório:** Nenhuma `\section` ou `\subsection` começa diretamente com uma `\subsubsection` sem um parágrafo de introdução?

---

## 7. Preparação para a Banca (Arguição Antecipada)
*Se você não sabe a resposta para as perguntas abaixo, revise seu texto.*

1. *Qual é a real contribuição do seu trabalho em relação ao estado da arte ou trabalhos correlatos listados no Capítulo 3?*
2. *Se você tivesse acesso a um cluster de GPUs infinito, a sua conclusão mudaria? Por quê?*
3. *Como você garante que os modelos comparados não memorizaram o dataset (overfitting)? As métricas de validação comprovam isso no seu texto?*
4. *Por que você usou a variante Small do YOLO e não a Nano ou a Medium? Qual evidência quantitativa sustenta que essa escolha garante uma comparação justa com o SSD e o Faster R-CNN?*
5. *O dataset utilizado é representativo do problema real? Quais são suas limitações de distribuição de classes?*
6. *Por que o tempo de inferência de 33 ms (30 FPS) foi adotado como limiar de referência para "tempo real"? Esse critério se aplica ao seu contexto de aplicação específico?*

---

## 🔴 Regras Críticas de Manutenção do `.bib` (Lições Aprendidas)
*Erros aqui quebram a compilação silenciosamente — as citações somem do PDF sem aviso claro.*

### Nunca renomeie uma chave `.bib` sem verificar todos os arquivos `.tex`

**O problema:** Renomear uma chave no `Referencias.bib` (ex: `su2025comparative` para `su2025`) quebra todos os `\cite{su2025comparative}` espalhados pelos demais capítulos. O LaTeX reporta apenas `undefined citation`, sem indicar qual arquivo causou o problema.

**A regra correta:**

1. Antes de qualquer renome, execute uma busca global pela chave antiga em **todos os `.tex`**:
   `grep -r "chave_antiga" textual/`
2. Se a chave **não for encontrada em nenhum `.tex`** → pode renomear com segurança.
3. Se a chave **for encontrada** → **não renomeie o `.bib`**. Atualize os `\cite{}` nos arquivos `.tex` para usar a chave que já existe.

> **Princípio:** A fonte da verdade é o `.bib`. Os `.tex` se adaptam a ele — nunca o contrário quando a chave já está em uso.