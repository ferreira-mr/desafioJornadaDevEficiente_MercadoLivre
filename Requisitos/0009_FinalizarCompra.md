# Realmente finaliza compra

## Necessidades
- A pessoa pode escolher a quantidade de itens daquele produto que ela quer comprar
- O estoque do produto é abatido 
- Um email é enviado para a pessoa que é dona(o) do produto informando que um usuário realmente disse que queria comprar seu produto.
- Uma compra é gerada informando o status INICIADA e com as seguintes informações:
- Gateway escolhido para pagamento
- Produto escolhido
- Quantidade
- Comprador(a)
- Suponha que o cliente pode escolher entre pagar com o Paypal ou Pagseguro.
- O meio de pagamento(pagseguro ou paypal) redireciona para a aplicação passando no mínimo 3 argumentos:
    - id da compra no sistema de origem
    - id do pagamento na plataforma escolhida
    - status da compra. Para o status vamos assumir os dois básicos(Sucesso, Falha). Os gateways de pagamento informam isso de maneira distinta.
- Meio de pagamento retorna para a aplicação o status da compra.
  - Paypal retorna o número 1 para sucesso e o número 0 para erro.
  - Pagseguro retorna a string SUCESSO ou ERRO.
- Precisamos registrar a tentativa de pagamento com todas as informações envolvidas. Além das citadas, é necessário registrar o exato instante do processamento do retorno do pagamento.
- Caso a compra tenha sido concluída com sucesso:
  - precisamos nos comunicar com o setor de nota fiscal que é um outro sistema. Ele precisa receber apenas receber o id da compra e o id do usuário que fez a compra.
- também precisamos nos comunicar com o sistema de ranking dos vendedores. Esse sistema recebe o id da compra e o id do vendedor.
- para fechar precisamos mandar um email para quem comprou avisando da conclusão com sucesso. Pode colocar o máximo de informações da compra que puder.
- Caso a compra não tenha sido concluída com sucesso, precisamos:
  - enviar um email para o usuário informando que o pagamento falhou com o link para que a pessoa possa tentar de novo.

## Restrições
- A quantidade é obrigatória
- A quantidade é positiva
- Precisa ter estoque para realizar a compra​
- id de compra, id de transação e status são obrigatórios para todas urls de retorno de dentro da aplicação.
- O id de uma transação que vem de alguma plataforma de pagamento só pode ser processado com sucesso uma vez.
- A transação da plataforma(qualquer que seja) de id X para uma compra Y só pode ser processada com sucesso uma vez.
- Uma transação que foi concluída com sucesso não pode ter seu status alterado para qualquer coisa outra coisa.
- Não podemos ter duas transações com mesmo id de plataforma externa associada a uma compra.

## Resultado esperado
- Caso a pessoa escolha o paypal seu endpoint deve gerar o seguinte redirect(302):
- Retorne o endereço da seguinte maneira: paypal.com/{idGeradoDaCompra}?redirectUrl={urlRetornoAppPosPagamento}
- Caso a pessoa escolha o pagseguro o seu endpoint deve gerar o seguinte redirect(302):
- Retorne o endereço da seguinte maneira: pagseguro.com?returnId={idGeradoDaCompra}&redirectUrl={urlRetornoAppPosPagamento}
- Caso aconteça alguma restrição retorne um status 400 informando os problemas. 
- Status 200 dizendo retornando o status do pagamento.
- Em caso de erro de validação, retorne 400 e o json com erros.