# ROLES - TREINAMENTO IAM

## CONCEITOS

* As funções do IAM permitem que você delegue acesso aos usuários e serviços que normalmente não têm acesso aos recursos da AWS da sua organização. 
* Os usuários do IAM ou os Serviços da AWS poderão assumir uma função para obter credenciais temporárias de segurança que possam ser usadas para fazer chamadas de API da AWS. 
* Você não precisará compartilhar credenciais em longo prazo ou definir permissões para cada entidade que necessite de acesso a um recurso. 

## CRIANDO UMA ROLE

* Clique no menu Role/Função
* Clique no botão criar função
* Selecione o Serviço AWS Lambda na tela inicial
* Clique em próximo
* Não anexe nada e clique em próximo
* Coloque o nome "lambda-funcao-iam-workshop"
* Clique em finalizar

## CRIANDO UMA ROLE CROSS ACCOUNT

* Clique no menu Role/Função
* Clique no botão criar função
* Selecione a opção "Conta da AWS"
* Coloque a conta 200984112386
* Procure pela política "AmazonS3ReadOnlyAccess", selecione ela e clique em avançar
* Coloque o nome "role-iam-outra-contra"
* Clique em finalizar

## ASSUMINDO ROLE EM OUTRA CONTA

* Execute o comando `eval $(aws sts assume-role --role-arn arn:aws:iam::ACCOUNTID:role/role-iam-outra-contra --role-session-name iamtempworkshop --profile iamworkshop | jq -r '.Credentials | "export AWS_ACCESS_KEY_ID=\(.AccessKeyId)\nexport AWS_SECRET_ACCESS_KEY=\(.SecretAccessKey)\nexport AWS_SESSION_TOKEN=\(.SessionToken)\n"')`
* Execute o comando `aws s3 ls s3://NOMEDOBUCKETDAOUTRACONTA`


## MATERIAL DE AJUDA

* https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_evaluation-logic.html
* https://www.youtube.com/watch?v=cBoUeS5uD0w&t=1374s - Live 100% sobre IAM

