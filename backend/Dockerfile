FROM maven AS backend
WORKDIR /app
COPY . .
RUN mvn package
RUN mv target/*.jar App.jar

FROM eclipse-temurin:21-alpine
WORKDIR /build
COPY --from=backend /app/App.jar .
CMD ["java","-jar","App.jar"]
EXPOSE 8080
