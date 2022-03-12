# POLÍTICA RBAC - TREINAMENTO IAM

## DEFINIÇÃO

* O modelo de autorização tradicional usado no IAM é chamado de controle de acesso baseado em função (RBAC).

## ELEMENTOS

* Os elementos são os mesmos de uma política padrão explicada no capítulo anterior

```
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "Stmt1647082799336",
      "Action": [
                "s3:List*",
                "s3:Get*"
            ],
      "Effect": "Allow",
      "Resource": ["arn:aws:s3:::leandro12345","arn:aws:s3:::leandro12345/*"]
    }
  ]
}
```

## CRIANDO UMA POLÍTICA RBAC

* Vamos utilizar o bucket criado no awscli no capítulo anterior
* Entre no link https://awspolicygen.s3.amazonaws.com/policygen.html
* Selecione "IAM Policy" no Type Of Policy
* Crie os statements com os seguintes campos:
  * Effect: Allow
  * AWS Service: S3
  * Actions: *
  * Resource: copie e o cole o resource name do bucket
* Clique em generate policy
* Anexe a política no seu usuário
* Suba um arquivo qualquer no seu bucket
* Execute o seguinte comando: `aws s3api get-object --bucket NOMEDOBUCKET --key NOMEDOARQUIVO saida.jpg --profile iamworkshop`

## LINK DE AJUDA

* https://docs.aws.amazon.com/pt_br/IAM/latest/UserGuide/introduction_attribute-based-access-control.html