# laravel-laradock
Laravel + Laradock

- Introduçao:
   - Laravel com ambiente em laradock.

- Laravel:
   - Clone o Laravel https://github.com/laravel/laravel.git
   - Jogar os arquivos da pasta "laravel" para a raiz do projeto
   - Gere o arquivo .env (cp .env.example .env)

- Laradock:
  - Obs: 
       - Laradock vai ser utilizado dentro do seu projeto LARAVEL.
  - Instalacao:
       - Clone o Laradock https://github.com/laradock/laradock
       - Adicionar pasta do laradock no .gitignore pois iremos iniciar os containeres do docker acessando essa pasta, como vai ser local, nao subir a pasta
  - Arquivo .env (dentro da pasta laradock):
      - Gere o arquivo .env (cp .env.example .env)

- Criação do Container + Configuração
   - MYSQL (dentro do projeto laradock):
      - localhost:"porta" (consta no .env, procurar por mysql)
      - user e senha padrao: root
      - Acessar ./config/database.php procurar por "mysql":
         - collation = uft8mb4_unicode_ci
         - Utilizar os mesmos parametros que se encontrando no.env (.env == database.php):
            - DB_HOST=
            - DB_DATABASE=
            - DB_USERNAME=
            - DB_PASSWORD=
           
   - Docker:
      - Obs (dentro do projeto laradock): 
         - Escolher as imagens que constam dentro do arquivo .env para criacao dos containers
            - ex: docker-compose up -d nginx mysql phpmyadmin (passar as extensoes pois o laradock usa o proprio dockerfile, entao vc precisa especificar quais quer usar)
              
      - Rodar o composer dentro do container docker:
         - docker-compose exec --user=laradock workspace  bash
         - rm -rf vendor && composer install
         - php artisan key:generate
         - php artisan migrate
         - npm install && npm run dev (caso de erro por conta do dev, trocar para development)
         - Basta acessar o projeto passando na url localhost:"porta"
      
       
       
       
       
