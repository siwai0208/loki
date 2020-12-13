# Loki and Grafana logging

git clone https://github.com/siwai0208/loki loki2

cd loki2

chown 472:472 grafana

docker-compose up 

docker-compose exec app composer create-project --prefer-dist laravel/laravel

docker-compose exec app bash

Your-Host-IP:3000

admin,admin

Setting->Data Source->Add data source->loki

http://loki:3100 -> Save & Test
