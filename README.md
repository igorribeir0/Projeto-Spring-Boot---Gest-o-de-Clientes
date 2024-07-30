# Projeto Spring Boot - Gestão de Clientes

Este é um projeto Spring Boot para a gestão de clientes, que está atualmente em desenvolvimento. A aplicação permite realizar operações CRUD (Create, Read, Update, Delete) em clientes, bem como a integração com o serviço ViaCEP para obter informações de endereço com base no CEP.

## Funcionalidades

- **Buscar todos os clientes**: `GET /clientes`
- **Buscar cliente por ID**: `GET /clientes/{id}`
- **Adicionar novo cliente**: `POST /clientes`
- **Atualizar cliente**: `PUT /clientes/{id}`
- **Deletar cliente**: `DELETE /clientes/{id}`

## Estrutura do Projeto

### Entidades

- **Cliente**: Representa um cliente com atributos como ID, nome e endereço.
- **Endereco**: Representa o endereço de um cliente com atributos como CEP, logradouro, complemento, bairro, localidade, UF, IBGE, GIA, DDD e SIAFI.

### Repositórios

- **ClienteRepository**: Interface que estende `CrudRepository` para realizar operações CRUD na entidade `Cliente`.
- **EnderecoRepository**: Interface que estende `CrudRepository` para realizar operações CRUD na entidade `Endereco`.

### Serviços

- **ClienteService**: Interface para definir os métodos de serviço para a entidade `Cliente`.
- **ClienteServiceImpl**: Implementação da interface `ClienteService` que contém a lógica de negócios para gerenciar clientes e integrar com o serviço ViaCEP.
- **ViaCepService**: Interface Feign para integrar com o serviço ViaCEP e obter informações de endereço com base no CEP.

### Controladores

- **ClienteRestController**: Controlador REST que expõe os endpoints para operações CRUD em clientes.

## Dependências

Certifique-se de adicionar as seguintes dependências no seu `pom.xml`:

```xml
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-data-jpa</artifactId>
</dependency>
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-web</artifactId>
</dependency>
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-data-rest</artifactId>
</dependency>
<dependency>
    <groupId>org.springframework.cloud</groupId>
    <artifactId>spring-cloud-starter-openfeign</artifactId>
</dependency>
<dependency>
    <groupId>com.h2database</groupId>
    <artifactId>h2</artifactId>
    <scope>runtime</scope>
</dependency>
```

## Dependências

```xml
spring.datasource.url=jdbc:h2:mem:testdb
spring.datasource.driverClassName=org.h2.Driver
spring.datasource.username=sa
spring.datasource.password=password
spring.jpa.database-platform=org.hibernate.dialect.H2Dialect
spring.jpa.hibernate.ddl-auto=update
spring.h2.console.enabled=true
```

## Executando a Aplicação

Para executar a aplicação, utilize o seguinte comando:

bash
Copiar código
mvn spring-boot:run
A aplicação estará disponível em http://localhost:8080.





