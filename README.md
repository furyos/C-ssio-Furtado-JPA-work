# Cassio-Furtado-JPA-work
Testes de Desempenho de Transações em Banco de Dados usando JMeter

Este projeto tem como objetivo a criação e teste de uma aplicação Java Spring Boot com transações em banco de dados.
Alunos:

    Cássio Furtado do Nascimento

Organização do Projeto
main

    controller/ (Controladores para requisições HTTP)
    model/ (Entidades do banco de dados)
    repository/ (Repositórios JPA)
    service/ (Regras de negócio)

test

    java/ (Testes unitários)
    jmeter/ (Testes de carga para 1 conta)

Entidades

    ContaBancaria
    ContaBancariaVersionada

Configuração do Banco de Dados H2

    Ajustes em application.properties:

# Configurações do Datasource
spring.datasource.driverClassName=org.h2.Driver
spring.datasource.url=jdbc:h2:file:./data/contas_db
spring.datasource.username=sa
spring.datasource.password=
spring.sql.init.mode=always

# Configurações do JPA/Hibernate
spring.jpa.database-platform=org.hibernate.dialect.H2Dialect
spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=false

spring.h2.console.enabled=true
spring.h2.console.path=/h2-console

Credenciais de acesso ao console:

    JDBC URL: jdbc:h2:file:./data/contas_db
    Username: sa
    Password: (deixe em branco)

Instalação

    Clone o repositório:

git clone https://github.com/luanhmilano/trabalho-jpa.git

    Navegue até o diretório do projeto:

cd trabalho-jpa

    Compile o projeto com Maven:

mvn clean install

    Rode a aplicação:

mvn spring-boot:run

    Acesse o console H2 no navegador em:

http://localhost:8080/h2-console

Execução dos Testes de Concorrência
Teste de Carga com JMeter

O projeto inclui 2 arquivoa de teste JMeter localizado no diretório jmeter/:

    deposito-retirada.jmx: Este arquivo contém o plano de teste configurado para simular requisições concorrentes às APIs de depósito e retirada referentes à entidade "ContaBancaria". Você pode carregá-lo no JMeter para executar testes de carga.
    conta-versionada.jmx: Este arquivo contém o plano de teste configurado para simular requisições concorrentes às APIs de depósito e retirada referentes à entidade "ContaBancariaVersionada". Você pode carregá-lo no JMeter para executar testes de carga.

Executando os Testes

    Inicie a aplicação Spring Boot.
    Abra o JMeter e carregue o arquivo de teste escolhido.
    Configure o número de threads (usuários) e o número de requisições.
    Execute o teste e visualize os resultados nos relatórios do JMeter.

Requisitos

    Java 17 ou superior
    Maven (para compilar e rodar a aplicação)
    JMeter (para executar os testes de carga)

About
No description, website, or topics provided.
Resources
Readme
Activity
Stars
0 stars
Watchers
1 watching
Forks
0 forks
Report repository
Releases
No releases published
Packages
No packages published
Languages

    Java 100.0% 

Footer
