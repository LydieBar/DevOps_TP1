# Première étape : Compilation avec JDK
FROM eclipse-temurin:17-jdk-alpine as builder

# Copiez le code source (Main.java) dans le conteneur
COPY Main.java /usr/src/Main.java

# Compilez le code source pour générer le bytecode (Main.class)
RUN javac /usr/src/Main.java

# Deuxième étape : Exécution avec JRE
FROM eclipse-temurin:17-jre-alpine

# Copiez le fichier Main.class depuis la première étape
COPY --from=builder /usr/src/Main.class .

# Définissez le répertoire de travail
WORKDIR /app

# Commande pour exécuter l'application Java
CMD ["java", "Main"]
