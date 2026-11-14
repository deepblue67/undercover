# 🕵️ Undercover Famille

Le jeu d'ambiance **Undercover**, pensé pour jouer **en famille sur un seul téléphone**.
Tout le monde reçoit un mot secret… sauf l'intrus, qui a un mot légèrement différent. À vous de le démasquer !

▶️ **Jouer en ligne** : `https://<votre-compte>.github.io/undercover-famille/`

![Icône](icons/icon-192.png)

## ✨ Fonctionnalités

- 📱 **Un seul téléphone** qui passe de main en main : le mot ne s'affiche que tant qu'on garde le doigt dessus
- 👨‍👩‍👧‍👦 De **3 à 8 joueurs**, avec un prénom et un avatar chacun
- 📚 **246 paires de mots** adaptées aux enfants, réparties en 11 thèmes et 3 niveaux
- ✏️ **Mots perso** : ajoutez vos propres paires (prénoms, lieux de vacances, blagues de famille)
- 🗳️ Vote à main levée « 3, 2, 1… montrez du doigt ! », départage en cas d'égalité, tirage au sort si besoin
- 🎯 **Dernière chance** : l'Undercover éliminé peut deviner le mot des civils
- 🎩 **Mr White** en option (un joueur sans mot qui doit bluffer)
- ⏱️ Minuteur par indice (optionnel), sons, confettis et podium final
- 🤫 Bouton « Revoir mon mot » pour ceux qui l'ont oublié
- 📊 Statistiques par joueur (victoires, fois Undercover, mots devinés)
- 💾 La partie est sauvegardée : on peut fermer l'appli et reprendre plus tard
- ✈️ **Fonctionne hors ligne** et s'installe sur l'écran d'accueil (PWA)
- 🔒 Aucun compte, aucun serveur, aucune donnée envoyée : tout reste dans le téléphone

## 🎲 Règles

1. Chacun découvre son mot en secret.
2. À tour de rôle, chacun donne **un indice** sur son mot (un mot ou une petite phrase).
3. Après les tours d'indices, tout le monde **montre du doigt** son suspect en même temps.
4. Le joueur désigné est éliminé et son rôle est révélé.

**Les civils** gagnent s'ils éliminent l'Undercover. **L'Undercover** gagne s'il tient jusqu'au bout (quand il ne reste plus qu'un civil face à lui).

| Situation | Points |
|---|---|
| Civils gagnants | +2 chacun |
| Undercover gagnant | +6 |
| Dernière chance réussie (Undercover éliminé qui devine le mot des civils) | +3 |
| Mr White gagnant (survit ou devine le mot des civils) | +6 |

Répartition des rôles : 1 Undercover jusqu'à 6 joueurs, 2 à partir de 7. Mr White est conseillé à partir de 5 joueurs.

## 🚀 Mise en ligne sur GitHub Pages

1. Créez un dépôt `undercover-famille` et poussez-y tous les fichiers de ce dossier.
2. Dans le dépôt : **Settings → Pages → Build and deployment → Source : Deploy from a branch**, branche `main`, dossier `/ (root)`.
3. Après une minute, le jeu est disponible sur `https://<votre-compte>.github.io/undercover-famille/`.
4. Sur le téléphone : ouvrez le lien, puis **Partager → Sur l'écran d'accueil** (iPhone) ou **⋮ → Installer l'application** (Android).

> Après une mise à jour, changez la valeur de `VERSION` dans `sw.js` pour que les téléphones récupèrent la nouvelle version.

Pour l'intégrer à un site existant, il suffit de faire un lien vers l'adresse GitHub Pages, ou de copier le dossier dans un sous-répertoire du site (tous les chemins sont relatifs).

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
