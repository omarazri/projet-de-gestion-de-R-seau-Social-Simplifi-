============================================
            RESEAU SOCIAL SNS
============================================

DESCRIPTION
-----------
Un système de réseau social implémenté en C qui permet de gérer des utilisateurs,
leurs relations (amis et abonnements), leurs publications, avec persistance des données.

FONCTIONNALITES
---------------
1. Gestion des utilisateurs (ABR - Arbre Binaire de Recherche)
2. Système de relations (listes chaînées)
   - Amis (relations mutuelles)
   - Abonnements (relations unidirectionnelles)
3. Publications de messages avec horodatage
4. Timeline personnalisée
5. Statistiques du réseau
6. Sauvegarde et chargement des données

STRUCTURES DE DONNEES
---------------------
1. Utilisateur (stocké dans un ABR)
   - id, nom
   - liste d'amis
   - liste d'abonnements
   - liste de publications
   - pointeurs gauche/droite pour l'ABR

2. Relation (liste chaînée)
   - idUser de la relation
   - pointeur vers la relation suivante

3. Message (liste chaînée)
   - contenu du message
   - timestamp (date/heure)
   - pointeur vers le message suivant

COMPILATION
-----------
gcc -o sns projet.c

EXECUTION
---------
./sns

MENU PRINCIPAL
--------------
1. Ajouter utilisateur
2. Supprimer utilisateur
3. Afficher utilisateurs
4. Ajouter ami
5. Ajouter abonnement
6. Afficher profil
7. Publier message
8. Voir timeline
9. Statistiques
10. Sauvegarder
0. Quitter

UTILISATION TYPIQUE
-------------------
1. Ajouter des utilisateurs (option 1)
2. Établir des relations (options 4 et 5)
3. Publier des messages (option 7)
4. Consulter la timeline (option 8)
5. Sauvegarder avant de quitter (option 10)

FICHIERS DE DONNEES
-------------------
1. utilisateurs.bin - Données binaires des utilisateurs
2. relations.txt - Relations au format texte

FORMAT DES RELATIONS
--------------------
Ligne: "ID:Ami1,Ami2,BAbon1,BAbon2,..."
- Préfixe A pour ami (ex: A1002)
- Préfixe B pour abonnement (ex: B1003)

FONCTIONS PRINCIPALES
---------------------
- creerUtilisateur()      Crée un nouvel utilisateur
- insererABR()           Insère dans l'arbre binaire
- rechercherABR()        Recherche un utilisateur
- supprimerABR()         Supprime un utilisateur
- ajouterRelation()      Ajoute une relation
- publierMessage()       Publie un message
- afficherTimeline()     Affiche la timeline
- sauvegarderDonnees()   Sauvegarde les données
- chargerDonnees()       Charge les données
- afficherStatistiques() Affiche les stats

STATISTIQUES
------------
- Nombre total d'utilisateurs
- Nombre d'utilisateurs actifs (avec publications)
- Taux d'activité du réseau

AUTEUR
------
Projet éducatif - Structures de données en C


NOTES
-----
- Les données sont sauvegardées automatiquement à la fermeture
- Les données sont chargées automatiquement au démarrage
- L'arbre binaire permet une recherche rapide 
- Les listes chaînées permettent une gestion dynamique des relations
