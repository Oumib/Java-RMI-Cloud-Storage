# ☁️ Cloud Storage Desktop App  Java 

Une application desktop (Java + Swing) connectée à un serveur **RMI** simulant un service de stockage en ligne, similaire à **OneDrive** ou **Google Drive**.  
Elle permet aux utilisateurs de :  
✅ Créer un compte  
✅ Se connecter  
✅ Synchroniser leurs fichiers locaux avec le cloud  
✅ Télécharger et supprimer des fichiers du cloud  
✅ Gérer leurs répertoires automatiquement  

---

## 🚀 Fonctionnalités  

### 👤 Gestion des utilisateurs  
- Inscription avec **nom, email, mot de passe, nom d’utilisateur**  
- Authentification sécurisée via RMI  
- Création automatique d’un répertoire personnel pour chaque utilisateur  

### 📂 Gestion des fichiers  
- **Upload automatique** grâce à un `DirectoryWatcher`  
- **Liste des fichiers cloud** affichée dans une `JTable`  
- **Téléchargement** avec choix de l’emplacement via `JFileChooser`  
- **Suppression sélective** :  
  - Seulement sur le cloud  
  - Sur le cloud + localement  

### 🖥️ Interface Graphique (Swing)  
- Navigation via un **menu multi-écrans** (`CardLayout`) :  
  - Accueil  
  - Inscription  
  - Connexion  
  - Espace Cloud  
- Interface colorée avec boutons (`JButton`), menus (`JMenu`), et formulaires  

---

## 🏗️ Architecture  

L’application est basée sur une architecture **Client-Serveur RMI** :  

+----------------------+ +----------------------+
| CloudClientGUI | <----> | Cloud |
| (Swing GUI) | | (Serveur RMI) |
+----------------------+ +----------------------+
| |
| |
+---------------+ +---------------+
| DirectoryWatcher | | Fichier système |
| (surveille local)| | (sauvegarde) |
+---------------+ +---------------+

- **Client** : Application Java Swing (GUI)  
- **Serveur** : Implémentation RMI (`Cloud`) exposant les services cloud  
- **Synchronisation** : `DirectoryWatcher` surveille un dossier local et envoie les changements au serveur  

---

## 📂 Organisation du projet  



📦 Cloud-Storage-App
┣ 📂 Client
┃ ┣ 📂 src/Drive
┃ ┃ ┣ CloudClientGUI.java
┃ ┃ ┣ Client.java
┃ ┃ ┣ ClientImpl.java
┃ ┃ ┣ DirectoryWatcher.java
┃ ┃ ┗ ...
┣ 📂 Server
┃ ┣ 📂 src/Drive
┃ ┃ ┣ Cloud.java
┃ ┃ ┣ CloudImpl.java
┃ ┃ ┗ ...
┣ README.md
┣ .gitignore
┗ LICENSE


---

## ⚙️ Installation et Exécution  

### ✅ Prérequis  
- **Java JDK 8+**  
- **Eclipse IDE** ou IntelliJ  
- **Git** pour cloner le projet  

### 1️⃣ Cloner le projet  
```bash
git clone https://github.com/USERNAME/Cloud-Storage-App.git
cd Cloud-Storage-App

👩‍💻# Auteurs

#Oumaima Bounekhla – Développement Client (Java Swing + RMI)
#Équipe projet – Développement Serveur & Architecture
