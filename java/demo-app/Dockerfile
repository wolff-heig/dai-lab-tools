# Utilise l'image officielle "alpine:latest", qui est une distribution Linux légère.
# Elle est couramment utilisée dans Docker pour créer des images compactes et efficaces.
FROM alpine:latest

# Installe OpenJDK version 21 à partir des dépôts de paquets APK, sans utiliser de cache local
# pour réduire la taille de l'image. Le "--no-cache" permet de ne pas stocker les métadonnées
# du gestionnaire de paquets, ce qui garde l'image légère.
RUN apk add --no-cache openjdk21

# Définit le répertoire de travail à "/app" à l'intérieur du conteneur.
# Ce sera le répertoire où les prochaines commandes seront exécutées.
WORKDIR /app

# Copie le fichier `.jar` généré par Maven depuis le répertoire `target/`
# de mon système hôte vers le répertoire `/app/` du conteneur.
# Le fichier `.jar` copié sera renommé "app.jar".
COPY target/*.jar /app/app.jar

# Définit la commande par défaut qui sera exécutée lorsque le conteneur démarrera.
# Ici, il exécute l'application Java en démarrant le fichier JAR avec "java -jar".
CMD ["java", "-jar", "app.jar"]
