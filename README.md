# 🤖 BobApp – CI/CD Automatisée pour l'application de blagues

Bienvenue sur le projet **BobApp** !  
Cette application propose une blague par jour, mais avait besoin d’un bon coup de boost côté qualité et déploiement.  
Ce repo met en place une **pipeline CI/CD complète** pour automatiser les tests, la qualité et le déploiement.

---

## 🚀 Fonctionnalités du projet

- Front-end : Angular (v14+) 🎨
- Back-end : Spring Boot + Java 11 🔧
- Tests unitaires & couverture (JaCoCo, Angular Coverage) ✅
- Analyse de qualité automatisée via SonarCloud 🧠
- Déploiement Docker (backend + frontend) 🐳

---

## 🧪 Lancer le projet en local

### Backend
```bash
cd back
mvn clean install
mvn spring-boot:run

Frontend
cd front
npm install
npm run start

Utilisation avec Docker
Build:
docker build -t bobapp-back ./back
docker build -t bobapp-front ./front

Lancer les conteneurs:
docker run -p 8080:8080 bobapp-back
docker run -p 4200:4200 bobapp-front

Pipeline CI/CD (GitHub Actions):

Étape                                      Description
tests-backend                          Tests Java + JaCoCo                         
tests-frontend                         Tests Angular + couverture
quality                                Analyse SonarCloud (qualité + dette technique)
deploy                                 Build + push sur Docker Hub


## Tous les détails dans le fichier docs/workflow-explained.md

Liens utiles:
   SonarCloud :  https://sonarcloud.io/project/overview?id=wsrahmanbalde_Gerez-un-projet-collaboratif-en-int-grant-une-demarche-CI-CD
   Rapport de couverture JaCoCo : back/target/site/jacoco/index.html
   Rapport coverage Angular : front/coverage/index.html

Docker Hub :
   bobapp-front: lien
   bobapp-back: lien

    •   Couverture de test : ≥ 80 %
	•	New Blocker Issues : 0
	•	Réduction de la dette technique
	•	Déploiement uniquement si tous les tests et analyses sont OK

Contribution:
    Les contributions sont les bienvenues !
    Merci de créer une issue ou une pull request avec des tests si possible.

Contact:
    Projet maintenu dans le cadre d’une mission pour OpenClassrooms.
    Développé par : BALDE Abdourahamane