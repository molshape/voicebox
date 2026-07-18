# Docker-Image aktualisieren

Um ein aktualisiertes Docker-Image zu erstellen, muss das geforkte Repository zunächst mit dem original Repository aktualisiert werden:

    git switch main
    git fetch upstream
    git merge upstream/main

Anschließend kann auf den Branch `local-main` mit den lokalen Anpassungen gewechselt (enthält z. B. diese `docker-compose.update.md` Datei, sowie die personalisierte `docker-compose.yml`) und die Änderungen von `main` gemerget werden:

    git switch local-main
    git merge main

Danach kann das Docker-Image neu gebaut und hochgefahren werden:

    docker compose up -d --build

Zuletzt kann der Fork auf GitHub aktualisiert werden:

    git push
    git switch main
    git push
