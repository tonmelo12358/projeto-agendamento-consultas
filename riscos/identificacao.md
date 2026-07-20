# Identificação de Riscos

**Projeto:** Aplicativo móvel de agendamento de consultas médicas
**Responsável:** Gerente de Projetos
**Data:** 19/07/2026

## Contexto

O projeto está em fase intermediária de desenvolvimento. Parte das funcionalidades (cadastro de usuários, gestão de agenda médica) já foi implementada; outras (agendamento, notificações, integração com prontuário externo) seguem em progresso. A equipe é composta por 4 desenvolvedores e 1 tester. A integração com o sistema externo de prontuário é crítica para a entrega.

Esta lista foi construída com apoio de um LLM, usado para explorar sistematicamente categorias de risco (técnico, requisitos, equipe/recursos, fornecedor externo, comunicação, qualidade e conformidade) a partir da descrição do cenário, e depois validada e ajustada pelo gerente de projetos ao contexto real do produto.

## Lista de Riscos

### R1 — Falha ou atraso na integração com o sistema de prontuário externo
**Descrição:** A API do sistema externo carece de documentação clara e sofreu mudanças recentes, causando instabilidade na integração já em desenvolvimento.
**Contexto de ocorrência:** Durante os testes de integração e em produção, sempre que o fornecedor externo alterar endpoints, contratos de dados ou políticas de autenticação sem aviso prévio adequado.

### R2 — Mudança de escopo por novas regras de negócio no fluxo de agendamento
**Descrição:** Stakeholders solicitaram alterações nos requisitos do fluxo de agendamento, incluindo novas validações e regras de negócio não previstas no planejamento original.
**Contexto de ocorrência:** Em qualquer momento do ciclo de desenvolvimento em que novas necessidades de negócio surgirem, especialmente quando não há um processo formal de controle de mudanças (change control).

### R3 — Sobrecarga da equipe de desenvolvimento e atraso no cronograma
**Descrição:** O aumento do volume de trabalho (retrabalho de integração + novos requisitos) pressiona uma equipe pequena (4 desenvolvedores), gerando risco de não cumprimento dos prazos estimados.
**Contexto de ocorrência:** Quando múltiplas frentes (correção da integração, novas regras de negócio, funcionalidades pendentes) competem pela mesma capacidade de equipe simultaneamente.

### R4 — Gargalo de qualidade por dependência de um único tester
**Descrição:** Com apenas 1 tester para toda a equipe, o aumento de escopo e de correções eleva o risco de testes superficiais ou atrasados, permitindo que defeitos cheguem a produção.
**Contexto de ocorrência:** Em períodos de pico, próximos a entregas, quando novas funcionalidades e correções de integração chegam para teste ao mesmo tempo.

### R5 — Dependência crítica de fornecedor externo (sistema de prontuário)
**Descrição:** Por ser uma integração crítica para a entrega, qualquer indisponibilidade, mudança de contrato comercial ou descontinuação de recursos da API externa impacta diretamente o cronograma do projeto.
**Contexto de ocorrência:** Fora do controle direto da equipe interna; ocorre quando o fornecedor prioriza sua própria evolução técnica sem considerar dependentes externos.

### R6 — Desalinhamento de expectativas com stakeholders
**Descrição:** Mudanças de requisito e atrasos, se não comunicados de forma clara e tempestiva, podem gerar percepção de descontrole do projeto e perda de confiança dos stakeholders.
**Contexto de ocorrência:** Quando a comunicação de status é reativa (apenas quando cobrada) em vez de proativa, ou quando o vocabulário técnico dificulta o entendimento por público não técnico.

### R7 — Exposição de dados sensíveis de saúde (conformidade com LGPD)
**Descrição:** O aplicativo trata dados de saúde de pacientes (categoria sensível conforme a LGPD) integrados a um sistema externo de prontuário; falhas na integração ou nas validações podem gerar exposição indevida de dados.
**Contexto de ocorrência:** Em cenários de instabilidade da integração, tratamento de erros mal implementado, ou logs que armazenem dados sensíveis sem mascaramento.

### R8 — Rotatividade ou esgotamento da equipe (burnout)
**Descrição:** A sobrecarga sustentada de uma equipe pequena, sem ajuste de prazos ou de escopo, aumenta o risco de queda de produtividade, erros e, no limite, saída de membros-chave da equipe.
**Contexto de ocorrência:** Quando picos de sobrecarga se tornam contínuos ao longo de várias semanas sem alívio de escopo, prazo ou reforço de equipe.
