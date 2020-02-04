# CarRent Solution

Para o desenvolvimento deste projeto foi abordado a modelagem DDD que segue um conjunto de práticas com
objetivo de facilitar a implementação de regras e processos de negócios que tratamos como domínio.

## Para isso o projeto foi arquitetado da seguinte forma:

Para o backend Foi criado a solution pelo visual studio chamada CarRentSolution. Dentro dela encontram-se os seguintes projetos:

- CarRentSolution.API (0)
- CarRentSolution.Test (1)
- CarRentSolution.Application (2)
- CarRentSolution.Domain (3)
- CarRentSolution.Infra.Data (4)

### SOFTWARES UTILIZADOS

- Visual Studio 2017
- Visual Code
- Microsoft SQL Server Express
- Microsoft SQL Server Management Studio 17
- Angular CLI versão 8.3.19

### FRONT-END

- Camada de Apresentação
- Angular 7 consultando a Web API

### BACK-END

- .NET Core 2.2.0
- Swagger para documentação da API
- EF Core utilizando a abordagem Code First

- Arquitetura:

Estes projetos foram criados a partir do template Class Library (.NET Core) do Visual Studio 2017.
	
	* API (0): Web API que disponibiliza os endpoints para a camada de apresentação
	* Domain (3): Serviço do domínio que atende partes do negócio que não se encaixam em entidades específicas, trabalha com diversas entidades, realiza persistência através de repositórios e etc.
	* Application (2): Serviço de aplicação que orquestra ações disparadas pela camada de apresentação e fornece DTOs para comunicação entre as demais camadas e para o consumo da camada de apresentação.
	* Infra (4): Realiza a persistência das entidades se comunicando diretamente com o meio de acesso aos dados, é utilizado apenas um repositório por agregação.
		** Data: Repositório dos dados
		** External Services: Faz comunicação com serviços externos como o Amazon SES para o envio de email
	
### Testes Automatizados

Estes projetos foram utilizados o template xUnit Test Project (.NET Core)

CarRentSolution.Tests - Tentei cobrir 80% da Web API bem como suas camadas adjacentes.

## Como Rodar a Aplicação

### Back-End 

1. Primeiro devemos alterar a string de conexão que fica no arquivo `appsettings.json` do projeto `CarRentSolution.Api` na chave `DefaultConnection`.
Coloque o valor do seu servidor de banco local
2. Build a Solução
3. No Package Manager Console crie as migrações (comandos: `Add-Migration nomeDamigrarion` e depois `Update-Database` lembrar de selecionar o projeto CarRentSolution.Infra.Data na opção Default project)
4. Start Debbuging (F5) a aplicação será executada na porta https://localhost:44399
5. Acesse https://localhost:44399/swagger/index.html para ver a documentação da API no Swagger
6. Para o front-end funcionar a web api deve estar rodando nesse endereço e porta: https://localhost:44399

## Development server

Run `ng serve` for a dev server. Navigate to `http://localhost:4200/`. The app will automatically reload if you change any of the source files.

## Code scaffolding

Run `ng generate component component-name` to generate a new component. You can also use `ng generate directive|pipe|service|class|guard|interface|enum|module`.

## Build

Run `ng build` to build the project. The build artifacts will be stored in the `dist/` directory. Use the `--prod` flag for a production build.

## Running unit tests

Run `ng test` to execute the unit tests via [Karma](https://karma-runner.github.io).

## Running end-to-end tests

Run `ng e2e` to execute the end-to-end tests via [Protractor](http://www.protractortest.org/).

## Further help

To get more help on the Angular CLI use `ng help` or go check out the [Angular CLI README](https://github.com/angular/angular-cli/blob/master/README.md).
