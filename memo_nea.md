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
cd ts-streamer-lg-1; ./docker-compose.sh up -d ; cd ../ts-streamer-lg-2; ./docker-compose.sh up -d ; cd ../ts-streamer-lg-3; ./docker-compose.sh up -d ; cd ../ts-streamer-lg-4; ./docker-compose.sh up -d ; cd ../ts-streamer-lg-5; ./docker-compose.sh up -d

cd ts-streamer-lg-1; ./docker-compose.sh down ; cd ../ts-streamer-lg-2; ./docker-compose.sh down ; cd ../ts-streamer-lg-3; ./docker-compose.sh down ; cd ../ts-streamer-lg-4; ./docker-compose.sh down ; cd ../ts-streamer-lg-5; ./docker-compose.sh down
```


## JQL

### Searching for TC in Testing Board

```
project = "NEA-DVR-SW" AND issueType = "Test Case" AND summary ~  "test_*1plus1"
```


## test-neadvr

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

## VSCODE

Problème ouverture gedit dans vscode :

```
unset GTK_PATH
```



*_http://SERVER_IP/admin/server-status_*