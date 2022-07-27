# docker_laravel

(参考サイト)
【超入門】20 分で Laravel 開発環境を爆速構築する Docker ハンズオン、「https://qiita.com/ucan-lab/items/56c9dc3cf2e6762672f4」、2022/03/14更新

<page>
・http://localhost:8080/   [webpage]
・127.0.0.1:8090  [phpadmin]

<git clone 時に行うこと>
(1)[mac] docker compose exec app bash
(2)[app] chmod -R 777 storage bootstrap/cache
(3)[app] composer install
(4)[app] cp .env.example .env
(5)[app] php artisan key:generate
(6)[app] php artisan storage:link
(7)[app] php artisan migrate
(8)[app] exit

<laravel の処理はどう行うのか？>
[docker compose exec app <コード>']
or
[docker compose exec app bash
<コード> ]

<docker 起動時の処理>
docker compose up -d (-d オプションはバックグラウンドで起動)
//データベースのマイグレーション
php artisan migrate

<全削除>
docker compose down --rmi all --volumes --remove-orphans
