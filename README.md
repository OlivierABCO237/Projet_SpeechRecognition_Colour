# Projet_SpeechRecognition_Colour
Reconnaissance vocale de couleurs avec une Arduino nano BLE Sense

## Etapes de réalisation: 
### Etape 1: **Data acquisition**
- Connecter l'arduino BLE Sense sur le PC, et créer un compte sur edge impulse
- Installer __CLI Arduino__ et __CLI edge impulse__
- Flasher la carte arduino avec __flash_windows.bat__ puis appuyer sur le bouton reset
- la commande **$ edge-impulse-daemon --clean** permet de connecter edge impulse à la carte arduino
- Choisir le type de capteur que vous voulez utiliser, et la taille des données
- Choisir un label, et débuter l'enregistrement des données. Pour cet exemple, ce sont des données audio, noms des couleurs **rouge**, **vert**, et **Jaune**

### Etape 2: **Entrainer le modèle**

L'interface de edge impulse simplifie grandement l'entrainement des modèles. Le notre est une classification, de types de couleurs.
- Avec les données crées, on créer une impulsion et l'enregistrer
- Enregistrer les paramètres par défaut et lancer la génération des fonctionnalités.
    Cette étape permet de représenter sur un diagramme, la repartition de nos données sur les labels créés.
- Lancer l'entrainement: Le resultat est une repartition des données de test sur un diagramme, et l'évaluation des performances du modèle. Un score est donné

### Etape 3: **Utilisation de l'algorithme pour applications**
De ce modèle, plusieurs bibliothèques peuvent etres créees pour des applications particulières. 
- Dans déploiement, sélectionner le type de données de sortie en phase avec votre application. Ici, il s'agit de bibliothèques arduino
- Installer et ouvrir la bibliothèque dans l'IDE Arduino, ouvrir un exemple
- Modifier l'exemple pour afficher sur la led RGB, chaque couleur prononcée par l'utilisateur:
- Rechercher sur le datasheet de la carte BLE sense, l'emplacement de la led RGB. 22,23 et 24
- Définir chacun de ces GPIO en output de tension, dans le code (setup)
- ecrire un code qui permet de mettre de maintenir etteint les deux autres couleurs, et d'allumer une seule quand le mot est prononcé.


