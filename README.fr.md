# 🚀 Proxy de Suivi Mixpanel

Un serveur proxy HTTP léger basé sur nginx pour l'API de suivi Mixpanel, forké et personnalisé pour des capacités de suivi améliorées. 📊

## 📋 Présentation

Ce proxy agit comme un intermédiaire entre les applications clientes et les points de terminaison API de Mixpanel, permettant :

- **🎯 Proxy API de Suivi** : Transmet les requêtes vers `api.mixpanel.com` avec une gestion appropriée des en-têtes
- **📚 Proxy de Bibliothèque JavaScript** : Sert les bibliothèques clientes de Mixpanel via `/lib.js` et `/lib.min.js`
- **🔀 Proxy API de Décision** : Gère les requêtes de fonctionnalités via le point de terminaison `/decide`
- **🌍 Préservation IP** : Maintient un suivi géolocalisation précis grâce à un transfert IP sophistiqué
- **🌐 Support Multi-Régional** : Configurable pour les exigences de résidence des données EU et IN

## ⚡ Démarrage Rapide

### 🐳 Déploiement Docker
```bash
docker build -t mixpanel-proxy .
docker run -p 8080:80 mixpanel-proxy
```

### ⚙️ Configuration
La configuration nginx inclut :
- ☁️ Support des plages IP Cloudflare et Render.com
- 🐛 En-têtes de débogage pour le dépannage
- ⚡ Paramètres haute performance avec optimisation du backlog de connexion

## ✨ Fonctionnalités

- **🔍 Préservation IP Client** : Logique avancée de détection et de transfert IP
- **📝 Journalisation de Débogage** : Capacités de débogage de requêtes complètes
- **⚖️ Prêt pour l'Équilibrage de Charge** : Optimisé pour les environnements haute concurrence
- **☁️ Agnostique du Fournisseur Cloud** : Fonctionne sur différentes plateformes d'hébergement

🍴 Forké du proxy de suivi Mixpanel original avec des capacités améliorées de débogage et de gestion IP.
