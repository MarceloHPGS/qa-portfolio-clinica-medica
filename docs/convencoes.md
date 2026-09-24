# Convenções do repositório

## Identificadores

- **Caso de teste:** `CT-<FEATURE>-<NN>` — `AUT`, `PAC`, `ESP`. Casos de limite: `CT-<FEATURE>-EDGE-<NN>`.
- **Defeito:** `BUG-<NNN>` (pasta `bugs/`) · **Melhoria sugerida:** `MEL-<NNN>` (pasta `melhorias/`).
- O mesmo ID vale no ClickUp, no nome do arquivo do cenário e na pasta de evidências.

## Status

| Ícone | Status | Quando usar |
|:-:|---|---|
| ✅ | Passou | resultado encontrado = esperado |
| ❌ | Falhou | divergência confirmada como defeito |
| ⚠️ | Divergência | resultado diferente do esperado, ainda a classificar (defeito × melhoria × requisito ambíguo) |
| 💡 | Melhoria | resultado diferente do esperado, avaliado como comportamento aceitável; a sugestão fica em `MEL-NNN` |
| ⏳ | Pendente | depende de pré-requisito (dado, perfil, ambiente) |
| ⚪ | Não executado | ainda não rodou |
| 📝 | A documentar | há evidência, mas o cenário ainda não foi escrito |

## Estrutura por feature

```text
features/<feature>/README.md                         objetivo, regras e tabela de CTs
features/<feature>/cenarios/CT-XXX-NN-<slug>.md      um arquivo por CT
features/<feature>/evidencias/CT-XXX-NN/NN-<etapa>.png
```

Para criar um CT novo: copie [templates/caso-de-teste.md](../templates/caso-de-teste.md), preencha, adicione as evidências e inclua uma linha na tabela do README da feature.

## Defeitos e melhorias

Toda ⚠️ Divergência precisa virar uma decisão:

- **Defeito** → status ❌ no CT + `bugs/BUG-NNN-<slug>.md` (modelo: [templates/relatorio-de-defeito.md](../templates/relatorio-de-defeito.md)).
- **Melhoria** → status 💡 no CT + `melhorias/MEL-NNN-<slug>.md` (modelo: [templates/melhoria.md](../templates/melhoria.md)).
- **Requisito ambíguo** → esclarecer com o coordenador antes de classificar e registrar a resposta no CT.

O defeito ou a melhoria linka o CT de origem e reaproveita os prints dele, sem copiar arquivos.

## Evidências (prints)

- Nome: `NN-<etapa>.png` — número de ordem + o que a imagem mostra (`01-condicao`, `02-sucesso`, `03-cpf-duplicado`). Minúsculas, sem espaços, uma única extensão.
- Destaque com um retângulo vermelho o ponto validado.
- Capture só a área do sistema: recorte barra de favoritos, foto de perfil e abas do navegador.
- Use apenas dados fictícios; em listagens, prefira filtrar pelo registro testado.
- Registre no CT a data, o ambiente e o navegador da execução — a interface muda entre entregas e o print precisa ser datável.

## Escrevendo cenários (Gherkin)

- Um comportamento por cenário; título no imperativo (*Bloquear…*, *Validar…*, *Impedir…*).
- Passos em linguagem de negócio: código HTTP, nome de campo técnico e mensagem literal ficam em **Resultado esperado**, não nos passos.
- `Dado` = estado inicial · `Quando` = ação · `Então` = resultado observável.
