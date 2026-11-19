# Protocolo de memória externa
## Recuperação
Ler README, REGRAS_GERAIS, CONTINUIDADE, ESTADO_ATUAL, PROGRESSO, PENDENCIAS, DECISOES, ULTIMO_COMANDO e índice de histórico do projeto identificado. Abrir registros adicionais somente quando necessários. Reconciliar com evidência nova do Agent quando mais recente; não reiniciar trabalho já comprovado.
## Após cada interação técnica relevante
1. Identificar projeto, data, fonte, fase e checkpoint. Preservar saída original autorizada; caso seja pública ou haja material sensível, registrar resumo técnico fiel e indicar omissões. Se a entrada for análise anterior, não rotular como relatório bruto.
2. Analisar entregas, evidências, problemas, regressões, percentual e próximos passos. Em caso de divergência, manter valor provisório e explicar.
3. Preparar comando completo e copiável quando solicitado. Registrar o texto exato realmente entregue; se não houver, declarar pendente.
4. Criar entrada cronológica imutável em historico/AAAA-MM-DD-NNN.md conforme MODELO_REGISTRO.md; conferir sequência disponível e atualizar índice. Relatórios, análises e comandos grandes podem ser armazenados separadamente quando privacidade permitir.
5. Atualizar arquivos consolidados afetados. Nunca apagar decisões antigas; registrar correções e justificativas.
6. Preferir um commit atômico por ciclo. Ler HEAD atual, preservar árvore, não usar force push; em conflito, reler e reconciliar.
7. Confirmar commit e arquivos publicados, informar SHA/link e falhas. Sem acesso, entregar conteúdo e declarar não sincronizado.
## Privacidade
Confira visibilidade antes de qualquer escrita. Em público, somente resumos técnicos minimizados. Em privado, ainda remover credenciais, dados pessoais e material sem autorização. Não registrar raciocínio interno privado do modelo. Esta estratégia depende de uma interação e acesso ao GitHub; não exporta chats em segundo plano.
