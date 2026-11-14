# 🕵️ Undercover Famille

Le jeu d'ambiance **Undercover**, pensé pour jouer **en famille sur un seul téléphone**… ou **avec un téléphone par joueur**.
Tout le monde reçoit un mot secret… sauf l'intrus, qui a un mot légèrement différent. À vous de le démasquer !

▶️ **Jouer en ligne** : `https://<votre-compte>.github.io/undercover-famille/`

![Icône](icons/icon-192.png)

## ✨ Fonctionnalités

- 📱 **Un seul téléphone** qui passe de main en main : le mot ne s'affiche que tant qu'on garde le doigt dessus
- 📱📱 **Ou un téléphone par joueur** (réglage « Téléphones ») : salle avec un code de 4 lettres et un QR code, mot sur chaque écran, **votes secrets** puis dépouillement (Supabase Realtime, gratuit)
- 👨‍👩‍👧‍👦 De **3 à 10 joueurs**, choisis dans une **liste de joueurs enregistrés** (prénom, avatar, couleur) au lancement de chaque partie
- 📚 **246 paires de mots** adaptées aux enfants, réparties en 11 thèmes et 3 niveaux
- ✏️ **Mots perso** : ajoutez vos propres paires (prénoms, lieux de vacances, blagues de famille)
- 🔄 **« Changer de mots »** : un mot pas compris ou une paire déjà jouée ? La manche recommence avec une nouvelle paire, sans toucher aux points
- 🗳️ Vote à main levée « 3, 2, 1… montrez du doigt ! » ; en cas d'égalité, nouveau tour d'indices puis nouveau vote
- 🎯 **Dernière chance** : l'Undercover éliminé peut deviner le mot des civils
- 🎩 **Mr White** en option (un joueur sans mot qui doit bluffer)
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

Répartition des rôles : 1 Undercover jusqu'à 6 joueurs, 2 à partir de 7. Mr White est conseillé à partir de 5 joueurs.

## 📱📱 Un téléphone par joueur

Dans **Réglages → Téléphones**, choisissez **Un par joueur**. Puis **Nouvelle partie** ouvre une salle :

1. Le téléphone de l'hôte affiche un **code de 4 lettres** et un **QR code**. L'hôte indique s'il joue aussi (son prénom) ou si son téléphone sert seulement d'écran de jeu.
2. Les autres ouvrent le jeu, touchent **📲 Rejoindre une partie** et tapent le code, ou scannent le QR code / ouvrent le lien d'invitation. Ils choisissent leur prénom dans la liste des joueurs de l'hôte ou en tapent un nouveau.
3. Chacun voit **son mot sur son écran**. Les indices se donnent toujours à voix haute : le téléphone du joueur dont c'est le tour affiche « À toi ! ».
4. **Vote secret** sur chaque téléphone (on peut changer d'avis tant que tout le monde n'a pas voté), puis dépouillement : qui a voté pour qui. Égalité → nouveau tour d'indices.
5. Dernière chance / Mr White : le joueur éliminé dit le mot à voix haute, les autres valident sur leur téléphone.

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
- **Sync GitHub Gist** : créez un [jeton GitHub](https://github.com/settings/tokens/new?scopes=gist&description=Undercover%20Famille) avec la seule permission `gist`, collez-le sur chaque appareil et touchez « Synchroniser ». Les données sont rangées dans un Gist secret `undercover-famille.json` et fusionnées à chaque synchro. Le jeton reste sur l'appareil et n'est jamais exporté.

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
