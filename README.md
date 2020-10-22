# INFO

W przypadku gdyby nie chciało wstawać to dodac ramu do kontenerów


W przypadku gdyby nie chciało wstawać a uruchamiasz na wsl a nie na hyperv, jak na linux to tylko 2 komenda

```
wsl -d docker-desktop
echo 262144 >> /proc/sys/vm/max_map_count
```

i restart docker

# URUCHOMIENIE

w folderze gdzie jest docker-compose.yml

```
docker-compose up --force-recreate
```

lub jeżeli chcemy uruchomić w tle

```
docker-compose up -d --force-recreate
```

# WYŁĄCZANIE Z CZYSZCZENIEM

w folderze gdzie jest docker-compose.yml

```
docker-compose down  --remove-orphans --volumes
```

Czyszczenie wszystkich kontenerów i volumes
```
docker rm -f $(docker ps -a -q)
docker volume rm $(docker volume ls -q)
```

# KIBANA

Po uruchomieniu usług wejdź na:

[http://localhost:5601/](http://localhost:5601/)


| User        | Password           
| ------------- |:-------------:|
| elastic    | playground

&nbsp;

> Po zalogowaniu można wybrać "try our examples data"
i potestować sobie jak to wygląda jak są już jakieś dane np. "Sample web logs"
