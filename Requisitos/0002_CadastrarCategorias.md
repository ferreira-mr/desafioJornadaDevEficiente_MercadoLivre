# Cadastro de Categorias

## Necessidades
- No mercado livre você pode criar hierarquias de categorias livres. Ex: Tecnologia -> Celulares -> Smartphones -> Android,Ios etc. Perceba que o sistema precisa ser flexível o suficiente para que essas sequências sejam criadas.
- Toda categoria tem um nome
- A categoria pode ter uma categoria mãe

## Restrições
- O nome da categoria é obrigatório
- O nome da categoria precisa ser único

## Resultado esperado
- Categoria criada e status 200 retornado pelo endpoint.
- Caso exista erros de validação, o endpoint deve retornar 400 e o json dos erros.