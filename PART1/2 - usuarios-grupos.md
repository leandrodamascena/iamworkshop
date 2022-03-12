# USUÁRIOS E GRUPOS - TREINAMENTO IAM

## GRUPO
<br />

### O que é um grupo

* Um grupo de usuários do IAM é um conjunto de usuários do IAM
* Você pode dar permissões globais para diversos usuários em um grupo
* Melhor gerenciamento de usuários

### Criando um grupo

* Clique em "User groups"
* Clique em "Create group"
* Informe um nome para o grupo em "User group name"
* Adicione as permissões e os usuários que deseja e clique em "Create group"

### Listando grupos

* Clique em "User groups"
* Verifique os grupos

<br><br>

## USUÁRIOS

### O que é um usuário

* Um usuário é uma entidade única no IAM que possui acesso ao console e/ou a chaves de acesso para utilizar SDK/CLI/API
* Um usuário pode herdar permissões do grupo ou ter suas próprias
* Toda interação do usuário é registrada em um serviço chamado Cloudtrail

### Criando um usuário

* Clique em "Users"
* Clique em "Add Users"
* Informe o nome do usuário
* Selecione se ele terá acesso ao console ou a chaves de API
  * Console: Interface gráfica da AWS para gerenciamento dos recursos
  * Chaves de API: Client e Secret ID utilizados para acesso programático
* Caso escolha a opção de "Password", por favor informe a password.
* Selecione as permissões ou adicione ele a um grupo
* Informe as tags
* Conclua a criação


