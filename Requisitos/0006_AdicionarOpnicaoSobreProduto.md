# Adicione uma opinião sobre um produto

## Necessidades
- Tem uma nota que vai de 1 a 5
- Tem um título. Ex: espetacular, horrível...
- Tem uma descrição
- O usuário logado que fez a pergunta
- O produto que para o qual a pergunta foi direcionada

## Restrições
- A restrição óbvia é que a nota é no mínimo 1 e no máximo 5
- Título é obrigatório
- Descrição é obrigatório e tem no máximo 500 caracteres
- Usuário é obrigatório
- O produto relacionado é obrigatório

## Resultado esperado
- Uma nova opinião é criada e status 200 é retornado
- Em caso de erro de validação, retorne 400 e o json com erros.