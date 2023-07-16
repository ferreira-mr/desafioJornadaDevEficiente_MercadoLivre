# Usuário logado adiciona imagem no seu produto

## Necessidades
- Adicionar uma ou mais imagens a um determinado produto do próprio usuário

## Restrições
- Tem uma ou mais fotos
- Só pode adicionar fotos ao produto que pertence ao próprio usuário

## Resultado esperado
- Imagens adicionadas e 200 como retorno
- Caso dê erro de validação retorne 400 e o json dos erros
- Caso tente adicionar imagens a um produto que não é seu retorne 403.