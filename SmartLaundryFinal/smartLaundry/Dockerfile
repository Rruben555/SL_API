# Tahap 1: Build project menggunakan Maven
FROM openjdk:17-jdk-slim AS build
COPY . .
RUN chmod +x smartLaundry/mvnw
RUN cd smartLaundry && ./mvnw clean package -DskipTests

# Tahap 2: Jalankan aplikasi menggunakan OpenJDK
FROM openjdk:17-jdk-slim
COPY --from=build smartLaundry/target/*.jar app.jar
EXPOSE 8080
ENTRYPOINT ["java", "-jar", "app.jar"]
