# wm-app-js

# comando para acessar postgree via terminal
- psql -U postgres -h localhost

# comandos postgree para acessar banco e realizar consultas
- CREATE DATABASE NOME   -> criação do banco de dados
- \c NOME                -> acessar o banco criado   
- \dt                    -> listar tabelas do banco

# comando para instalação do knex globalmente
- npm i -g knex

# caso o comando acima apresente erro
set-ExecutionPolicy RemoteSigned -Scope CurrentUser
Get-ExecutionPolicy
Get-ExecutionPolicy -list

# comando para rodar o knex
- knex init

# coamndo para criação de migrations
- knex migrate:make create_table_users

# comando para rodar as migrations definidas no sistema
- knex migrate:latest


# #####################################################################################
SOLUÇÕES DE ERROS BACKEND
# #####################################################################################
Solução dos erros do Backend - Projeto Base de Conhecimento



Erro: knex não é um comando reconhecido
Solução:

Instalar o knex globalmente.

Comando: npm i -g knex
Erro knex init: No such file or directory
Solução:

Basta você ir na pasta do projeto > versao-inicial > backend > node_modules > knex > lib

Quando chegar aí, crie uma nova pasta com o nome migrations e depois mova a pasta migrate para dentro dela.

Créditos ao aluno Wenderson pela solução!
Erro Knex migrate:make create_table_users: Cannot find module '../migrate'
Solução:

Acessar a pasta node_modules (versao-inicial/backend/node_modules), dentro dela achar a pasta knex/lib/util e abrir o arquivo make-knex.js

Achar a linha referente ao migrate: var _migrate e corrigir para var _migrate = require('../migrations/migrate');

Rodar o comando (create_table_users) novamente.
Erro: knex Timeout (versao-inicial/backend)
Solução:

Atualizar pg para versão "^8.0.3"

Será necessário apagar a pasta node_modules e o arquivo package-lock.json e refazer a instalação usando o comando npm i.
Erro: Unhandled Promise Rejection (MongoDB) - EADDRINUSE
Solução:

Verificar se não há duas instâncias do npm start do backend rodando.

Parar uma das duas usando o comando Ctrl + C.
Erro: Cannot find module './env'
Solução:

No knexfile.js, corrigir a primeira linha para const { db } = require('./.env')

Atualizar dependência pg para "^8.0.3"

Modificar os arquivos do postgres (C:\Arquivos de Programas\Postgres\13\data):

No pga_hbconf: METHOD de scram-sha-256 para md5

No postgresql.conf: password_encryption = md5