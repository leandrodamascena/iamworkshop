# POLÍTICA ABAC - TREINAMENTO IAM

## DEFINIÇÃO

* As permissões de ABAC são dimensionadas com inovação, geralmente por tags.
* As permissões de ABAC são dimensionadas com inovação.
* Usando o ABAC, as equipes podem mudar e crescer rapidamente.
* Permissões granulares são possíveis usando ABAC

## ELEMENTOS

* Os elementos são os mesmos de uma política padrão explicada no capítulo anterior, porém com uma condição que vai definir 

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": [
                "s3:List*",
                "s3:Get*"
            ],
            "Resource": "*",
            "Condition": {
                "StringEquals": {
                    "s3:ExistingObjectTag/iamworkshop": "hoje"
                }
            }
        }
    ]
}
```

## CRIANDO UMA POLÍTICA ABAC

* Vamos utilizar o bucket criado no awscli no capítulo anterior
* Vamos modificar a política criada anteriormente
* Substitua o campo "Action" pelos valores do Action na política acima
* Em resource remova o nome do bucket e coloque *
* Adicione o condition acima
* Anexe a política no seu usuário
* Suba um arquivo qualquer no seu bucket e em propriedades coloque a tag "iamworkshop" e o valor "hoje"
* Suba outro arquivo no seu bucket e não coloque tag alguma
* Execute o seguinte comando: `aws s3api get-object --bucket NOMEDOBUCKET --key NOMEDOARQUIVO saida.jpg --profile iamworkshop`

## LINK DE AJUDA

* https://docs.aws.amazon.com/pt_br/IAM/latest/UserGuide/introduction_attribute-based-access-control.html