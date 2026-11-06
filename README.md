# contas-dados

Rotinas que atualizam os dados do site [Contas Públicas](https://www.contaspublicasbrasil.com.br).

Cada rotina em `.github/workflows` busca dados públicos oficiais (Tesouro Nacional, TSE, Câmara, Senado, PNCP, INEP, Portal da Transparência),
roda os scripts do site e grava o resultado no repositório do site. Este repositório não guarda dados nem código do site:
só os agendamentos. A chave de acesso ao repositório do site fica no segredo `SITE_TOKEN`.

| Rotina | Quando roda (horário de Brasília) |
|---|---|
| `dados.yml` (gastos, votações, emendas) | todo dia, 06:17 |
| `contratos.yml` (PNCP) | todo dia, 06:13 |
| `arrecadacao.yml` (SICONFI, rankings) | a cada 6 horas |
| `federal.yml` (cartão corporativo e viagens) | segundas, 07:53 |
| `municipais.yml` (eleitos em 2024) | dia 3 de cada mês |
| `ideb.yml` (INEP) | dia 5 de cada mês |
| `campanhas.yml` (prestação de contas no TSE) | dia 7 de cada mês |

Para rodar fora de hora: aba Actions, escolha a rotina, "Run workflow".
