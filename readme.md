# Symfony VOX API 

Esta api simula um pequeno sistema para cadastro e gerenciamento de empresas e seus quadro societários.

## Sobre a estrutura

Como o pedido foi especifico para criar a API em symfony, tentei aplicar o máximo possível os recursos do framework em detrimento
de abordagens desacopladas.

Adicionado à migration um usuário admin que tem autorização para criar outros usuários, pois tem o ROLE_ADMIN nele que é o ROLE necessário para acessar a rota de registro. 
Adicionado autenticação com token JWT com prazo de validade
Adicionado testes funcionais aos controllers.
Adicionado paginação aos endpoints de listagem.
Adicionado DTO's para validação dos dados de entrada e uso do recurso padrão de normalização e json encoder do framework para a saída dos dados.
Adicionado relacionamento many to many bi-direcional nas entidades company e partners.

### Tecnologias


- Docker
- Docker compose
- Symfony 7.1
- PHP 8.2
- PHP-CS-Fix para
- PHP-UNIT