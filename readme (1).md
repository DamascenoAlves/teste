
# Avaliação Java / Spring: API Rest para Controle de Contatos

## Descrição do Projeto
Este projeto consiste na criação de uma API Rest para gerenciar um sistema de cadastro de Pessoas e seus respectivos Contatos. Cada Pessoa pode ter vários Contatos e o objetivo é permitir operações CRUD (Criar, Ler, Atualizar, Deletar) na estrutura de Pessoas e Contatos.

## Tecnologias Utilizadas
- **Java com Spring Boot (Versão 3.2.7)**
- **JPA/Hibernate** para persistência de dados
- **Banco de dados:** PostgreSQL ou H2
- **Segurança:** Bearer token baseado em JWT
- **Validação de dados:** Bean Validation
- **Documentação:** Swagger (OpenAPI)

## Funcionalidades Implementadas
### CRUD de Pessoas
1. **Criar Pessoa**
2. **Obter Pessoa por ID**
3. **Obter Pessoa por ID para mala direta**
4. **Listar todas as Pessoas**
5. **Atualizar Pessoa por ID**
6. **Deletar Pessoa por ID**

### CRUD de Contatos
1. **Adicionar um novo Contato a uma Pessoa**
2. **Obter Contato por ID**
3. **Listar todos os Contatos de uma Pessoa**
4. **Atualizar Contato por ID**
5. **Deletar Contato por ID**

## Modelagem
### Pessoa
- **ID** (único, não pode ser nulo)
- **Nome** (não pode ser nulo)
- **Endereço** (pode ser nulo)
- **CEP** (pode ser nulo)
- **Cidade** (pode ser nulo)
- **UF** (pode ser nulo)

### Contato
- **ID** (único, não pode ser nulo)
- **Tipo contato** (não pode ser nulo) [0: Telefone, 1: Celular]
- **Contato** (não pode ser nulo)
- **Relacionamento com a entidade Pessoa** (OneToMany e ManyToOne)

## Endpoints
### Pessoa
- **POST /api/pessoas**: Cria uma nova Pessoa
- **GET /api/pessoas/{id}**: Retorna os dados de uma Pessoa por ID
- **GET /api/pessoas/maladireta/{id}**: Retorna os dados de uma Pessoa por ID para mala direta
- **GET /api/pessoas**: Lista todas as Pessoas
- **PUT /api/pessoas/{id}**: Atualiza uma Pessoa existente
- **DELETE /api/pessoas/{id}**: Remove uma Pessoa por ID

### Contato
- **POST /api/contatos**: Adiciona um novo Contato a uma Pessoa
- **GET /api/contatos/{id}**: Retorna os dados de um Contato por ID
- **GET /api/contatos/pessoa/{idPessoa}**: Lista todos os Contatos de uma Pessoa
- **PUT /api/contatos/{id}**: Atualiza um Contato existente
- **DELETE /api/contatos/{id}**: Remove um Contato por ID

## Como Executar a Aplicação
1. Clone o repositório do projeto:
    ```bash
    git clone <link-do-repositorio>
    ```
2. Navegue até o diretório do projeto:
    ```bash
    cd <diretorio-do-projeto>
    ```
3. Configure o banco de dados no arquivo `application.properties` ou `application.yml`:
    ```properties
    spring.datasource.url=jdbc:mysql://localhost:3306/seu_banco_de_dados
    spring.datasource.username=seu_usuario
    spring.datasource.password=sua_senha
    ```
4. Execute a aplicação:
    ```bash
    ./mvnw spring-boot:run
    ```
5. Acesse a documentação do Swagger para testar os endpoints:
    ```
    http://localhost:8080/swagger-ui.html
    ```

## Contribuições
Contribuições são bem-vindas! Sinta-se à vontade para abrir issues e enviar pull requests.

## Autor
Matheus Damasceno Alves
