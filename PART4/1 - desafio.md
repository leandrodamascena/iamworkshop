# DESAFIO - TREINAMENTO IAM

## Criando um tópico SNS

* Vá até o SNS
* Clique em tópicos
* Selecione o modo padrão/standard
* Digite o nome "TOPICO-EMAIL"
* Vá em política de acesso
* Clique em avançado (editar JSON)
* No editor JSON cole a política abaixo
```
{
  "Version": "2008-10-17",
  "Id": "__default_policy_ID",
  "Statement": [
    {
      "Sid": "__default_statement_ID",
      "Effect": "Deny",
      "Principal": {
        "AWS": "*"
      },
      "Action": [
        "SNS:Publish",
        "SNS:RemovePermission",
        "SNS:SetTopicAttributes",
        "SNS:DeleteTopic",
        "SNS:ListSubscriptionsByTopic",
        "SNS:GetTopicAttributes",
        "SNS:AddPermission",
        "SNS:Subscribe"
      ],
      "Resource": "*"
    }
  ]
}
```
* Copie o ARN desse tópico

## Criando uma assinatura de tópico

* Vá até assinaturas
* Clique em criar assinatura
* Selecione o ARN do tópico o ARN do tópico "TOPICO-EMAIL"
* No protocolo selecione email e clique em "Criar assinatura"
* Vá até seu email e confirme o email criado na AWS

## Criando o Lambda

* Vá até o Lambda e clique em "Criar função"
* No nome da função coloque "lambda-envia-email"
* Selecione o runtime "Python 3.9"
* Abra o item "Alterar a função de execução padrão"
* Selecione "Usar uma função existente"
* Escolha a função criada no tópico de "roles" chamada "lambda-funcao-iam-workshop"
* Clique em criar função

```
import json
import boto3

def lambda_handler(event, context):
    message = {"EU SOU": "FERA"}
    client = boto3.client('sns')
    response = client.publish(
        TargetArn='TOPICARN', // COLOQUE AQUI SEU ARN DO TOPICO
        Message=json.dumps({'default': json.dumps(message)}),
        MessageStructure='json'
    )
    return {
        'statusCode': 200,
        'body': json.dumps('Sucesso!')
    }
```

* Clique em deploy
* Clique em test e coloque o nome "evento de teste"
* Clique em test novamente