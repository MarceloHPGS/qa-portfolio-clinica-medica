# 🏥 Portfólio de QA — Clínica Médica

> Casos de teste em **BDD (Gherkin)**, evidências de execução e gestão ágil no **ClickUp**, produzidos como **QA Aprendiz** no projeto colaborativo da **Comunidade Galera do TI**.

## 📌 Resumo

- **Sistema sob teste:** aplicação web hospedada de gestão de clínica médica — login, perfis (Administrador e Recepcionista), pacientes e especialidades. Código: [GaleradoTI/clinica-medica](https://github.com/GaleradoTI/clinica-medica).
- **Abordagem:** testes manuais funcionais — positivos, negativos, limites (*edge*), regras de negócio e integridade de dados.
- **Documentação:** um arquivo por caso de teste, com o cenário em Gherkin (pt-BR), resultado esperado × encontrado e as evidências (prints) no mesmo lugar.
- **Gestão:** ClickUp compartilhado com o mentor e os outros aprendizes, com cards, subtarefas e dependências.
- **Em estudo:** testes de API (Postman) e automação.

## 📊 Cobertura atual

| Feature | CTs | ✅ Passou | 💡 Melhoria | ⏳ Pendente / ⚪ Não executado | 📝 A documentar |
|---|:-:|:-:|:-:|:-:|:-:|
| [Autenticação](features/autenticacao/) | 3 | 2 | – | 1 | – |
| [Pacientes](features/pacientes/) | 6 | 5 | – | – | 1 |
| [Especialidades](features/especialidades/) | 6 | 3 | 1 | 1 | 1 |
| **Total** | **15** | **10** | **1** | **2** | **2** |

**Melhoria sugerida:** [MEL-001](melhorias/MEL-001-avisar-ao-inativar-especialidade-com-medicos-vinculados.md) — avisar o usuário ao inativar uma especialidade que ainda tem médicos vinculados (origem: [CT-ESP-04](features/especialidades/cenarios/CT-ESP-04-impedir-remocao-de-especialidade-com-medicos-vinculados.md)).

## 🗂️ Estrutura do repositório

```text
features/
├── autenticacao/
│   ├── README.md          # objetivo, regras e tabela de CTs com status
│   ├── cenarios/          # um arquivo por caso de teste (CT-AUT-01-<slug>.md)
│   └── evidencias/        # uma pasta por CT (CT-AUT-01/01-inicial.png)
├── pacientes/             # mesma estrutura
└── especialidades/        # mesma estrutura
melhorias/                 # melhorias sugeridas (MEL-001)
docs/
└── convencoes.md          # IDs, status, padrão de evidências e de escrita
templates/                 # modelos de caso de teste, defeito e melhoria
```

Convenções (IDs, status, nomes de arquivo, como tirar os prints): [docs/convencoes.md](docs/convencoes.md).

## 🤝 Contexto

Iniciativa da **Comunidade Galera do TI**: um projeto colaborativo *hands-on* coordenado pelo QA **Gabriel Marques**, que estruturou a base técnica (backend e frontend), definiu as regras de negócio e mentora o grupo. Participo como **QA Aprendiz** — testes manuais, escrita de cenários e planejamento da qualidade — para consolidar os fundamentos e evoluir para testes de API e automação.

## 🚀 Próximos passos


- [ ] Executar os CTs pendentes (CT-AUT-03, CT-ESP-03)
- [ ] Cenários de restrição de acesso a dados clínicos (perfil Recepcionista)
- [ ] Cenários para os módulos Médicos e Usuários
- [ ] Regressão a cada nova entrega
- [ ] Testes de API com Postman
- [ ] Automação dos cenários mais estáveis

## 🙏 Agradecimentos

À **Comunidade Galera do TI** pelo ambiente colaborativo e ao **Gabriel Marques** pelo tempo, pela paciência e pelo conhecimento técnico na mentoria.
