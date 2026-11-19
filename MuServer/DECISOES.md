# Decisões — MuServer
- 19/11/2026: manter 34,48% provisórios, conferir divergência de 0,25 ponto.
- Priorizar implementação e regressões direcionadas; suíte integral em marcos.
- Priorizar capacidade e equipamentos avançados, depois asas/pets, progressão, gameplay avançado e integração.
- Robustecer Lua para eventos/scripts grandes sem derrubar GameServer; não apenas aumentar tamanho permitido.
- Manter continuidade técnica local e memória de gestão versionada neste repositório.
- Não presumir compatibilidade cliente; distinguir relato de inspeção.

- 19/11/2026: substituir referência provisória por 34,05% conforme correção relatada; F12 e 12B sem crédito. Priorizar Lua motor de eventos e quotas globais, AOI/persistência/autenticação limitada, regressões de capacidade comparáveis. 2000 ativos sintéticos não significam capacidade de produção. Meta proposta de gameplay a avaliar: p95 <=100 ms, p99 <=250 ms a 1000 ativos; sem redução da segurança de login.

- Rodada 11: nota 9/10 baseada no relato; manter matriz de 58 itens, indicadores separados para Lua/capacidade/cliente. Fechar 12B.16 com incremento 3 de escopo limitado; refinamentos não bloqueantes no backlog. Priorizar F12 e gameplay 13–17 sem pausas artificiais. Metas de latência propostas, não comprovadas.

## Decisão de capacidade — 19/11/2026
Usuário autorizou manter 2.000 jogadores ativos simultâneos como meta principal caso 5.000 não sejam viáveis. 5.000 é objetivo opcional, não bloqueia fases 13–17. Priorizar estabilidade, integridade, soak e latência de gameplay. Objetivos de engenharia propostos: p95 <=100 ms e p99 <=250 ms, avaliar em carga alvo; não são resultados comprovados. Baseline de 2.000 sintéticos ainda apresenta p95 1.014 ms e p99,9 15,9 s; não declarar capacidade de produção antes de validar melhorias. Comando anterior já enviado pelo usuário, permanece inalterado; aplicar decisão no próximo retorno. Matriz permanece 19,75/58 = 34,05%.
