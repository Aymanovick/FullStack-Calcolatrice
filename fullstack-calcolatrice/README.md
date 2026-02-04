# Calcolatrice con pipeline di operazioni

## UV

installa uv da https://docs.astral.sh/uv/#installation

``` shell
uv venv
```

Attivare l'ambiente di sviluppo

``` shell
source .ve.v/bin/activate    (Linux/Mac)
.venv/Scripts/activate     (Windows)
```

## Utilizzo 

``` shell
uv run python calcolatrice.py
```

## Installazione dipendenze 

``` shell
uv pip compile fullstack-calcolatrice/requirements/requirements-test.in -o fullstack-calcolatrice/requirements/requirements-test.txt
uv pip compile fullstack-calcolatrice/requirements/requirements.in -o fullstack-calcolatrice/requirements/requirements.txt
uv pip install -r fullstack-calcolatrice/requirements/requirements-test.txt
uv pip install -r fullstack-calcolatrice/requirements/requirements.txt
```

## Utilizzo 

``` shell
uv run python fullstack-calcolatrice/calcolatrice.py
python3 calcolatrice.py
```

## Esecuzione test

``` shell
pytest -v
```

## Dockerfile

Per costruire un'immagine Docker

``` shell
docker build -f Dockerfile.debian -t calcolatrice:debian .
docker build -f Dockerfile -t calcolatrice:alpine .
```

Per eseguire il container 

``` shell
docker run -it --rm calcolatrice:local
docker run -it --rm calcolatrice:alpine
```

Per costruire l'immagine Docker e caricarla su Docker Hub

``` shell
docker build -f Dockerfile -t aymanovick/fullstack-calcolatrice:alpine .
docker push aymanovick/fullstack-calcolatrice:alpine
```

Per costruire un immagine multiarchitettura (windows: amd64 / Mac: arm64) e caricarla su Docker Hub

``` shell
docker buildx build --platform linux/amd64,linux/arm64 -f Dockerfile -t aymanovick/fullstack-calcolatrice:alpine --push .
```
