# LaravelJWT
Projeto em Laravel, usando Dokcer,Nginx,Mysql e Redis

[*] FIX MEMMORY LEAK MYSQL:5.7.22

### Passo a passo
Clone Repositório (opcional)
```sh
git clone https://github.com/baku01/LaravelJWT
```

Clone os Arquivos do Laravel (opcional)
```sh
git clone https://github.com/laravel/laravel.git app-laravel
```

Copie os arquivos docker-compose.yml, Dockerfile e o diretório docker/ para o seu projeto (opcional)
```sh
cp -rf setup-docker-laravel/* app-laravel/
```
```sh
cd app-laravel/
```


Crie o Arquivo .env 
```sh
cp env.example .env
```


Atualize as variáveis de ambiente do arquivo .env
```dosini
APP_NAME="laravel"
APP_URL=http://localhost:80

DB_CONNECTION=mysql
DB_HOST=db
DB_PORT=3306
DB_DATABASE=laravel
DB_USERNAME=root
DB_PASSWORD=root

CACHE_DRIVER=redis
QUEUE_CONNECTION=redis
SESSION_DRIVER=redis

REDIS_HOST=redis
REDIS_PASSWORD=null
REDIS_PORT=6379
```


Suba os containers do projeto
```sh
docker-compose up -d
```

### Dentro do docker principal 

Acessar o container
```sh
docker-compose exec app bash
```

Instalar as dependências do projeto
```sh
composer install
```

Gerar a key do projeto Laravel
```sh
php artisan key:generate
```

Adicionar secret JWT
```sh
php artisan jwt:secret
```

Adicionar tabelas
```sh
php artisan migrate
```

Adicionar úsuario para teste do db
```sh
php artisan db:seed
```




Acessar o projeto
[http://localhost:80](http://localhost:80)
