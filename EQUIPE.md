# L'équipe HACKTIVITI — AgriCoop Connect

Répartition des rôles et des livrables produits par chaque membre de l'équipe sur le projet **AgriCoop Connect** (digitalisation de la coopérative COMAKI, Kintélé).

---

## Vue d'ensemble

| Membre | Rôle(s) | Périmètre |
|---|---|---|
| **Val PEDRO** | Lead du groupe / Repo Admin / Dev FS1 | Infrastructure du repo, Login + Dashboard |
| **Luc M'VOULA** | PO / BA | Cadrage produit & spécifications |
| **Jaurès VOUETA** | Marketing | Persona & proposition de valeur |
| **Gilles BITEMO** | Lead Fullstack / Dev FS2 | Coordination technique, Membres + Comptes |
| **Joseph ONKA** | Dev FS3 | Livraisons |
| **Alain INIENGO** | Dev FS4 | Paiements |
| **Ryzal IBARA** | Dev FS5 | Ventes & Stock |
| **Val PEDRO / Gilles BITEMO** | Dev FS6 (binôme) | Statistiques |
| **Rodrigue MOPATI** | Data Science | Logique métier backend |

---

## Détail des contributions

### 🧭 Product Owner / Business Analyst — Luc M'VOULA

Cadrage produit complet, en amont du développement :

- **Discovery** — analyse du besoin terrain de la coopérative COMAKI
- **FRD** (Functional Requirements Document) — spécifications fonctionnelles détaillées
- **User stories** — expression du besoin par profil utilisateur (Secrétaire, Président, Trésorière, Responsable dépôt, Membre)
- **BPMN** — modélisation des processus métier (livraison, paiement, vente)
- **Backlog produit** — priorisation et découpage du travail pour l'équipe

### 📣 Marketing — Jaurès VOUETA

- **Fiche persona** — profils types des utilisateurs de l'application (Secrétaire, membres de la coopérative)
- **Proposition de valeur** — positionnement du produit pour la présentation Demo Day

### 🧪 Data Science — Rodrigue MOPATI

- Développement des **20 fonctions métier** de `backend/logic.py` (réparties en 4 zones), couvrant l'ensemble des calculs et règles métier (RM-1 à RM-7) exposés ensuite via l'API

### 🧑‍💻 Lead du groupe & Repo Admin / Dev FS1 — Val PEDRO

**Repo Admin :**
- Stratégie de branches (`develop` / `main`)
- Templates GitHub (issues, PR)
- Board Kanban
- Rédaction du `README.md` et `CONTRIBUTING.md`

**Dev FS1 :**
- Pages **Login** et **Dashboard** (HTML/CSS, layout, responsive mobile-first)
- Fonctions `validerFormulaireLogin`, `compterJoursActifs` dans `functions.js`

### 🧑‍💻 Lead Fullstack / Dev FS2 — Gilles BITEMO

**Lead Fullstack :** coordination technique entre les développeurs Full Stack (cohérence de la charte graphique, du header/navbar, des conventions CSS entre pages)

**Dev FS2 :**
- Pages **Membres** et **Comptes** (HTML/CSS, layout, responsive mobile-first)
- Fonctions `filtrerMembresParStatut`, `rechercherMembreParNom`, `validerFormulaireNouveauMembre` dans `functions.js`

### 🧑‍💻 Dev FS3 — Joseph ONKA

- Page **Livraisons** (HTML/CSS, layout, responsive mobile-first)
- Fonctions `validerFormulaireLivraison`, `trierLivraisonsParDate` dans `functions.js`

### 🧑‍💻 Dev FS4 — Alain INIENGO

- Page **Paiements** (HTML/CSS, layout, responsive mobile-first)
- Fonctions `validerFormulairePaiement`, `calculerTotalPaiements` dans `functions.js`

### 🧑‍💻 Dev FS5 — Ryzal IBARA

- Page **Ventes & Stock** (HTML/CSS, layout, responsive mobile-first)
- Fonctions `getBadgeStock`, `formaterMontant` dans `functions.js`

### 🧑‍💻 Dev FS6 — Val PEDRO & Gilles BITEMO (binôme)

- Page **Statistiques** (HTML/CSS, layout, responsive mobile-first)
- Fonctions `trierClassementParVolume`, `formaterDate` dans `functions.js`

> Val Pedro et Gilles Bitemo ont chacun cumulé une double casquette (lead + page Dev FS supplémentaire) en plus de leur périmètre principal, pour couvrir les 6 pages Full Stack avec une équipe de 4 développeurs dédiés.

---

## Ce que ça donne mis bout à bout

- **1 cadrage produit complet** (discovery → FRD → user stories → BPMN → backlog)
- **1 stratégie marketing** (persona + proposition de valeur)
- **20 fonctions métier** testées côté backend
- **8 pages** frontend construites et stylisées, mobile-first
- **1 infrastructure de repo** opérationnelle du premier jour au Demo Day
