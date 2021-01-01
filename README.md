# Loki and Grafana logging

## **About**

Docker環境向けのLokiロギング＋Grafana可視化

## **Inside Package**
* loki
* promtail
* grafana
* web nginx:latest
* app php:7.3-fpm
* db  mysql:5.7

## **How to use**

1. clone the repository
```
$ git clone https://github.com/siwai0208/loki
```

2. chown grafana directory
```
$ sudo chown -R 472:472 grafana
```

3. up docker-compose
```
$ docker-compose up
```

4. confirm container status by docker-compose ps
```
$ docker-compose ps
loki_app_1        docker-php-entrypoint php-fpm    Up      9000/tcp
loki_grafana_1    /run.sh                          Up      0.0.0.0:3000->3000/tcp
loki_loki_1       /usr/bin/loki -config.file ...   Up      0.0.0.0:3100->3100/tcp
loki_mysql_1      docker-entrypoint.sh mysqld      Up      0.0.0.0:3306->3306/tcp, 33060/tcp
loki_promtail_1   /usr/bin/promtail -config. ...   Up
loki_web_1        /docker-entrypoint.sh ngin ...   Up      0.0.0.0:8000->80/tcp
```

5. Access via web browser

Grafana: x.x.x.x:3000 (default login username : admin password : admin)

![grafana](https://user-images.githubusercontent.com/53518005/103404535-7ffe3880-4b86-11eb-8bd3-7e89c89ff742.PNG)

6. Add Loki Data Source

Setting->Data Source->Add data source->loki

![grafana](https://user-images.githubusercontent.com/53518005/103442343-e4ed8780-4c87-11eb-9385-a01aeceba3e1.PNG)

add URL http://loki:3100 and "Save & Test"

![grafana](https://user-images.githubusercontent.com/53518005/103442345-e4ed8780-4c87-11eb-9427-e438a834a89f.PNG)


Dashboard Sample on Grafana

![grafana](https://user-images.githubusercontent.com/53518005/103442336-e1f29700-4c87-11eb-897e-fb5088312538.PNG)



7. (Option) Continue to setup laravel application, see [Here](https://github.com/siwai0208/food-app)
