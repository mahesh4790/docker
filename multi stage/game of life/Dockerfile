FROM maven:3-jdk-8 AS mvn 
RUN git clone https://github.com/wakaleo/game-of-life.git && cd game-of-life && mvn package

FROM openjdk:8
LABEL author="mahesh"
COPY --from=mvn /game-of-life/gameoflife-web/target/gameoflife.war /usr/local/tomcat/webapps/gameoflife.war
EXPOSE 8080