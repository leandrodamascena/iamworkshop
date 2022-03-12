# PRIMEIRA POLÍTICA - TREINAMENTO IAM

## ELEMENTOS

* Version - A versão que define o formato do documento JSON. Geralmente você nunca irá mudar isso até que a AWS crie um novo modelo de documento
* Id - Um valor aleatório que você pode atribuir a sua política
* Statement - Um bloco que vai definir todos ou parte dos acessos da sua política
* Sid - Um identificar único deste bloco
* Effect - Se vai permitir ou negar
* Action - As ações permitidas
* NotAction - Quaisquer ações diferentes das informadas
* Principal - Os "Principal" permitidos numa política de recursos
* NotPrincipal - Qualquer "Principal" diferente dos definidos
* Resource - Qual ARN que vai ser controlado por aquela política
* NotResource - Qualquer ARN diferente dos informados 
* Condition - Condições para que aquela política seja analisada

```
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "Stmt1647082799336",
      "Action": [
        "s3:PutObject"
      ],
      "Principal": {
                "AWS": "**"
            },
      "Effect": "Allow",
      "Resource": ["arn:aws:s3:::leandro12345","arn:aws:s3:::leandro12345/*"]
      "Condition": {
        "IpAddress": {
          "aws:SourceIp": "10.10.10.10/32"
        }
      }
    }
  ]
}
```

## LINK DE AJUDA

* https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_elements.html
