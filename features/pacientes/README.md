# Pacientes

**Objetivo:** Gerenciar o ciclo de vida dos pacientes com controle de perfis, unicidade de dados e rastreabilidade.

**Principais regras / cenários cobertos**

- Cadastro bem-sucedido de pacientes
- Validação de campos obrigatórios (telefone)
- Integridade de CPF (formato e unicidade)
- Edição de dados cadastrais

## Casos de teste

| ID | Cenário | Tags | Status | Prints |
|---|---|---|---|:-:|
| [CT-PAC-01](cenarios/CT-PAC-01-cadastrar-paciente-com-sucesso.md) | Cadastrar paciente com sucesso | Funcional · Positivo · Ciclo de vida de Pacientes | ✅ Passou | [2](evidencias/CT-PAC-01/) |
| [CT-PAC-02](cenarios/CT-PAC-02-validar-obrigatoriedade-de-meio-de-contato-do-paciente.md) | Validar obrigatoriedade de meio de contato do paciente | Regra de negócio · Validação de campos | ✅ Passou | [1](evidencias/CT-PAC-02/) |
| [CT-PAC-03](cenarios/CT-PAC-03-impedir-cadastro-com-cpf-invalido-ou-duplicado.md) | Impedir cadastro com CPF inválido ou duplicado | Validação · Integridade de dados | ✅ Passou | [2](evidencias/CT-PAC-03/) |
| [CT-PAC-04](cenarios/CT-PAC-04-editar-dados-cadastrais-do-paciente.md) | Editar dados cadastrais do paciente | Funcional · Atualização | ✅ Passou | [2](evidencias/CT-PAC-04/) |
| [CT-PAC-05](cenarios/CT-PAC-05-a-documentar.md) | (cenário a documentar) | — | 📝 A documentar | [2](evidencias/CT-PAC-05/) |
| [CT-PAC-EDGE-01](cenarios/CT-PAC-EDGE-01-tentativa-de-cadastro-com-data-de-nascimento-irreal.md) | Tentativa de cadastro com data de nascimento irreal | Validação · Limites de domínio e datas | ✅ Passou | [1](evidencias/CT-PAC-EDGE-01/) |

## Observações

- **CT-PAC-05** — evidências já capturadas; cenário BDD a documentar.

---
[← Voltar ao README principal](../../README.md) · Convenções em [docs/convencoes.md](../../docs/convencoes.md)
