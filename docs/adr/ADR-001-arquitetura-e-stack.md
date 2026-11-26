# ADR-001 — Monolito modular em Java com Spring Modulith e SPA em React

- **Situação:** proposta
- **Data:** 2026-11-26
- **Participantes:** Maria Eduarda Aguiar Duarte, Jefferson da Silva Marques Braga, João Pedro Batista Fernandes de Carvalho, Vinicius Vieira Ribeiro Gonçalves

## Contexto

O Connexa ajuda estudantes a encontrar e formar grupos de estudo compatíveis por disciplina e horário, apoia a monitoria no acompanhamento dos grupos e dá à coordenação uma visão agregada por curso e período. Algumas restrições pesaram na escolha:

- **Equipe e prazo:** quatro integrantes, cada um com cerca de 6h por semana, e sprints curtas de 3 semanas.
- **Domínio:** o backlog tem territórios bem separados: perfil, grupos, encontros, acompanhamento, painel e identidade. As histórias precisam ser entregues como fatias verticais (tela, API e banco).
- **Requisitos de TI:** e-mail institucional comprovado, senha sob guarda do próprio Connexa e acessibilidade (teclado e leitor de tela) não negociável.
- **Forma de trabalho:** as Tasks são executadas por um agente de IA supervisionado. Precisamos de fronteiras verificáveis automaticamente, para que uma mudança não invada outro território sem ninguém perceber.
- **Material da disciplina:** existe um template pronto (`connexa-modelo-java`) com CI, verificação de fronteiras e usuário simulado.

## Decisão

Adotamos um **monolito modular com fatias verticais** no back-end, usando **Java 21, Spring Boot 4, Spring Modulith, Spring Data JPA, Flyway e PostgreSQL**. Cada território é um módulo com schema próprio, e o `ArquiteturaModularTest` verifica as fronteiras. No front-end usamos uma **SPA em React 19 com TypeScript e Vite**, organizada por funcionalidade. Partimos do template `connexa-modelo-java` sem alterar sua estrutura.

## Alternativas consideradas

| Alternativa | Por que não foi escolhida |
|---|---|
| Microsserviços (um serviço por território) | Custo de infraestrutura, deploy e comunicação alto demais para 4 pessoas com 6h semanais; o volume de uso de uma instituição não exige escalar partes separadamente. |
| Monolito em camadas tradicional (controller/service/repository globais) | Sem fronteiras entre territórios, o agente de IA poderia misturar regras de módulos diferentes; incentiva Tasks por camada, que a disciplina pede para evitar. |
| Template Node.js (`connexa-modelo-node`) | Viável, mas a disciplina e o guia da Sprint 1 usam o modelo Java como referência, o que facilita tirar dúvidas e comparar com os exemplos. |
| Template .NET (`connexa-modelo-dotnet`) | A equipe tem menos familiaridade com C#/.NET do que com Java. |

## Consequências

- **Positivas:**
  - cada história vira uma fatia dentro de um módulo (`perfil`, `grupos`…), o que facilita Tasks verticais e revisões pequenas;
  - as fronteiras são verificadas no CI;
  - um único deploy e um único banco simplificam o ambiente (Codespaces);
  - se um território crescer, ele pode ser extraído depois.
- **Negativas:**
  - todos os módulos compartilham o mesmo processo e o mesmo deploy;
  - a comunicação entre módulos exige eventos ou tipos públicos do pacote raiz, o que dá mais trabalho do que uma chamada direta;
  - a stack (Spring Modulith, Flyway, TanStack Query) tem curva de aprendizado para parte da equipe.
- **Como verificar:**
  - o `ArquiteturaModularTest` roda no CI a cada pull request (check "Back-end (testes e fronteiras)") e falha se um módulo usar o `internal/` de outro ou se houver ciclo;
  - o lint do front-end bloqueia importação interna entre features;
  - a revisão `[REV]` confere se o diff ficou dentro do módulo da Task.
