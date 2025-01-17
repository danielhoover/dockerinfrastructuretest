# dockerinfrastructuretest

Im Beispiel wollen wir verstehen wie docker run und docker compose funktioniert.

## Vorbedingungen / prerequesits

* Docker muss installiert sein und laufen.

## docker run

Ermöglicht es spezifische container zu starten. Dafür notwendig sind der Name des images und etwaige nötige optionen.

https://docs.docker.com/reference/cli/docker/container/run/

Im folgenden Beispiel starten wir eine Datenbank (mariadb)

```
docker run --name mariadbtest -e MYSQL_ROOT_PASSWORD=mypass -p 3306:3306 -d docker.io/library/mariadb:10.3
```

Startet das image mariadb in der Version 10.3 der Port 3306 wird auf den Host Port 3306 gemapped. (verfügbar gemacht) -d sagt, dass das ganze im Hintergrund ausgeführt werden soll und gibt die Container ID aus. (im anderen Fall würde die Shell blockiert sein) MYSQL_ROOT_PASSWORD ist eine Option die wir setzten müssen, damit wir eine Chance hätten uns als root anzumelden.

Was nutzt uns das?

Sollten wir in der Entwicklung mariadb nutzen müsste (ohne Docker) jemand in der Firma am entsprechenden Rechner z.B. im Falle von Windows folgende Schritte durchführen https://mariadb.com/kb/en/installing-mariadb-msi-packages-on-windows/

Seite vom image im docker hub https://hub.docker.com/_/mariadb
