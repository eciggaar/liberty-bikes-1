FROM openliberty/open-liberty:19.0.0.12-kernel-java11-openj9-ubi
ADD --chown=1001:0 build/libs/auth-service.war /config/dropins
COPY --chown=1001:0 src/main/liberty/config /config/
RUN printf 'frontend_url=http://lb-frontend:12000/login\n\
auth_url=https://lb-auth:8082/auth-service' > /config/server.env
RUN printf 'httpPort=8082\n\
httpsPort=8482' > /config/bootstrap.properties

EXPOSE 8082 8482