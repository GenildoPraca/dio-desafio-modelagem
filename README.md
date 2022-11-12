# Projeto conceitual e-commerce
Desenvolvimento de um diagrama conceitual para a implantação de um e-commerce onde há um forncedor por produto, mas podem existir terceiros disponibilizando produtos para venda na plataforma.

## Refinamento do projeto modelo
* Cliente PJ e PF - uma conta pode ser PJ ou PF, mas não pode ter as duas informações
    > Criado o atributo **tipo_pessoa** que deverá conter F (pessoa física) ou J (pessoa jurídica). Ao atribuir "F" será exigido um CPF válido pela aplicação, do contrário será exigido um CNPJ no campo **Identificação**.
* Pagamento - pode ser cadastrada mais de uma forma de pagamento
    > Criada uma entidade específica para permitir o cadastro de mais de uma forma de pagamento. Nessa entidade também consta a **forma de pagamento** para identificar quais atributos serão obrigatórios de acordo com a forma escolhida (cartão, boleto, etc.).
* Entrega - possui status e código de rastreio
    > Esses atributos foram inseridos diretamente na entidade Pedido por ser uma informação específica para cada pedido o que dispensa a criação de uma entidade apenas para esses dados.

### Outras Melhorias
* Na entidade Produto_Pedido foi inserido o atributo "Valor_Venda" esse visa determinar com precisão o preço praticado no momento da venda, visto que a alteração do preço é algo corriqueiro no mundo real.
* Foram inseridos novos campos na entidade Pedido com intuito de identificar dados ausentes no modelo inicial: data de cadastro e cancelamento, motivo cancelamento, etc.
* Tanto a entidade Cliente quanto Pedido possuem dados do endereço, pois o endereço de entrega pode ser diferente do endereço do cliente. O campo **CEP** além do caráter informacional visa permitir determinar o valor do frete de acordo com a distância do endereço de entrega.
