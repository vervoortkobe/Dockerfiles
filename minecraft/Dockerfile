FROM openjdk:23
COPY . .
WORKDIR /
EXPOSE 25565
RUN echo "eula=true" > eula.txt
CMD ["java", "-Xmx2G", "-Xms2G", "-jar", "minecraft-server.jar", "nogui"]