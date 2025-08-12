# 🚀 Proxy de Suivi Mixpanel

Un serveur proxy HTTP léger basé sur nginx pour l'API de suivi Mixpanel, forké et personnalisé pour des capacités de suivi améliorées. 📊

## 📋 Aperçu

Ce proxy agit comme un intermédiaire entre les applications clientes et les points de terminaison API de Mixpanel, permettant :

- **🎯 Proxy d'API de Suivi** : Transmet les requêtes vers `api.mixpanel.com` avec une gestion appropriée des en-têtes
- **📚 Proxy de Bibliothèque JavaScript** : Sert les bibliothèques clientes de Mixpanel via `/lib.js` et `/lib.min.js`
- **🔀 Proxy d'API de Décision** : Gère les requêtes de feature flags via le point de terminaison `/decide`
- **🌍 Préservation d'IP** : Maintient un suivi géographique précis grâce à une transmission d'IP sophistiquée
- **🌐 Support Multi-Régions** : Configurable pour les exigences de résidence de données EU et IN

## ⚡ Démarrage Rapide

### 🐳 Déploiement Docker
```bash
docker build -t mixpanel-proxy .
docker run -p 8080:80 mixpanel-proxy
```

### ⚙️ Configuration
La configuration nginx inclut :
- ☁️ Support des plages d'IP Cloudflare et Render.com
- 🐛 En-têtes de débogage pour le dépannage
- ⚡ Paramètres haute performance avec optimisation du backlog de connexion

## ✨ Fonctionnalités

- **🔍 Préservation d'IP Client** : Logique avancée de détection et de transmission d'IP
- **📝 Journalisation de Débogage** : Capacités complètes de débogage des requêtes
- **⚖️ Prêt pour l'Équilibrage de Charge** : Optimisé pour les environnements haute concurrence
- **☁️ Agnostique aux Fournisseurs Cloud** : Fonctionne sur différentes plateformes d'hébergement

🍴 Forké depuis le proxy de suivi Mixpanel original avec des capacités améliorées de débogage et de gestion d'IP.
