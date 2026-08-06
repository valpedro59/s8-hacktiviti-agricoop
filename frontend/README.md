# AgriCoop Connect

**Digitaliser la gestion de la coopérative agricole COMAKI, à Kintélé.**

Application web permettant à la coopérative de suivre ses membres, ses livraisons de récoltes (manioc, maïs, arachide), les paiements versés, le stock, les ventes aux acheteurs et les statistiques d'activité — avec un contrôle d'accès par rôle (Secrétaire, Président, Trésorière, Responsable dépôt, Membre).

Projet développé dans le cadre d'Akieni Academy (Phase 2 — HTML/CSS & Git) par une équipe pluridisciplinaire : PO/BA, Data Scientists, Marketing, et plusieurs développeurs Full Stack.

---

## Modules de l'application

| Page               | Rôle                                                                                                         |
| ------------------ | ------------------------------------------------------------------------------------------------------------ |
| **Login**          | Authentification par rôle                                                                                    |
| **Dashboard**      | Indicateurs clés (stock, montant dû, membres actifs, livraisons du mois) + graphique d'activité hebdomadaire |
| **Membres**        | Liste, recherche/filtre par statut, création de nouveaux membres                                             |
| **Livraisons**     | Enregistrement et historique des livraisons de récoltes                                                      |
| **Paiements**      | Enregistrement des paiements aux membres, historique, total versé                                            |
| **Ventes & Stock** | Suivi des ventes aux acheteurs et du stock disponible                                                        |
| **Comptes**        | Création de comptes utilisateurs — réservé au rôle Secrétaire                                                |
| **Statistiques**   | Classement des membres, jours à forte activité, rapport partenaire (anonymisé)                               |

---

## Stack technique

- **Frontend** — HTML/CSS/JavaScript vanilla, pas de framework. Google Fonts (Poppins/Inter), FontAwesome pour les icônes.
- **Backend** — Python (`app.py`), API REST consommée en `fetch` depuis `main.js`.
- **Données** — `backend/data/comaki.json` (source unique de vérité, ne pas modifier).
- **Communication** — `http://localhost:5000/api/...` (voir routes ci-dessous).

---

## Structure du repo

```
├── backend/
│   ├── app.py              # Point d'entrée API — NE PAS MODIFIER
│   ├── controllers.py       # NE PAS MODIFIER
│   ├── logic.py             # 20 fonctions métier à compléter (Data Science)
│   ├── data/comaki.json     # Jeu de données — source unique de vérité
│   └── requirements.txt
├── frontend/
│   ├── login/
│   ├── dashboard/
│   ├── membres/
│   ├── livraisons/
│   ├── paiements/
│   │   └── images/           # Logos Mobile Money (MTN, Airtel)
│   ├── ventes/
│   ├── comptes/
│   ├── statistiques/
│   ├── functions.js          # Fonctions pures à compléter (Full Stack)
│   ├── functions.test.html   # Suite de tests (25 tests)
│   └── main.js                # NE PAS MODIFIER — branchement au backend
├── docs/
│   └── CHANGELOG.md         # Historique des changements du projet
├── .gitignore
├── CONTRIBUTING.md
└── README.md
```

Chaque page a son propre sous-dossier avec un `.html` et un `.css` dédiés.

---

## Lancer le projet en local

**1. Démarrer l'API** (un terminal, à laisser ouvert)

```bash
cd backend
pip install -r requirements.txt
python app.py
```

L'API tourne sur `http://localhost:5000`.

**2. Ouvrir le site**

Ouvrez `frontend/login/login.html` directement dans le navigateur, ou via l'extension **Live Server** de VS Code.

Tant que `python app.py` tourne, toutes les pages peuvent appeler l'API normalement.

### Comptes de test

| Rôle               | Nom d'utilisateur | Mot de passe     |
| ------------------ | ----------------- | ---------------- |
| Secrétaire (Admin) | `smalonga`        | `Secretaire2026` |
| Président          | `floubota`        | `President2026`  |
| Trésorière         | `abikindou`       | `Tresoriere2026` |
| Responsable dépôt  | `jmabiala`        | `Depot2026`      |
| Membre             | `ankounkou`       | `Membre2026`     |

> Mots de passe volontairement en clair dans `data/comaki.json` — choix pédagogique pour se concentrer sur la logique métier, pas la cryptographie. À ne jamais reproduire en production.

### En cas de souci

- **Section vide sur une page** → la fonction correspondante n'est pas encore codée, normal en cours de développement.
- **Message d'erreur affiché** → il indique la fonction à regarder ; le détail complet est dans le terminal de `python app.py`.
- **Rien ne s'affiche** → vérifiez que le terminal API tourne sans erreur, puis rafraîchissement forcé (`Ctrl+Maj+R` / `Cmd+Maj+R`) après modification de `main.js` ou `functions.js`.

---

## Équipe & répartition

| Rôle                                             | Périmètre                                                                                                                                                 |
| ------------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Val Pedro - Lead du groupe - Repo Admin -Dev FS1 | `login/` + `dashboard/` — `validerFormulaireLogin`, `compterJoursActifs`, `formaterDate`                                                                  |
| Luc M'Voula - PO / BA                            | Cahier des charges, règles métier, analyse COMAKI                                                                                                         |
| Rodrigue Mopati - Data Scientist                 | `backend/logic.py` — 20 fonctions réparties en 4 zones                                                                                                    |
| Jaures Voueta - Marketing                        | Supports de communication, identité visuelle                                                                                                              |
| Gilles Bitemo - Lead Stack FS2                   | `membres/` + `comptes + `statistiques/`—`filtrerMembresParStatut`, `rechercherMembreParNom`, `validerFormulaireNouveauMembre`, `trierClassementParVolume` |
| Joseph Onkoa - Dev FS3                           | `livraisons/` — `validerFormulaireLivraison`, `trierLivraisonsParDate`                                                                                    |
| Alain Iniengo -Dev FS4                           | `paiements/` — `validerFormulairePaiement`, `calculerTotalPaiements`                                                                                      |
| Ryzal Ibara - Dev S5                             | `ventes/` — `getBadgeStock`, `formaterMontant`                                                                                                            |

**Câblage à ne jamais modifier** : les `id`, formulaires et scripts marqués `<!-- NE PAS MODIFIER -->` dans le HTML sont utilisés par `main.js` pour injecter les données. Un `id` renommé = données qui ne s'affichent plus.

**Règle d'or JS** : uniquement des fonctions pures (paramètres → `return`), jamais d'accès réseau ou de DOM dans `functions.js` — c'est `main.js` qui s'en charge.

---

## Workflow Git

- Branche principale de travail : `develop` (merge vers `main` en fin de sprint / avant démo)
- Convention de commits : [Conventional Commits](https://www.conventionalcommits.org/) — ex. `fix(paiements): corrige débordement navbar`, `feat(membres): ajoute filtre par village`
- Voir `CONTRIBUTING.md` pour le détail : branches, PR, templates d'issues, board Kanban
- Historique des changements : `docs/CHANGELOG.md`

---

## Règles métier (RM)

| Règle | Description                                                                                       |
| ----- | ------------------------------------------------------------------------------------------------- |
| RM-1  | Une livraison à quantité ≤ 0 est refusée.                                                         |
| RM-2  | Seuls Manioc, Maïs et Arachide sont acceptés comme cultures.                                      |
| RM-3  | Un paiement ne peut jamais dépasser le solde restant dû à un membre.                              |
| RM-4  | Une vente ne peut jamais dépasser le stock disponible.                                            |
| RM-5  | Le rapport partenaire ne contient jamais de donnée nominative.                                    |
| RM-6  | Un utilisateur ne peut accéder qu'aux actions autorisées pour son rôle.                           |
| RM-7  | Un doublon quasi certain de membre propose la fiche existante plutôt que d'en créer une nouvelle. |

---

## Demo Day

Démo live : connexion avec un compte de test, navigation sur les 8 pages, enregistrement d'une livraison et d'un paiement réels, création d'un nouveau membre — avec explication des règles métier respectées.

---

## Contexte

Projet réalisé dans le cadre d'Akieni Academy. Jeu de données fictif inspiré d'une coopérative agricole réelle près de Kintélé, Congo-Brazzaville.
