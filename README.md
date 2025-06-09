# 🎙️ Détecteur ALMA - Reconnaissance Vocale Locale

Une application web de reconnaissance vocale en français qui détecte le mot "ALMA" en temps réel et active un voyant LED visuel.

## ✨ Fonctionnalités

- **Reconnaissance vocale locale** : Utilise Vosk.js pour la reconnaissance vocale hors ligne en français
- **Détection du mot-clé "ALMA"** : Active automatiquement un voyant LED rouge
- **Analyse audio en temps réel** : Affichage du niveau sonore et détection des silences
- **Interface moderne** : Design responsive avec animations et indicateurs visuels
- **Historique des transcriptions** : Affichage des résultats avec timestamps
- **Écoute permanente** : Surveillance continue du microphone

## 🚀 Installation et Utilisation

### Prérequis
- Navigateur web moderne supportant l'API Web Audio
- Serveur HTTP local (pour l'accès au microphone)
- Connexion internet pour le chargement initial de Vosk.js

### Lancement
1. Clonez ce repository
2. Lancez un serveur HTTP local :
   ```bash
   python3 -m http.server 8000
   ```
3. Ouvrez votre navigateur à `http://localhost:8000`
4. Autorisez l'accès au microphone
5. L'écoute démarre automatiquement après le chargement du modèle

## 🎯 Comment ça marche

1. **Chargement du modèle** : L'application charge le modèle Vosk français (`model.tar.gz`)
2. **Capture audio** : Accès au microphone avec paramètres optimisés (16kHz, mono)
3. **Reconnaissance** : Traitement en temps réel avec Vosk.js
4. **Détection** : Recherche du mot "ALMA" dans les résultats (insensible à la casse)
5. **Activation** : Voyant LED rouge pendant 10 secondes lors de la détection

## 📁 Structure du projet

```
WebSpeechAPI/
├── index.html          # Application principale
├── model.tar.gz        # Modèle Vosk français (requis)
├── README.md          # Documentation
└── .gitignore         # Fichiers à ignorer
```

## 🛠️ Technologies utilisées

- **Vosk.js** - Reconnaissance vocale hors ligne
- **Web Audio API** - Capture et analyse audio
- **HTML5/CSS3/JavaScript** - Interface utilisateur
- **Modèle Vosk français** - Reconnaissance vocale en français

## 🎨 Interface utilisateur

- **Voyant LED** : Indicateur visuel rouge qui s'active lors de la détection d'ALMA
- **Niveau audio** : Barre de progression montrant l'intensité sonore
- **Statut de silence** : Détection et affichage des périodes de silence
- **Historique** : Liste des transcriptions avec horodatage
- **Indicateur d'écoute** : Animation pulsante pendant l'écoute active

## ⚙️ Configuration

### Paramètres audio
- Fréquence d'échantillonnage : 16 kHz
- Canaux : Mono
- Suppression d'écho : Activée
- Suppression de bruit : Désactivée (pour l'analyse)

### Seuils de détection
- Seuil de silence : 1% du niveau audio maximum
- Durée minimum de silence : 1 seconde
- Durée d'activation LED : 10 secondes

## 🔒 Sécurité et Permissions

- L'accès au microphone nécessite l'autorisation de l'utilisateur
- Traitement audio local (aucune donnée envoyée sur internet)
- Fonctionne uniquement en HTTPS ou localhost

## 🐛 Dépannage

**Le modèle ne se charge pas** : Vérifiez que `model.tar.gz` est présent et accessible

**Pas d'accès au microphone** : Autorisez l'accès dans les paramètres du navigateur

**Reconnaissance peu fiable** : Assurez-vous d'un environnement peu bruyant

**Erreurs de CORS** : Utilisez un serveur HTTP local, pas l'ouverture directe du fichier

## 📝 Licence

Projet open source - libre d'utilisation et de modification.

## 🤝 Contribution

Les contributions sont bienvenues ! N'hésitez pas à ouvrir des issues ou proposer des pull requests. 