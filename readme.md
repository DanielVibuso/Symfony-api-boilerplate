# Symfony API Boilerplate

Esta api simula um pequeno sistema para cadastro e gerenciamento de empresas e seus quadro societários.
## Para rodar o projeto

certifique-se de que as portas configuradas no docker-compose desse projeto não estejam em uso e rode os seguintes comandos.

1 - docker-compose build

2 - docker-compose up -d

3 - docker-compose exec app composer install

4 - docker-compose exec app php bin/console lexik:jwt:generate-keypair

5 - docker-compose exec app php bin/console doctrine:database:create

6 - docker-compose exec app php bin/console doctrine:migration:migrate

## Sobre a estrutura

API em symfony,  aplicado o máximo possível dos recursos do framework em detrimento
de abordagens desacopladas.<br>

Adicionado à migration um usuário admin que tem autorização para criar outros usuários, pois tem o ROLE_ADMIN nele que é o ROLE necessário para acessar a rota de registro.  <br>
Adicionado autenticação com token JWT com prazo de validade<br>
Adicionado testes funcionais aos controllers.<br>
Adicionado paginação aos endpoints de listagem.<br>
Adicionado DTO's para validação dos dados de entrada e uso do recurso padrão de normalização e json encoder do framework para a saída dos dados.<br>
Adicionado relacionamento many to many bi-direcional nas entidades company e partners.<br>

### Documentação dos endpoints

Bom, troquei alguns socos com as dependencias do swagger então fica o TODO aqui.

na raiz do projeto tem a coleção do insomnia com todos os endpoints 
criados. Basta importar no insomnia ou no postman ou qualquer outro api client de sua preferencia e tudo estará lá! 
nome do arquivo: insomnia_collection.json


### Tecnologias

- Docker
- Docker compose
- Symfony 7.1
- PHP 8.2
- PHP-CS-Fix para identação padronizada
- PHP-UNIT

### TESTES 

para rodar iniciar o banco de testes, execute: <br>
docker-compose exec app php bin/console doctrine:database:create --env=test <br>

para rodar as migrations para o banco de teste: <br>
docker-compose exec app php bin/console doctrine:migration:migrate --env=test <br>

para rodar os testes, na raiz do projeto execute: <br>
docker-compose exec app ./vendor/bin/phpunit <br>
