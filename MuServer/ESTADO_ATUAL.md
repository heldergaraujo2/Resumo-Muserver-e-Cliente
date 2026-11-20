# Estado atual — MuServer
## Rodada 20/11/2026 — F12–17
Fonte: resumo do relatório Agent fornecido pelo usuário; não inspeção independente. Matriz v1.18: 21,50/58 = 37,07%, anterior 19,75/58 = 34,05%, +1,75 ponto (+3,02 p.p. arredondados). ECON-03 +0,25 equipamentos e +0,25 asas; GAME-03 +0,50; QUEST-01 +0,25; SOC-03 +0,50. Lua 12B.16 fechado segundo relato (2×305 s soak, morte externa sem perda/duplicação). F12 AOI, auth backpressure, shutdown SQLite, instrumentação; F13 equipamentos avançados e transferências; F14 asas/pets/montarias; F15 evolução/mastery/quests; F16 alianças, Siege, invasões; F17 E2E com restart. Bateria 23/23, ZeroLicense 109, builds sem erros/avisos; balanceamento relatado dentro das metas. Capacidade: 2.000 sintéticos, 5.000 saturou; 1.000 com latência 292–390 ms reportada, tick lag 3,2 s, cauda harness ~38 s; 500 p95 102,77 ms. Produção não validada. Cliente Season 6.20 não validado. Código ainda não commitado. Fila 12–17 encerrada, capacidade residual e funcionalidades parciais permanecem. Usuário reiterou 2.000 como meta suficiente; 5.000 não obrigatório. Análise: 9,2/10 subjetivo; preservar marco antes de ampliar. Próximo plano proposto F18–24: social/PvP, combos, quests, salas Lua/persistência eventos, rolls de itens, desempenho 2.000 e integração. Numeração nova proposta, não fase anterior. Resumo minimizado por visibilidade pública.

## Histórico anterior (superado quando divergente)
# Estado atual — MuServer
Referência 19/11/2026; dados relatados, sem inspeção independente nesta inicialização.
| Indicador | Valor |
|---|---|
| Matriz | v1.14 |
| Progresso | 34,05% (19,75/58), corrigido conforme relatório |
| Anterior | 34,05% (19,75/58) |
| Avanço | 0,00 p.p.; nenhum crédito novo |
| Fases | 12 baseline e 12B incremento 2 |
| Duração | 57m33s |
| Compatibilidade cliente original | Não validada; 0% no resumo |
| Agent | MiMo/OpenCode |

| Sistema | Situação relatada |
|---|---|
| Chaos Machine/joias | Parcial |
| Upgrade +0 a +9 | Implementado |
| Marketplace/rankings | Parcial |
| Leilões/VIP/loteria | Implementados |
| Excellent/Ancient/Harmony/Sockets | Pendentes |
| Asas/pets/montarias | Pendentes |
| Comércio de itens aprimorados | Pendente |

## Métricas p50 relatadas
XP 0,039 ms; atributos do protocolo 0,072 ms; persistência de vitais 0,952 ms; autenticação 34,8 ms (PBKDF2 120 mil iterações). Baseline sintético novo abaixo; capacidade de produção desconhecida.
## Balanceamento anterior
PvP 48,17–51,22% (meta 48–52%); PvE diferença 1,73% (meta até 3%). Fazer regressão direcionada com novos itens, sem repetir 2,8 milhões de duelos.
## Limitação
Diferença de 0,25 reconciliada pelo Agent; não inspecionada diretamente.

## Rodada 19/11 — F12 e 12B incremento 1
Fonte: relatório do Agent, não inspeção independente. Matriz corrigida: 19,75/58 = 34,05%; erro de soma de 0,25 na 10b; deltas 0,50+0,25+0,25+0,25=1,25. Sem crédito novo. F12 baseline e 12B incompletas.
Carga sintética (ativos; cmd/s; p95 ms; p99,9 ms): 50;20784;5,2;9,8 / 100;11139;12,4;809 / 250;12683;40,3;152 / 500;5273;128,6;10000 / 1000;6794;268,7;1400 / 2000;2556;1014;15900. 5000 falhou na conexão em massa. 2000 passou sem erros de protocolo, mas latências não aceitáveis para produção; soak pendente. Gargalos broadcast quadrático, escrita SQLite, autenticação em massa. Wakeup outbound corrigido.
Lua: processo isolado, Job Object, sandbox, allocator e hooks; fonte nominal 256 MB, maior script testado 100005 linhas/8178687 bytes/~320 ms, 32 workers paralelos, módulos require com ciclos/traversal rejeitados, watchdog compilação e diagnósticos. Seis cenários de falha isolados com servidor vivo. Limites lab 512 MB memória/execução, 120 s, 500 M instruções, profundidade 512, 8 dirs. Teto de fonte não validado. Zero eventos reais/timers; pool, quotas globais, API gameplay, hot reload, métricas, soak e evento extremo pendentes. Isolamento não elimina competição CPU/RAM.
Testes relatados: LuaSafety 20/20, LuaWorker 13/13, ServerRuntime 60/60, self-test e lab PASS, ZeroLicense 89, builds sem avisos. Combate inalterado; regressões de equipamento ainda necessárias. Checkpoints técnicos de capacidade e modernização Lua relatados. Duração 1h35m.

## Rodada 11 — 12B incremento 2 (19/11/2026)
Relatório Agent MiMo, duração 57m33s, 35 tok/s; não inspeção independente. Matriz 19,75/58 = 34,05%, delta zero: Lua não tem linha própria, 12B.16 incompleto, F12 apenas baseline. Sem alteração de cliente/originais; Season 6.20 não validada (0% relatado).
Entregas: quatro perfis fail-closed; pool slots fixos/fila limitada/backpressure/timeout, cota global RAM, hard cap CPU, quarantine/backoff, reciclagem/cancelamento, VM nova; API de gameplay allow-list/quotas/CAS, estado persistente schema v12; eventos reais, callbacks, timers, módulos, hot reload atômico/rollback, métricas. Teste LUA_EVENTS PASS: spawn, join, kill score 1, timer e fase modular, recompensa ouro +100 transacional, reload, 12 ticks, stop, restart preservou score. Saturação pool rejeitou 10/completou 2 com 1 worker; binário ausente testou quarantine/backoff, não crash externo. Testes direcionados 6/6 PASS; ZeroLicense 93, builds 0/0; Lua lab PASS. Limites anteriores de script 100005 linhas/8,18MB/~320ms mantidos, teto nominal 256MB não demonstrado. Não confundir 12 ticks com soak >=5 min.
Capacidade inalterada: 2000 ativos sintéticos, p95 1014 ms, p99,9 15,9s; 5000 saturou. AOI, fila SQLite, pool conexão não implementados. Fases 13–17 não iniciadas. Pendências Lua: crash externo com recuperação, soak >=5 min, multi-instância/sala, CPU/RAM por worker, eventos simultâneos, GC/política por script, evento extremo e fechamento 12B.16. Sessão ociosa não autenticada fecha ~6s, não mapeado. Checkpoint relatado docs/CHECKPOINT-20261119-LUA-EVENTS.md; rodada 11 em docs/CONTINUIDADE.md.

## Decisão de capacidade — 19/11/2026
Usuário autorizou manter 2.000 jogadores ativos simultâneos como meta principal caso 5.000 não sejam viáveis. 5.000 é objetivo opcional, não bloqueia fases 13–17. Priorizar estabilidade, integridade, soak e latência de gameplay. Objetivos de engenharia propostos: p95 <=100 ms e p99 <=250 ms, avaliar em carga alvo; não são resultados comprovados. Baseline de 2.000 sintéticos ainda apresenta p95 1.014 ms e p99,9 15,9 s; não declarar capacidade de produção antes de validar melhorias. Comando anterior já enviado pelo usuário, permanece inalterado; aplicar decisão no próximo retorno. Matriz permanece 19,75/58 = 34,05%.
