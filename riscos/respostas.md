# Estratégias de Resposta aos Riscos

Foco nos riscos de exposição **Crítica** e **Alta** identificados na análise (R1, R2, R3, R5, R8), com R4, R6 e R7 tratados de forma complementar.

## R1 — Falha na integração com o prontuário externo (Crítica)
**Estratégia:** Mitigar
**Justificativa:** A integração é crítica para a entrega e não pode ser eliminada (evitar) nem transferida integralmente, já que o fornecedor é externo e não controlável. Mitigar reduz probabilidade e impacto a um nível gerenciável.
**Ações associadas:**
- Solicitar formalmente ao fornecedor documentação de API atualizada e um canal técnico direto de suporte.
- Implementar camada de abstração (adapter) entre o app e a API externa, isolando o impacto de mudanças futuras.
- Criar ambiente de testes de contrato (contract testing) para detectar mudanças da API antes de afetar produção.
- Definir modo degradado (ex.: agendamento sem sincronização automática de prontuário) como contingência temporária.

## R2 — Mudança de escopo no fluxo de agendamento (Alta)
**Estratégia:** Mitigar
**Justificativa:** Não é possível evitar mudanças solicitadas por stakeholders, mas é possível controlar seu impacto por meio de um processo estruturado de gestão de mudanças.
**Ações associadas:**
- Instituir processo formal de change request, com avaliação de impacto em prazo/custo antes da aprovação.
- Consolidar as novas regras de negócio em um backlog priorizado, negociando quais entram no escopo atual e quais ficam para uma fase 2.
- Validar protótipos das novas regras com stakeholders antes da implementação, reduzindo retrabalho.

## R3 — Sobrecarga da equipe / atraso no cronograma (Crítica)
**Estratégia:** Mitigar
**Justificativa:** O risco não pode ser evitado sem cortar escopo, mas pode ser reduzido ajustando prazo, escopo ou capacidade da equipe de forma proativa.
**Ações associadas:**
- Revisar e repriorizar o cronograma com base no impacto real de R1 e R2.
- Negociar com stakeholders prazos realistas ou entrega em fases (MVP primeiro, funcionalidades secundárias depois).
- Avaliar reforço temporário de equipe (freelancer ou realocação interna) para os módulos mais críticos.
- Monitorar carga de trabalho semanalmente para antecipar sinais de sobrecarga.

## R5 — Dependência crítica de fornecedor externo (Alta)
**Estratégia:** Transferir (parcialmente) + Mitigar
**Justificativa:** Parte do risco pode ser transferida via contrato formal de SLA com o fornecedor; a parte que não pode ser transferida (indisponibilidade técnica) é mitigada com contingência interna.
**Ações associadas:**
- Formalizar SLA com o fornecedor, incluindo prazos de aviso prévio para mudanças na API.
- Mapear fornecedores/APIs alternativas como plano B de longo prazo.
- Manter comunicação periódica com o time técnico do fornecedor.

## R8 — Rotatividade/burnout da equipe (Alta)
**Estratégia:** Mitigar
**Justificativa:** Risco de origem interna e gerenciável diretamente pela liderança do projeto, agindo sobre suas causas (R3).
**Ações associadas:**
- Ajustar prazos/escopo (ligado às ações de R3) para reduzir sobrecarga sustentada.
- Realizar check-ins individuais periódicos para identificar sinais de esgotamento.
- Redistribuir tarefas críticas para evitar dependência de uma única pessoa.

## R4 — Gargalo de qualidade (1 tester) (Moderada)
**Estratégia:** Mitigar
**Justificativa:** Impacto relevante em um recurso escasso; investimento em automação reduz a dependência de um único profissional.
**Ações associadas:**
- Priorizar automação de testes de regressão nos fluxos críticos (agendamento, integração).
- Envolver desenvolvedores em testes unitários, reduzindo a carga exclusiva do tester.

## R6 — Desalinhamento com stakeholders (Moderada)
**Estratégia:** Mitigar
**Justificativa:** Risco de comunicação, plenamente controlável com um processo de reporte estruturado (ver Etapa 4).
**Ações associadas:**
- Estabelecer cadência fixa de comunicação de status (ex.: quinzenal).
- Padronizar relatório de status com linguagem acessível a público não técnico.

## R7 — Exposição de dados sensíveis / LGPD (Moderada, impacto alto)
**Estratégia:** Mitigar
**Justificativa:** Baixa probabilidade não elimina a necessidade de tratamento, dado o alto impacto legal e reputacional de um incidente com dados de saúde.
**Ações associadas:**
- Revisar tratamento de erros e logs para garantir mascaramento de dados sensíveis.
- Incluir casos de teste específicos de segurança e conformidade com LGPD no plano de testes.
- Realizar revisão de conformidade antes do lançamento da integração em produção.
