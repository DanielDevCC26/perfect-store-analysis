
# Perfect Store Analysis

### Análise de desempenho operacional e financeiro de uma rede de restaurantes

Projeto de análise de dados desenvolvido em **Python**, utilizando informações de **50 filiais e 600 avaliações mensais de 2024** para identificar oportunidades de melhoria operacional e investigar a relação entre desempenho e resultados financeiros.

**Tecnologias:** Python · Pandas · NumPy · Matplotlib · Seaborn · Jupyter Notebook · Excel

## Resultados em destaque

| Indicador | Resultado |
| :--- | :--- |
| Filiais analisadas | 50 |
| Avaliações mensais | 600 |
| Melhor filial | Filial 045 — PSS 88,86 |
| Menor desempenho anual | Filial 005 — PSS 82,45 |
| Avaliações mensais classificadas como Loja Perfeita | 18,50% |
| Filiais que atingiram a meta anual de 90 pontos | 0 |
| Principal oportunidade de melhoria | Execução promocional |
| Correlação anual entre PSS e faturamento | 0,0416 |

**Principal descoberta:** nenhuma filial atingiu a meta de excelência operacional na média anual. A execução promocional e a disponibilidade do cardápio foram os indicadores com maior impacto negativo no Perfect Store Score.

## Visualizações da análise

### 1. Ranking das 10 melhores filiais

Comparação das filiais com maior Perfect Store Score médio anual, utilizando a meta de 90 pontos como referência.

![Top 10 filiais por PSS médio](images/top_10_filiais.png)

### 2. Ranking das 10 filiais com menor desempenho

Identificação das unidades com menor PSS médio anual e maior necessidade de acompanhamento operacional.

![Bottom 10 filiais por PSS médio](images/bottom_10_filiais.png)

### 3. Impacto dos indicadores operacionais

Avaliação da contribuição de cada indicador para a perda de pontos no PSS, considerando seu peso na composição do índice.

![Impacto dos indicadores no PSS](images/impacto_indicadores.png)

**Destaque:** execução promocional e disponibilidade do cardápio representam, juntas, aproximadamente 55,5% dos pontos perdidos no indicador.

### 4. Relação entre PSS e faturamento anual

Análise exploratória da associação entre o desempenho operacional médio e o faturamento anual das 50 filiais.

![Relação entre PSS médio e faturamento anual](images/pss_faturamento_anual.png)

**Resultado:** a correlação de Pearson foi de aproximadamente 0,0416, indicando ausência de associação linear relevante nesta amostra.

---

## Objetivo do projeto

Avaliar o desempenho operacional de uma rede de restaurantes por meio do **Perfect Store Score (PSS)**, um indicador composto por cinco critérios ponderados.

A análise busca responder às seguintes perguntas de negócio:

- Quais filiais apresentam os melhores e piores desempenhos?
- Quais indicadores operacionais mais prejudicam o PSS?
- Como o desempenho varia entre regiões e ao longo do ano?
- Existe associação entre o PSS e o faturamento ou ticket médio?

## Base de dados

O conjunto de dados contém **600 registros**, correspondentes a 50 filiais avaliadas mensalmente durante os 12 meses de 2024.

As informações incluem:

- Código da filial, cidade e região.
- Mês de referência.
- Cinco indicadores de desempenho operacional.
- Faturamento mensal.
- Número de pedidos.
- Ticket médio.

### Validação dos dados

Foram realizadas verificações de valores ausentes, duplicidades, intervalos dos indicadores, cobertura mensal e consistência cadastral.

A base não apresentou valores ausentes nem duplicidades nas combinações de filial e mês.

Entretanto, foram identificadas inconsistências na associação dos códigos das filiais às cidades e regiões. Essa limitação foi considerada durante a análise.

## Metodologia

### Cálculo do Perfect Store Score

O PSS foi calculado utilizando a média ponderada de cinco indicadores:

| Indicador | Peso |
| :--- | ---: |
| Disponibilidade do cardápio | 30% |
| Preço correto | 25% |
| Execução promocional | 20% |
| Padrão visual | 15% |
| Tempo de atendimento | 10% |
| **Total** | **100%** |

Cada indicador recebe uma pontuação de 0 a 100.

A fórmula aplicada foi:

**PSS = (Disponibilidade × 0,30) + (Preço × 0,25) + (Promoções × 0,20) + (Padrão Visual × 0,15) + (Atendimento × 0,10)**

### Classificação operacional

| Classificação | Faixa de PSS |
| :--- | :--- |
| Loja Perfeita | PSS ≥ 90 |
| Atenção | 75 ≤ PSS < 90 |
| Crítico | PSS < 75 |

### Etapas da análise

1. Importação e exploração dos dados.
2. Validação e verificação de consistência.
3. Cálculo do Perfect Store Score.
4. Classificação das avaliações mensais.
5. Construção do ranking anual das filiais.
6. Análise dos indicadores com maior perda ponderada.
7. Comparação regional e evolução mensal.
8. Análise de correlação entre PSS e indicadores financeiros.
9. Criação de visualizações e recomendações de negócio.

## Principais conclusões

### Desempenho das filiais

A **Filial 045** apresentou o maior PSS médio anual, com **88,86 pontos**, enquanto a **Filial 005** registrou o menor, com **82,45 pontos**.

Todas as 50 filiais permaneceram na classificação "Atenção" quando considerada a média anual.

Nas avaliações mensais, 18,50% dos registros alcançaram a classificação "Loja Perfeita".

### Indicadores prioritários

A execução promocional apresentou a maior perda ponderada, aproximadamente **4,29 pontos de PSS**, seguida pela disponibilidade do cardápio, com **3,88 pontos**.

Esses resultados indicam onde as ações de melhoria operacional podem ter maior impacto sobre o índice.

### Desempenho regional

O Nordeste apresentou o maior PSS médio registrado (**85,53**), enquanto o Sudeste apresentou o menor (**84,85**).

Essas comparações consideram a região informada em cada registro mensal e devem ser interpretadas com cautela devido às inconsistências cadastrais.

### Evolução mensal

O PSS médio apresentou uma redução de **1,46 ponto** entre janeiro e dezembro de 2024.

Janeiro registrou o maior PSS médio mensal, enquanto setembro apresentou o menor.

### Relação com indicadores financeiros

As correlações anuais calculadas foram:

| Relação analisada | Correlação de Pearson |
| :--- | ---: |
| PSS × Faturamento anual | 0,0416 |
| PSS × Ticket médio anual | −0,0404 |

Os resultados não indicaram associações lineares relevantes.

Isso não significa que a qualidade operacional não influencia os resultados financeiros, mas que essa relação não foi evidenciada pelas correlações calculadas nesta base.

## Recomendações de negócio

- **Execução promocional:** investigar falhas na implementação das campanhas e monitorar sua conformidade.
- **Disponibilidade do cardápio:** identificar causas de indisponibilidade e melhorar o planejamento de abastecimento.
- **Filiais com menor desempenho:** estabelecer planos de ação e acompanhar a evolução mensal dos indicadores.
- **Boas práticas:** investigar os processos das filiais mais bem avaliadas e considerar sua replicação.
- **Qualidade cadastral:** corrigir as associações entre filiais, cidades e regiões para permitir análises geográficas confiáveis.

## Limitações da análise

Os mesmos códigos de filiais aparecem associados a diferentes cidades e regiões durante o período analisado.

Para evitar distorções:

- O ranking anual foi calculado exclusivamente pelo código da filial.
- As comparações regionais utilizaram a região registrada em cada avaliação mensal.
- Não foi elaborado um mapa geográfico das filiais, pois a localização cadastral não é confiável.
- As análises de correlação são exploratórias e não estabelecem relações de causa e efeito.

A correção dos dados cadastrais é recomendada antes de realizar análises geográficas mais detalhadas.

## Estrutura do projeto

```text
perfect-store-analysis/
├── data/
│   └── projeto1_vendas_perfect_store.xlsx
├── images/
│   ├── top_10_filiais.png
│   ├── bottom_10_filiais.png
│   ├── impacto_indicadores.png
│   └── pss_faturamento_anual.png
├── notebooks/
│   └── perfect_store_analysis.ipynb
├── .gitignore
└── README.md
```

## Como executar o projeto

### 1. Clonar o repositório

Clone o repositório pelo Git ou faça o download dos arquivos e abra a pasta no VS Code.

### 2. Preparar o ambiente

Crie e ative um ambiente virtual Python.

Instale as dependências:

```bash
pip install pandas numpy matplotlib seaborn jupyter openpyxl
```

### 3. Executar a análise

Abra o arquivo:

`notebooks/perfect_store_analysis.ipynb`

Selecione o ambiente virtual como kernel do Jupyter e execute as células na ordem apresentada.

O notebook utiliza o arquivo Excel disponível na pasta `data/`.

## Status do projeto

**Concluído.**

Análise exploratória, validação de dados, construção de indicadores, ranking de filiais, visualizações, análise financeira e recomendações de negócio finalizadas.
