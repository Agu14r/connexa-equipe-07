# Sprint 1 — Registro de uso de IA

Durante o planejamento (Etapas 10 e 11), as Tasks foram propostas por um assistente de IA (Claude) a partir das histórias #24, #26 e #27, seguindo o prompt e o molde do Guia da Parte 2 (seções 5 e 6). Cada proposta foi conferida com o checklist de auditoria (seção 7 do guia) antes de ser gravada no board. A tabela abaixo registra o que foi aceito, modificado ou rejeitado.

> **A equipe precisa revisar esta tabela.** A auditoria é da equipe: confirmem ou alterem cada decisão e o motivo antes de abrir o pull request do planejamento.

## Decisões sobre propostas do agente

| Data | Work item | Proposta do agente (resumo) | Decisão | Motivo |
|---|---|---|---|---|
| 26/11/2026 | AB#24, AB#26, AB#27 | Meta "estudante informa disciplinas, vê os grupos e pede ingresso", com as histórias #24, #26 e #27 | Aceita | Sustenta uma meta observável sem depender de autenticação; #37, #38 e #39 são de identidade; a #25 não é necessária para a meta. |
| 26/11/2026 | AB#41–AB#55 | Esqueleto com `[ESP]`, `[BE]`, `[FE]`, `[VER]` e `[REV]` por história, cada `[BE]` cobrindo todos os cenários da sua história | Aceita | Cada `[BE]` entrega comportamento verificável de ponta a ponta na API; nenhuma Task é por camada técnica ("criar entidade", "criar tabela"). A persistência fica dentro da `[BE]` que precisa dela. |
| 26/11/2026 | AB#52 | Dividir a `[BE]` da #27 em duas (solicitar / cancelar) | Rejeitada | Cada parte ficaria abaixo de 2h no mesmo módulo e com os mesmos dados de exemplo. Uma Task de 4h com 3 cenários continua dentro do limite de 8h. |
| 26/11/2026 | AB#51, AB#52, AB#53 | Cenários da #27 dependem da disponibilidade declarada na #25 (fora da sprint) → usar disponibilidade semeada para o estudante simulado | Aceita | Mantém os três cenários verificáveis sem puxar a #25 para a sprint. Registrado em comentário na história #27. |
| 26/11/2026 | AB#42, AB#43 | Cenário "Remover uma disciplina já cursada" inclui "deixo de receber sugestões" (#29) | Modificada | A Task verifica só a remoção no perfil; a parte de sugestões fica explícita em "Fora de escopo" e no comentário da #24. |
| 26/11/2026 | AB#48 | Opção "criar um grupo" no cenário de disciplina sem grupos | Modificada | A opção aparece na tela, mas pode ficar desabilitada com aviso, porque o fluxo de criação é a #28. |
| 26/11/2026 | AB#43, AB#48, AB#53 | Verificação das `[FE]` só com os estados de sucesso, erro e vazio | Modificada | Acrescentados os critérios aplicáveis da #40 (operação só por teclado, rótulo em cada campo, `aria-live` para mudança de status), já que a #40 não entrou como história. |
| 26/11/2026 | AB#41–AB#55 | Primeira versão das descrições com seções extras do roteiro (Contrato, módulos que podem ser alterados e comando de verificação) | Modificada | O guia da Parte 2 pede só Objetivo, História e cenários, O que entregar, Como verificar e Fora de escopo, com comportamento e sem detalhes de código. As descrições foram reescritas nesse molde. |
| 26/11/2026 | AB#41–AB#55 | Tasks sem Activity e capacidade sem atividade | Modificada | O guia exige Activity: Design (`[ESP]`), Development (`[BE]`, `[FE]`) e Testing (`[VER]`, `[REV]`). A capacidade foi dividida por atividade (Maria: Design 0,3 + Development 0,3; Vinicius e João: Development 0,6; Jefferson: Testing 0,6) para nenhuma barra passar do limite. |

## Falhas do agente

| Work item | Tentativas | Causa (A–E) | O que mudou na Task |
|---|---|---|---|
| | | | |
