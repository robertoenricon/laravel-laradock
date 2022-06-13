# laravel-laradock
Laravel + Laradock

- Introduçao:
   - Laravel com ambiente em laradock.

- Laravel:
   - Clone o Laravel https://github.com/laravel/laravel.git
   - Arquivo .env:
      - Gere o arquivo .env (cp .env.example .env)

- Laradock:
  - Obs: 
       - Laradock vai ser utilizado em sua maquina. Nao subira para o repositorio.
       - Nao precisa clonar dentro da pasta do projeto Laravel, pode ser uma pasta fora
  - Instalacao:
       - Clone o Laradock https://github.com/laradock/laradock
  - Arquivo .env:
      - Gere o arquivo .env (cp .env.example .env)

- Criação do Container + Configuração
   - Docker:
      - Obs (dentro do projeto laradock): 
         - Escolher as imagens que constam dentro do arquivo .env para criacao dos containers
         - ex: docker-compose up -d nginx mysql phpmyadmin
         - Basta acessar o projeto passando na url localhost:"porta"

   - MYSQL:
      - localhost:"porta" (consta no .env, procurar por mysql)
      - user e senha padrao: root
      - Acessar config/database.php procurar pela estrutura do mysql e pegar qual o tipo de collation que o Laravel usa
      - Assim que estiver com a collation, criar o seu banco
      - Acessar o .env, procurar o MYSQL_DATABASE e colocar o nome do banco que voce criou na opcao anterior e o user e pass

   - Rodar o composer dentro do container docker:
      - docker-compose exec "nome container" bash (dentro do arquivo .env "COMPOSE_PROJECT_NAME" = nome do container)
      - composer install 
      - php artisan migration
      - npm install && npm run dev (caso de erro por conta do dev, trocar para development)
      
       
       
       
       
