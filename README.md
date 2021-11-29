Les étapes de création d'un micro service (Inventory Service):
-----------------------------------
Création classe "Product.java" avec les attributs nécessaires + les annotations nécessaires JPA(@Entity @Data @AllArgsConstructor @NoArgsConstructor @ToString)

-----------------------------------
Création du Repository "ProductRepository.java" qui heritera de l'interface JpaRepositroy + l'annotation (@RepositoryRestResource). 
@RepositoryRestResource crée le service HATEOAS avec Spring JPA et les opérations seront exposées au format HATEOAS.

-----------------------------------
Configuration application.properties où on mentionne : 
-Port du server 8082.
-Nom du micro service en cours => de préference en majuscule pour qu'il soit détecté par le gateway(INVENTORY-SERVICE).
-La base de donnée 
-L'activation du cloud discovery.

-----------------------------------
L'application est testé par CommandLineRunner est une interface Spring Boot simple avec une méthode run .
Spring Boot appellera automatiquement la méthode run de tous les beans implémentant cette interface une fois le contexte de l'application chargé.
Les dépendances nécessaires: 
-Spring web
-Spring Data JPA 
-H2 DataBase 
-RestRepositories
-Lombok 
-Spring Boot DevTools 
-Eureka Discovery Client
-Spring Boot Actuator
