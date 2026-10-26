# Analise-de-Dados

### **Módulo 1: SQL (Structured Query Language) — Gerenciamento e Extração de Dados**

1. **Fundamentos e Configuração do Ambiente**
   - Criação e povoamento de bancos de dados via scripts SQL (`CREATE DATABASE`, `CREATE TABLE`, `INSERT INTO`).
   - Execução de consultas e navegação no editor de queries.

2. **Consultas Básicas (`SELECT` e Filtragem Inicial)**
   - Sintaxe do `SELECT`, seleção de colunas específicas e uso do caractere coringa `*`.
   - Filtragem de dados com a cláusula `WHERE` e operadores de comparação (`=`, `!=`, `>`, `<`, `>=`, `<=`).
   - Operadores lógicos (`AND`, `OR`, `NOT`) e precedência aritmética (`PEMDAS`).
   - Busca por padrões de texto com o operador `LIKE` e caracteres coringas (`%` e `_`).
   - Controle de exibição com `LIMIT`, deslocamento por vírgula e ordenação com `ORDER BY` (`ASC` / `DESC`).
   - Eliminação de duplicatas (`DISTINCT`) e renomeação de colunas (`Aliasing` com `AS`).

3. **Agregação e Agrupamento de Dados**
   - Funções de agregação de linha: `SUM()`, `AVG()`, `COUNT()`, `MIN()`, `MAX()`.
   - Agrupamento de dados com `GROUP BY` e suas regras de colunas não agregadas.
   - Filtragem pós-agrupamento: Diferença essencial entre `WHERE` (filtra linhas antes do agrupamento) e `HAVING` (filtra agregações após o agrupamento).

4. **Junções e Combinação de Tabelas**
   - Conceito de chaves relacionais e ambiguidade de colunas.
   - **`INNER JOIN`**: Retorno exclusivo de correspondências exatas em ambas as tabelas.
   - **`LEFT JOIN` e `RIGHT JOIN`**: Preservação de registros da tabela à esquerda ou à direita com inclusão de `NULL` onde não há correspondência.
   - **`SELF JOIN`**: Junção de uma tabela consigo mesma (ex.: atribuição de pares ou hierarquias).
   - Junção de múltiplas tabelas em uma única consulta através de tabelas de referência.
   - **`UNION` vs. `UNION ALL`**: Empilhamento vertical de linhas mantendo consistência de colunas (remoção automática de duplicatas vs. exibição de todas as linhas).

5. **Lógica de Condição e Manipulação de Strings**
   - Estruturas condicionais na consulta com `CASE STATEMENTS` (`WHEN ... THEN ... ELSE ... END`).
   - Funções de texto: `LENGTH()`, `UPPER()`, `LOWER()`, `TRIM()`, `LEFT()`, `RIGHT()`, `SUBSTRING()`, `REPLACE()` e `LOCATE()`.

6. **Consultas Avançadas e Modularização**
   - **Subqueries**: Subconsultas inseridas nas cláusulas `WHERE` (filtragem dinâmica), `SELECT` e `FROM` (tabelas derivadas).
   - **Tabelas Temporárias (`Temp Tables`)**: Criação de tabelas em memória na sessão para manipulação intermediária.
   - **`CTEs` (Common Table Expressions)**: Bloco de subconsulta nomeado com a cláusula `WITH` para aumentar a legibilidade e reutilização.
   - **`Window Functions`**: Uso do operador `OVER()` e `PARTITION BY` para calcular agregações sem aglutinar as linhas individuais.
   - Totais acumulados (`Rolling Totals`) combinando `SUM() OVER(ORDER BY ...)`.
   - Funções de numeração e ranking: `ROW_NUMBER()`, `RANK()` e `DENSE_RANK()`.

7. **Automação no Banco de Dados**
   - **`Stored Procedures`**: Criação de procedimentos reutilizáveis, alteração de delimitadores (`DELIMITER //`), bloco `BEGIN ... END` e passagem de parâmetros de entrada.
   - **`Triggers` e `Events`**: Gatilhos automáticos disparados por eventos de tabela (`AFTER INSERT`, `NEW.coluna`) e agendamento de tarefas temporais.

8. **Projetos Práticos Integrados de SQL**
   - **Projeto 1: Limpeza de Dados (`Data Cleaning`)**: Remoção de duplicatas com `ROW_NUMBER()`, padronização de textos e países, conversão do tipo texto para `DATE`, tratamento de valores nulos/em branco com `JOIN` de atualização e descarte de dados irrelevantes.
   - **Projeto 2: Análise Exploratória de Dados (`EDA`)**: Investigação de estatísticas descritivas, tendências temporais por substring de ano/mês, totais acumulados e ranking das maiores ocorrências por ano utilizando CTEs encadeadas.

> **Análise do Aprendizado Incremental em SQL:**
> O aprendizado do SQL começa com o simples ato de **extrair e filtrar** registros (`SELECT`, `WHERE`). Quando o volume aumenta, surge a necessidade de **resumir dados** (`GROUP BY`, `HAVING`). Em seguida, compreende-se que bancos de dados reais são relacionalmente divididos, exigindo a habilidade de **conectar tabelas** (`JOINS`). À medida que as perguntas de negócio se tornam mais complexas, aprende-se a **modularizar a lógica** (`Subqueries`, `Temp Tables`, `CTEs`) e realizar análises avançadas linha a linha sem perder detalhes (`Window Functions`), culminando na **automação e projetos reais** de limpeza e exploração.

---

### **Módulo 2: Excel — Manipulação, Tratamento e Análise Dinâmica**

#### **Tópicos e Subtópicos:**
1. **Limpeza e Padronização de Dados**
   - Identificação visual e estrutural de inconsistências em conjuntos de dados.
   - Remoção automatizada de linhas duplicadas (`Remove Duplicates`).
   - Padronização de caixas de texto (`UPPER`, `PROPER`, `LOWER`) e remoção de espaços sobressalentes (`TRIM`).
   - Ajuste e padronização do formato de datas e conversão de fórmulas em valores fixos (`Paste as Value`).

2. **Fórmulas e Funções Essenciais**
   - Funções de estatística básica: `MAX`, `MIN`, `SUM`, `COUNT`.
   - Lógica condicional: `IF` simples, `IFS` (múltiplas condições) e instruções de decisão.
   - Agregações condicionais: `SUMIF`, `SUMIFS`, `COUNTIF`, `COUNTIFS`.
   - Manipulação de texto: `LEN` (comprimento), `LEFT`, `RIGHT`, `CONCATENATE` e `SUBSTITUTE`.
   - Cálculo de dias úteis e datas (`NETWORKDAYS`).

3. **Pesquisa e Associação de Dados (`XLOOKUP`)**
   - Evolução histórica: Por que o `XLOOKUP` substitui o `VLOOKUP` de forma mais segura e sem quebrar ao inserir colunas.
   - Sintaxe fundamental: Valor procurado (`lookup_value`), Matriz de procura (`lookup_array`) e Matriz de retorno (`return_array`).
   - Recursos avançados: Retorno de múltiplas colunas simultâneas, tratamento de erros integrado (`if_not_found`), busca com caracteres coringas (`wildcard match` `*`) e alteração da ordem de busca (do topo ao fim ou do fim ao topo).
   - Combinação de `XLOOKUP` com funções matemáticas como `SUM`.

4. **Análise Visual e Tabelas Dinâmicas (`Pivot Tables`)**
   - Formatação condicional: Regras de realce (valores maiores/menores, texto contido, duplicatas), barras de dados, escalas de cor e ícones de tendência.
   - Criação de Tabelas Dinâmicas: Configuração de Linhas, Colunas, Valores e Filtros.
   - Agrupamentos, expansão/recolhimento de campos e criação de Campos Calculados (`Calculated Fields`).
   - Gráficos no Excel: Colunas agrupadas, empilhadas, linhas e barras.

5. **Projeto Guiado Completo em Excel**
   - Criação de planilha de trabalho a partir dos dados brutos.
   - Limpeza e substituição de códigos textuais por rótulos claros com `Ctrl + H`.
   - Agrupamento customizado por faixas etárias através de fórmulas `IF` aninhadas.
   - Construção de múltiplas Tabelas Dinâmicas e Gráficos Dinâmicos alinhados às perguntas de negócio.
   - Montagem de um Dashboard interativo: Remoção de linhas de grade, criação de cabeçalhos e inclusão de Segmentadores de Dados (`Slicers`) conectados a todas as tabelas dinâmicas.

> **Análise do Aprendizado Incremental no Excel:**
> O aluno inicia garantindo a **integridade da planilha** através da limpeza e padronização. Com os dados limpos, aprende a **extrair métricas e aplicar lógicas** com fórmulas condicionais e relacionais (`IF`, `XLOOKUP`). Em seguida, avança para a **sumarização dinâmica** com Tabelas Dinâmicas, culminando no **desenvolvimento visual e interativo** de dashboards executivos.

---

### **Módulo 3: Business Intelligence (BI) — Power BI e Tableau**

#### **Submódulo A: Microsoft Power BI**
1. **Conexão e Preparação de Dados no Power Query**
   - Instalação e interface do Power BI Desktop.
   - Importação de dados (Excel, CSV, tabelas dinâmicas) e navegação no Power Query Editor.
   - Operações de ETL: Promoção de cabeçalhos, remoção de linhas/colunas nulas ou desnecessárias, alteração de tipos de dados.
   - Transposição e Despivotamento de colunas (`Unpivot Columns`) para transformar datas em estrutura tabular de linhas.
   - Rastreamento e auditoria de alterações no painel de Etapas Aplicadas (`Applied Steps`).

2. **Modelagem de Dados e Relacionamentos**
   - Interface do Modelo (`Model View`) e detecção automática de conexões.
   - Conceito e configuração de Cardinalidade: Muitos para Um (`*:1`), Um para Muitos (`1:*`), Um para Um (`1:1`) e Muitos para Muitos (`*:*`).
   - Direção do filtro cruzado (`Cross filter direction`): Única vs. Ambas.

3. **Cálculos Analíticos com DAX (Data Analysis Expressions)**
   - Diferença fundamental entre **Colunas Calculadas** (calculadas linha a linha na carga) e **Medidas** (calculadas dinamicamente no contexto de visualização).
   - Funções de agregação e iteração: `SUM()`, `COUNT()`, `AVERAGE()` vs. `SUMX()`.
   - Funções de data e tempo (`WEEKDAY`, `DAY`, `YTD`) e lógica condicional (`IF`) em DAX.

4. **Visualizações e Interatividade Avançada**
   - Gráficos de barras agrupadas/empilhadas, colunas 100% empilhadas, linhas e dispersão (`Scatter Plot`).
   - Agrupamentos por lista e faixas numéricas (`Bins` e `Lists`).
   - Perfuração de dados em níveis hierárquicos (`Drill Down` e `Drill Up`).
   - Formatação condicional em matrizes e tabelas (escalas de cor, ícones e barras de dados).
   - Projeto Guiado de Power BI: Construção completa do ETL à publicação do dashboard.

#### **Submódulo B: Tableau**
1. **Fundamentos e Conexão**
   - Instalação do Tableau Public e navegação na interface.
   - Conceito de **Dimensões** (dados categóricos/qualitativos) vs. **Medidas** (dados numéricos/quantitativos).
   - Definição de Joins tradicionais vs. Relacionamentos do Tableau.

2. **Visualizações e Cálculos no Tableau**
   - Gráficos de colunas, linhas combinadas, mapa de densidade e *Box and Whisker Plots*.
   - Agrupamento em intervalos (`Bins`) e Cálculos Rápidos de Tabela (`Percent of Total`).
   - Campos Calculados simples para apuração de métricas e diferenças.
   - Aplicação de filtros interativos no painel.
   - Projeto Guiado de Tableau: Integração de dados de hospedagem/vendas e montagem de painel executivo.

> **Análise do Aprendizado Incremental em Business Intelligence:**
> A jornada em BI começa no **ETL/Tratamento de dados** (Power Query / Conexões), pois dados brutos não geram visuais corretos. Em seguida, aprende-se a **conectar esquemas de tabelas** (Modelagem e Relacionamentos). Com a estrutura pronta, insere-se a **camada de inteligência de negócios** através de fórmulas calculadas (DAX / Campos Calculados). Por fim, desenvolve-se a **camada de apresentação e interatividade** (`Drill Down`, `Slicers`, Dashboards).

---

### **Módulo 4: Python para Análise de Dados — Automação e Programação**

#### **Tópicos e Subtópicos:**
1. **Ambiente de Desenvolvedor e Execução**
   - Instalação da distribuição **Anaconda** e inicialização do **Jupyter Notebook**.
   - Estrutura de Notebooks: Células de Código vs. Células de Formatação Texto (`Markdown`).
   - Atalhos de execução (`Shift + Enter`), gerenciamento do Kernel (reinício e interrupção) e organização de blocos.

2. **Variáveis e Convenções**
   - Conceito de variáveis como contêineres de memória e atribuição dinâmica de tipos.
   - Sobrescrita de variáveis e sensibilidade a maiúsculas/minúsculas (`Case Sensitivity`).
   - Atribuição múltipla em uma única linha.
   - Boas práticas e estilos de nomenclatura: *Camel Case*, *Pascal Case* e **`Snake Case`** (padrão recomendado em Python).
   - Regras e restrições de nomes de variáveis (caracteres proibidos e números no início).

3. **Tipos de Dados Nativo e Conversão (`Type Casting`)**
   - **Tipos Numéricos**: Inteiros (`int`), Decimais (`float`) e Números Complexos (`complex`).
   - **Booleanos (`bool`)**: Valores lógicos `True` e `False`.
   - **Texto (`str`)**: Aspas simples, duplas e triplas (multilinhas), indexação (``), fatiamento (*slicing*) (`[2:5]`), indexação negativa e concatenação/multiplicação.
   - **Coleções**:
     - *Listas (`list`)*: Ordenadas, mutáveis, aceitam múltiplos tipos de dados, indexação aninhada e método `.append()`.
     - *Tuplas (`tuple`)*: Ordenadas e **imutáveis** (utilizadas para dados fixos).
     - *Conjuntos (`set`)*: Desordenados, não indexados e contêm apenas **valores únicos**; operações de conjuntos (União `|`, Intersecção `&`, Diferença `-`).
     - *Dicionários (`dict`)*: Estrutura de pares **Chave-Valor** (`Key-Value`), métodos `.keys()`, `.values()`, `.items()`, atualização (`.update()`) e deleção (`del`).
   - **Conversão de Tipos (`Casting`)**: Modificação explícita de tipos com `int()`, `float()`, `str()`, `list()`, `tuple()`, `set()` e conversão de chaves/valores de dicionários em listas.

4. **Operadores**
   - Operadores de Comparação: Igualdade (`==`), Diferença (`!=`), Maior/Menor (`>`, `<`, `>=`, `<=`).
   - Operadores Lógicos: `and` (ambos verdadeiros), `or` (pelo menos um verdadeiro) e `not` (inversão lógica).
   - Operadores de Membro: `in` e `not in` (verificação de presença em sequências ou coleções).

5. **Estruturas de Controle de Fluxo e Laços de Repetição**
   - **Condicionais**: Estrutura `if`, `elif` e `else`, indentação obrigatória e condicionais aninhadas.
   - Sintaxe condicional simplificada em linha única.
   - **Laços `for`**: Iteração sobre sequências (listas, dicionários com `.items()`), variáveis temporárias e laços aninhados.
   - **Laços `while`**: Repetição baseada em condição lógica, controle de contadores e laço `while-else`.
   - Comandos de controle de laço: `break` (interrupção imediata) e `continue` (pula para a próxima iteração).

6. **Funções e Modularização de Código**
   - Definição de funções com a palavra-chave `def`, passagem de argumentos e retorno.
   - Múltiplos parâmetros e personalização de cálculos.
   - **Argumentos Arbitrários (`*args`)**: Passagem de quantidade variável de argumentos em formato de tupla.
   - **Argumentos Nomeados (`Keyword Arguments`)**: Passagem explícita pelo nome do argumento.
   - **Argumentos Nomeados Arbitrários (`**kwargs`)**: Passagem flexível em formato de dicionário.

7. **Extensões do Aprendizado em Python (Sequência para Análise)**
   - Introdução à biblioteca **Pandas** para manipulação de dataframes, *Regular Expressions* (Regex), *Web Scraping* e visualização com Matplotlib/Seaborn.

> **Análise do Aprendizado Incremental em Python:**
> A programação exige o entendimento prévio da **sintaxe básica e variáveis**. Compreendidos os contêineres, aprende-se a diferença entre **tipos de dados simples e estruturas de dados complexas** (`str`, `list`, `dict`), assim como a transição entre eles (`Casting`). A partir daí, insere-se a **lógica de tomada de decisão** (`if/else`) e a **automação de repetições** (`for/while`). O encadeamento final se dá através da **modularização em funções**, preparando o analista para utilizar bibliotecas avançadas de análise de dados (como Pandas).

---

### **Módulo 5: Projetos de Portfólio, Currículo e Estratégia de Carreira**

#### **Tópicos e Subtópicos:**
1. **Construção de Portfólio de Projetos**
   - Importância de demonstrar habilidades técnicas aplicadas a cenários reais em vez de apenas exibir certificados.
   - Composição ideal do portfólio: 3 a 5 projetos completos cobrindo SQL, Excel, BI e Python.
   - Criação e hospedagem de um **Site de Portfólio Gratuito** (utilizando GitHub Pages).

2. **Otimização de Currículo para Análise de Dados**
   - Estruturação do currículo colocando **Projetos e Habilidades Técnicas no topo**.
   - Redação baseada em resultados e impacto de negócio (descrever a ferramenta, o processo de tratamento e os *insights* gerados).

3. **Estratégia de Candidatura e Entrada no Mercado**
   - Otimização do perfil no **LinkedIn** e criação de redes de contato ativas.
   - Abordagem de candidatura direcionada vs. candidaturas automatizadas em massa.
   - Preparação para **Entrevistas Técnicas** (especialmente testes práticos de SQL e resolução de casos de negócio).

> **Análise do Aprendizado Incremental na Carreira:**
> Esta fase encerra o ciclo cumulativo. O conhecimento técnico adquirido nos módulos anteriores (SQL, Excel, BI, Python) é transformado em **projetos práticos aplicados**. Esses projetos alimentam o **portfólio visual e o currículo**, que por sua vez fornecem o repertório necessário para ter bom desempenho em **entrevistas técnicas e contratações**.

---

### **Síntese Geral da Ordem do Conhecimento Cumulativo (Aprendizado Incremental)**

A sequência pedagógica demonstrada ao longo do bootcamp responde a uma lógica encadeada de dependências do trabalho real de um analista de dados:

1. **SQL Primeiro (A Fonte):** Antes de analisar ou criar gráficos, o analista precisa extrair e estruturar os dados de onde eles originalmente residem (bancos de dados relacionais).
2. **Excel em Segundo (O Tratamento Ágil):** Permite entender a estrutura tabular, fazer limpezas rápidas, entender a lógica de fórmulas e criar protótipos de análises dinâmicas.
3. **Power BI / Tableau em Terceiro (A Visualização Executiva):** Com os dados limpos e modelados, o foco passa a ser o *storytelling*, a interatividade executiva e a disponibilização de painéis de tomada de decisão.
4. **Python em Quarto (A Automação e Análise Avançada):** Adiciona poder de escala, automações complexas, raspagem de dados e análises estatísticas para problemas que superam a capacidade do Excel ou BI.
5. **Projetos e Carreira ao Final (A Consolidação):** Transforma todas as ferramentas aprendidas de forma isolada em um conjunto integrado de soluções públicas (portfólio), validando a capacidade profissional para o mercado de trabalho.
