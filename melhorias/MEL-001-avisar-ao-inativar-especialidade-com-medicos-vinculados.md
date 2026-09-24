# MEL-001 — Avisar ao inativar especialidade com médicos vinculados

- **Feature:** [Especialidades](../features/especialidades/README.md)
- **Origem:** [CT-ESP-04](../features/especialidades/cenarios/CT-ESP-04-impedir-remocao-de-especialidade-com-medicos-vinculados.md)
- **Tipo:** Melhoria (não é defeito)
- **Status:** Sugerida
- **Ambiente:** aplicação web hospedada da Comunidade Galera do TI · perfil Administrador
- **Evidências registradas em:** 2026-09-23

## Contexto

O CT-ESP-04 esperava que o sistema impedisse a remoção de uma especialidade com médicos vinculados. Na execução, o Administrador conseguiu **inativar** a especialidade **Cardiologia** mesmo havendo um médico ativo com Cardiologia como especialidade principal.

A listagem oferece apenas **Editar** e **Ativar/Inativar** (não há ação de excluir) e o módulo prevê exclusão lógica (inativação). Por isso o comportamento foi tratado como aceitável — sobra uma oportunidade de melhoria, não um defeito.

## Comportamento atual

- Ao clicar em **Inativar**, a especialidade passa a **Inativa** na hora, sem aviso sobre os médicos vinculados.
- A listagem de especialidades não mostra quantos médicos estão vinculados a cada uma.
- Nos cenários do módulo, a regra de especialidade inativa cobre novos vínculos; o tratamento dos vínculos já existentes não está descrito.

## Proposta

Ao inativar uma especialidade que possui médicos vinculados, exibir uma **confirmação** informando quantos médicos serão impactados, por exemplo: *"Esta especialidade possui N médico(s) vinculado(s). Deseja inativar mesmo assim?"*

Complemento opcional: mostrar na listagem a **quantidade de médicos vinculados** por especialidade.

**Alternativa (mudança de regra, a decidir com o coordenador):** bloquear a inativação enquanto houver médicos vinculados, exigindo desvinculá-los antes — é o comportamento que o CT-ESP-04 esperava originalmente.

## Benefício

- Evita inativar por engano uma especialidade em uso.
- Deixa o impacto visível antes da ação.

## Evidências

**01 · Condição** — médico ativo com Cardiologia como especialidade principal (tela Médicos).

<img src="../features/especialidades/evidencias/CT-ESP-04/01-condicao.png" alt="MEL-001 — condição" width="720">

**02 · Resultado** — Cardiologia inativada, com o botão Ativar disponível (tela Especialidades).

<img src="../features/especialidades/evidencias/CT-ESP-04/02-melhoria.png" alt="MEL-001 — resultado" width="720">
