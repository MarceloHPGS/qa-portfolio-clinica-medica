# CT-ESP-03 — Restringir gerenciamento ao perfil Administrador

- **Feature:** [Especialidades](../README.md)
- **Tags:** Regra de negócio · Permissão de perfil
- **Status:** ⚪ Não executado
- **Pré-condições:** O usuário deve estar autenticado com o perfil de Recepcionista.

**Descrição:** Validar que apenas usuários com perfil de Administrador podem acessar as funcionalidades de cadastro e edição de especialidades.

## Cenário

```gherkin
# language: pt
Funcionalidade: Especialidades

  @CT-ESP-03 @regra-de-negocio @permissao-de-perfil
  Cenário: Restringir gerenciamento ao perfil Administrador
    Dado que o usuário autenticado possui o perfil de Recepcionista
    Quando ele tenta acessar a funcionalidade de cadastro ou edição de especialidades
    Então o sistema deve bloquear o acesso à funcionalidade
    E informar que a ação é restrita ao perfil de Administrador
```

## Execução

| Data | Ambiente | Navegador | Resultado | Executor |
|---|---|---|---|---|
| a definir | Windows 11 Pro | Chrome | ⚪ |  |



## Resultado

- **Esperado:** O acesso é negado e uma mensagem de restrição de perfil é exibida ao usuário.
- **Encontrado:** ainda não registrado

## Evidências

- Ainda não evidenciado.