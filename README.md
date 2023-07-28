# keycloak-simple-setup

Dieses Repository enthält Docker-Compose Dateien für ein Testsetup von Keycloak im Verbund mit dem Reverse-Proxy Caddy, so wie im Artikel "Passkey-Pionier,  So ergänzen Sie Passkey-Logins in eigenen Webdiensten" beschrieben, der in [c't 18/2023](https://www.heise.de/select/ct/2023/18/2317312461291282951) erschienen ist. Auf Ihrem Linux-Host muss Docker installiert sein und Sie müssen einen DNS-Eintrag, beispielsweise keycloak.example.com setzen, der auf die IP-Adresse Ihres Servers zeigt. 

Klonen Sie zur Installation dieses Repository und navigieren dann in das Verzeichnis keycloak-simple-setup.

Legen Sie anschließend das Docker-Netzwerk "proxy" an:

```
docker network create proxy
```

Tragen Sie dann Ihre Domain in der Datei /caddy/config/Caddyfile ein und passen Sie die Einträge in der Datei /keycloak/.env an. Starten Sie dann dann sowohl Caddy als auch Keycloak, indem Sie `docker compose up -d` im Ordner caddy und im Ordner keycloak ausführen.

