FROM openjdk:11

RUN mkdir -p /opt/shinyproxy/
RUN wget https://www.shinyproxy.io/downloads/shinyproxy-2.6.1.jar -O /opt/shinyproxy/shinyproxy.jar
COPY application.yml /opt/shinyproxy/application.yml

WORKDIR /opt/shinyproxy/

EXPOSE 8080
CMD ["java", "-jar", "/opt/shinyproxy/shinyproxy.jar"]