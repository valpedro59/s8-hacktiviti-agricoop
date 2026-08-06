# Note de Branche / Changelog

## Informations Générales

**Branche :** feature/ventes-stock
**Auteur(s) :** @Ryzal IBARA

## Résumé des Modifications

Mise en place de la page **Ventes & Stock** permettant la gestion et le suivi des produits disponibles, des mouvements de stock et des opérations de vente.
Ajout d'un tableau de gestion des stocks avec les informations principales sur les produits, les quantités disponibles, les prix et les actions associées.

## Changements Techniques

### Interface Ventes & Stock :

- Création de la structure principale de la page avec une section dédiée aux ventes et au suivi du stock.
- Ajout d'un en-tête présentant le titre de la page et une zone d'action pour faciliter la gestion des opérations.
- Mise en place d'une interface claire séparant les informations liées aux produits et aux transactions.

### Tableau de Gestion du Stock :

- Création d'un tableau réactif affichant les informations essentielles :
  - Nom du produit.
  - Catégorie.
  - Quantité disponible.
  - Prix unitaire.
  - Statut du stock.
  - Actions disponibles.

- Ajout d'un système visuel permettant d'identifier rapidement l'état des stocks :
  - Stock disponible.
  - Stock faible.
  - Rupture de stock.

- Mise en place d'un design adapté aux différents formats d'écran avec gestion du débordement horizontal sur mobile.

### Gestion des Ventes :

- Ajout d'une section permettant le suivi des ventes réalisées.

- Affichage des données principales :
  - Produit vendu.
  - Quantité vendue.
  - Montant total.
  - Date de transaction.

- Préparation de la structure pour une future connexion avec les données dynamiques provenant de la base de données.

### Styles et Responsive Design :

- Application d'un style cohérent avec l'identité visuelle du projet.

- Utilisation d'une mise en page flexible pour garantir l'adaptation sur :
  - Ordinateurs.
  - Tablettes.
  - Smartphones.

- Ajout d'un comportement responsive pour le tableau avec une barre de défilement horizontale afin de conserver la lisibilité des données sur petits écrans.

## Captures d'Écran

![alt text](<Ventes - capture.webp>)

## ⚠️ Points d'Attention / Impact

[ ] Connecter les données du stock aux informations réelles provenant de la base de données.

[ ] Ajouter la fonctionnalité d'ajout, modification et suppression des produits.

[ ] Implémenter la gestion automatique des quantités après chaque vente.

[ ] Ajouter les filtres et recherches pour faciliter la navigation dans le tableau.

[ ] Vérifier le comportement responsive sur les différents formats d'écran.

## Procédure de Test

1. Naviguer vers la route `/ventes-stock`.

2. Vérifier l'affichage correct du tableau des produits.

3. Tester le comportement responsive sur différentes tailles d'écran.

4. Vérifier que le défilement horizontal du tableau fonctionne correctement sur mobile.
