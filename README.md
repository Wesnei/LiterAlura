
# LiterAlura - Catálogo de Livros (Desafio Alura)

Projeto de um catálogo de livros desenvolvido como parte do desafio de Java do programa Alura. A aplicação consome a API pública [Gutendex](https://gutendex.com/), persiste os dados em um banco de dados PostgreSQL e permite ao usuário interagir com as informações salvas através de um menu no console.

## Funcionalidades

  - **Busca de Livros na Web**: Consulta livros por título diretamente na API Gutendex.
  - **Persistência de Dados**: Armazena no banco de dados as informações dos livros e autores pesquisados.
  - **Listagem de Livros e Autores**: Exibe todos os livros e autores registrados no banco de dados local.
  - **Busca de Autores por Ano**: Permite encontrar autores que estavam vivos em um determinado ano.
  - **Busca de Livros por Idioma**: Filtra e exibe os livros registrados em um idioma específico.

## Tecnologias Utilizadas

  - Java 17
  - Spring Boot & Spring Data JPA
  - PostgreSQL (Banco de Dados)
  - Maven (Gerenciador de Dependências)

## Pré-requisitos

  - **Java 17** ou superior.
  - **Maven 3.8** ou superior.
  - **PostgreSQL** instalado e em execução.

## Configuração do Ambiente

Para que a aplicação funcione, ela precisa se conectar a um banco de dados PostgreSQL.

1.  **Instale o PostgreSQL**
    Se você ainda não o tem, baixe e instale o PostgreSQL a partir do [site oficial](https://www.postgresql.org/download/).

2.  **Crie o Banco de Dados e o Usuário**
    Após a instalação, você precisa criar o banco de dados e o usuário que a aplicação usará. Você pode fazer isso através de um cliente gráfico (como o pgAdmin) ou pela linha de comando (`psql`):

    ```sql
    -- Crie o banco de dados para o projeto
    CREATE DATABASE literalura;

    -- Crie um usuário para a aplicação com uma senha
    CREATE USER docker WITH PASSWORD 'docker';

    -- Conceda todas as permissões no banco de dados para o usuário criado
    GRANT ALL PRIVILEGES ON DATABASE literalura TO docker;
    ```

3.  **Configure a Aplicação**
    O arquivo `src/main/resources/application.properties` deve conter as informações para que o Spring se conecte ao banco de dados que você acabou de criar:

    ```properties
    # Configuração da conexão com o banco de dados PostgreSQL
    spring.datasource.url=jdbc:postgresql://localhost:5432/literalura
    spring.datasource.username=docker
    spring.datasource.password=docker

    # Configuração do Hibernate para criar/atualizar tabelas automaticamente
    spring.jpa.hibernate.ddl-auto=update
    ```

## Instalação e Execução

1.  **Clone o repositório:**

    ```bash
    git clone https://github.com/Wesnei/literalura.git
    ```

2.  **Navegue até o diretório do projeto:**

    ```bash
    cd literalura
    ```

3.  **Garanta que seu serviço do PostgreSQL esteja rodando.**

4.  **Compile e execute a aplicação com Maven:**

    ```bash
    mvn spring-boot:run
    ```
    A aplicação será iniciada e o menu interativo será exibido no seu terminal.

## 📜 Licença

Este projeto está sob a licença MIT.

Copyright © 2025 - [Wesnei Paiva](https://github.com/Wesnei)
