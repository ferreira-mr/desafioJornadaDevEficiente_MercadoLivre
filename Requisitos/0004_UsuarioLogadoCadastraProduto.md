# Usuário logado cadastra novo produto

## Necessidades
- Tem um nome
- Tem um valor
- Tem quantidade disponível
- Características(cada produto pode ter um conjunto de características diferente)
- Da uma olhada nos detalhes de produtos diferentes do mercado livre.
- Tem uma descrição que vai ser feita usando Markdown
- Pertence a uma categoria
- Instante de cadastro

## Restrições
- Nome é obrigatório
- Valor é obrigatório e maior que zero
- Quantidade é obrigatório e >= 0
- O produto possui pelo menos três características
- Descrição é obrigatória e tem máximo de 1000 caracteres.
- A categoria é obrigatória

## Resultado esperado
- Um novo produto criado e status 200 retornado
- Caso dê erro de validação retorne 400 e o json dos erros