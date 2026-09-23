# 🚀 StratAds — Écosystème GTM & Tracking Server-Side Multi-Plateformes

**StratAds** fournit des templates Google Tag Manager (Web & Serveur) prêts à l'emploi pour déployer en quelques minutes une infrastructure de tracking e-commerce robuste, dédoublonnée et conforme au Consent Mode v2.

---

## 🎯 Plateformes prises en charge

L'infrastructure synchronise en temps réel la collecte côté client (navigateur) et côté serveur (Cloud Run / sGTM) pour les 6 régies publicitaires majeures :

* **Meta Ads** : Pixel navigateur + Conversions API (CAPI)
* **Google Ads & GA4** : Balise Google + Relais Serveur + Conversion Linker
* **TikTok Ads** : Pixel TikTok + Events API
* **Pinterest Ads** : Tag Pinterest + Conversions API (CAPI)
* **Snapchat Ads** : Pixel Snapchat + Conversions API (CAPI)
* **Microsoft Advertising (Bing)** : Balise UET + Conversions API (CAPI)

---

## 📦 Contenu du dépôt

Le dossier `/public/templates` (ou `/templates`) contient les 4 conteneurs GTM préconfigurés au format JSON :

| Fichier | Usage & Compatibilité |
| :--- | :--- |
| `StratAds_WEB_Universel.json` | CMS sur-mesure, PrestaShop, Web Apps, SaaS et génération de leads. |
| `StratAds_WEB_Shopify.json` | Boutiques Shopify (Checkout standard et Web Pixels). |
| `StratAds_WEB_WooCommerce.json` | Boutiques WordPress / WooCommerce (compatible GTM4WP). |
| `StratAds_SERVER.json` | Conteneur sGTM multi-plateformes (Meta, TikTok, Pinterest, Snapchat, Bing, GA4). |

---

## ⚡ Fonctionnalités clés

* **Dédoublonnement fiable (`event_id`)** : génération automatique d'identifiants uniques côté client et transmission transparente côté serveur pour éliminer les doublons de conversion.
* **Event Match Quality (EMQ) optimisé** : transmission et hachage (SHA-256) sécurisés des signaux utilisateurs (`email`, `phone`).
* **Conformité RGPD** : gestion native du Consent Mode v2 (`ad_storage`, `ad_user_data`) sur l'ensemble des balises de tracking.
* **Architecture optimisée Cloud Run** : transport allégé vers le serveur via le protocole de mesure GA4 et redistribution vers les CAPI respectives.

---

## 🛠️ Guide d'installation

1. **GTM Serveur :**
   * Créez un conteneur GTM de type **Serveur**.
   * Importez `StratAds_SERVER.json` en mode **Fusionner**.
   * Renseignez vos identifiants réels (Pixel IDs, API Access Tokens, UET Tag ID) dans les variables constantes préfixées par `[StratAds] -`.

2. **GTM Web (Client) :**
   * Choisissez le template adapté à votre plateforme (`Universel`, `Shopify` ou `WooCommerce`).
   * Importez le fichier JSON correspondant en mode **Fusionner**.
   * Renseignez votre URL de conteneur serveur Cloud Run (`[StratAds] - Server URL`) et vos différents identifiants de pixels.

---

## 👤 À propos

Développé par **StratAds** — Solutions d'hébergement Server-Side, cycle de vie SSL et monitoring tracking (Contournement ITP / AdBlocker).