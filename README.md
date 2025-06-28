# BobApp – Pipeline CI/CD complète pour une app de blagues

Bienvenue sur **BobApp** !  
Cette application propose une blague du jour, mais avait besoin d'une **industrialisation** moderne pour assurer sa qualité, sa fiabilité et son déploiement automatisé.  
Ce repository met en place une **CI/CD professionnelle** avec GitHub Actions, Docker, SonarCloud et des tests complets.

---

## Technologies utilisées

| Côté              | Techno                             |
|-------------------|-------------------------------------|
| Front-end         | Angular (v14+)                      |
| Back-end          | Spring Boot + Java 11              |
| Qualité code      | SonarCloud                         |
| Tests back        | JUnit + JaCoCo                     |
| Tests front       | Angular CLI + Coverage             |
| Conteneurisation  | Docker (backend & frontend)        |
| CI/CD             | GitHub Actions                     |

---

## Lancement du projet en local

### ▶Backend

\`\`\`bash
cd back
mvn clean install
mvn spring-boot:run
\`\`\`

### ▶Frontend

\`\`\`bash
cd front
npm install
npm run start
\`\`\`

---

## Utilisation avec Docker

### Build des conteneurs

\`\`\`bash
docker build -t bobapp-back ./back
docker build -t bobapp-front ./front
\`\`\`

### ▶Exécution des conteneurs

\`\`\`bash
docker run -p 8080:8080 --name bobapp-back -d bobapp-back
docker run -p 4200:4200 --name bobapp-front -d bobapp-front
\`\`\`

---

## Workflows GitHub Actions (CI/CD)

Chaque étape est automatisée et s’exécute sur les branches `main` :

| Étape         | Description                                               |
|---------------|-----------------------------------------------------------|
| `tests.yml`   | Exécution des tests unitaires backend & frontend          |
| `quality.yml` | Analyse de la qualité de code via **SonarCloud**          |
| `docker.yml` | Build & push des images Docker vers **Docker Hub**        |
| `ci.yml`    | Pipeline de base – validation de déclenchement CI/CD      |

**Le déploiement sur Docker Hub ne s’exécute que si tous les tests et la qualité passent.**

---

## Indicateurs clés (KPI)

- **Couverture de tests minimum** : `80 %`
- **Nouveaux bugs bloquants (New Blocker Issues)** : `0`
- **Dette technique maîtrisée**
- **Déploiement uniquement si tout est vert**

---

## Liens utiles

- **SonarCloud** :  
  [Lien vers le projet](https://sonarcloud.io/project/overview?id=wsrahmanbalde_Gerez-un-projet-collaboratif-en-int-grant-une-demarche-CI-CD)

- **Rapports de couverture** :
   - Back-end (JaCoCo) : `back/target/site/jacoco/index.html`
   - Front-end (Angular Coverage) : `front/coverage/index.html`

- **Images Docker** :
   - `bobapp-front` : [Lien Docker Hub – à compléter]
   - `bobapp-back` : [Lien Docker Hub – à compléter]

---

## Contribution

Les contributions sont les bienvenues !  
Merci de :
- Créer une *issue* pour décrire un problème ou une idée,
- Proposer une *pull request* incluant des tests si possible.

---

## Auteur

Développé par **BALDE Abdourahamane**  
Dans le cadre du projet OpenClassrooms – _Gérez un projet collaboratif en intégrant une démarche CI/CD_.
