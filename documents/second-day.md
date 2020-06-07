### 2º dia: Back-end da aplicação

[] Explicando conceitos 
	[] Rotas e Recursos
	[] Método HTTP
	[] Tipos de parâmetros
[] Utilizando Insomnia
	[] Qual banco de dados vamos utilizar?
		[] SQL: Postgres, MySQL, SQlite, SQL Server
			O escolhido foi o SQlite com a biblioteca (http://knexjs.org/)
		[] NoSQL: MongoDB, CouchDB
[] Criação de um arquivo de rotas e exportacao  (routes.ts)
[] Configurando conexao com o Banco
	[] criação de uma pasta database
	[] instalar o knex via npm
	[] criar arquivo de conecção (connection.ts)
		- o arquivo basicamente possui o client e o caminho do banco.
		- importar a funcao path do express
		- variavel global __dirname , retorna o caminho do diretório do arquivo
	[] instalar o pacote do banco sqlite3
[] Identificando entidades da aplicação
	- Tabela ponto de coleta (ponints)
		- point_id
		- image
		- nome
		- email
		- whatsapp
		- latitude
		- longitude
		- city
		- UF
	- Tabela dos itens (items)
		- item_id
		- image
		- title
	- Relacionamento [N->N] (tabela pivot) (point-items) - itens que o ponto coleta
		- point_id
		- item_id
		
	Migrations(documentação do knex)
		mantém o histórico do banco
		`import Knex from 'knex'`
		[] Criando uma pasta migrations
			- usar a notacao ex.: 00_ points/01_items/03_points_items
		criar na raiz um arquivo knexfile.ts 
		 configuracoes tem necessidade um module.exports = {}
		 useNullAsDefault
		 instalar a extensao sqlite 
		criar a pasta migrations dentro de database
		construir e colocar na raiz o arquivo 'knexfile.ts'
		rodar o comando  `npx knex migrate:latest --knexfile knexfile.ts migrate:latest`


[] Funcionalidades da aplicação
	[] cadastro
**	1:26:00
	[] listar itens disponiveis de coleta
	[] listar pontos por {UF, City e Items)- mobile
	[] listar unico ponto de coleta
	
	criar a pasta Seed (criar os itens defaults)

	por conveção as funcoes criadas nos Controllers são
	- index()
	- show()
	- create()
	- update()
	- delete()
	
[] Construção do app
[] Adicionando CORS		