# Note de branche / Changelog

## Informations Générales

- Branche : 'feature/livraisons'
- Auteur : Joseph Miere

---

## Résumé des modifications

- Mise en place de la page de gestion des livraisons avec un formulaire d’enregistrement, un tableau de consultation et un bouton de tri par date.
- Intégration de la navigation de la page de tableau de bord dans la page des livraisons pour une cohérence visuelle.
- Ajustement du style du formulaire et du tableau afin d’améliorer la lisibilité, l’ergonomie et l’affichage responsive sur mobile et tablette.

## Changements techniques

- Mise en place du tableau HTML avec le corps `liste-livraisons` pour l’injection dynamique des données.
- Adaptation du CSS pour harmoniser la navigation, le formulaire et le tableau sur les différentes tailles d’écran.

## Capture d'écran

![alt text](<Livraisons - capture.webp>)

## Points d’attention / impact

- La page dépend du backend pour charger les livraisons existantes et enregistrer une nouvelle livraison.
- Le formulaire doit être utilisé avec un serveur backend actif pour que l’envoi et l’affichage fonctionnent correctement.
- Si les données ne sont pas encore disponibles côté API, le tableau peut rester vide ou afficher un message d’erreur.
- Les styles ont été ajustés pour un rendu plus propre, mais une validation visuelle complète reste recommandée sur navigateur réel.

## Procédure de test

1. Naviguer vers la route '/livraisons'
2. vérifier le bon survol des liens dans la sidebar
3. Vérifier que le formulaire s’affiche correctement et que le tableau se remplit avec les livraisons disponibles.
4. Tester l’enregistrement d’une livraison avec un membre, une culture et une quantité valides.
5. Vérifier que le message de succès ou d’erreur s’affiche correctement et que le tableau se met à jour.
