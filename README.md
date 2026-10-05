# simulador-investimentos-excel
Planilha interativa de alocação de investimentos e estimativa de patrimônio futuro por perfil de investidor.
# 🐷 DIO INVEST — Simulador de Investimentos & Projeção de Dividendos
O **DIO INVEST** é uma ferramenta de planejamento financeiro desenvolvida em Microsoft Excel. Ela permite simular aportes mensais, projetar o acúmulo de patrimônio ao longo do tempo (até 30 anos) e calcular a renda passiva mensal estimada em dividendos, além de recomendar a distribuição de aportes em Fundos Imobiliários (FIIs) conforme o perfil do investidor.
---
## ❓ 1. As 5 Perguntas que a Ferramenta Responde
A ferramenta foi desenhada para ser intuitiva e responde diretamente às seguintes dúvidas:
1. **Quanto devo investir por mês com base na recomendação sobre minha renda?**
   - *Onde aparece:* Na seção **CONFIGURAÇÕES** (`Recomendação de investimento`) e na seção **INVESTIMENTO MENSAL** (`Quanto investir por mês?`).
2. **Qual é o patrimônio acumulado no tempo de aporte desejado?**
   - *Onde aparece:* Na seção **INVESTIMENTO MENSAL** no campo `Patrimonios acumulados?`.
3. **Quanto vou receber de renda passiva mensal (dividendos)?**
   - *Onde aparece:* Na seção **INVESTIMENTO MENSAL** no campo `Dividendos Mensais?`.
4. **Qual a evolução do meu patrimônio e dividendos em múltiplos prazos (2 a 30 anos)?**
   - *Onde aparece:* Na tabela **CENÁRIO**, detalhada para 2, 5, 10, 20 e 30 anos.
5. **Como devo fatiar meu aporte mensal entre as categorias de FIIs?**
   - *Onde aparece:* Na tabela de alocação por **TIPO DE FII** (Papel, Tijolo, Híbrido, FOFs, Desenvolvimento e Hotelaria), calculando o valor exato em R$ para cada categoria.
---
## 🧮 2. Como as Fórmulas `VF` e `PROCV` Entram nos Cálculos
- **`VF` (Valor Futuro):** Utilizada na tabela de **CENÁRIO** e no campo `Patrimonios acumulados?` para calcular o rendimento composto dos aportes.
  - *Lógica da Fórmula:* `=VF(taxa_rendimento_mensal; anos * 12; -aporte_mensal; 0)`
  - *Exemplo real da foto:* Aportando **R$ 500,00/mês** a uma taxa de **1,08% a.m.** durante **5 anos (60 meses)**, a função `VF` resulta no montante acumulado de **R$ 41.888,46**.
- **`PROCV` (Busca Vertical):** Utilizada na tabela de alocação por **TIPO DE FII**.
  - *Lógica da Fórmula:* `=PROCV(Perfil_Selecionado; Tabela_Matriz_Perfis; Coluna_Tipo_FII; FALSO)`
  - *Exemplo real da foto:* Quando o perfil selecionado no campo `PERFIL` é **CONSERVADOR**, o `PROCV` busca automaticamente a linha correspondente e preenche a coluna `PERCENTUAL SUGERIDO` (ex: 30% em Papel, 50% em Tijolo, 10% em Híbrido, etc.).
---
## 🏷️ 3. Intervalos Nomeados Criados
Para deixar as fórmulas limpas e legíveis, foram criados os seguintes intervalos nomeados:
- `Perfil_Usuario`: Célula de seleção do perfil (`CONSERVADOR`, `MODERADO`, `ARROJADO`).
- `Aporte_Mensal`: Célula com o valor a ser investido mensalmente (ex: `R$ 500,00`).
- `Taxa_Mensal`: Célula com a taxa de rendimento estimada (ex: `1,08%`).
- `Tabela_Perfis_FII`: Intervalo contendo a matriz de percentuais por categoria de FII para a consulta do `PROCV`.
---
## 📊 4. Percentuais por Perfil e Origem dos Dados
A distribuição do aporte mensal foi focada na classe de **Fundos Imobiliários (FIIs)**:
- **Perfil CONSERVADOR (Exemplo das evidências):**
  - **Tijolo (50%)** e **Papel (30%)**: Foco em alta previsibilidade, imóveis físicos consolidados e recebíveis com garantias.
  - **Híbrido (10%)** e **FOFs (10%)**: Pequena diversificação.
  - **Desenvolvimento (0%)** e **Hotelaria (0%)**: Exposição zero a setores de maior risco/volatilidade.
> *Origem dos dados:* Os percentuais foram estruturados com base nos conceitos de alocação defensiva ensinados nos módulos de investimento da DIO e nas boas práticas de gestão de risco em FIIs do mercado financeiro.
---
## 🚀 5. Diferenciais em Relação à Ferramenta do Expert
1. **Identidade Visual Própria (DIO INVEST):** Layout moderno com cabeçalho estilizado, paleta de cores verde/azul/cinza e agrupamento intuitivo.
2. **Projeção Dupla (Patrimônio + Dividendos):** Além de calcular o valor total no tempo, a ferramenta calcula a estimativa de **renda mensal em dividendos** para cada horizonte temporal (2, 5, 10, 20 e 30 anos).
3. **Foco Prático em FIIs:** Em vez de focar apenas em Renda Fixa vs Variável genérica, a planilha detalha a compra exata em R$ para 6 categorias de Fundos Imobiliários.
---
## 🖼️ 6. Evidências de Funcionamento (Prints)
### Simulação no Perfil CONSERVADOR
<img width="718" height="579" alt="Captura de tela 2026-10-05 190443" src="https://github.com/user-attachments/assets/90723fa3-6250-442d-85e4-f19b60fa6cb1" />

<img width="710" height="275" alt="Captura de tela 2026-10-05 190501" src="https://github.com/user-attachments/assets/a62617a6-1e4e-4e99-9b08-dad946750040" />


