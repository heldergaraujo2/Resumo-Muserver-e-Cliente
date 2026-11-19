# MuServer — continuidade
Atualização inicial: 19/11/2026. Fonte: resumo apresentado pelo usuário da conversa anterior e contexto histórico parcial. Nenhuma inspeção independente do código foi feita nesta inicialização.

## Objetivo
Reconstrução independente e completa do servidor MU Online, com código próprio, gameplay, rede, persistência, eventos, administração, segurança, desempenho, manutenção e compatibilidade com cliente-alvo. Originais preservados como referência autorizada.
## Estratégia
OpenCode/Agent MiMo; REA para análise autorizada; SQLite operacional segundo relato. docs/ESTADO.md, docs/CONTINUIDADE.md e checkpoints locais sustentam recuperação. Caminhos e identificadores privados omitidos por visibilidade pública.
## Estado atual relatado
Matriz corrigida: 19,75/58 = 34,05% conforme relatório. Fase 9: 18,50/58 = 31,90%. Erro de soma da 10b corrigido. F12 baseline e 12B incremento 1 sem crédito novo.
Chaos Machine e joias parciais, upgrade +0 a +9, marketplace parcial, leilões, VIP, loteria, rankings parciais. Transações, retenção de valores, prevenção de duplicação e persistência relatadas, integração parcial com combate. Sistemas anteriores de conexão, autenticação, dados, personagens, movimentação, combate, inventário, lojas, party/guild e eventos clássicos relatados; completude e integração não comprovadas.
## Próximas fases
12 baseline entregue, otimização/soak pendentes; concluir 12B Lua incremento 2; 13 equipamentos avançados e transferências; 14 asas/pets/montarias; 15 evolução de personagens; 16 gameplay avançado; 17 integração/desempenho. Lua robusto é prioridade transversal. Compatibilidade real com cliente ainda não validada.
## Retomada
Ler ESTADO_ATUAL, PROGRESSO, DECISOES, PENDENCIAS, ULTIMO_COMANDO e historico/README.md. Consultar saída mais recente do Agent quando disponível. Não repetir auditorias/suítes sem motivo.

## Rodada 19/11 — F12 e 12B incremento 1
Fonte: relatório do Agent, não inspeção independente. Matriz corrigida: 19,75/58 = 34,05%; erro de soma de 0,25 na 10b; deltas 0,50+0,25+0,25+0,25=1,25. Sem crédito novo. F12 baseline e 12B incompletas.
Carga sintética (ativos; cmd/s; p95 ms; p99,9 ms): 50;20784;5,2;9,8 / 100;11139;12,4;809 / 250;12683;40,3;152 / 500;5273;128,6;10000 / 1000;6794;268,7;1400 / 2000;2556;1014;15900. 5000 falhou na conexão em massa. 2000 passou sem erros de protocolo, mas latências não aceitáveis para produção; soak pendente. Gargalos broadcast quadrático, escrita SQLite, autenticação em massa. Wakeup outbound corrigido.
Lua: processo isolado, Job Object, sandbox, allocator e hooks; fonte nominal 256 MB, maior script testado 100005 linhas/8178687 bytes/~320 ms, 32 workers paralelos, módulos require com ciclos/traversal rejeitados, watchdog compilação e diagnósticos. Seis cenários de falha isolados com servidor vivo. Limites lab 512 MB memória/execução, 120 s, 500 M instruções, profundidade 512, 8 dirs. Teto de fonte não validado. Zero eventos reais/timers; pool, quotas globais, API gameplay, hot reload, métricas, soak e evento extremo pendentes. Isolamento não elimina competição CPU/RAM.
Testes relatados: LuaSafety 20/20, LuaWorker 13/13, ServerRuntime 60/60, self-test e lab PASS, ZeroLicense 89, builds sem avisos. Combate inalterado; regressões de equipamento ainda necessárias. Checkpoints técnicos de capacidade e modernização Lua relatados. Duração 1h35m.
