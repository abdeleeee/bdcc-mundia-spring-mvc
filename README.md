# bdcc-mundia-spring-mvc

Application web **Spring MVC** construite avec **Spring Boot 4.1.2** et **Java 21**. Elle utilise Thymeleaf pour les vues, Spring Data JPA pour la persistance et Spring Security pour l'authentification et l'autorisation.

## Technologies

| Domaine | Technologie |
|---|---|
| Langage | Java 21 |
| Framework | Spring Boot 4.1.2 (Spring MVC) |
| Persistance | Spring Data JPA |
| Sécurité | Spring Security 6 + `thymeleaf-extras-springsecurity6` |
| Vues | Thymeleaf + Thymeleaf Layout Dialect |
| Validation | Spring Boot Starter Validation |
| Interface | Bootstrap 5.3.8 (WebJar) |
| Bases de données | H2 (développement, avec console) et MySQL (production) |
| Utilitaires | Lombok |
| Build | Maven (Maven Wrapper inclus) |

## Prérequis

- JDK 21
- Maven 3.9+ (facultatif, le wrapper `mvnw` est fourni)
- MySQL (uniquement si vous utilisez le profil MySQL)

## Installation et lancement

Cloner le dépôt puis, à la racine du projet :

```bash
# Linux / macOS
./mvnw spring-boot:run

# Windows
mvnw.cmd spring-boot:run
```

L'application est ensuite accessible sur http://localhost:8080.

### Compiler et exécuter le JAR

```bash
./mvnw clean package
java -jar target/bdcc-mundia-spring-mvc-0.0.1-SNAPSHOT.jar
```

### Lancer les tests

```bash
./mvnw test
```

## Configuration

La configuration se trouve dans `src/main/resources/application.properties`.

### H2 (développement)

```properties
spring.datasource.url=jdbc:h2:mem:testdb
spring.h2.console.enabled=true
spring.jpa.hibernate.ddl-auto=update
```

La console H2 est disponible sur `/h2-console`.

### MySQL

```properties
spring.datasource.url=jdbc:mysql://localhost:3306/ma_base
spring.datasource.username=root
spring.datasource.password=votre_mot_de_passe
spring.jpa.hibernate.ddl-auto=update
```

Adaptez le nom de la base et les identifiants à votre environnement.

## Structure du projet

```
src/
├── main/
│   ├── java/net/abdel/...      # Code source (contrôleurs, entités, repositories, sécurité)
│   └── resources/
│       ├── templates/          # Vues Thymeleaf
│       ├── static/             # Ressources statiques
│       └── application.properties
└── test/                       # Tests
```

## Documentation utile

- [Spring Boot](https://docs.spring.io/spring-boot/4.1.2/reference/)
- [Spring Data JPA](https://docs.spring.io/spring-boot/4.1.2/reference/data/sql.html#data.sql.jpa-and-spring-data)
- [Spring Security](https://docs.spring.io/spring-boot/4.1.2/reference/web/spring-security.html)
- [Thymeleaf](https://www.thymeleaf.org/documentation.html)
- [Bootstrap 5](https://getbootstrap.com/docs/5.3/)

