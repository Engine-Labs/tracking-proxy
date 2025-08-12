# 🚀 Proxy de suivi Mixpanel

Un serveur proxy HTTP léger basé sur nginx pour l’API de suivi de Mixpanel, forké et personnalisé pour des capacités de suivi améliorées. 📊

## 📋 Aperçu

Ce proxy agit comme un intermédiaire entre les applications clientes et les points de terminaison de l’API Mixpanel, permettant :

- **🎯 Proxy de l’API de suivi** : transmet les requêtes vers `api.mixpanel.com` avec une gestion appropriée des en‑têtes
- **📚 Proxy de la bibliothèque JavaScript** : sert les bibliothèques clientes de Mixpanel via `/lib.js` et `/lib.min.js`
- **🔀 Proxy de l’API Decide** : gère les requêtes de feature flags via le point de terminaison `/decide`
- **🌍 Préservation de l’IP** : maintient une géolocalisation précise grâce à un transfert d’IP sophistiqué
- **🌐 Prise en charge multi‑régions** : configurable pour les exigences de résidence des données UE et IN (Inde)

## ⚡ Démarrage rapide

### 🐳 Déploiement Docker
```bash
docker build -t mixpanel-proxy .
docker run -p 8080:80 mixpanel-proxy
```

### ⚙️ Configuration
La configuration nginx inclut :
- ☁️ Prise en charge des plages d’IP Cloudflare et Render.com
- 🐛 En‑têtes de débogage pour le diagnostic
- ⚡ Paramètres hautes performances avec optimisation du backlog de connexions

## ✨ Fonctionnalités

- **🔍 Préservation de l’IP client** : logique avancée de détection et de transfert d’IP
- **📝 Journalisation de débogage** : capacités complètes de diagnostic des requêtes
- **⚖️ Prêt pour l’équilibrage de charge** : optimisé pour les environnements à forte concurrence
- **☁️ Indépendant du fournisseur cloud** : fonctionne sur différentes plateformes d’hébergement

🍴 Fork du proxy de suivi Mixpanel original avec des capacités améliorées de débogage et de gestion des IP.
