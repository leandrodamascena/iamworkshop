# ROOT ACCOUNT - TREINAMENTO IAM

## Acesso

* Acesse com sua root account - seu email que você criou a conta
* Clique em seu nome no meu superior direito e "Security Credentials"
* Vamos revisar

## Configurando MFA

* Clique em "Activate MFA"
* Leia o QR CODE
* Digite os dois códigos do MFA consecutivos
* Seu MFA está habilitado

## Definindo a política de senha

* Clique em "Account Settings"
* Clique em Change
* Defina a política de senha
* Clique em Save Changes

## Boas praticas em um geral

* A senha da Root Account deve ser guardada em um cofre
* A Root Account deve ser protegida SEMPRE por um MFA
* NUNCA crie keys para a Root Account 

## Criando um user administrador

* Clique em "Users"
* Clique em "Add Users"
* Informe o nome do usuário com "worhshopadmin"
* Selecione a opção de Console ou Password e informe uma senha.
* Adicione a permissão de "Administrador Access"
* Informe as tags
* Conclua a criação
* Baixe o CSV