# Espace Soned Afrique — V10

Développé par Mamadou Fall, sous l'encadrement de M. Djiby.

## Mise en ligne (mise à jour depuis la V9)
1. **Apps Script** : remplacer tout le contenu de `Code.gs` par `apps-script/Code.gs` (version 10.1), enregistrer.
2. Lancer **une fois** la fonction `setup` (autoriser si Google le demande). Elle crée le jeton du QR d'entrée et remet les envois automatiques (rapport 8h, points 10h/19h, clôture 18h).
3. **Déployer → Gérer les déploiements → Modifier (crayon) → Nouvelle version → Déployer.** L'adresse `/exec` ne change pas.
4. Mettre les fichiers du site sur GitHub (dossier complet, y compris `lib/`). Si l'adresse `/exec` a changé, la modifier dans `script.js` (`endpoint`).
5. Espace RH → **QR d'entrée** : choisir le mode de pointage, imprimer l'affiche. → **Personnes** : importer la liste. → **Réglages** : adresses e-mail.

## Ajouts de la version 10.1
- **Effacer toutes les données** (Réglages, RH seulement) : efface personnel, cartes QR, codes, pointages, congés, messages et réglages, puis crée un nouveau code provisoire. Il faut taper « EFFACER » ; une copie des données peut être téléchargée avant. Les téléphones déjà enregistrés reviennent à l'écran de départ.
- **Utilisation** (RH et informaticien) : pour chaque personne, date du dernier pointage et nombre de téléphones validés. Les données restent sur le serveur si quelqu'un supprime l'application.
- **Fiche employé** : matricule saisi à la main (unique), date de naissance (l'âge se calcule tout seul) et date de signature chez Soned. Modifiables par le RH seulement ; affichés en haut de la fiche.


## Ce qui change en V10
- **QR d'entrée** : un seul QR affiché à l'entrée. L'employé cherche son nom dans la liste (avec son poste), crée son code à 4 chiffres la première fois, puis pointe. Position vérifiée (hors zone = signalé en rouge).
- **Trois modes** (RH → QR d'entrée) : carte personnelle seulement, QR d'entrée seulement, ou les deux. Même application, mêmes réglages.
- **Appareils** : chaque téléphone a une clé unique ; le RH valide jusqu'à 2 téléphones par employé. Pointage depuis un téléphone validé = coche bleue. Depuis un autre téléphone = accepté quand même, signalé « appareil non reconnu » (jamais déclaré absent).
- **Espace RH** : premier code provisoire (créé par `setup`) → chaque gestionnaire crée son compte et son mot de passe → un RH connecté invite les autres. Nouveaux onglets : Mon pointage, Appareils, Télétravail, QR d'entrée.
- **Mon pointage** : le RH, l'informaticien et les gestionnaires pointent pour eux-mêmes (jamais pour un autre).
- **Import** de la liste (Personnes → Importer un fichier) : Excel, CSV ou PDF texte ; colonnes Nom (ou Prénom + Nom) et Poste ; aperçu avant d'ajouter.
- **Télétravail** depuis le site : « Je travaille à distance » → nom → code → 4 lieux enregistrés ; le RH voit et retire les lieux, autorise ou non le télétravail.
- **Bouton Installer** qui fonctionne : installation directe quand le navigateur le permet, sinon mode d'emploi adapté (iPhone, Android, ordinateur). Bouton toujours visible en haut.
- Chargement plus robuste (seconde tentative automatique, liste des noms gardée en mémoire).

## À savoir
- Sur iPhone, l'application installée sur l'écran d'accueil et Safari ne partagent pas leurs données : le téléphone peut apparaître deux fois dans Appareils (valider les deux).
- La coche bleue prouve que le pointage vient d'un téléphone validé, pas que la personne est bien celle qui tient le téléphone : le code à 4 chiffres et la position complètent.
- Le télétravail repose sur des lieux déclarés par l'employé : l'application signale tout écart, mais ne prouve pas qu'un lieu est un domicile.

## Auteur et licence
Espace Soned Afrique (pointage V10) a été conçu et développé par **Mamadou Fall**, stagiaire, sous l'encadrement de M. Djiby, pour Soned Afrique.

© 2026 Mamadou Fall. Le code est fourni sous licence MIT (fichier `LICENSE`) : Soned Afrique peut l'utiliser, l'héberger et le modifier, à condition de **conserver la mention de l'auteur** et le fichier `LICENSE` dans toutes les copies. La mention « Développé par Mamadou Fall » de l'écran « À propos » (Réglages) et des documents fait partie de cette condition.
