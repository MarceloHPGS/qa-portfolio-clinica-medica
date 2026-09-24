# CT-AUT-03 — Impedir acesso de usuário inativo

- **Feature:** [Autenticação](../README.md)
- **Tags:** Regra de negócio · Segurança
- **Status:** ⏳ Pendente
- **Pré-condições:** Deve existir um usuário cadastrado com o status Inativo na base.

**Descrição:** Validar que contas de usuários com status inativo não consigam autenticar na plataforma.

## Cenário

```gherkin
# language: pt
Funcionalidade: Autenticação

  @CT-AUT-03 @regra-de-negocio @seguranca
  Cenário: Impedir acesso de usuário inativo
    Dado que o usuário possui uma conta com o status Inativo no sistema
    Quando ele tenta realizar o login informando seu e-mail e sua senha corretos
    Então o sistema deve bloquear o acesso à aplicação
    E exibir uma mensagem informando que a conta encontra-se inativa
```

## Execução

| Data | Ambiente | Navegador | Resultado | Executor |
|---|---|---|---|---|
|  A definir| Windows 11 Pro | Chrome | ... | … |


## Resultado
migável
- **Esperado:** O login é bloqueado e uma mensagem clara de conta inativa é apresentada ao usuário.
- **Encontrado:** ainda não registrado
- **Observação:** Pendente até a liberação do login com outras credenciais para inativar um usuário e realizar o teste.
