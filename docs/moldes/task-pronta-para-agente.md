# Molde — Task pronta para agente

Molde do Guia da Sprint 1, Parte 2 (seção 5). Vale para qualquer prefixo: `[ESP]`, `[BE]`, `[FE]`, `[VER]` e `[REV]`.

```text
Título: [BE] <verbo> <resultado observável> — <história>

Objetivo
  <o que passa a funcionar, em uma frase>
História e cenários
  AB#<id> · "<cenário>", "<cenário>"
O que entregar
  <comportamento, sem detalhes de código>
Como verificar
  <o que precisa ser verdade para a Task fechar>
Fora de escopo
  <o que não fazer, mesmo parecendo útil>
```

Ao gravar no Azure Boards:

- **Description:** o texto aprovado na auditoria.
- **Activity:** Design (`[ESP]`), Development (`[BE]`, `[FE]`) ou Testing (`[VER]`, `[REV]`).
- **Remaining Work:** esforço humano em horas, no máximo 8h.

## Checklist de auditoria (seção 7 do guia)

- [ ] O objetivo cabe em uma frase e descreve um resultado observável
- [ ] Cita a história e nomeia os cenários que cobre
- [ ] Entrega comportamento, e não "criar a camada X"
- [ ] Diz como verificar que ficou pronta
- [ ] Tem entre 1h e 8h de esforço humano
- [ ] Nada depende de login real
- [ ] Quem não escreveu entende o que será entregue lendo **só** a Task
