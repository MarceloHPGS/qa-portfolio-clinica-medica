# Autenticação

**Objetivo:** Garantir a segurança no acesso ao sistema e a validação de identidade dos usuários por meio de credenciais.

**Principais regras / cenários cobertos**

- Login bem-sucedido com credenciais corretas
- Bloqueio de tentativas com senhas incorretas
- Restrição de acesso para contas inativas

## Casos de teste

| ID | Cenário | Tags | Status | Prints |
|---|---|---|---|:-:|
| [CT-AUT-01](cenarios/CT-AUT-01-realizar-login-com-credenciais-validas.md) | Realizar login com credenciais válidas | Funcional · Positivo · Autenticação | ✅ Passou | [2](evidencias/CT-AUT-01/) |
| [CT-AUT-02](cenarios/CT-AUT-02-bloquear-login-com-senha-incorreta.md) | Bloquear login com senha incorreta | Funcional · Negativo · Segurança | ✅ Passou | [1](evidencias/CT-AUT-02/) |
| [CT-AUT-03](cenarios/CT-AUT-03-impedir-acesso-de-usuario-inativo.md) | Impedir acesso de usuário inativo | Regra de negócio · Segurança | ⏳ Pendente | — |

## Observações

- **CT-AUT-03** — Pendente até a liberação do login com outras credenciais para inativar um usuário e realizar o teste.

---
[← Voltar ao README principal](../../README.md) · Convenções em [docs/convencoes.md](../../docs/convencoes.md)
