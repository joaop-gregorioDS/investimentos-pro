# 📖 Manual Completo do Usuário — Investimentos Pro
### Guia Operacional, Tipos de Ordem, Indicadores Técnicos e Algo Trading

---

## 📑 Sumário
1. [Visão Geral e Propósito](#1-visão-geral-e-propósito)
2. [Instalação e Primeiros Passos](#2-instalação-e-primeiros-passos)
3. [Explorando a Interface Desktop](#3-explorando-a-interface-desktop)
4. [Guia de Ordens e Chart Trading](#4-guia-de-ordens-e-chart-trading)
5. [Cálculo de Resultados Financeiros e Pontuação](#5-cálculo-de-resultados-financeiros-e-pontuação)
6. [Catálogo de Indicadores Técnicos](#6-catálogo-de-indicadores-técnicos)
7. [Algo Trading (Programação de Robôs)](#7-algo-trading-programação-de-robôs)
8. [Relatório de Desempenho Operacional](#8-relatório-de-desempenho-operacional)
9. [Atalhos de Teclado](#9-atalhos-de-teclado)
10. [Isenção de Responsabilidade Legal](#10-isenção-de-responsabilidade-legal)

---

## 1. Visão Geral e Propósito

O **Investimentos Pro** é um simulador de day trade na B3. Serve para treinar boleta, gráfico, indicadores e robôs **sem risco financeiro**.

Cotações e saldo são **fictícios** e ficam só neste computador. Não há conexão com corretora, banco ou feed da bolsa.

---

## 2. Instalação e Primeiros Passos

Disponibilizamos duas modalidades de executáveis para Windows (64-bit):

### A. Instalador Oficial (`Investimentos Pro Setup 1.1.0.exe`)
* **Como usar:** Execute o arquivo com dois cliques e siga o assistente de instalação.
* **Benefícios:** Instala a aplicação de forma limpa, cria atalhos automáticos na Área de Trabalho e no Menu Iniciar do Windows.

### B. Versão Portátil Standalone (`Investimentos Pro 1.1.0.exe`)
* **Como usar:** Não requer instalação. Basta salvar o arquivo em qualquer pasta (ex: Documentos ou Pendrive) e clicar duas vezes para abrir.
* **Ideal para:** Testes rápidos ou execução sem privilégios de administrador.

### 💰 Conta Demonstrativa Inicial
Ao abrir o aplicativo pela primeira vez, uma conta de treino com **R$ 100.000,00** é criada localmente. Todos os saldos e histórico de trades são salvos automaticamente no banco de dados local do seu navegador/aplicativo (**IndexedDB**), preservando seus dados mesmo ao fechar e reabrir o app.

---

## 3. Explorando a Interface Desktop

```text
+-----------------------------------------------------------------------------------+
|  Arquivo   Exibir   Inserir   Gráficos   Ferramentas   Ajuda              [v1.1.0] | <- Menu superior
+-----------------------------------------------------------------------------------+
|  [Logo] Ativo: WINQ26   | Saldo: R$ 100.000,00 | Patrimônio: R$ 100.000,00        | <- Navbar de Status
+----+-------------------+--------------------------------------------+-------------+
|    | OBSERVAÇÃO DE     | [Aba 1: WINQ26] [Aba 2: PETR4]             | CHART       |
|    | MERCADO (Ctrl+M)  |--------------------------------------------| TRADING     |
| S  |                   |                                            |             |
| I  | WINQ26  128.450 ▲ |           GRÁFICO DE CANDLESTICKS          | Qtd: [  1 ] |
| D  | WDOU26    5.420 ▼ |                                            |             |
| E  | PETR4     38,90 ▲ |             + Médias Móveis / VWAP         | [COMPRAR]   |
| B  | VALE3     61,20 ▼ |                                            | [VENDER]    |
| A  | ...15 Ativos      |                                            |             |
| R  |                   |--------------------------------------------| [ZERAR]     |
|    |                   | [🤖 Robô Algo Trading (Canto Inferior)]    | [INVERTER]  |
+----+-------------------+--------------------------------------------+-------------+
```

### Barra Superior (Menus Clássicos)
* **Arquivo:** Criar nova aba de ativo (`Ctrl+T`), fechar aba atual, resetar conta demo para R$ 100.000 e sair.
* **Exibir:** Exibir/ocultar a Observação de Mercado (`Ctrl+M`), a boleta de Chart Trading, o painel de posições ou alternar tela cheia (`F11`).
* **Inserir:** Gerenciador de Indicadores Técnicos.
* **Gráficos:** Ajuste de timeframes (1m, 5m, 15m, 1H, 1D) e controle de arraste livre.
* **Ferramentas:** Acesso ao Algo Trading e exportação de trades em CSV.
* **Ajuda:** Atalhos e informações da versão.

### Observação de Mercado (Watchlist de 15 Ativos)
Pressione `Ctrl + M` para abrir o painel lateral com os 15 papéis **simulados** (não é cotação da B3):
* **Futuros:** `WINQ26` (Mini Índice) e `WDOU26` (Mini Dólar).
* **Ações:** `PETR4`, `VALE3`, `ITUB4`, `BBDC4`, `B3SA3`, `ABEV3`, `BBAS3`, `WEGE3`, `RENT3`, `PRIO3`, `GGBR4`, `SUZB3`, `MGLU3`.
* **Interações:**
  * **Clique simples:** Seleciona o ativo para a aba ativa.
  * **Duplo clique:** Abre o papel em uma **nova aba de gráfico** independente!

---

## 4. Guia de Ordens e Chart Trading

A boleta lateral direita é o centro de execução das suas operações manuais.

### Definição dos Tipos de Ordem

| Ordem / Botão | Tipo de Execução | Descrição Operacional |
| :--- | :--- | :--- |
| **C Mercado** | A Mercado | Envia ordem de **compra imediata** no preço atual de mercado (melhor oferta de venda). Execução garantida instantânea. |
| **V Mercado** | A Mercado | Envia ordem de **venda imediata** no preço atual de mercado (melhor oferta de compra). Execução garantida instantânea. |
| **Comprar** | Limite | Posiciona uma ordem de compra no preço definido no campo **Preço**. É executada apenas quando o mercado atinge esse valor. |
| **Vender** | Limite | Posiciona uma ordem de venda no preço definido no campo **Preço**. É executada apenas quando o mercado atinge esse valor. |
| **Zerar** | A Mercado | Encerra imediatamente qualquer posição aberta no ativo atual. Se você estiver comprado em 2 contratos, envia venda a mercado de 2 contratos. |
| **Inverter** | A Mercado | Reverte a direção da sua mão instantaneamente. Exemplo: se você estiver **comprado em 2** contratos, o botão envia uma ordem de venda de **4 contratos**, deixando você imediatamente **vendido em 2**. |
| **Cancel Ord.** | Comando | Cancela todas as ordens pendentes (limite) que ainda não foram executadas no ativo. |
| **Cancelar + Zerar** | A Mercado + Comando | **Ação de emergência ("botão de pânico"):** cancela todas as ordens pendentes e zera a posição aberta a mercado no mesmo milissegundo. |

### ⚙️ Como Personalizar os Botões da Boleta
No cabeçalho da boleta, clique no ícone de **engrenagem** (`⚙️`). Um menu de seleção rápida permitirá marcar ou desmarcar quais botões você deseja exibir (ideal para simplificar a tela para scalpers que utilizam apenas Mercado e Zerar).

---

## 5. Cálculo de Resultados Financeiros e Pontuação

O simulador adota as especificações oficiais da B3 para cálculo de ganhos e perdas:

### 1. Mini Índice Bovespa (`WINQ26`)
* **Variação mínima (tick):** 5 pontos.
* **Valor do Ponto:** **R$ 0,20 por ponto por contrato**.
* *Exemplo:* Comprado em 2 contratos a 128.000 pontos e vendido a 128.150 (+150 pontos):
  $$\text{Resultado} = 150 \times 2 \times R\$\,0,20 = R\$\,60,00$$

### 2. Mini Dólar Comercial (`WDOU26`)
* **Variação mínima (tick):** 0,5 ponto.
* **Valor do Ponto:** **R$ 10,00 por ponto por contrato** (R$ 5,00 por meio ponto).
* *Exemplo:* Vendido em 1 contrato a 5.430,0 e zerado a 5.425,0 (+5 pontos):
  $$\text{Resultado} = 5 \times 1 \times R\$\,10,00 = R\$\,50,00$$

### 3. Ações à Vista (`PETR4`, `VALE3`, etc.)
* **Variação mínima:** R$ 0,01 (centavo).
* **Multiplicador:** R$ 1,00 por variação de centavos multiplicado pela quantidade de ações.

### Entendendo os Resultados na Boleta
* **Res. Aberto (Não Realizado / Flutuante):** Ganho ou perda da posição enquanto ela ainda está aberta, oscilando com o preço atual.
* **Res. do Dia (Realizado):** Soma dos lucros e prejuízos de todas as operações já encerradas na sessão.
* **Total:** A soma do Resultado Realizado com o Resultado Aberto.

---

## 6. Catálogo de Indicadores Técnicos

Para inserir indicadores, acesse **Inserir -> Indicadores Técnicos...** na barra superior ou clique no ícone de indicadores no topo do gráfico.

1. **SMA (Simple Moving Average):** Média aritmética dos preços de fechamento dos últimos $N$ períodos (padrões: 9, 20, 50, 200).
2. **EMA (Exponential Moving Average):** Média que atribui maior peso aos dados recentes, reagindo mais rápido a mudanças bruscas de tendência (padrões: 9, 21).
3. **VWAP (Volume Weighted Average Price):** Média ponderada pelo volume financeiro acumulado no dia. Referência essencial para players institucionais.
4. **Bandas de Bollinger:** Média móvel central envolvida por duas faixas a 2 desvios padrão de distância. Identifica volatilidade, contrações e rompimentos.
5. **RSI / IFR (Índice de Força Relativa):** Oscilador de 0 a 100 que mede o momentum do ativo. Níveis acima de 70 indicam sobrecompra; abaixo de 30 indicam sobrevenda.
6. **MACD (Moving Average Convergence Divergence):** Indicador seguidor de tendência com linha MACD, linha de sinal e histograma de aceleração.
7. **Estocástico Lento:** Oscilador de momentum que compara o preço de fechamento com a faixa de máximas e mínimas em determinado período.
8. **ATR (Average True Range):** Mede a volatilidade média do ativo em pontos ou centavos, excelente para posicionar stop loss e alvo.
9. **HiLo Activator:** Escadinha seguidora de tendência calculada sobre as máximas e mínimas dos períodos anteriores.

---

## 7. Algo Trading (Programação de Robôs)

O Investimentos Pro inclui uma ferramenta de **automação algorítmica** que executa seu script a cada tick de cotação.

O painel fica discretamente posicionado no **canto inferior esquerdo**, sem tampar o gráfico, e conta com modo compacto/minimizado.

### Variáveis Globais Injetadas no Robô

| Variável | Tipo | Descrição |
| :--- | :--- | :--- |
| `price` | `number` | Preço atual do ativo no tick exato. |
| `positions` | `Array` | Lista de posições abertas no momento. |
| `indicators` | `Object` | Objeto contendo os valores calculados: `sma9`, `sma20`, `ema9`, `ema21`, `vwap`, `rsi`, `bollingerUpper`, `bollingerLower`, `atr`, `hiloState`. |
| `buy(qtd)` | `Function` | Envia ordem de compra a mercado da quantidade indicada. |
| `sell(qtd)` | `Function` | Envia ordem de venda a mercado da quantidade indicada. |

---

### Exemplos Prontos de Robôs (Copie e Cole)

#### Exemplo 1: Robô de IFR / RSI (Scalper de Reversão)
Compra quando o RSI estiver sobrevendido (< 30) e vende quando estiver sobrecomprado (> 70):

```javascript
// Verifica se já não estamos posicionados
if (positions.length === 0) {
  if (indicators.rsi < 30) {
    buy(1); // Compra a mercado 1 contrato/lote
  } else if (indicators.rsi > 70) {
    sell(1); // Vende a mercado 1 contrato/lote
  }
}
```

#### Exemplo 2: Robô de Cruzamento de Médias Móveis (Trend Following)
Compra quando a média rápida (SMA 9) cruza acima da média lenta (SMA 20):

```javascript
if (positions.length === 0) {
  if (indicators.sma9 > indicators.sma20) {
    buy(1);
  }
} else {
  // Se estiver comprado e a média rápida cruzar para baixo, encerra a posição
  const pos = positions[0];
  if (pos.type === 'BUY' && indicators.sma9 < indicators.sma20) {
    sell(pos.quantity); // Zera a posição
  }
}
```

#### Exemplo 3: Robô de Rompimento de Bandas de Bollinger
Entra a favor da expansão de volatilidade:

```javascript
if (positions.length === 0) {
  if (price > indicators.bollingerUpper) {
    buy(1); // Rompeu banda superior com força
  } else if (price < indicators.bollingerLower) {
    sell(1); // Rompeu banda inferior com força
  }
}
```

---

## 8. Relatório de Desempenho Operacional

Clique no ícone de **gráfico de pizza** na barra lateral ou no menu **Exibir -> Relatório de Desempenho** para auditar suas métricas:
* **Fator de Lucro (*Profit Factor*):** Relação entre o lucro bruto total e o prejuízo bruto total. Valores acima de `1.5` indicam consistência.
* **Taxa de Assertividade (*Win Rate*):** Percentual de trades vencedores sobre o total de trades.
* **Média de Ganho vs Média de Perda (*Payoff*):** Demonstra se os ganhos médios são superiores aos riscos assumidos.
* **Exportação CSV:** Exporte todo o seu diário de trades para o Microsoft Excel ou Google Sheets via menu **Ferramentas -> Exportar Relatório em CSV**.

---

## 9. Atalhos de Teclado

| Atalho | Função |
| :--- | :--- |
| `Ctrl + M` | Abrir / Ocultar Observação de Mercado |
| `Ctrl + T` | Criar Nova Aba de Gráfico |
| `F11` | Alternar Modo Tela Cheia |
| `+` | Zoom In no Gráfico |
| `-` | Zoom Out no Gráfico |
| `Setas Direita / Esquerda` | Rolar histórico temporal de velas |

---

## 10. Isenção de Responsabilidade Legal & Aviso sobre Marcas

> [!CAUTION]
> **AVISO IMPORTANTE:** O aplicativo **Investimentos Pro** é uma ferramenta de estudo e simulação técnica sem qualquer vínculo financeiro com o mercado real. 
> 
> O mercado de renda variável, futuros e daytrade envolve riscos elevados de perda patrimonial. Resultados positivos em ambiente simulado não são garantia de resultados no mercado real. Use esta ferramenta como auxílio educacional e gerencie sempre seu risco com responsabilidade.

### 📌 Marcas Registradas Citadas
* **MetaTrader 5®** é marca registrada de **MetaQuotes Software Corp.**
* **ProfitChart®** é marca registrada de **Nelogica Sistemas de Software Ltda.**

O **Investimentos Pro** é uma iniciativa independente voltada a estudos de desenvolvimento de software e simulação computacional, **sem vínculo societário, representação, endosso ou afiliação oficial** com as titulares das referidas marcas. Todas as menções no software ou na documentação têm finalidade meramente descritiva de usabilidade e mercado de referência.
