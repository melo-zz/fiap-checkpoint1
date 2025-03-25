# API de Pedidos - Checkpoint 1

## Descrição
Este é um projeto de API REST desenvolvida com **Spring Boot**. A API gerencia pedidos e oferece funcionalidades para criar, listar, atualizar e deletar pedidos. O banco de dados utilizado é o **H2 Database** e as operações de CRUD são realizadas com **Spring Data JPA**.

## Estrutura do Projeto
A estrutura do projeto é organizada da seguinte forma:

src/main/java/br/com/fiap/checkpoint1 ├── controller # Responsável pelos endpoints ├── model # Representação das entidades (dados) ├── repository # Interface para interação com o banco de dados ├── service # Lógica de negócios

markdown
Copiar

## Tecnologias Utilizadas

- **Spring Boot 3.1.x**
- **Java 17**
- **Spring Data JPA** (para persistência de dados)
- **H2 Database** (banco de dados em memória)
- **Lombok** (para reduzir boilerplate de código)
- **Spring Web** (para criação da API REST)
- **Spring Boot DevTools** (para desenvolvimento)

## Endpoints da API

### 1. Criar um novo pedido
- **Método**: `POST`
- **URL**: `/pedidos`
- **Corpo da requisição**:
  ```json
  {
      "clienteNome": "João",
      "valorTotal": 150.0
  }
Resposta: 201 Created

json
Copiar
{
    "id": 1,
    "clienteNome": "João",
    "dataPedido": "2025-03-25",
    "valorTotal": 150.0
}
2. Listar todos os pedidos
Método: GET

URL: /pedidos

Resposta:

json
Copiar
[
    {
        "id": 1,
        "clienteNome": "João",
        "dataPedido": "2025-03-25",
        "valorTotal": 150.0
    }
]
3. Buscar um pedido por ID
Método: GET

URL: /pedidos/{id}

Resposta:

json
Copiar
{
    "id": 1,
    "clienteNome": "João",
    "dataPedido": "2025-03-25",
    "valorTotal": 150.0
}
4. Atualizar um pedido
Método: PUT

URL: /pedidos/{id}

Corpo da requisição:

json
Copiar
{
    "clienteNome": "Carlos",
    "valorTotal": 200.0
}
Resposta:

json
Copiar
{
    "id": 1,
    "clienteNome": "Carlos",
    "dataPedido": "2025-03-25",
    "valorTotal": 200.0
}
5. Deletar um pedido
Método: DELETE

URL: /pedidos/{id}

Resposta: 204 No Content

Banco de Dados
A aplicação utiliza o H2 Database para armazenamento dos dados. O banco de dados é em memória, ou seja, os dados são descartados quando a aplicação é finalizada.

Você pode acessar o console do H2 no seguinte endereço:
URL do console: http://localhost:8080/h2-console
JDBC URL: jdbc:h2:mem:testdb
Usuário: sa
Senha: password

Configuração do Banco de Dados
No arquivo src/main/resources/application.properties, a configuração do H2 Database é feita automaticamente. Caso precise de ajustes, altere as propriedades conforme necessário.

Como Executar o Projeto
Pré-requisitos
Java 17 ou superior instalado.

Maven instalado para rodar os comandos do projeto.

Passo 1: Clonar o Repositório
Clone este repositório para o seu ambiente local:

bash
Copiar
git clone https://github.com/usuario/checkpoint1.git
cd checkpoint1
Passo 2: Instalar Dependências e Executar
Para compilar o projeto e rodar a aplicação, execute o seguinte comando:

bash
Copiar
mvn clean install
mvn spring-boot:run
Passo 3: Acessar a API
A API estará disponível em http://localhost:8080. Você pode começar a fazer requisições usando ferramentas como Postman ou cURL.

Testando a API
Você pode usar o Postman ou outro cliente HTTP para testar os seguintes endpoints:

POST /pedidos: Cria um novo pedido.

GET /pedidos: Retorna todos os pedidos.

GET /pedidos/{id}: Retorna um pedido pelo ID.

PUT /pedidos/{id}: Atualiza um pedido.

DELETE /pedidos/{id}: Deleta um pedido.

Contribuindo
Se você gostaria de contribuir com o projeto, sinta-se à vontade para fazer um fork, criar uma branch, e enviar um pull request com suas melhorias.

Licença
Este projeto está licenciado sob a MIT License.

