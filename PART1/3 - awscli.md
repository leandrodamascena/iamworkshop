# AWS CLI - TREINAMENTO IAM

## BAIXANDO O AWS CLI

* Vá em https://docs.aws.amazon.com/pt_br/cli/latest/userguide/cli-chap-welcome.html e clique na seção Conceitos Básicos -> Instalar / Atualizar.
* Instale de acordo com seu sistema operacional

## CONFIGURANDO O AWS CLI

* Digte o comando `aws configure --profile iamworkshop`
* Insira a sua access key
* Insira a sua secret key
* Digite a região us-east-1
* Digite json


## UTILIZANDO O AWS CLI

* Digite o comando `aws help`
* Visualize todas as opções disponíveis

## LISTANDO RECURSOS ATRAVÉS DO AWS CLI

* Digite o comando `aws s3 ls --profile iamworkshop`
* Digite o comando `aws ec2 describe-instances --output table --profile iamworkshop`


## CRIANDO RECURSOS

* Digite o comando `aws s3api create-bucket --bucket SEUNOME12345 --profile iamworkshop`

## OBTENDO AJUD

* Veja mais comandos e leia a documentação oficial em https://awscli.amazonaws.com/v2/documentation/api/latest/reference/index.html#cli-aws