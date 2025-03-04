# 🚀 Automatisation de la Configuration Jenkins avec JCasC et Docker

## 📌 Description
Ce projet vise à automatiser la configuration de Jenkins en utilisant **Jenkins Configuration as Code (JCasC)** et **Docker**. L'objectif est d'améliorer la résilience, la portabilité et la reproductibilité des environnements CI/CD.

## 🎯 Objectifs
- Automatiser la configuration de Jenkins avec **JCasC**.
- Assurer une meilleure **résilience** en rendant la configuration indépendante de l’infrastructure physique.
- **Faciliter le déploiement** en utilisant **Docker**.
- Sécuriser les informations sensibles via des **variables d’environnement** et des **fichiers secrets**.

## 🛠 Technologies utilisées
- **Jenkins** : CI/CD automation
- **Jenkins Configuration as Code (JCasC)** : Gestion de la configuration via un fichier YAML
- **Docker** : Conteneurisation pour une portabilité accrue
- **GitHub/GitLab** : Gestion du code et intégration avec Jenkins
- **Plugin CLI de Jenkins** : Extraction et gestion de la configuration
- **Credential Binding Plugin** : Sécurisation des secrets

## 🏗 Installation et Déploiement

### 1️⃣ Prérequis
- **Docker** installé sur votre machine ([Installation Docker](https://docs.docker.com/get-docker/))
- **Jenkins** installé en mode JCasC
- Un fichier `.env` contenant les informations sensibles

### 2️⃣ Construction et exécution du conteneur Jenkins
```bash
docker build -t jenkins:jcasc .
docker run --name jenkins-up --rm -p 8090:8080 --env-file .env jenkins:jcasc
```
L’interface Jenkins sera accessible via `http://localhost:8090/`.

## 📄 Structure du projet
```
📂 Projet
 ├── 📂 config/              # Fichiers de configuration JCasC
 │    ├── jcasc.yaml         # Configuration Jenkins au format YAML
 │    ├── plugins.txt        # Liste des plugins Jenkins
 │    ├── .env               # Variables d'environnement (non versionné)
 ├── 📂 docker/              # Configuration Docker
 │    ├── Dockerfile         # Image Docker personnalisée pour Jenkins
 ├── 📜 README.md            # Documentation du projet
```

## 🔐 Sécurité
- **Gestion des secrets** via des variables d’environnement et fichiers `.env`.
- **Plugins Credentials Binding** pour éviter l’exposition des mots de passe.
- **Stockage sécurisé des configurations** pour éviter les fuites de données sensibles.

## 🚀 Améliorations possibles
- Intégration avec **Kubernetes** pour un déploiement scalable.
- Utilisation de **HashiCorp Vault** ou **AWS Secrets Manager** pour une gestion plus sécurisée des secrets.
- Ajout de **monitoring avancé** avec Prometheus/Grafana.

