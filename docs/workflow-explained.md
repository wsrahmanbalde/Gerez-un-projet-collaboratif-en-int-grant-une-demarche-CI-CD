# 📦 CI/CD – Documentation Technique pour BobApp

## 🔁 Pipeline GitHub Actions

Le pipeline CI/CD est déclenché à chaque `push` ou `pull request` sur la branche `main`.  
Il est composé de **4 étapes principales** :

### 1. ✅ Tests Backend + Rapport de couverture
- Lance les tests unitaires Java (Junit + Maven)
- Génére un rapport de couverture avec JaCoCo
- Résultat : `/target/site/jacoco/index.html`

### 2. ✅ Tests Frontend Angular
- Lance les tests avec `ng test` en mode headless
- Génére un rapport de couverture dans `/coverage/`

### 3. ✅ Analyse de qualité via SonarCloud
- Vérifie les bugs, code smells, duplications, complexité, dette technique…
- Basée sur le code backend uniquement (front possible avec config plus poussée)
- Analyse hébergée : [https://sonarcloud.io](https://sonarcloud.io)

### 4. ✅ Déploiement Docker automatique
- Build + push des images `bobapp-front` et `bobapp-back` sur Docker Hub
- Le déploiement **n'est exécuté que si les tests et la qualité sont valides**

---

## 🛠️ Outils utilisés

| Outil         | Utilité                                       |
|---------------|-----------------------------------------------|
| GitHub Actions| CI/CD (intégration et déploiement continus)   |
| Maven         | Build + gestion des tests backend             |
| JaCoCo        | Couverture de test backend                    |
| Angular CLI   | Tests et build frontend                       |
| SonarCloud    | Analyse qualité du code (via SonarQube Cloud) |
| Docker & Hub  | Conteneurisation & dépôt des images           |

---

## 📊 KPIs Qualité Proposés (Quality Gates)

| Indicateur                        | Seuil souhaité     | Objectif métier                        |
|----------------------------------|---------------------|----------------------------------------|
| ✅ Taux de couverture des tests   | **≥ 80 %**          | Maintenir un haut niveau de fiabilité  |
| 🚫 Nombre de **New Blocker Issues** | **= 0**              | Aucun blocage sur le code livré        |
| 📉 Code Smells autorisés         | < 5 par PR         | Réduction de la dette technique        |

---

## 📈 Métriques obtenues (exemple réel à adapter)

| Analyse        | Valeur obtenue          |
|----------------|-------------------------|
| Coverage back  | 72 %                    |
| New Issues     | 1 minor, 0 blocker      |
| Bugs           | 0                       |
| Code Smells    | 4                       |
| Duplications   | 0.0 %                   |

📌 À noter : couverture encore insuffisante (objectif : 80 %), mais bonne stabilité.

---

## 📢 Analyse des retours utilisateurs

🎤 **Retour #1** :  
_"Le bouton de suggestion plante le navigateur"_  
→ Reproduction du bug en test manuel, crash lié à une boucle infinie JS côté front.

🎤 **Retour #2** :  
_"Les bugs restent en ligne plusieurs semaines"_  
→ Manque de suivi. La CI/CD + Sonar permet d’automatiser la détection dès la PR.

🎤 **Retour #3** :  
_"Aucune réponse après signalement"_  
→ Nécessité d’un **template de ticket GitHub**, suivi avec labels `bug`, `feature`.

---

## 🔧 Recommandations immédiates pour Bob

1. **Fixer la couverture de test à 80 % minimum**
    - Ajouter tests unitaires sur composants critiques
2. **Corriger les “code smells” détectés dans SonarCloud**
3. **Ajouter un template d’issue GitHub pour remonter les bugs**
4. **Mettre en place un label `priorité` sur les tickets**
5. **Documenter dans le README comment contribuer au projet (CONTRIBUTING.md)**

---

📎 CI/CD opérationnelle et automatisée.  
📢 Prochaine étape : **mobiliser la communauté open source** !