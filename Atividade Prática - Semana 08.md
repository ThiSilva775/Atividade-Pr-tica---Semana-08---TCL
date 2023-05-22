Curso de Engenharia de Software - UniEVANGÉLICA 
Disciplina de Sisetmas Gerenciadores de Banco de Dados
Dev: Thiago Silva Soares
DATA : 21/05/2023

BEGIN TRANSACTION; -- Inicia a transação

INSERT INTO Usuario (nome, email, senha, altura, peso, objetivo) -- Insere um novo usuário na tabela Usuario
VALUES ('João', 'joao@email.com', '123456', 1.80, 80, 'Ganhar massa muscular');

DECLARE @_id INT; -- Declara uma variável para armazenar o ID do usuário recém-criado
SET @usuario_id = SCOPE_IDENTITY(); -- Armazena o ID do usuário recém-criado naável @usuario_id

INSERT INTO Treino (nome, descricao) -- Insere um novo treino na tabela Treino
VALUES ('Treino de Peito', 'Treino focado no desenvolvimento músculos do peito');

DECLARE @treino_id INT; -- Declara uma variável para armazenar o ID do treino recém-criado
SET @treino_id = SCOPE_IDENTITY(); -- Armazena o ID do treino recém-criado na variável @treino_id

INSERT INTO ExercicioTreino (treino_id, exercicio_id, ordem_exercicio, series, repeticoes) -- Adiciona um exercício ao treino na tabela ExercicioTreino
VALUES (@treino_id, 1, 1, 3, 10);

COMMIT; -- Confirma as alterações realizadas na transação
