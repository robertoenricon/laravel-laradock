# laravel-laradock
Laravel + Laradock

- Introduçao:
   - Laravel com ambiente em laradock.

- Laravel:
   - Clone o Laravel https://github.com/laravel/laravel.git
   - Gere o arquivo .env (cp .env.example .env)

- Laradock:
  - Obs: 
       - Laradock vai ser utilizado dentro do seu projeto LARAVEL.
  - Instalacao:
       - Clone o Laradock https://github.com/laradock/laradock
       - Adicionar pasta do laradock no .gitignore pois iremos iniciar os containeres do docker acessando essa pasta, como vai ser local, nao subir a pasta
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
      - Acessar ./config/database.php procurar pela estrutura do mysql e pegar qual o tipo de collation que o Laravel usa
      - Assim que estiver com a collation, criar o seu banco
      - Acessar o .env (raiz do projeto), procurar o DB_DATABASE:
         - DB_HOST=mysql
         - DB_USERNAME=root
         - DB_PASSWORD=root

   - Rodar o composer dentro do container docker:
      - docker-compose exec --user=laradock workspace  bash
      - rm -rf vendor && composer install
      - php artisan key:generate
      - php artisan migrate
      - npm install && npm run dev (caso de erro por conta do dev, trocar para development)
      
       
       
       
       
