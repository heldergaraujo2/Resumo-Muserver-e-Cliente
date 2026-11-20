# Último comando — MuServer
20/11/2026 — entregue ao usuário nesta resposta. Resumo técnico minimizado do comando, pois repositório público; não é transcrição integral.

MISSÃO — Expansão funcional F18–F24. Recuperar estado, continuidade, matriz v1.18 e checkpoints F12–17. Base 21,50/58=37,07%, anterior 34,05%, +1,75 ponto; Lua fechado segundo relato; 2.000 ativos como meta, 5.000 não obrigatório; cliente não validado.

0. Preservar alterações, verificar status/diff/branch, consolidar checkpoint e commit autorizado, informar SHA, sem incluir segredos ou material proprietário, sem testes redundantes.
F18: Gens, Guild War, Arena PvP; participação, regras, pontuação, classificação, recompensas, autorização, persistência, recuperação, exploits, desconexão e concorrência; integrar guildas, alianças, itens e combate; avaliar SOC-03.
F19: combos e CustomCombo, sequências, janelas, validação server-side, cooldowns e antiabuso; equilíbrio das sete classes, equipamentos equivalentes; avaliar GAME-03.
F20: quests ramificadas, múltiplos pré-requisitos, objetivos, progressão persistente, recompensas transacionais, anti-duplicação e integração NPC/eventos/combate.
F21: persistir e recuperar fases Siege/invasões; salas e instâncias Lua com isolamento, timers, estado, recompensas, limites e encerramento; reutilizar runtime aprovado.
F22: rolls persistentes por instância, integração com geração, upgrade, fusion, inventário, equipamento, comércio, leilão, armazenamento e combate; identidade, atomicidade, migrações, anti-duplicação.
F23: otimizar 2.000 ativos, não tentar 5.000; investigar fan-out, tick lag 3,2 s, cauda harness ~38 s, latência a 1.000, filas, contenção, alocações, persistência. Separar harness de servidor; agrupar quando seguro; preservar visibilidade, ordenação, segurança, durabilidade e PBKDF2. Testes comparáveis 250/500/1000/2000, p50/p95/p99/p99.9, tick lag, TPS, CPU/RAM, filas, erros, desconexões e duração. Metas p95<=100 ms e p99<=250 ms; soak >=30 min a 2.000 se seguro. Não declarar produção por PASS sintético. Registrar gargalos e não bloquear demais sistemas indefinidamente.
F24: integração equipamentos, combate, economia, progressão, quests, PvP, Lua, restart e persistência. Regressões direcionadas; suíte integral no marco. PvP 48–52%, PvE diferença <=3%; cliente real permanece não validado.
Regras: avançar sem pausas artificiais, corrigir riscos de integridade, sem retrabalho, documentação não pontua, matriz 58 pontos sem duplicar créditos, originais e cliente intocados, checkpoints e continuidade atualizados, licenciamento respeitado. Relatório com cálculo, deltas, entregas, testes, regressões, capacidade, pendências, checkpoints e commits; indicadores Lua/capacidade/cliente separados. Parar apenas por bloqueio real, risco ou limite.
