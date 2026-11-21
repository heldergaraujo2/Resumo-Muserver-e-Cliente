# Pendências atuais — 21/11/2026
Primeiro teste real local cliente Season 6.20 ↔ MuServer: inicialização, handshake, login, personagens, Lorencia, movimento, combate, inventário, persistência. Compatibilidade ainda não comprovada. Meta operacional 2.000: SLO de latência não atingido (p95 502,9 ms em 2.000); OPS-04 sem crédito. Revalidar código/commit informado; preservar originais e não exigir PS GameGuard comercial no servidor independente. F18–F24 concluídas segundo relato, sem nova pontuação F21–24.

## Histórico anterior (não representa pendências atuais quando superado)
# Pendências atuais — MuServer
Gens/guild-war/arena, combos, quests ramificadas, salas Lua, persistência de fases Siege/invasões, rolls por instância, capacidade 2.000 com SLO/soak, integração cliente, commit do código. Lua 12B.16 fechado segundo relato; F13–17 entregues no escopo relatado, não repetir. 5.000 não obrigatório.

## Histórico anterior (reconciliado acima)
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

## Decisão de capacidade — 19/11/2026
Usuário autorizou manter 2.000 jogadores ativos simultâneos como meta principal caso 5.000 não sejam viáveis. 5.000 é objetivo opcional, não bloqueia fases 13–17. Priorizar estabilidade, integridade, soak e latência de gameplay. Objetivos de engenharia propostos: p95 <=100 ms e p99 <=250 ms, avaliar em carga alvo; não são resultados comprovados. Baseline de 2.000 sintéticos ainda apresenta p95 1.014 ms e p99,9 15,9 s; não declarar capacidade de produção antes de validar melhorias. Comando anterior já enviado pelo usuário, permanece inalterado; aplicar decisão no próximo retorno. Matriz permanece 19,75/58 = 34,05%.
