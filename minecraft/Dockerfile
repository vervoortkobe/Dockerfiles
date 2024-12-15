FROM openjdk:23-jdk-slim-bookworm
WORKDIR /data
COPY . /data/
EXPOSE 35565
RUN echo "eula=true" > eula.txt
CMD ["java", "-Xmx2G", "-Xms2G", "-jar", "minecraft-server.jar", "nogui"]