# Lab de Padrões de Projeto com Spring Boot

Este repositório contém implementações de alguns padrões de projeto em Java utilizando o framework **Spring Boot**. O objetivo deste projeto é demonstrar como diferentes padrões de projeto podem ser aplicados de maneira prática em aplicações Spring, além de explorar o uso de bibliotecas e ferramentas como **OpenFeign**, **Swagger/OpenAPI** e **H2 Database**.

## Padrões de Projeto Implementados

1. **Singleton**
2. **Strategy/Repository**
3. **Facade**

### 1. Singleton
O padrão Singleton garante que uma classe tenha apenas uma única instância. Ele é útil quando você precisa de um ponto de controle global sobre determinado objeto na aplicação.

- **Exemplo prático:** Um serviço de configuração que mantém uma única instância acessível em toda a aplicação.

### 2. Strategy / Repository
O padrão Strategy permite a troca dinâmica de algoritmos ou comportamentos de um objeto em tempo de execução. O padrão Repository facilita a abstração da camada de persistência.

- **Exemplo prático:** Diferentes estratégias de cálculo de descontos aplicadas em produtos, combinadas com a persistência usando JPA.

### 3. Facade
O padrão Facade fornece uma interface simples para um subsistema complexo, ocultando sua complexidade e facilitando o uso.

- **Exemplo prático:** Uma fachada para simplificar a comunicação com um sistema externo de pagamento usando o OpenFeign.

## Tecnologias Utilizadas

### Spring Boot
Framework que facilita a criação de aplicações Java standalone, que podem ser executadas com um simples comando `java -jar`. Neste projeto, ele é usado para estruturar a aplicação e fornecer suporte ao desenvolvimento dos padrões de projeto.

### Spring Data JPA
Fornece uma implementação JPA que facilita a integração com bancos de dados relacionais, simplificando o gerenciamento de repositórios e transações.

- **Uso no projeto:** Implementação do padrão **Repository** para manipulação de dados de forma abstrata e fácil.

### Spring Web
Facilita o desenvolvimento de APIs RESTful, fornecendo recursos para criar e gerenciar controladores e rotas HTTP.

- **Uso no projeto:** Implementação de controladores para expor os serviços que utilizam os padrões de projeto **Facade** e **Strategy**.

### Spring Cloud OpenFeign
Biblioteca que permite fazer chamadas HTTP a outros serviços usando interfaces Java. É usada para simplificar a integração entre microserviços.

- **Uso no projeto:** Aplicado ao padrão **Facade** para fazer requisições HTTP a APIs externas.

### Springdoc OpenAPI (Swagger UI)
Permite a geração automática de documentação para APIs REST, facilitando a visualização e teste dos endpoints expostos pela aplicação.

- **Uso no projeto:** Fornece uma interface gráfica para testar os serviços REST da aplicação, acessível via Swagger UI.

### H2 Database
Banco de dados em memória usado para testes e desenvolvimento local. O H2 é ideal para simulações rápidas de ambientes de persistência sem a necessidade de configurar um banco de dados externo.

- **Uso no projeto:** Configurado para armazenar dados temporários durante a execução da aplicação.

### Maven
Ferramenta de build e gerenciamento de dependências. O Maven é usado para compilar o projeto, gerenciar suas dependências e empacotá-lo em um arquivo `.jar` executável.

### Testes
- **Spring Boot Starter Test**: Utilizado para testes automatizados no projeto, com suporte ao JUnit. Ele permite garantir a qualidade do código e a correta implementação dos padrões.

## Pré-requisitos

- **Java 11** ou superior
- **Maven 3.6+**

## Executando o Projeto

1. Clone este repositório:

   ```bash
   git clone https://github.com/lurregiabarreto/lab-padroes-projeto-spring.git
   ```

2. Acesse o diretório do projeto:

   ```bash
   cd lab-padroes-projeto-spring
   ```

3. Execute o projeto com o Maven:

   ```bash
   mvn spring-boot:run
   ```

4. A aplicação será iniciada na porta `8080`. Para acessar a documentação Swagger UI, vá para:

   [http://localhost:8080/swagger-ui.html](http://localhost:8080/swagger-ui.html)

## Documentação da API

Este projeto usa o **Swagger/OpenAPI** para gerar documentação interativa da API. Após iniciar o projeto, a documentação pode ser acessada em:

```
http://localhost:8080/swagger-ui.html
```

## Banco de Dados H2

A aplicação está configurada para usar o banco de dados H2 em memória. Para acessar o console H2:

1. Inicie o projeto.
2. Acesse [http://localhost:8080/h2-console](http://localhost:8080/h2-console).
3. Use as seguintes credenciais:

    - **JDBC URL:** `jdbc:h2:mem:testdb`
    - **User:** `sa`
    - **Password:** (em branco)

## Contribuindo

Contribuições são bem-vindas! Sinta-se à vontade para abrir issues ou enviar pull requests para melhorar este projeto.

## Licença

Este projeto é licenciado sob a licença MIT. Consulte o arquivo [LICENSE](LICENSE) para mais detalhes.



