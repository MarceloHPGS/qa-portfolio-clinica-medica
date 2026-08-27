# BDD — Cenários de Comportamento (Autenticação e Pacientes)

# BDD — Cenários de Comportamento

Documento de referência com todos os cenários BDD mapeados para os módulos de Autenticação e Pacientes.

**Objetivo:** Garantir que todas as regras de negócio, validações e restrições de perfil estejam alinhadas antes da implementação e validação dos testes.

* * *
## 1\. Módulo de Autenticação
**Objetivo:** Garantir a segurança no acesso ao sistema e a validação de identidade dos usuários por meio de credenciais.

**Principais Regras / Cenários Cobertos:**
*   Login bem-sucedido com credenciais corretas
*   Bloqueio de tentativas com senhas incorretas
*   Restrição de acesso para contas inativas

* * *
### CT-AUT-01: Realizar login com credenciais válidas
Teste Funcional Positivo Autenticação

**Descrição:** Validar se o sistema permite o acesso de usuários devidamente cadastrados e ativos com credenciais corretas.

**Dado** que o usuário possui um cadastro ativo e credenciais válidas no sistema
**Quando** o usuário informa seu e-mail e sua senha corretamente na tela de login
E confirma o seu acesso clicando no botão _Entrar_
**Então** o sistema deve autenticar o usuário com sucesso
**E** direcioná-lo para a página inicial/dashboard correspondente ao seu perfil

**Resultado Esperado:** O usuário é autenticado com sucesso e redirecionado para o dashboard da aplicação.

**Resultado Encontrado:** Conforme esperado. ✅

* * *
### CT-AUT-02: Bloquear login com senha incorreta
Teste Funcional Negativo Segurança

**Descrição:** Garantir que o sistema proteja o acesso contra tentativas de login com senhas inválidas.

**Dado** que o usuário está na tela de login do sistema
**Quando** ele preenche um e-mail cadastrado, mas informa uma senha incorreta
**E** confirma a tentativa de acesso
**Então** o sistema deve bloquear a autenticação
**E** exibir uma mensagem amigável informando que as credenciais são inválidas, mantendo o usuário na tela de login

**Resultado Esperado:** O acesso é negado, a mensagem de erro amigável é exibida e o usuário permanece na tela de login.

**Resultado Encontrado:** Conforme esperado. ✅

* * *
### CT-AUT-03: Impedir acesso de usuário inativo
Teste de Regra de Negócio Segurança

**Descrição:** Validar que contas de usuários com status inativo não consigam autenticar na plataforma.

**Pré-condições:** Deve existir um usuário cadastrado com o status Inativo na base.

**Dado** que o usuário possui uma conta com o status Inativo no sistema
**Quando** ele tenta realizar o login informando seu e-mail e sua senha corretos
**Então** o sistema deve bloquear o acesso à aplicação
**E** exibir uma mensagem informando que a conta encontra-se inativa

**Resultado Esperado:** O login é bloqueado e uma mensagem clara de conta inativa é apresentada ao usuário.

**Resultado Encontrado:** —

Pendente até a liberação do login com outras credenciais para inativar um usuário e realizar o teste.

* * *
## 2\. Módulo de Pacientes
**Objetivo:** Gerenciar o ciclo de vida dos pacientes com controle de perfis, unicidade de dados e rastreabilidade.

**Principais Regras / Cenários Cobertos:**
*   Cadastro bem-sucedido de pacientes
*   Validação de campos obrigatórios (telefone)
*   Integridade de CPF (formato e unicidade)
*   Edição de dados cadastrais

* * *
### CT-PAC-01: Cadastrar paciente com sucesso
Teste Funcional Positivo Ciclo de vida de Pacientes

**Descrição:** Validar o registro bem-sucedido de um novo paciente preenchendo todos os dados obrigatórios e válidos.

**Dado** que um recepcionista ou administrador está na tela de cadastro de pacientes
**Quando** ele preenche todos os dados obrigatórios válidos (Nome completo, CPF válido e único, Data de nascimento e pelo menos um meio de contato)
**E** clica em salvar o registro
**Então** o sistema deve cadastrar o paciente com o status ativo
**E** exibir uma mensagem de sucesso, listando o novo paciente na base de dados da clínica

**Resultado Esperado:** O paciente é salvo com status ativo, exibe mensagem de sucesso e aparece na listagem.

**Resultado Encontrado:** —

* * *
### CT-PAC-02: Validar obrigatoriedade de meio de contato do paciente
Teste de Regra de Negócio Validação de Campos

**Descrição:** Garantir que o sistema exija o número do telefone como meio de comunicação para contato com o paciente.

**Pré-condições:** O usuário deve estar na tela de cadastro de novo paciente.

**Dado** que o usuário está preenchendo o formulário de cadastro de um novo paciente
**Quando** ele informa nome, CPF e data de nascimento, mas deixa o campo de Telefone totalmente em branco
**E** tenta submeter o formulário
**Então** o sistema deve bloquear o cadastro do paciente
**E** exibir uma mensagem indicando a obrigatoriedade de preencher o campo Telefone

**Resultado Esperado:** O sistema bloqueia o envio e aponta o erro de validação do campo de contato obrigatório.

**Resultado Encontrado:** Conforme esperado. ✅
* * *
### CT-PAC-03: Impedir cadastro com CPF inválido ou duplicado
Teste de Validação e Integridade de Dados

**Descrição:** Validar as barreiras de integridade para o campo CPF (formato correto e unicidade na base).

**Pré-condições:** Deve existir um paciente cadastrado com um CPF específico na base.

**Dado** que já existe um paciente cadastrado com um CPF específico no sistema
**Quando** o operador tenta cadastrar um novo paciente informando um número de CPF com formato inválido ou repete um CPF já existente
**E** tenta salvar as informações
**Então** o sistema deve rejeitar a operação em ambos os casos
**E** apresentar uma mensagem de erro clara alertando sobre o formato incorreto ou a duplicidade do documento

**Resultado Esperado:** A operação é rejeitada e mensagens específicas de formato inválido ou CPF duplicado são exibidas.

**Resultado Encontrado:** Conforme esperado. ✅

* * *
### CT-PAC-04: Editar dados cadastrais do paciente
Teste Funcional de Atualização

**Descrição:** Validar a capacidade de atualizar informações cadastrais de um paciente já existente.

**Pré-condições:** O paciente deve estar previamente cadastrado e ativo no sistema.

**Dado** que o paciente já possui um cadastro ativo no sistema
**Quando** o recepcionista/administrador edita as informações permitidas (como telefone, endereço ou observações)
**E** confirma as alterações
**Então** os dados do paciente devem ser atualizados com sucesso na tela

**Resultado Esperado:** As alterações são salvas na interface.

**Resultado Encontrado:** Conforme o esperado. ✅

* * *
