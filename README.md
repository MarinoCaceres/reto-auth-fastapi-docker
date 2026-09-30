# auth-fastapi — módulo de identidad de referencia

Autenticación y autorización para el reto de TC2007B: **FastAPI + PostgreSQL**,
con el mismo contrato que `https://startdroid.com/api` (Práctica 6). La app de
Android de la práctica funciona contra este servidor cambiando solo `BASE_URL`.

Todo corre en Docker: la base, el servidor y, si lo pides, un túnel HTTPS.

    cp .env.example .env                   # y cambia JWT_SECRET y CODIGO_PROFESOR
    docker compose up -d                   # http://localhost:8000/docs
    bash smoke.sh                          # los 20 casos del contrato, con sus códigos
    docker compose --profile tunel up -d   # el túnel; su dirección sale en:
    docker compose logs tunel

`.env` nunca se sube al repositorio. `smoke.sh` lee de ahí el código de profesor.

La guía de lectura es el anexo del curso: https://startdroid.com/practicas/anexo-auth-docker
