
FROM python:3.8-slim

# Définition du répertoire de travail dans l'image
WORKDIR /app

# Copie du requirements.txt spécifique à cast-service dans le répertoire de travail
COPY ./requirements.txt .

# Installation des dépendances Python spécifiées dans requirements.txt
RUN apt-get update \
    && apt-get install gcc -y \
    && apt-get clean

RUN pip install -r requirements.txt \
    && rm -rf /root/.cache/pip

# Copie du reste des fichiers de l'application
COPY . .

# Commande par défaut pour démarrer l'application
CMD [ "python", "app.py" ]
