# Azimutal

> **Version 1.1.7-alpha.5, version pour essayer (Mac et Windows).** La dernière version stable est la 1.1.6. Azimutal peut encore contenir des erreurs, planter, changer d'une version à l'autre, ou produire des cartes à vérifier avant tout usage important. **Ne comptez pas sur elle pour un travail sans copie de sauvegarde**, et gardez toujours vos fichiers d'origine (Azimutal ne les modifie pas, mais un projet peut être mal enregistré). Vos remarques sont les bienvenues.

Azimutal est une application de cartographie pour **Mac et Windows**, pensée pour l'enseignement : on prépare une carte thématique, on l'imprime ou on l'exporte en PDF, SVG ou PNG (le PNG n'est pas encore disponible sous Windows). Elle fonctionne **hors ligne**, sans compte, sans serveur et sans télémétrie.

La dernière version est celle de la page **Releases** de ce dépôt. Deux téléchargements existent :

- **Mac** : fichier `.dmg`, pour les **Mac Apple Silicon** (puces M1, M2, M3, M4…) sous **macOS 14 (Sonoma) ou plus récent**. Il ne fonctionne pas sur les Mac à processeur Intel.
- **Windows** : fichier `.exe` (installeur), pour **Windows 10 ou 11, 64 bits**.

# Sur Mac

## Installer

1. Ouvrez le fichier `.dmg` téléchargé.
2. Glissez **Azimutal** sur le dossier **Applications**.
3. Fermez la fenêtre, puis éjectez le volume « Azimutal » dans le Finder.

## Premier lancement : macOS va refuser, c'est normal

Azimutal n'est pas encore signée par Apple (ce serait payant pour l'auteur ; c'est prévu plus tard). macOS affiche donc un message du type « Azimutal ne peut pas être ouverte » ou « ne peut pas être vérifiée ». L'app n'est pas modifiée ; macOS ne sait simplement pas qui l'a publiée. Pour l'ouvrir **une seule fois** :

1. Double-cliquez sur Azimutal dans Applications. Le message apparaît : cliquez sur **OK** (ou « Terminé »).
2. Ouvrez **Réglages Système → Confidentialité et sécurité**.
3. Descendez jusqu'à la section **Sécurité** : une ligne dit « Azimutal a été bloquée ». Cliquez sur **Ouvrir quand même**, puis confirmez avec votre mot de passe ou Touch ID.
4. Azimutal s'ouvre. Les fois suivantes, elle s'ouvre normalement.

Si le message dit que l'app est « endommagée » (sans bouton « Ouvrir quand même »), ouvrez l'app **Terminal** et collez cette ligne, puis appuyez sur Entrée :

```
xattr -dr com.apple.quarantine /Applications/Azimutal.app
```

Elle retire seulement la mention « téléchargé depuis Internet » posée par macOS sur l'app. Vous pouvez ensuite l'ouvrir.

### Vérifier le fichier téléchargé (facultatif)

Le fichier `SHA256SUMS.txt` publié avec le téléchargement contient l'empreinte du `.dmg`. Dans le Terminal :

```
shasum -a 256 ~/Downloads/Azimutal_*.dmg
```

Le résultat doit être identique à celui de `SHA256SUMS.txt`.

# Sur Windows

## Installer

1. Téléchargez le fichier `Azimutal_…_x64-setup.exe` de la page **Releases**.
2. Double-cliquez dessus. L'installation se fait pour votre compte seulement : aucun mot de passe administrateur n'est demandé.
3. Suivez les écrans de l'installeur, puis ouvrez Azimutal depuis le menu Démarrer.

## Premier lancement : Windows va avertir, c'est normal

Azimutal n'est pas encore signée par un certificat payant. Windows affiche donc « **Windows a protégé votre ordinateur** » (SmartScreen). L'application n'est pas modifiée ; Windows ne sait simplement pas qui l'a publiée. Pour continuer :

1. Dans la fenêtre bleue, cliquez sur **Informations complémentaires**.
2. Cliquez sur **Exécuter quand même**.
3. L'installation se déroule normalement. Les fois suivantes, Azimutal s'ouvre sans avertissement.

Si votre antivirus ou votre navigateur bloque le téléchargement, vous pouvez vérifier le fichier avant de le garder (voir ci-dessous).

### Vérifier le fichier téléchargé (facultatif)

Le fichier `SHA256SUMS.txt` publié avec le téléchargement contient l'empreinte de l'installeur. Dans **PowerShell** :

```
Get-FileHash $env:USERPROFILE\Downloads\Azimutal_*_x64-setup.exe -Algorithm SHA256
```

Le résultat doit être identique à celui de `SHA256SUMS.txt`.

## Désinstaller

Ouvrez **Paramètres → Applications → Applications installées**, choisissez Azimutal, puis **Désinstaller**. Vos projets (fichiers `.gpkg`) restent là où vous les avez enregistrés.

## Raccourcis clavier

Sous Windows, la touche **Ctrl** remplace la touche ⌘ du Mac (Ctrl+K pour chercher une commande, Ctrl+1 à Ctrl+6 pour les étapes, Ctrl+S pour enregistrer).

## Ce qu'Azimutal fait et ne fait pas

- Aucune connexion Internet. Vos fichiers restent sur votre ordinateur et ne sont jamais modifiés : Azimutal en lit une copie.
- Pas de mise à jour automatique : pour une nouvelle version, téléchargez-la et installez-la par-dessus l'ancienne (Mac : remplacez-la dans Applications ; Windows : relancez l'installeur).
- Vos cartes sont à vous. Vous pouvez les utiliser en classe ou les publier, en gardant les mentions de sources imprimées sur l'export. Voir `CONDITIONS_UTILISATION.md`.

## Documents

- `CONDITIONS_UTILISATION.md` : ce que vous pouvez faire de l'app et de vos cartes.
- `THIRD_PARTY_NOTICES.md` : licences des composants libres embarqués.

## Signaler un problème

Utilisez la page **Contact** du site d'Altaïr Lab : https://altairlab.vercel.app/contact. Indiquez la version d'Azimutal (menu Azimutal → À propos), votre système (version de macOS ou de Windows) et ce que vous faisiez.
