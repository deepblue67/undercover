# 🕵️ Undercover Famille

Le jeu d'ambiance **Undercover**, pensé pour jouer **en famille sur un seul téléphone**… ou **avec un téléphone par joueur**.
Tout le monde reçoit un mot secret… sauf l'intrus, qui a un mot légèrement différent. À vous de le démasquer !

▶️ **Jouer en ligne** : `https://<votre-compte>.github.io/undercover-famille/`

![Icône](icons/icon-192.png)

## ✨ Fonctionnalités

- 📱 **Un seul téléphone** qui passe de main en main : la carte se retourne pour montrer le mot tant qu'on garde le doigt dessus
- 📱📱 **Ou un téléphone par joueur** (réglage « Téléphones ») : salle avec un code de 4 lettres et un QR code, mot sur chaque écran, **votes secrets** puis dépouillement (Supabase Realtime, gratuit)
- ✍️ **Fil des indices** (mode un téléphone par joueur) : chacun tape son indice, tous les indices restent affichés jusqu'au vote et sont relus en fin de manche avec les rôles
- 🗳️ **Dépouillement** bulletin par bulletin, avec barres de score, sur tous les écrans
- 🔍 **Bonus détective** : +1 pour chaque civil qui a voté contre l'intrus éliminé
- 👨‍👩‍👧‍👦 De **3 à 10 joueurs**, choisis dans une **liste de joueurs enregistrés** (prénom, avatar, couleur) au lancement de chaque partie
- 👥 **Groupes de joueurs** (Famille, Amis, Travail… renommables, on peut en ajouter) : un joueur peut appartenir à plusieurs groupes, et le maître de jeu choisit le groupe qui joue. Seuls ses joueurs sont proposés dans « Qui joue ? » et dans le « Qui es-tu ? » des téléphones
- 📚 **246 paires de mots** adaptées aux enfants, réparties en 11 thèmes et 3 niveaux
- ✏️ **Mots perso** : ajoutez vos propres paires (prénoms, lieux de vacances, blagues de famille)
- 🔄 **« Changer de mots »** : un mot pas compris ou une paire déjà jouée ? La manche recommence avec une nouvelle paire, sans toucher aux points
- 🗳️ Vote à main levée « 3, 2, 1… montrez du doigt ! » ; en cas d'égalité, nouveau tour d'indices puis nouveau vote
- 🎯 **Dernière chance** : l'Undercover éliminé peut deviner le mot des civils. On **tape sa réponse**, vérifiée avec tolérance (accents, pluriel, « le / la / un… », petite faute de frappe) ; sinon les autres décident si ça compte
- 🎩 **Mr White** en option (un joueur sans mot qui doit bluffer)
- 🎛️ **Rôles au choix** : 1 à 3 Undercovers (ou automatique) et 0 à 2 Mr White, ajustés si les joueurs ne suffisent pas
- 🏁 **Fin de partie** au nombre de manches ou **« premier à X points »** (10, 15, 20 ou 30)
- 👎 **Paire nulle** : en fin de manche, une paire mal choisie peut être écartée pour toujours (liste et remise en jeu dans « Mes mots », incluse dans la synchronisation)
- 📳 **Vibrations** quand c'est ton tour en mode un téléphone par joueur (Android)
- 📺 **Écran TV** : un écran en plus (TV, iPad recopié sur la TV, ordinateur) affiche le déroulement de la partie, à qui le tour et le classement en direct, dans les deux modes
- ⏱️ Minuteur par indice (optionnel), sons, confettis et podium final
- 🤫 Bouton « Revoir mon mot » pour ceux qui l'ont oublié
- 🗂️ **Historique des parties** : classement et détail de chaque manche (mots, intrus, gagnants)
- 📊 Statistiques par joueur calculées depuis l'historique (victoires, fois Undercover, mots devinés)
- 🔄 **Synchronisation entre appareils** : export / import par code texte ou fichier, ou synchro automatique via un **GitHub Gist** secret
- 💾 La partie est sauvegardée : on peut fermer l'appli et reprendre plus tard
- ✈️ **Fonctionne hors ligne** et s'installe sur l'écran d'accueil (PWA)
- 🔒 Aucun compte : tout reste dans le téléphone (sauf synchro Gist vers votre propre compte GitHub, et en mode « un téléphone par joueur » où les messages de la partie transitent par Supabase sans y être enregistrés)

## 🎲 Règles

1. Chacun découvre son mot en secret.
2. À tour de rôle, chacun donne **un indice** sur son mot (un mot ou une petite phrase).
3. Après les tours d'indices, tout le monde **montre du doigt** son suspect en même temps. En cas d'égalité, on refait un tour d'indices et on revote.
4. Le joueur désigné est éliminé et son rôle est révélé.

**Les civils** gagnent s'ils éliminent l'Undercover. **L'Undercover** gagne s'il tient jusqu'au bout (quand il ne reste plus qu'un civil face à lui).

| Situation | Points |
|---|---|
| Civils gagnants | +2 chacun |
| Undercover gagnant | +6 |
| Dernière chance réussie (Undercover éliminé qui devine le mot des civils) | +3 |
| Mr White gagnant (survit ou devine le mot des civils) | +6 |
| Bonus détective (un téléphone par joueur, réglable) : civil ayant voté contre l'intrus éliminé | +1 |

Répartition des rôles : réglable dans **Réglages** (1 à 3 Undercovers, 0 à 2 Mr White). En automatique : 1 Undercover jusqu'à 6 joueurs, 2 à partir de 7. Il faut toujours au moins 2 civils et au moins autant de civils que d'intrus : sinon le jeu réduit les intrus et le signale. Mr White est conseillé à partir de 5 joueurs.

## 👥 Groupes de joueurs

- **Ranger les joueurs** : Réglages → Joueurs enregistrés. Sous chaque joueur, touchez les pastilles des groupes auxquels il appartient (plusieurs possibles). Les filtres en haut montrent les membres de chaque groupe ; « ⚙️ Groupes » permet de renommer, changer l'icône, ajouter ou supprimer un groupe (supprimer un groupe ne supprime aucun joueur).
- **Choisir le groupe qui joue** : Réglages → « Groupe qui joue » (aussi affiché sur « Qui joue ? » et dans la salle de jeu). « Tous » propose tout le monde.
- En mode un téléphone par joueur, le « Qui es-tu ? » des invités ne montre que les joueurs de ce groupe ; quelqu'un d'extérieur peut toujours taper son prénom.
- Un joueur créé pendant qu'un groupe est choisi est rangé directement dans ce groupe. Les joueurs enregistrés avant l'arrivée des groupes ont été placés dans « Famille ».

## 📱📱 Un téléphone par joueur

Dans **Réglages → Téléphones**, choisissez **Un par joueur**. Puis **Nouvelle partie** ouvre une salle :

1. Le téléphone de l'hôte affiche un **code de 4 lettres** et un **QR code**. L'hôte indique s'il joue aussi (son prénom) ou si son téléphone sert seulement d'écran de jeu.
2. Les autres ouvrent le jeu, touchent **📲 Rejoindre une partie** et tapent le code, ou scannent le QR code / ouvrent le lien d'invitation. Ils choisissent leur prénom dans la liste des joueurs de l'hôte ou en tapent un nouveau.
3. Chacun voit **son mot sur son écran**. Quand c'est son tour, le téléphone affiche « À toi ! » : on **tape son indice** (réglage « Indices : Écrits », par défaut) et il s'ajoute au fil des indices visible par tous. Un indice qui contient son propre mot est refusé. Avec le réglage « À voix haute », on le dit simplement et on valide.
4. **Vote secret** sur chaque téléphone (on peut changer d'avis tant que tout le monde n'a pas voté), puis **dépouillement** bulletin par bulletin sur tous les écrans. Égalité → nouveau tour d'indices. Si l'intrus est éliminé, les civils qui ont voté contre lui gagnent le **bonus détective**.
5. Dernière chance / Mr White : le joueur éliminé tape sa réponse sur son téléphone. Si elle est reconnue (même avec une petite faute), c'est validé ; sinon les autres voient la réponse et décident sur leur téléphone. Ils peuvent aussi valider une réponse donnée à voix haute.

Le téléphone de l'hôte garde la partie : il doit rester allumé avec le jeu ouvert (l'écran reste allumé automatiquement). Si un joueur ferme le jeu par erreur, il le rouvre et retrouve la partie tout seul. Si un téléphone est déconnecté, l'hôte peut passer son tour d'indice ou clôturer le vote. La partie est enregistrée dans l'historique de l'hôte et de chaque joueur.

### Configurer Supabase (une seule fois, gratuit)

1. Créez un compte sur [supabase.com](https://supabase.com) puis un nouveau projet.
2. **Project Settings → API Keys** : copiez l'adresse du projet (`https://xxxx.supabase.co`) et la clé **Publishable** (`sb_publishable_…`). Aucune table à créer : le jeu n'utilise que les canaux *Broadcast* et *Presence* de Realtime.
3. Deux possibilités :
   - **Recommandé** : renseignez `SUPABASE_URL` et `SUPABASE_KEY` en haut du script de `index.html`. Tous les téléphones sont alors connectés d'office.
   - Ou collez-les dans **Réglages → Connexion en ligne** sur le téléphone de l'hôte. Les invités n'ont rien à saisir : le lien d'invitation et le QR code transmettent la connexion.

> La clé « Publishable » est faite pour être visible dans une appli web. Ne mettez jamais la clé « secret ». Si la connexion échoue, vérifiez dans **Realtime → Settings** que les canaux publics sont autorisés. Un projet gratuit inutilisé pendant longtemps peut être mis en pause : il suffit de le réactiver depuis le tableau de bord.

### Tester sur un ordinateur, sans serveur

Ouvrez plusieurs onglets du même navigateur avec `?local=1&p=nom` (un nom différent par onglet, par exemple `index.html?local=1&p=hote`, `?local=1&p=alice`…). Les onglets communiquent entre eux et chacun a ses propres données.

## 📺 Écran TV

Dans **Réglages → 📺 Écran TV**, choisissez **Oui**. Un écran supplémentaire affiche alors la partie en grand, au format paysage : à qui le tour (distribution des mots, indices), le minuteur, le vote et son décompte « 3, 2, 1 » (mode un téléphone), le fil des indices et le dépouillement (mode un téléphone par joueur), le rôle révélé, les mots de fin de manche, le **classement en direct** et le podium. La TV joue aussi les sons.

**Mise en route**

1. Sur le téléphone de l'hôte : « Qui joue ? » (un téléphone) ou la salle de jeu (un par joueur) affiche une carte **📺 Écran TV** avec le code de la salle et un bouton **QR / lien**.
2. Sur l'appareil relié à la TV : ouvrez le jeu, touchez **« 📺 Afficher sur la TV »** et tapez le code (ou scannez le QR code / ouvrez le lien `…/?tv=CODE`). La carte de l'hôte passe à « connecté ✓ ».
3. **Avec un iPad ou un iPhone** : Centre de contrôle → **Recopie de l'écran** → la TV (AirPlay), puis tournez l'appareil à l'horizontale. Le bouton « ⛶ Plein écran » masque les barres du navigateur quand c'est possible. **Avec un ordinateur** : HDMI ou « cast » de l'onglet. Le navigateur intégré de certaines TV peut aussi fonctionner, selon le modèle.

L'écran TV ne reçoit jamais les mots secrets ni les rôles avant leur révélation. En mode un téléphone, il faut internet pour la TV, mais la partie continue normalement sur le téléphone si la connexion tombe (seule la TV se fige). Si la TV se recharge, elle retrouve la partie toute seule.

## 🚀 Mise en ligne sur GitHub Pages

1. Créez un dépôt `undercover-famille` et poussez-y tous les fichiers de ce dossier.
2. Dans le dépôt : **Settings → Pages → Build and deployment → Source : Deploy from a branch**, branche `main`, dossier `/ (root)`.
3. Après une minute, le jeu est disponible sur `https://<votre-compte>.github.io/undercover-famille/`.
4. Sur le téléphone : ouvrez le lien, puis **Partager → Sur l'écran d'accueil** (iPhone) ou **⋮ → Installer l'application** (Android).

> Après une mise à jour, changez la valeur de `VERSION` dans `sw.js` pour que les téléphones récupèrent la nouvelle version.

Pour l'intégrer à un site existant, il suffit de faire un lien vers l'adresse GitHub Pages, ou de copier le dossier dans un sous-répertoire du site (tous les chemins sont relatifs).

## 🔄 Synchroniser plusieurs appareils

Dans **Réglages → Synchronisation entre appareils** :

- **Exporter mes données** : un code texte (commence par `UCF2:`) ou un fichier `.json` contenant joueurs, réglages, mots perso et historique.
- **Importer des données** : collez le code ou choisissez le fichier, puis **Fusionner** (ajoute ce qui manque, sans rien effacer) ou **Tout remplacer**.
- **Sync GitHub Gist** : créez un [jeton GitHub](https://github.com/settings/tokens/new?scopes=gist&description=Undercover) avec la seule permission `gist`, collez-le sur chaque appareil et touchez « Synchroniser ». Les données sont rangées dans un Gist secret `undercover-famille.json` et fusionnées à chaque synchro. Le jeton reste sur l'appareil et n'est jamais exporté.

**Comment la fusion décide** : chaque modification (joueur renommé, avatar, groupes cochés, groupe renommé…) est datée, et c'est la plus récente qui gagne. Chaque suppression (joueur, groupe, mot perso, partie, historique effacé, paire remise en jeu) laisse une trace datée qui part avec la synchro : les autres appareils suppriment l'élément à leur tour au lieu de le rajouter. Un joueur recréé plus tard avec le même prénom est bien conservé. Pour que tout soit à jour partout, synchronisez chaque appareil (l'ordre n'a pas d'importance).

## 🛠️ Personnaliser

Tout est dans `index.html`, sans dépendance ni étape de compilation.

- **Ajouter des mots au jeu** : objet `RAW`, format `mot1/mot2/niveau` séparés par des `;` (niveau 1 = facile, 3 = difficile).
- **Ajouter un thème** : une entrée dans `THEMES` et une dans `RAW` avec la même clé.
- **Changer les points** : objet `PTS`.
- **Couleurs** : section `<style>` en haut du fichier.

## 📁 Structure

```
undercover-famille/
├── index.html            # le jeu complet (HTML + CSS + JS)
├── manifest.webmanifest  # installation sur l'écran d'accueil
├── sw.js                 # mode hors ligne
├── icons/                # icônes de l'application
├── LICENSE
└── README.md
```

## 📄 Licence

MIT. Fait avec ❤️ pour les soirées en famille. [cdesmottes.fr](https://cdesmottes.fr)
