# MsBanqueApplication - Spring Boot @RestController

Ce projet est une application Spring Boot démontrant la création de services RESTful avec `@RestController`, l'utilisation de Spring Data JPA avec une base de données H2 en mémoire, et le support des formats JSON et XML.

## Fonctionnalités
- **CRUD complet** pour la gestion des comptes bancaires.
- **Support multi-format** : JSON et XML via les en-têtes `Accept` et `Content-Type`.
- **Base de données H2** : Base de données en mémoire avec console d'administration.
- **Documentation OpenAPI** : Intégration de Swagger UI pour tester les endpoints.
- **Lombok** : Utilisation de Lombok pour réduire le code boilerplate (Getters, Setters, etc.).

## Structure du Projet
Le projet suit une architecture standard en couches :
- `ma.rest.spring.entities` : Contient l'entité `Compte` et l'énumération `TypeCompte`.
- `ma.rest.spring.repositories` : Contient l'interface `CompteRepository`.
- `ma.rest.spring.controllers` : Contient le `CompteController` gérant les requêtes REST.
- `ma.rest.spring` : Classe principale `MsBanqueApplication` avec initialisation des données.

## Configuration
L'application est configurée sur le port **8082**.
La base de données H2 est accessible via : `http://localhost:8082/h2-console`
- **JDBC URL** : `jdbc:h2:mem:banque`
- **User** : `sa`
- **Password** : *(vide)*

## Documentation API
Une fois l'application lancée, la documentation interactive Swagger est disponible à l'adresse :
`http://localhost:8082/swagger-ui.html`

## Tests des Endpoints
Vous pouvez tester les endpoints avec `curl`, Postman ou SoapUI.

### Exemples de requêtes
- **Liste des comptes (JSON)** :
  ```bash
  curl -X GET "http://localhost:8082/banque/comptes" -H "Accept: application/json"
  ```
- **Liste des comptes (XML)** :
  ```bash
  curl -X GET "http://localhost:8082/banque/comptes" -H "Accept: application/xml"
  ```
- **Création d'un compte** :
  ```bash
  curl -X POST "http://localhost:8082/banque/comptes" -H "Content-Type: application/json" -d '{"solde": 1500.0, "dateCreation": "2024-11-01", "type": "COURANT"}'
  ```

## Captures d'écran
*(Note: Les captures d'écran ci-dessous illustrent le fonctionnement de l'application)*

1. **Structure du projet**
2. **Console H2 - Visualisation des données**
3. **Swagger UI - Documentation des endpoints**
4. **Réponse XML via SoapUI**
5. **Réponse JSON via SoapUI**

## Prérequis
- Java 17+
- Maven 3.6+
