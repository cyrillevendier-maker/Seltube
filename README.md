# Seletube pour Android

Ce dossier contient l'application Android de Seletube : une coque légère qui affiche `selztube.html`
(dans `app/src/main/assets/`). Tout reste stocké sur le téléphone, comme dans la version web.

Il faut Android 10 ou plus récent.

## Obtenir l'APK sans rien installer (GitHub)

1. Créez un dépôt GitHub (privé ou public) et envoyez-y **tout le contenu de ce dossier**
   (bouton « Add file » > « Upload files » ; pensez au dossier caché `.github`).
2. Ouvrez l'onglet **Actions**, choisissez « Construire l'APK Seletube » puis **Run workflow**
   (il se lance aussi tout seul à chaque envoi).
3. Au bout de 3 à 5 minutes, ouvrez l'exécution terminée et téléchargez **seletube-apk**
   (un .zip qui contient `app-debug.apk`).
4. Copiez l'APK sur le téléphone et ouvrez-le. Android demandera d'autoriser l'installation
   depuis cette source (« sources inconnues ») : acceptez, puis installez.

Les polices et les icônes sont embarquées pendant cette construction, donc l'appli marche aussi hors connexion.

## Avec Android Studio

1. Ouvrez ce dossier dans Android Studio et laissez la synchronisation Gradle se terminer.
2. Menu **Build > Build Bundle(s) / APK(s) > Build APK(s)**.
3. L'APK est dans `app/build/outputs/apk/debug/app-debug.apk`.
4. Facultatif : lancez `python3 tools/fetch_fonts.py` avant, pour embarquer les polices (sinon elles se chargent en ligne).

## Mettre à jour l'appli

Remplacez `app/src/main/assets/selztube.html` par la nouvelle version, puis reconstruisez l'APK.

## À savoir

- L'APK produit est signé avec la clé de débogage : parfait pour l'installer chez soi.
  Pour le publier sur le Play Store, il faudra une clé de signature personnelle.
- Les fichiers reçus d'un ami (réseau local) sont enregistrés dans `Téléchargements/Seletube`.
- Le bouton Retour ferme la fenêtre ou le jeu ouvert, puis ramène à l'accueil, puis quitte.
- Le réseau local fonctionne entre téléphones sur le même Wi‑Fi (certains Wi‑Fi « invités » isolent les appareils).
