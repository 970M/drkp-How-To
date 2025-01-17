# ATEME cheat sheet

[README.md](README.md)


## Downgrade NEA-DVR

```
ENABLED=yes /usr/share/commands/upgrade @AFI
```


## EDS debbuging

### Test de la partition drdb :

```
cd /tmp 
mkdir toto
mount /dev/sde ./toto
ls toto
pgrep -alf storage
umount toto
parted /dev/drdb0 print
```

## NEA

### Redémarrache d'apache si trop chargé
```
regset apache_monitoring/threshold_restart 200
```


### Nettoyer les channels radicalement
```
cd /var/www/live/disk1
rm -rf *
```

### Prometheus/Grafana
```
ssh gdaguetdvr-grafana.ateme.net
su - ateme
cd /etc/prometheus
yamllint .
sudo service Prometheus reload
sudo -l
sudo service Prometheus restart
```

### Utiliser un Webplayer externe (proxy anevia)

Remplacer http:// par https://https-proxy.anevia.com/

http://172.27.114.45:80/live/disk1/ch_000/sa_dash/ch_000.mpd

==>

https://https-proxy.anevia.com/172.27.114.45:80/live/disk1/ch_000/sa_dash/ch_000.mpd

## Apache Server Status

[https://doc-rd.anevia.com/files/extract/NEA-DVR/master/configuration-keys.html#server-status]

[http://SERVER_IP/admin/server-status]
[https://nea-dvr-perf.lab1.anevia.com:8443/admin/server-status]

## Logging

### Log en chache du NEA

```
cd /var/log/anevia
```

### Log Consolidés du NEA

```
cd /mnt/streams0/anevia_logs
```
```
sl | grep -i error | tee "$(hostname)_$(date +'%Y%m%d_%H%M%S').log"
```
```
sl | grep -i error | tee "$(echo $test)_$(hostname)_$(date +'%Y%m%d_%H%M%S').log"
```
```
grep -i -e eds -e ext4 /var/log/anevia/system.log | cl
```

### Conserver les log dans un fichier

```
sl | grep -i error | tee "$(hostname)_$(date +'%Y%m%d_%H%M%S').log"
```


## Check service on host

```
watch -n2 "
/etc/init.d/apache-htcacheclean status;
/etc/init.d/apache2 status;
/etc/init.d/dbbackup-monitoring status;
/etc/init.d/db-monitoring status;
/etc/init.d/dvr-rest-api-server status;
/etc/init.d/edredon status
/etc/init.d/logd status;
/etc/init.d/monitoring-ott-live status;
/etc/init.d/monitoring-ott-npvr status;
/etc/init.d/pgbouncer status;
/etc/init.d/phanes-config-db-listener status;
/etc/init.d/phanes-recording-archive-manager status;
/etc/init.d/servicestatusd status;
/etc/init.d/drmgateway status
"
```


## Re-démarrer Apache

```
/etc/init.d/apache2 restart
```


## Accèder à corp.ateme.com ou arti

```
sudo mount -t cifs -v -o ro,username=gdaguet,password=<active_dir_pwd> //warehouse-vz.ateme.net/warehouse/ ./warehouse
```

## Variable registry 

### Commande de base
```
regget
regunset
regdump
```

### Activer le mode debug 

```
regset debug/server_status_enabled 1
```
```
regset debug/display_devel 1 && /etc/init.d/logd reload
```


## Modifier le fichier de configuration OTT

```
gron Anevia-NEA-DVR-PERF-2023-02-03_15-35-11.conf | sed "s/239.10.0.1/239.26.134.3/g" | gron -u | jq . | sponge NewConf.conf
```


## Media information

```
mediainfo */stream.ts | grep Duration
```


## Streamers


```
ssh root@qas-neadvr-streamer-2.lab1.anevia.com
```


```
cd ts-streamer-lg-1; ./docker-compose.sh up -d ; cd ../ts-streamer-lg-2; ./docker-compose.sh up -d ; cd ../ts-streamer-lg-3; ./docker-compose.sh up -d ; cd ../ts-streamer-lg-4; ./docker-compose.sh up -d ; cd ../ts-streamer-lg-5; ./docker-compose.sh up -d

cd ts-streamer-lg-1; ./docker-compose.sh down ; cd ../ts-streamer-lg-2; ./docker-compose.sh down ; cd ../ts-streamer-lg-3; ./docker-compose.sh down ; cd ../ts-streamer-lg-4; ./docker-compose.sh down ; cd ../ts-streamer-lg-5; ./docker-compose.sh down
```


## JQL

### Searching for TC in Testing Board

```
project = "NEA-DVR-SW" AND issueType = "Test Case" AND summary ~  "test_*1plus1"
```


## Tests : test-neadvr

```
pytest --config configs/gda-3.cfg tests/live/test_retry_report_portal.py --reportportal -o rp_api_key="gda-rp-token_rIFcluKnQe29aMZZoGlmok5kFlzoXqxl0glXxYKn7e_zkVC-u-C5EJ51ypSiUiYF" -o rp_launch="py:fw-st-live-dev" -o rp_endpoint="http://report-portal.ateme.net:8080" -o rp_launch_attributes=":DVR-14623 PLAN_ID:DVR-14041 VERSION:4.23.0 PIPELINE_TYPE:test-retry PRODUCT_TYPE:firmware"
```

### Lancer un pytest

```
pytest --config configs/gda.cfg test_file::test_case
```

```
cd ~/src/tests-neadvr/pytest
pytest --config configs/gda-3.cfg --test-environments firmware --priority_marker highest --feature_marker sa --collect-only tests
pytest --config configs/gda-3.cfg --test-environments firmware --collect-only tests
```

### Rechercher les tests qui ont des markers spécifiques

```
pytest --config configs/gda-3.cfg --test-environments firmware --feature_marker flaky,failed  --collect-only tests| grep '<Function' | sed -e 's/^ */%/g' | cut -d' ' -f2 | sed -e 's/>$//g' | sort

pytest --config configs/gda-3.cfg --test-environments firmware --feature_marker flaky,failed  --collect-only tests | grep '<Function' | sed -e 's/^ */%/g' | sed -e 's/n t/%t/g' | cut -d'%' -f3 | sed -e 's/>$//g' | sort

```

### Lancer un cypress

```
configure_host.py --config gda.cfg create-cypress-config-js
./scripts/configure_host.py --config pytest/configs/gda.cfg create-cypress-config-js
```

```
npx cypress run
```

To run in CLI and select a specific test:

```
npx cypress run --spec cypress/e2e/profiles/sa_create_edit.cy.js
```

To run in CLI and select several tests:

```
npx cypress run --spec cypress/e2e/profiles/*.cy.js
```

Use Google Chrome like browser is required for scrambled output. To select it, we must use this command:

```
npx cypress run --spec cypress/e2e/player/player_live.cy.js --browser chrome --headed
```

## How to push/pull a docker image on nexus-rennes?

Login to nexus-rennes
```
docker login -u <user> nexus-rennes.ateme.net:10444
```

Pull the external docker image in local docker pull <external_docker>
```
docker pull cypress/browsers:node-20.10.0-chrome-118.0.5993.88-1-ff-118.0.2-edge-118.0.2088.46-1
```

Tag the docker image docker tag <external_docker> <nexus_repositiry>:<tag>
```
docker tag cypress/browsers:node-20.10.0-chrome-118.0.5993.88-1-ff-118.0.2-edge-118.0.2088.46-1 nexus-rennes.ateme.net:10444/cypress/browsers:node20.10.0-chrome118
```

Push the docker on nexus repository
```
docker push nexus-rennes.ateme.net:10444/cypress/browsers:node20.10.0-chrome118
```


### Execute ateme-black (version nexus)
```
docker pull nexus-rennes.ateme.net:10444/open/python-conform
docker image ls
docker run -it 837d5fd94483
docker run -v /home/gdaguet/src/tests-neadvr/benchmark/scripts:/home 837d5fd94483 /usr/local/bin/ateme-black --check /home
docker run -v /home/gdaguet/src/tests-neadvr/benchmark/scripts:/home 837d5fd94483 /usr/local/bin/ateme-black /home
```




## VSCODE

Problème ouverture gedit dans vscode :

```
unset GTK_PATH
```



*_http://SERVER_IP/admin/server-status_*
