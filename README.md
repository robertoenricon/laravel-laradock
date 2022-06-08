# laravel-laradock
Laravel + Laradock

- 1. Introduçao:
   - Esse repositorio é um repositorio meu conteudo meu projeto já em laravel. Caso voce nao tenha o Laravel, va para o item 2 e clone o repositorio padrao do Laravel

- 2. Laravel:
   - Clone o Laravel https://github.com/laravel/laravel.git

- 3. Laradock:
  - 3.1. Importante: 
       - Laradock vai ser utilizado em sua maquina. Nao subira para o repositorio.
       - Nao precisa clonar dentro da pasta do projeto Laravel, pode ser uma pasta fora
  
  - 3.2. Instalacao:
       - Clone o Laradock https://github.com/laradock/laradock
  
  - 3.3. Arquivo .env
       - Gere o arquivo .env (cp env-example .env)
 
4. Docker:
   Obs: Escolher as imagens que constam dentro do arquivo .env para criacao dos containers
   
   - docker-compose up -d nginx mysql phpmyadmin
   - Basta acessar o projeto passando na url localhost:"porta"

5. MYSQL:
   - localhost:"porta" (consta no .env, procurar por mysql)
   - user e senha padrao: root
   - Acessar config/database.php procurar pela estrutura do mysql e pegar qual o tipo de collation que o Laravel usa
   - Assim que estiver com a collation, criar o seu banco
   - Acessar o .env, procurar o MYSQL_DATABASE e colocar o nome do banco que voce criou na opcao anterior e o user e pass

6. Rodar o composer dentro do container docker:
   - docker-compose exec "nome container" bash
   - composer install 
   - php artisan migration
   - npm install && npm run dev (caso de erro por conta do dev, trocar para development)
      
       
       
       
       
