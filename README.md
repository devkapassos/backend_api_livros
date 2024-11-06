# backend_api_livros
Este projeto é um backend em Django e Django Ninja para um sistema de cadastro, avaliação e sorteio de livros, permitindo a criação, visualização, avaliação e exclusão de livros. A API inclui um filtro avançado para sorteio de livros baseado em critérios definidos pelo usuário.

## Funcionalidades
- Cadastro de Livros: Adiciona livros com nome, plataforma de streaming (F ou AK) e categorias associadas.
- Avaliação de Livros: Permite que o usuário avalie livros, incluindo nota e comentários.
- Visualização de Livros: Retorna a lista de todos os livros cadastrados.
- Sorteio de Livros: Filtra e sorteia um livro com base em critérios opcionais, como nota mínima e categorias.
- Exclusão de Livros: Remove um livro específico do banco de dados.

## Tecnologias e Bibliotecas Utilizadas
- Django: Framework principal para a construção do backend.
- Django Ninja: Permite a criação de APIs com suporte a tipagem e validação de dados.
- PostgreSQL (opcional): Recomendado para o banco de dados, mas pode ser adaptado para outro de sua escolha.


## Estrutura do Código
- Rotas (livros_router):
  - GET /: Retorna todos os livros cadastrados.
  - POST /: Cadastra um novo livro.
  - PUT /{livro_id}: Avalia um livro existente.
  - DELETE /{livro_id}: Exclui um livro.
  - GET /sortear/: Sorteia um livro com base em filtros específicos.
- Schemas (schemas.py):
  - LivrosSchema: Esquema de dados para cadastro de livros.
  - LivrosViewSchema: Esquema de visualização de livros.
  - AvaliacaoSchema: Esquema para dados de avaliação.
  - FiltrosSortear: Esquema para filtros do sorteio de livros.
- Exceções e Tratamento de Erros:
  - Verificação de erro para entradas incorretas (exemplo: plataforma de streaming inválida).
  - Retornos com códigos HTTP específicos para resultados como sucesso, erro do servidor e item não encontrado.

## Como Configurar e Executar
***Pré-requisitos***
- Python 3.11+
- Django
- Django Ninja

### Passo a Passo
1. Clone o repositório e instale as dependências:
   ```bash
   pip install -r requirements.txt
2. Configure as variáveis de ambiente e o banco de dados no arquivo settings.py.
3. Execute as migrações:
    ```bash
    python manage.py migrate
4. Inicie o servidor:
   ```bash
   python manage.py runserver
A API estará disponível em http://localhost:8000.
