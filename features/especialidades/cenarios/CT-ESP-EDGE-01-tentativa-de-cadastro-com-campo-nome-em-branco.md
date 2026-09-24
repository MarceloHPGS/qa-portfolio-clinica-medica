# CT-ESP-EDGE-01 — Tentativa de cadastro com campo Nome em branco

- **Feature:** [Especialidades](../README.md)
- **Tags:** Validação · Campos obrigatórios
- **Status:** ✅ Passou

**Descrição:** Validar que o sistema impede o cadastro de uma especialidade quando o campo obrigatório Nome está em branco.

## Cenário

```gherkin
# language: pt
Funcionalidade: Especialidades

  @CT-ESP-EDGE-01 @validacao @campos-obrigatorios
  Cenário: Tentativa de cadastro com campo Nome em branco
    Dado que o administrador está na tela de cadastro de especialidades
    Quando ele deixa o campo Nome em branco
    E tenta salvar o registro
    Então o sistema deve bloquear o cadastro
    E exibir uma mensagem indicando que o campo Nome é obrigatório
```

## Execução

| Data | Ambiente | Navegador | Resultado | Executor |
|---|---|---|---|---|
| 11/09/2026 | Windows 11 Pro | Chrome | ✅ | Marcelo Henrique |






## Resultado

- **Esperado:** O cadastro é bloqueado e uma mensagem de erro de validação do campo obrigatório é exibida.
- **Encontrado:** Conforme o esperado. ✅

## Evidências

**01 · Sucesso**

<img src="../evidencias/CT-ESP-EDGE-01/01-sucesso.png" alt="CT-ESP-EDGE-01 — Sucesso" width="720">
