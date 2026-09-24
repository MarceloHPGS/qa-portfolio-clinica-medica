# Especialidades

**Objetivo:** Gerenciar o catálogo de áreas de atuação médica da clínica, garantindo a padronização e o controle de vínculos com os médicos.

**Principais regras / cenários cobertos**

- Cadastro de especialidade com nome único.
- Apenas administradores podem gerenciar (criar/alterar) as especialidades.
- Impedimento de remoção de especialidades com médicos vinculados.
- Exclusão lógica (inativação) e bloqueio de novos vínculos para especialidades inativas.

## Casos de teste

| ID | Cenário | Tags | Status | Prints |
|---|---|---|---|:-:|
| [CT-ESP-01](cenarios/CT-ESP-01-cadastrar-especialidade-com-sucesso.md) | Cadastrar especialidade com sucesso | Funcional · Positivo · Cadastro | ✅ Passou | [2](evidencias/CT-ESP-01/) |
| [CT-ESP-02](cenarios/CT-ESP-02-bloquear-cadastro-de-especialidade-com-nome-duplicado.md) | Bloquear cadastro de especialidade com nome duplicado | Regra de negócio · Integridade | ✅ Passou | [2](evidencias/CT-ESP-02/) |
| [CT-ESP-03](cenarios/CT-ESP-03-restringir-gerenciamento-ao-perfil-administrador.md) | Restringir gerenciamento ao perfil Administrador | Regra de negócio · Permissão de perfil | ⚪ Não executado | — |
| [CT-ESP-04](cenarios/CT-ESP-04-impedir-remocao-de-especialidade-com-medicos-vinculados.md) | Impedir remoção de especialidade com médicos vinculados | Integridade referencial | 💡 Melhoria | [2](evidencias/CT-ESP-04/) |
| [CT-ESP-05](cenarios/CT-ESP-05-a-documentar.md) | Desativar especialidade sem vínculos ativos | Funcional · Inativação lógica| ✅ Passou | [2](evidencias/CT-ESP-05/) |
| [CT-ESP-EDGE-01](cenarios/CT-ESP-EDGE-01-tentativa-de-cadastro-com-campo-nome-em-branco.md) | Tentativa de cadastro com campo Nome em branco | Validação · Campos obrigatórios | ✅ Passou | [1](evidencias/CT-ESP-EDGE-01/) |

## Observações

- **CT-ESP-03** — resultado ainda não registrado.
- **CT-ESP-04** — O sistema permitiu inativação da especialidade, mesmo tendo pelo menos um médico vinculado à especialidade testada. Classificado como melhoria: [MEL-001](../../melhorias/MEL-001-avisar-ao-inativar-especialidade-com-medicos-vinculados.md).


---
[← Voltar ao README principal](../../README.md) · Convenções em [docs/convencoes.md](../../docs/convencoes.md)
