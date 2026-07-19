# Análise Qualitativa de Riscos

Escala utilizada — **Probabilidade:** Baixa / Média / Alta. **Impacto:** Baixo / Médio / Alto (considerando prazo, custo, escopo e qualidade). **Exposição** (P × I): Baixa, Moderada, Alta ou Crítica — usada para priorizar riscos na Etapa 3.

| ID | Risco | Probabilidade | Impacto | Exposição |
|----|-------|:---:|:---:|:---:|
| R1 | Falha na integração com prontuário externo | Alta | Alto | **Crítica** |
| R2 | Mudança de escopo no fluxo de agendamento | Alta | Médio | **Alta** |
| R3 | Sobrecarga da equipe / atraso no cronograma | Alta | Alto | **Crítica** |
| R4 | Gargalo de qualidade (1 tester) | Média | Médio | Moderada |
| R5 | Dependência crítica de fornecedor externo | Média | Alto | **Alta** |
| R6 | Desalinhamento com stakeholders | Média | Médio | Moderada |
| R7 | Exposição de dados sensíveis (LGPD) | Baixa | Alto | Moderada |
| R8 | Rotatividade/burnout da equipe | Média | Alto | **Alta** |

## Análise detalhada

### R1 — Falha na integração com o prontuário externo
**Impacto:** Compromete diretamente a entrega, já que a integração é crítica para o projeto; pode atrasar o cronograma geral, gerar retrabalho técnico e comprometer a confiabilidade de dados clínicos apresentados no app.
**Fatores condicionantes:** ausência de documentação de API atualizada; mudanças unilaterais do fornecedor externo; falta de ambiente de homologação estável para testes de integração; dependência de um único ponto de integração sem contingência.

### R2 — Mudança de escopo no fluxo de agendamento
**Impacto:** Retrabalho em funcionalidades já desenvolvidas, aumento do esforço estimado e risco de novos atrasos em cascata sobre outras entregas.
**Fatores condicionantes:** ausência de um processo formal de gestão de mudanças; requisitos iniciais pouco detalhados; comunicação direta de stakeholders com a equipe sem passar por triagem do PM.

### R3 — Sobrecarga da equipe / atraso no cronograma
**Impacto:** Redução da qualidade das entregas, aumento de erros, atraso nos prazos contratuais e possível necessidade de renegociação de escopo ou data de entrega com stakeholders.
**Fatores condicionantes:** equipe pequena (4 devs) sem folga de capacidade; acúmulo simultâneo do retrabalho de integração (R1) com novos requisitos (R2); ausência de repriorização formal do backlog.

### R4 — Gargalo de qualidade (1 tester)
**Impacto:** Testes incompletos podem deixar passar defeitos para produção, especialmente em fluxos críticos como agendamento e integração com prontuário, aumentando risco reputacional e de retrabalho pós-entrega.
**Fatores condicionantes:** aumento do volume de itens para testar sem aumento proporcional de capacidade de teste; ausência de automação de testes; pressão de prazo reduzindo tempo dedicado a testes exploratórios.

### R5 — Dependência crítica de fornecedor externo
**Impacto:** Qualquer instabilidade, descontinuação de endpoint ou mudança de política de acesso do sistema externo pode bloquear uma funcionalidade essencial do produto, fora do controle direto da equipe.
**Fatores condicionantes:** ausência de contrato de nível de serviço (SLA) claro com o fornecedor; falta de canal direto de suporte técnico; inexistência de plano de contingência (ex.: modo degradado sem integração).

### R6 — Desalinhamento com stakeholders
**Impacto:** Perda de confiança na condução do projeto, decisões tomadas com base em expectativas desatualizadas, e maior resistência a negociações futuras de prazo ou escopo.
**Fatores condicionantes:** comunicação pouco frequente ou excessivamente técnica; ausência de reportes estruturados de status; múltiplos riscos (R1, R2, R3) ocorrendo ao mesmo tempo sem uma narrativa consolidada.

### R7 — Exposição de dados sensíveis (LGPD)
**Impacto:** Dados de saúde são categoria sensível; uma exposição gera risco legal, multas e dano reputacional severo, mesmo com baixa probabilidade de ocorrência.
**Fatores condicionantes:** tratamento de erros e logs mal configurados durante a instabilidade da integração (R1); ausência de mascaramento de dados sensíveis; testes de segurança insuficientes por sobrecarga do tester (R4).

### R8 — Rotatividade/burnout da equipe
**Impacto:** Perda de conhecimento técnico acumulado, necessidade de onboarding de novos membros em meio ao projeto, e agravamento adicional do atraso já existente.
**Fatores condicionantes:** sobrecarga sustentada (R3) sem ajuste de escopo ou prazo; ausência de reconhecimento ou suporte da liderança; falta de rotação ou redistribuição de tarefas.

## Observações sobre fatores condicionantes comuns

Os riscos R1, R2 e R3 estão interligados: a instabilidade técnica da integração (R1) consome capacidade da equipe, que é a mesma capacidade demandada pelas mudanças de escopo (R2), gerando o risco de cronograma (R3). Esse efeito cascata amplia a exposição de R4, R6 e R8, reforçando a importância de tratar R1, R2 e R3 como prioridade imediata.
