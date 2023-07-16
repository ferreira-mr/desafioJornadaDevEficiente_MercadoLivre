# Faça uma pergunta ao vendedor(a)

## Necessidades
- A pergunta tem um título
- Tem instante de criação
- O usuário que fez a pergunta
- O produto relacionado a pergunta
- O vendedor recebe um email com a pergunta nova e o link para a página de visualização do produto(ainda vai existir)
- O email não precisa ser de verdade. Pode ser apenas um print no console do servidor com o corpo.

## Restrições
- O título é obrigatório
- O produto é obrigatório
- O usuário é obrigatório

## Resultado esperado
- Uma nova pergunta é criada e a lista de perguntas, com a nova pergunta adicionada, é retornada. Status 200
- Em caso de erro de validação, retorne 400 e o json com erros.