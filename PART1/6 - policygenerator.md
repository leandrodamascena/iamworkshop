# POLICY GENERATOR - TREINAMENTO IAM

## CRIANDO A PRIMEIRA POLÍTICA

* Entre no link https://awspolicygen.s3.amazonaws.com/policygen.html
* Selecione "IAM Policy" no Type Of Policy
* Crie os statements com os seguintes campos:
  * Effect: Allow
  * AWS Service: S3
  * Actions: *
  * Resource: *
* Clique em generate policy

## ADICIONANDO CONDIÇÕES

* Repita os passos acima até a parte de Resource
* Clique em "Add Conditions"
  * Em condition selecione "IpAdrress"
  * Em Key selecione "aws:Sourceip"
  * Em value digite seu IP e adicione /32 no final.