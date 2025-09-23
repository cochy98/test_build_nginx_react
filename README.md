## Scopo
Questo test è stato effettuato in data 22/09/2025. Ha lo scopo di rendere disponibile sul web un'app React già compilata.

## Panoramica
L'app viene servita tramite un container Nginx esposto sulla porta 80.

## Requisiti
- Docker e Docker Compose installati

## Avvio rapido
1. Verifica i file presenti (`build/`, `nginx/default.conf`, `docker-compose.yml`).
2. Avvia lo stack:

```bash
docker compose up -d
```

3. Apri il browser su `http://localhost` (porta 80).

## Struttura del progetto (sintesi)
```text
build/                # output statico dell'app React (già compilata)
nginx/default.conf    # configurazione virtual host Nginx
docker-compose.yml    # definizione dei servizi/container
```

## Configurazione Nginx
- Il file `nginx/default.conf` punta alla directory `build/` come root dei contenuti statici.
- Assicurati che i percorsi per gli asset (CSS/JS) siano relativi o gestiti correttamente per SPA.

## Note
- Se la porta 80 è occupata, modifica la mappatura porte in `docker-compose.yml` (es. `8080:80`) e apri `http://localhost:8080`.
- Importante: questo setup è pensato per test/sviluppo e non è ottimizzato per ambienti di produzione (mancano hardening Nginx, HTTPS/HTTP2, caching e compressione avanzate, header di sicurezza, log/monitoring, scaling e CI/CD). Valuta di aggiungere questi aspetti prima del go-live.