# Investimentos Pro

Simulador desktop de **day trade** na B3 — boleta, gráfico, indicadores e robôs em JavaScript. Roda 100% na máquina. **Não opera conta real e não se conecta a corretora nem ao feed da bolsa.**

Cotações, saldo e PnL são fictícios. Persistência local (IndexedDB).

---

## Demonstração

Windows 10/11 (x64). Conta de treino com **R$ 100.000** ao abrir.

| Arquivo | Uso |
| :--- | :--- |
| [Investimentos.Pro.Setup.1.1.0.exe](https://github.com/joaop-gregorioDS/investimentos-pro/releases/download/v1.1.0/Investimentos.Pro.Setup.1.1.0.exe) | Instalador (atalhos no Menu Iniciar) |
| [Investimentos.Pro.1.1.0.exe](https://github.com/joaop-gregorioDS/investimentos-pro/releases/download/v1.1.0/Investimentos.Pro.1.1.0.exe) | Portátil (duplo clique) |

[Releases · v1.1.0](https://github.com/joaop-gregorioDS/investimentos-pro/releases/tag/v1.1.0) · [Manual](MANUAL_DO_USUARIO.md)

**Caminho do avaliador:** instalar → escolher `WINQ26` ou `PETR4` → comprar/vender a mercado → ver resultado na boleta → relatório (fator de lucro, win rate) → opcional: colar um robô de RSI do manual.

Não há login, API remota nem Swagger.

---

## O que é real e o que é simulado

| No app (local) | Não é |
| :--- | :--- |
| Ordens a mercado e limite, zerar, inverter | Conta de corretora |
| Mini índice, mini dólar e ações (15 papéis) | Feed B3 / tempo real de mercado |
| 12 indicadores e robô em JavaScript | Consultoria ou recomendação |
| PnL, CSV, saldo de treino | Dinheiro real |

Pontuação no simulador segue a especificação da B3 (WIN R$ 0,20/pt, WDO R$ 10,00/pt). Os preços das velas são gerados no próprio app.

---

## Código

Este repositório publica o **produto** (instalador, manual e isenção). O avaliador demonstra pelo `.exe`.

Stack do app: Electron · React · IndexedDB.

---

## Marcas

MetaTrader 5® (MetaQuotes) e ProfitChart® (Nelogica) são marcas de terceiros. Este projeto **não é afiliado** a elas. Referências são só de usabilidade.

---

## Licença

MIT. Ver [LICENSE](LICENSE). Não é recomendação de investimento.
