-- 1.criar tabela de clientes 
CREATE TABLE IF NOT EXISTS cardapio(
  id SERIAL PRIMARY KEY,
  nome_burguer VARCHAR(100) NOT NULL,
  tipo_pao VARCHAR(200) NOT NULL,
  gramas_carne INT NOT NULL,
  preco DECIMAL(10,2) DEFAULT 0.00,
  pontuacao_estrelas DECIMAL(10,2) DEFAULT 0.00,
  vegetariano BOOLEAN DEFAULT FALSE
);


-- 2. Inserir dados demonstraveis 
INSERT INTO cardapio_burgers (nome_burger, tipo_pao, gramas_carne, preco, pontuacao_estrelas, vegetariano) VALUES 
('Smash Duplo cheddar bacon', 'brioche', 180,36.90,4.9, FALSE),
('truffle gourmet burger', 'australiano', 200, 48.00, 4.8, FALSE),
('crispy chicken supreme', 'gergilim', 150, 32.50, 4.6, FALSE),
('green falafel burger','vegano', 150, 34.00, 4.7, TRUE),
('monster triplo monster', 'brioche', 300,52.90, 5.0, FALSE),
('classic cheeseburger Jr', 'brioche', 100, 24.00, 4.4, FALSE);

============================================================
FICHA DE ENTREGA DA ATIVIDADE - BANCO DE DADOS & SUPABASE
============================================================
Aluno(a): Jhenifer Jholly de Abreu Teobaldo
Tema Atribuído: Tema 08 - Hamburgueria Artesanal
Vídeo de Demonstração (YouTube): (Não informado)
============================================================

-- [Missão 1: Projeção & Aliases]
SELECT nome_burger AS "lanche Artesanal", preco AS "Preco unitario" FROM cardapio_burgers;

-- [Missão 2: Transformação Aritmética]
SELECT nome_burger, preco, (preco + 14.50) AS "preco do combo" FROM cardapio_burgers;

-- [Missão 3: Filtro com WHERE e Lógica]
SELECT * FROM cardapio_burgers WHERE tipo_pao = 'brioche' AND vegetariano = FALSE AND gramas_carne > 150;

-- [Missão 4: Lapidação (ORDER BY e LIMIT)]
SELECT nome_produto, pontuacao_estrela, preco FROM cardapio_burgers ORDER BY pontucao_estrelas DESC LIMIT 3;