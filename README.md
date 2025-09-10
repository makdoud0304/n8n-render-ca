# n8n-render-ca
Déploiement de n8n sur Render (render.com) via un service Web Docker dédié, avec base de données PostgreSQL et stockage persistant (option disque). Mode simplifié avec bouton de déploiement.


# n8n sur Render — déploiement en 1 clic (CA/FR)

[![Deploy to Render](https://render.com/images/deploy-to-render-button.svg)](https://render.com/deploy?repo=https://github.com/makdoud0304/n8n-render-ca)

Ce dépôt permet de déployer **n8n** sur **Render** avec :
- un **service Web** Docker,
- une **base PostgreSQL** gérée par Render (plan *free*),
- (optionnel) un **disque persistant** pour `/home/node/.n8n`.

> **Région** : Render n’a pas (encore) de région Canada → on utilise **`oregon`** (latence correcte pour le Québec).  
> **Fuseau/locale** : `America/Toronto`, `fr`.

## Déploiement (1-clic)
1. Clique sur le bouton **Deploy to Render** ci-dessus.
2. Choisis la branche **main** et laisse Render créer **n8n** (Web) + **n8n-db** (Postgres).
3. Une fois en ligne, va dans **n8n → Environment** :
   - copie l’**URL publique** (lien violet en haut),
   - ajoute `WEBHOOK_URL` = cette URL (ex. `https://n8n-xxxxx.onrender.com/`).
4. Connecte-toi à l’UI n8n avec l’auth basique (voir variables `N8N_BASIC_AUTH_*`).

## Option “Disque persistant”
Si ton plan le permet, ajoute un **Disk** et monte-le sur `/home/node/.n8n` (1–2 GB suffisent) pour persister des fichiers locaux.

## Dépannage
- Le bouton ouvre un autre repo ? → vérifie que l’URL du bouton pointe bien vers **ce dépôt**.
- Render n’affiche pas la config ? → assure-toi que `render.yaml` est **à la racine** et s’appelle bien `render.yaml`.
- Repo privé ? → sur Render, **Account → Linked Repositories** : autorise explicitement `makdoud0304/n8n-render-ca` (ou rends le repo public le temps du déploiement).

