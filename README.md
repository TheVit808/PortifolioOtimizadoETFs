Otimização de Portfólio com ETFs Diversificados

## 1. Introdução

Este projeto visa demonstrar a construção e análise de um portfólio de investimentos diversificado, utilizando Exchange Traded Funds (ETFs) que representam diferentes classes de ativos e setores. O objetivo principal é aplicar conceitos da Teoria Moderna do Portfólio, notadamente a otimização de Markowitz, para identificar portfólios eficientes e analisar métricas de risco e retorno, como o Índice Sharpe e a correlação móvel. Todo o processo é apresentado através de scripts em Jupyter Notebook, culminando em um dashboard interativo para facilitar a exploração dos dados.

## 2. Seleção e Explicação dos Ativos (ETFs)

Para garantir uma diversificação robusta, foram selecionados ETFs que cobrem uma ampla gama de mercados e classes de ativos, incluindo ações de diferentes setores nos EUA, mercados internacionais, renda fixa, commodities e exposição a criptomoedas e moedas fiduciárias. Os dados históricos foram obtidos do Yahoo Finance desde 2015, utilizando os preços de fechamento (`Close`).

A tabela a seguir detalha os ETFs selecionados e suas respectivas descrições:

| Ticker | Descrição                                                      |
|--------|----------------------------------------------------------------|
| SPY    | SPDR S&P 500 ETF (Ações EUA - Amplo Mercado)                   |
| XLK    | Technology Select Sector SPDR Fund (Ações EUA - Tecnologia)    |
| XLF    | Financial Select Sector SPDR Fund (Ações EUA - Financeiro)     |
| XLE    | Energy Select Sector SPDR Fund (Ações EUA - Energia)           |
| XLP    | Consumer Staples Select Sector SPDR Fund (Ações EUA - Consumo Essencial) |
| EFA    | iShares MSCI EAFE ETF (Ações Internacionais - Mercados Desenvolvidos) |
| TLT    | iShares 20+ Year Treasury Bond ETF (Renda Fixa - Títulos do Tesouro EUA) |
| GLD    | SPDR Gold Shares (Commodities - Ouro)                          |
| VNQ    | Vanguard Real Estate ETF (Setor Imobiliário - REITs EUA)       |
| BITO   | ProShares Bitcoin Strategy ETF (Criptomoedas - Futuros de Bitcoin) |
| UUP    | Invesco DB US Dollar Index Bullish Fund (Moedas - Dólar Americano) |

## 3. Metodologias de Análise

O projeto empregou diversas metodologias de análise quantitativa para avaliar o desempenho e o risco dos ativos e portfólios:

### 3.1. Retornos e Volatilidade

Os retornos diários foram calculados a partir dos preços de fechamento, e posteriormente anualizados para obter o retorno esperado e a volatilidade anual de cada ativo. Uma taxa livre de risco (exemplo: 2% ao ano) foi utilizada para cálculos de métricas ajustadas ao risco.

### 3.2. Correlação Móvel (Rolling Correlation)

A correlação móvel foi utilizada para analisar como a relação entre os pares de ativos se comporta ao longo do tempo. Este indicador é crucial para entender a dinâmica da diversificação, pois a correlação entre ativos pode variar significativamente em diferentes períodos de mercado. Uma janela de 252 dias úteis (aproximadamente um ano) foi empregada para este cálculo.

### 3.3. Índice Sharpe

O Índice Sharpe é uma medida de desempenho ajustada ao risco, indicando o retorno excedente por unidade de risco (volatilidade). Foi calculado tanto para cada ativo individualmente quanto de forma móvel ao longo do tempo, permitindo identificar ativos com melhor relação risco-retorno e observar a evolução dessa métrica.

### 3.4. Otimização de Portfólio de Markowitz

A Teoria Moderna do Portfólio de Markowitz é a espinha dorsal da otimização. Através da simulação de milhares de portfólios com diferentes combinações de pesos para os ativos, foi possível:

*   **Fronteira Eficiente:** Identificar o conjunto de portfólios que oferecem o maior retorno esperado para um dado nível de risco, ou o menor risco para um dado nível de retorno esperado.
*   **Carteira de Mínima Variância:** O portfólio na fronteira eficiente com o menor risco absoluto.
*   **Carteira Ótima (Maior Sharpe):** O portfólio na fronteira eficiente que maximiza o Índice Sharpe, representando a melhor relação risco-retorno.

## 4. Dashboard Interativo

Para tornar a análise mais acessível e dinâmica, foi desenvolvido um dashboard interativo. Inicialmente, uma versão em Streamlit foi proposta, mas para compatibilidade direta com o Google Colab, optou-se por uma implementação utilizando **IPyWidgets** e **Plotly** dentro de um Jupyter Notebook. Este dashboard permite ao usuário:

*   **Selecionar Ativos:** Escolher quais ETFs incluir na análise.
*   **Definir Período:** Ajustar as datas de início e fim para os dados históricos.
*   **Ajustar Taxa Livre de Risco:** Modificar a taxa livre de risco para recalcular as métricas.
*   **Visualizações Dinâmicas:** Todos os gráficos (correlação móvel, Sharpe individual e temporal, risco-retorno com linha do ativo livre de risco, e a fronteira eficiente com as carteiras otimizadas) são interativos, permitindo zoom, pan e exibição de detalhes ao passar o mouse.

## 5. Conclusão

Este projeto fornece uma estrutura completa para a análise e otimização de portfólios de investimento, combinando a robustez de dados históricos com metodologias financeiras consagradas e uma interface interativa para exploração. As ferramentas desenvolvidas são valiosas para investidores e analistas que buscam tomar decisões informadas sobre a alocação de capital, compreendendo as relações de risco e retorno entre diferentes classes de ativos. É fundamental lembrar que análises passadas não garantem retornos futuros e que a taxa livre de risco utilizada deve ser ajustada conforme o contexto de mercado para uma análise mais rigorosa.
