# Estado atual — MuServer
Referência 19/11/2026; dados relatados, sem inspeção independente nesta inicialização.
| Indicador | Valor |
|---|---|
| Matriz | v1.14 |
| Progresso | 34,05% (19,75/58), corrigido conforme relatório |
| Anterior | 34,48% (20/58), incorreto |
| Avanço | -0,43 p.p. correção; nenhum crédito novo |
| Fases | 12 baseline e 12B incremento 1 |
| Duração | 1h35m |
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
