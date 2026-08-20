# Sistema de Cadastro de Alunos WEB com o MySQL em Docker

Sistema de Cadastro de Aluno WEB com Banco de Dados MySQL em Docker.

## Sobre o projeto
 - O projeto foi desenvolvido no NetBeans deve ser chamado **cadastroaluno_web_mysql_docker**.
 - Utiliza o **Java 8**.
 - Utiliza o **Apache Tomcat 9** como servidor de aplicações Web.
 - Utiliza o **Apache Maven** para automatizar o processo de construção da aplicação.
 - A aplicação é empacotada no formato **WAR (Web Application Archive)**.
 - Utiliza o **Docker** para criar e executar o container do banco de dados MySQL.
 - Utiliza o **Docker Compose** para definir e gerenciar o serviço do banco de dados. 
 - Utiliza o **MySQL 8.4** como banco de dados da aplicação. 
 - O projeto é um **CRUD** para os dados de aluno (id, nome, idade, curso e fase).
 - As classes do projeto está organizado nos **pacotes** visão, controle, modelo e dao.
 - Toda iteração com banco de dados é tratada diretamente pelo **DAO**(Data Access Object).
 - Os dados de **configuração** (Servidor, Database, Usuario, Senha) da integração do java com o banco de dados estão no arquivo src/dao/AlunoDAO.java.
 - A **interface gráfica** foi construída utilizando HTML, JavaScript e CSS.

## Docker
 - Utilizar o terminal do Windows Powershel em modo administrador.

### Para criar o conteiner e o serviço do banco de dados.
 - ```docker compose up -d```

### Para verificar o serviço em execução
 - ```docker compose ps```

### Parar o serviço
 - ```docker compose down -v```

### Remover a imagem
 - ```docker compose down --rmi all```

## Banco de dados

- O banco de dados e a tabela são criados no primeiro acesso ao banco de dados MySQL.

### Cria a tabela de tb_alunos

- Abaixo o script SQl se precisar criar o banco de dados e a tabela[banco.sql](banco.sql).

```
# Criar o database chamado db_alunos
create database if not exists db_alunos;

# Entrar no database db_alunos
use db_alunos;

# Remover a tabela para recriá-la
drop table if exists tb_alunos;

# Criar a tabela de tb_alunos
create table tb_alunos (id      integer not null, 
                        nome    varchar(100), 
                        idade   integer,
                        curso   varchar(50),
                        fase    integer,
                        constraint pk_tb_alunos primary key(id));

```

## Interface gráfica WEB

### Tela do menu principal do programa.
![tela1](tela1.png)

### Tela para cadastrar novos alunos.
![tela2](tela2.png)

### Tela para gerenciar alunos (alterar e apagar).
![tela3](tela3.png)

## Arquivos

- banco.sql - Script do banco de dados.
- pom.xml - Arquivo de configuração da ferramenta de automação Maven.
- *.png - Arquivos de imagens do README.md.
- compose.yml - Arquivo de configuração da composição do Docker.