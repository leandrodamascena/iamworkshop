# O FLUXO DO IAM - TREINAMENTO IAM

## CONCEITOS

* Por padrão TODO request é negado pelo IAM
* O nome que se dá a negação do request por padrão se chama "Deny Implict"
* O IAM vai analisar as políticas em busca de um deny e o primeiro DENY que ele encontrar ele vai negar sua requisição
* O fluxo de analise de um request é:
  * Analise de todas as políticas
  * SCP
  * Resource-based
  * Identity-based
  * IAM Boundaries
  * Session Policies
* O IAM só vai autorizar seu request se ele encontrar um ALLOW para a requisição solicitada

## MATERIAL DE AJUDA

* https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_evaluation-logic.html
* https://www.youtube.com/watch?v=cBoUeS5uD0w&t=1374s - Live 100% sobre IAM

