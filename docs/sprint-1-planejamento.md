# Sprint 1 — Planejamento

**Projeto:** Connexa · **Equipe:** Conexxa Team · **Sprint:** 26/11/2026 a 16/12/2026 (3 semanas, 15 dias úteis, segunda a sexta)
**Board:** https://dev.azure.com/SportClubCorinthiansPaulista/Conexxa/_sprints/taskboard/Conexxa%20Team/Conexxa/Sprint%201

---

## 1. Meta da sprint

> **Ao final desta sprint, um estudante consegue informar as disciplinas que está cursando, ver os grupos de estudo que já existem em cada uma delas e pedir para entrar em um grupo.**

- **Papel:** estudante (o estudante simulado pelo template, sem autenticação real).
- **Resultado observável:** alguém de fora da equipe abre a aplicação, marca "Algoritmos" no perfil, vê a lista de grupos de "Algoritmos" e envia uma solicitação que aparece como "Pendente".

---

## 2. Conta da capacidade

Cada integrante declarou **6 h por semana** de esforço humano no projeto.

```
Horas declaradas por integrante, por semana ...... 6h
Integrantes ..................................... 4
Semanas da sprint ............................... 3
------
Capacidade bruta ................................ 72h

( - ) reserva para imprevistos, provas e retrabalho (20%) .... 14,4h
( - ) reuniões da equipe (2h por semana) ..................... 6h
------
Capacidade de planejamento ...................... 51,6h
Alvo da primeira sprint (75%) ................... 38,7h → 38h
```

**Registro no Azure (aba Capacity):** 38h ÷ 4 integrantes ÷ 15 dias úteis = 0,63 h/dia, **arredondado para baixo: 0,6 h/dia** por integrante, ou seja, 9h por pessoa e **36h para a equipe**. Nenhuma ausência conhecida no período.

> A sprint tem **três semanas**, como pede o post da atividade. O guia e a apresentação usam o exemplo de duas semanas.

| Integrante | Horas/semana | Activity e horas/dia no Azure | Horas na sprint | Planejado | Caminho de IA |
|---|---|---|---|---|---|
| Maria Eduarda Aguiar Duarte | 6h | Design 0,3 + Development 0,3 | 9h | 8h | _(preencher)_ |
| Jefferson da Silva Marques Braga | 6h | Testing 0,6 | 9h | 5h | _(preencher)_ |
| João Pedro Batista Fernandes de Carvalho | 6h | Development 0,6 | 9h | 8h | _(preencher)_ |
| Vinicius Vieira Ribeiro Gonçalves | 6h | Development 0,6 | 9h | 8h | _(preencher)_ |
| **Equipe** | | | **36h** | **29h** | |

A Activity de cada integrante foi escolhida para que a capacidade por tipo de trabalho cubra o plano: Design 4,5h para 4h de `[ESP]`; Development 22,5h para 19h de `[BE]` e `[FE]`; Testing 9h para 6h de `[VER]` e `[REV]`.

O Prof. Claudio Nunes faz parte do time no Azure, mas não entra na conta (capacidade 0).

---

## 3. Justificativa da seleção

O backlog foi percorrido do topo para baixo, perguntando se cada história sustenta a meta.

| Ordem | História | Decisão | Motivo |
|---|---|---|---|
| 1 | #37 Cadastrar-se com e-mail institucional | **Pulada** | Território de identidade: fora da Sprint 1 pela regra do roteiro (o template simula um estudante autenticado). |
| 2 | #38 Comprovar o endereço institucional | **Pulada** | Território de identidade. |
| 3 | #40 Garantir acessibilidade nas telas principais | **Pulada como história** | Requisito transversal que inclui a tela de cadastro (identidade). Os critérios que valem para as telas desta sprint (operação só por teclado, rótulos nos campos, anúncio de mudança de status) entraram na verificação de cada `[FE]`. |
| 4 | **#24 Declarar disciplinas cursadas** | **Selecionada** | Primeira parte da meta: sem disciplinas no perfil não há em que disciplina procurar grupo. |
| 5 | #25 Declarar horários de disponibilidade | **Não selecionada** | Não é necessária para a meta (ver e pedir ingresso). Entraria como 4ª história, mas a soma passaria do alvo. A disponibilidade do estudante simulado vem de dados de exemplo (comentário na #27). |
| 6 | **#26 Visualizar grupos existentes por disciplina** | **Selecionada** | Segunda parte da meta e base visual para a #27. |
| 7 | **#27 Solicitar ingresso em grupo existente** | **Selecionada** | Terceira parte da meta: o resultado observável final. |
| 8 | #39 Recuperar acesso por senha esquecida | **Pulada** | Território de identidade. |
| — | #28 em diante | Não selecionadas | Não sustentam a meta desta sprint. |

**Fatia vertical completa:** as três histórias têm tela (`[FE]`), API e persistência (`[BE]`).

**Refinamentos registrados em comentário nas histórias (26/11):**
- **#24:** a parte "deixo de receber sugestões" do cenário de remoção depende da #29 e não é verificada nesta sprint.
- **#26:** a opção "criar um grupo" aparece, mas o fluxo de criação é a #28. O tamanho máximo do grupo é 6.
- **#27:** a disponibilidade do estudante simulado vem de dados de exemplo, porque a #25 está fora da sprint. Aprovar ou recusar a solicitação é a #30.

---

## 4. Esqueleto de tarefas

| Task | Título (resumo) | Responsável | Remaining Work |
|---|---|---|---|
| **#24 Declarar disciplinas cursadas** (2 SP) | | | **9h** |
| AB#41 | [ESP] Contrato de salvar e consultar disciplinas | Vinicius | 1h |
| AB#42 | [BE] Salvar e remover disciplinas cursadas no perfil | Vinicius | 3h |
| AB#43 | [FE] Tela de perfil permite marcar, desmarcar e salvar disciplinas | Vinicius | 3h |
| AB#44 | [VER] Executar os cenários de Declarar disciplinas | Jefferson | 1h |
| AB#45 | [REV] Revisar os PRs de Declarar disciplinas | Maria | 1h |
| **#26 Visualizar grupos existentes por disciplina** (3 SP) | | | **9h** |
| AB#46 | [ESP] Contrato da listagem de grupos por disciplina | João | 1h |
| AB#47 | [BE] Listar grupos com horário, integrantes e situação de vagas | João | 3h |
| AB#48 | [FE] Tela lista os grupos com estados de vagas e lista vazia | João | 3h |
| AB#49 | [VER] Executar os cenários de Visualizar grupos | Jefferson | 1h |
| AB#50 | [REV] Revisar os PRs de Visualizar grupos | Maria | 1h |
| **#27 Solicitar ingresso em grupo existente** (3 SP) | | | **11h** |
| AB#51 | [ESP] Contrato de solicitar e cancelar ingresso | Maria | 2h |
| AB#52 | [BE] Registrar e cancelar solicitação de ingresso | Maria | 4h |
| AB#53 | [FE] Tela permite solicitar, confirmar aviso de horário e cancelar | Jefferson | 3h |
| AB#54 | [VER] Executar os cenários de Solicitar ingresso | João | 1h |
| AB#55 | [REV] Revisar os PRs de Solicitar ingresso | Vinicius | 1h |
| **Total** | | | **29h** |

- Nenhuma Task passa de 8h.
- `[VER]` e `[REV]` de cada história ficam com quem **não** supervisionou a `[BE]` nem a `[FE]` dela.
- Task de documentação fora da sprint: **AB#56 — Registrar o planejamento da Sprint 1** (Maria).

Activity das Tasks: Design (`[ESP]`), Development (`[BE]`, `[FE]`) e Testing (`[VER]`, `[REV]`). Todas as descrições seguem o molde em `docs/moldes/task-pronta-para-agente.md`.

**Conferência no Work details (26/11):**
- **Equipe:** 29h de 36h.
- **Por atividade:** Design 4 de 4,5h; Development 19 de 22,5h; Testing 6 de 9h.
- **Por integrante:** Maria 8/9h, João 8/9h, Vinicius 8/9h e Jefferson 5/9h.

Nenhuma barra passou do limite, então nenhuma história foi devolvida ao backlog.

---

## 5. Riscos e resposta prevista

| # | Risco | Resposta prevista |
|---|---|---|
| 1 | **Cota do agente esgota** no meio de uma `[BE]` ou `[FE]` (Copilot Student ou Codex gratuito). | Uma Task por sessão do agente. Como a especificação está no work item, outro integrante continua a mesma Task com a própria cota. |
| 2 | **O agente falha repetidamente** em uma Task (ex.: altera testes ou sai do módulo). | Protocolo de falha: no máximo 3 tentativas. Depois, corrigir a especificação da Task e registrar a falha no registro de IA. |
| 3 | **Dependência entre histórias:** a `[FE]` da #27 usa a tela da lista de grupos da #26. | Fazer a `[BE]` e a `[FE]` da #26 primeiro; o João avisa a equipe quando a tela estiver no `main`. |
| 4 | **Dados de exemplo divergentes** (disponibilidade e grupos semeados) entre #26 e #27, porque #25 e #28 estão fora da sprint. | Definir os dados de exemplo nas `[ESP]` #46 e #51, num único lugar do módulo `grupos`, e usar os mesmos dados nos testes e na `[VER]`. |
| 5 | **Provas de fim de semestre** em dezembro reduzem as horas disponíveis. | Reserva de 20% já descontada. Se alguém marcar ausência, recalcular no Work details e devolver ao backlog a história de menor prioridade (#27). |

---

## 6. Definition of Done da história

- [ ] Cada cenário Gherkin coberto por `[BE]` tem um teste de aceitação automatizado com nome correspondente
- [ ] Os checks do pull request mostram o vermelho (commit dos testes) e o verde (commit da implementação)
- [ ] A sabotagem controlada está registrada no pull request, com pelo menos um teste falhando
- [ ] Os cenários foram executados manualmente na aplicação por quem não supervisionou a implementação (`[VER]`)
- [ ] Os pull requests foram revisados por outro integrante com o checklist D, e o CI está verde (testes e fronteiras)
- [ ] Todos os commits e pull requests citam `AB#<id>`
- [ ] As decisões sobre propostas do agente estão no registro de IA
- [ ] Todas as Tasks estão em `Closed`; a história foi movida para `Resolved` por quem executou e para `Closed` pelo guardião da qualidade
- [ ] **(acréscimo da equipe)** Toda tela da história é operável só pelo teclado, e todo campo tem rótulo para leitor de tela (critérios da #40)

---

## 7. Registro da reunião de planejamento

- **Data:** 26/11/2026
- **Duração:** _(preencher)_
- **Participantes:** _(preencher)_
- **Decisões:** meta da seção 1; histórias #24, #26 e #27; capacidade de 0,6 h/dia por integrante; responsáveis da seção 4.
