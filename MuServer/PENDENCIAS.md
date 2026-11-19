# Pendências — MuServer
| Prioridade | Tarefa | Aceitação |
|---|---|---|
| Crítica | Compatibilidade cliente-alvo | Sessão real e contratos de protocolo com evidência |
| Alta | Fase 12 capacidade/concorrência | Carga progressiva, CPU/RAM, p50/p95/p99, erros e estabilidade |
| Alta | Fase 13 Excellent/Ancient/Harmony/Sockets | Persistência, transferências transacionais, prevenção de duplicação e combate integrado |
| Alta | Lua robusto | Scripts grandes, falhas contidas, limites configuráveis, recuperação e estresse |
| Alta | Balanceamento | Regressões das sete classes com equipamento equivalente |
| Alta | Fase 14 asas/pets/montarias | Efeitos, evolução e integração |
| Alta | Fase 15 evolução | Classes, Master Skill Tree, progressão e quests |
| Alta | Fase 16 gameplay avançado | Castle Siege, invasões, bosses, eventos, guildas e alianças |
| Alta | Fase 17 integração | Sistemas combinados, comparação baseline e regressão de marco |
| Resolvida segundo relato | Matriz | Correção 19,75/58; não reaplicar |

## Lua — requisitos a avaliar
Execução protegida, quotas configuráveis de memória/tempo/instruções, watchdog/cancelamento, isolamento de falhas, proteção de chamadas nativas, evitar bloqueio do tick, módulos e scripts grandes, agendamento concorrente controlado, hot reload transacional/rollback, logs e stack traces. Avaliar worker/processo isolado; pcall não contém crash nativo. Testar sintaxe inválida, loops infinitos, OOM controlado, recursão, concorrência, arquivos grandes, recuperação. Definir metas quantitativas com baseline, sem prometer limites inventados.

## Prioridade atual
12B incremento 2 entregou perfis, pool, quotas globais, timers, API gameplay, hot reload e métricas. Fechar 12B.16: crash externo, soak >=5 min, multi-instância/sala, CPU/RAM por worker, limite de eventos, GC, evento extremo, autorização e idempotência. F12 AOI, SQLite, autenticação limitada, retestes/soak. Depois 13–17. Investigar fechamento ocioso ~6s quando relevante. Não repetir entregas já aprovadas sem mudança.
