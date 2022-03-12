# RESOURCE POLICY - TREINAMENTO IAM

## DEFINIÇÃO

* As políticas baseadas em recurso são anexadas a um recurso.
* Mesmo que um usuário tenha uma política permitindo o acesso ao recurso, a resource based ainda pode proibir esse acesso.

## ELEMENTOS

* Os elementos são os mesmos de uma política padrão explicada no capítulo anterior, porém com um elemento que estará sempre presente em resource-based: o Principal.
* Um principal é um recurso associado a AWS e pode contemplar os seguintes itens
  * AWSConta e usuário raiz da
  * Funções do IAM
  * Sessões de função
  * Usuários do IAM
  * Sessões de usuário federado 
  * Serviços AWS
  * Todas as entidades principais

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "Statement1",
            "Effect": "Deny",
            "Principal": "*",
            "Action": "s3:*",
            "Resource": [
                "arn:aws:s3:::leandro12345",
                "arn:aws:s3:::leandro12345/*"
            ]
        }
    ]
}
```

## CRIANDO UMA RESOURCE BASED POLICY

* Vamos utilizar o bucket criado no awscli no capítulo anterior
* Vá até a aba permissões
* Em política do Bucket clique em "editar" e cole o documento JSON acima.
* Substitua os ARN com o nome do seu bucket
* Vamos testar o comando anterior
* Suba um arquivo qualquer no seu bucket
* Execute o seguinte comando: `aws s3api get-object --bucket NOMEDOBUCKET --key NOMEDOARQUIVO saida.jpg --profile iamworkshop`

## LINK DE AJUDA

* https://docs.aws.amazon.com/pt_br/IAM/latest/UserGuide/introduction_attribute-based-access-control.html