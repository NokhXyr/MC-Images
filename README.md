# MC-Images

Public image hosting for the pages of NokhXyr's Minecraft mods: CurseForge pages, Modrinth pages
and GitHub READMEs. This repository holds images only, and only images about these mods.

## Why this repository exists

A presentation page on CurseForge or Modrinth does not store its images: it loads them from an
address on the web. Some of the mods behind those pages live in **private** repositories, and a
visitor cannot load anything from a private repository, so their images would show up broken.

This repository is **public** and holds only images. Each page loads its images from here, through
the [jsDelivr](https://www.jsdelivr.com/) CDN, whatever the visibility of the mod's own repository.
The source code stays where it is; only the published images live here.

## Layout

One folder per mod, named exactly like the mod's GitHub repository (an addon kept in its mod's
repository gets its own folder, named after the repository with the addon's suffix):

```
MC-Images/
├── MC-ChiseledBlocks/     Chiseled Blocks (Minecraft mod)
├── MC-ChiseledBlocks-Create/  Chiseled Blocks: Create (addon of Chiseled Blocks)
├── MC-MostLight/          MostLight (Minecraft mod)
├── MC-MostDecoration/     MostDecoration (Minecraft mod), empty until its page is made
└── MC-Nokh-Frame/         Nokh Frame (Minecraft mod)
```

Inside a mod folder, files keep the layout they have in the mod's `images/` folder:

| Path | Content |
|---|---|
| `hero.gif` | Main banner at the top of the page |
| `badge-*.png` | Badges: issues link, Minecraft version, loader, side, required mods |
| `lang-*.gif`, `title-*-<lang>.gif`, `divider.gif` | Language labels, section titles and separator |
| `*.gif` (others) | Animated feature demonstrations |
| `icons/` | Small icons in front of each feature line |
| `screenshots/` | Full in-game screenshots |

## Using an image

Image addresses follow this pattern:

```
https://cdn.jsdelivr.net/gh/NokhXyr/MC-Images@main/<Repository>/<file>
```

For example:

```html
<img src="https://cdn.jsdelivr.net/gh/NokhXyr/MC-Images@main/MC-MostLight/hero.gif" alt="MostLight" width="800">
```

Use jsDelivr rather than `raw.githubusercontent.com`: GitHub limits anonymous requests on raw
addresses, and a page with many images ends up with some of them broken.

In a mod that generates its page with the page tools, set `images_base` in
`images/tools/page.toml` to the folder of that mod:

```toml
images_base = "https://cdn.jsdelivr.net/gh/NokhXyr/MC-Images@main/MC-MostLight/"
```

Bug reports and suggestions for the mods go to [MC-Issues](https://github.com/NokhXyr/MC-Issues),
not here.

## Updating images

1. Generate or edit the images in the mod's own `images/` folder, as usual.
2. Copy the published files into the matching folder here, keeping the same relative paths.
3. Commit and push.
4. jsDelivr keeps a file of a branch in cache for up to 12 hours. To refresh one image right away,
   open its purge address:
   `https://purge.jsdelivr.net/gh/NokhXyr/MC-Images@main/<Repository>/<file>`

Rules for this repository:

- Only images of NokhXyr's Minecraft mods that a public page actually uses. No work previews, no
  review captures, no sources.
- File names in lowercase with hyphens, without spaces.
- Keep each file under 2 MB: CurseForge and Modrinth handle heavier images poorly.
- Never rename or delete a file that a published page still loads: update the page first.
- No personal information in an image or in its metadata (name, address, server IP, local path).

## License

All rights reserved. The images belong to NokhXyr and to the mods they present. This repository
is public only so that pages can display them; it grants no right to reuse them. See
[LICENSE](LICENSE).

## Credits

Author: NokhXyr

---

# MC-Images (Version Française)

Hébergement public des images des pages des mods Minecraft de NokhXyr : pages CurseForge, pages
Modrinth et README GitHub. Ce dépôt contient uniquement des images, et uniquement sur ces mods.

## Pourquoi ce dépôt existe

Une page de présentation sur CurseForge ou Modrinth ne stocke pas ses images : elle les charge
depuis une adresse sur le web. Certains des mods derrière ces pages sont dans des dépôts
**privés**, et un visiteur ne peut rien charger depuis un dépôt privé : leurs images
s'afficheraient cassées.

Ce dépôt est **public** et ne contient que des images. Chaque page charge ses images d'ici, via le
CDN [jsDelivr](https://www.jsdelivr.com/), quelle que soit la visibilité du dépôt du mod. Le code
source reste là où il est ; seules les images publiées vivent ici.

## Organisation

Un dossier par mod, nommé exactement comme le dépôt GitHub du mod (une extension gardée dans le
dépôt de son mod a son propre dossier, nommé d'après le dépôt avec le suffixe de l'extension) :

```
MC-Images/
├── MC-ChiseledBlocks/     Chiseled Blocks (mod Minecraft)
├── MC-ChiseledBlocks-Create/  Chiseled Blocks: Create (extension de Chiseled Blocks)
├── MC-MostLight/          MostLight (mod Minecraft)
├── MC-MostDecoration/     MostDecoration (mod Minecraft), vide en attendant sa page
└── MC-Nokh-Frame/         Nokh Frame (mod Minecraft)
```

Dans le dossier d'un mod, les fichiers gardent l'organisation qu'ils ont dans le dossier
`images/` du mod :

| Chemin | Contenu |
|---|---|
| `hero.gif` | Bannière principale en haut de la page |
| `badge-*.png` | Badges : lien vers les tickets, version de Minecraft, loader, côté, mods requis |
| `lang-*.gif`, `title-*-<langue>.gif`, `divider.gif` | Étiquettes de langue, titres de section et séparateur |
| `*.gif` (autres) | Démonstrations animées des fonctionnalités |
| `icons/` | Petites icônes devant chaque ligne de fonctionnalité |
| `screenshots/` | Captures d'écran complètes en jeu |

## Utiliser une image

Les adresses des images suivent ce modèle :

```
https://cdn.jsdelivr.net/gh/NokhXyr/MC-Images@main/<Dépôt>/<fichier>
```

Par exemple :

```html
<img src="https://cdn.jsdelivr.net/gh/NokhXyr/MC-Images@main/MC-MostLight/hero.gif" alt="MostLight" width="800">
```

Utilisez jsDelivr plutôt que `raw.githubusercontent.com` : GitHub limite les requêtes anonymes sur
les adresses brutes, et une page avec beaucoup d'images finit avec certaines cassées.

Dans un mod qui génère sa page avec les outils de page, réglez `images_base` dans
`images/tools/page.toml` sur le dossier de ce mod :

```toml
images_base = "https://cdn.jsdelivr.net/gh/NokhXyr/MC-Images@main/MC-MostLight/"
```

Les signalements de bugs et les suggestions pour les mods vont dans
[MC-Issues](https://github.com/NokhXyr/MC-Issues), pas ici.

## Mettre à jour les images

1. Générez ou modifiez les images dans le dossier `images/` du mod, comme d'habitude.
2. Copiez les fichiers publiés dans le dossier correspondant ici, en gardant les mêmes chemins.
3. Faites un commit et un push.
4. jsDelivr garde un fichier d'une branche en cache jusqu'à 12 heures. Pour rafraîchir une image
   tout de suite, ouvrez son adresse de purge :
   `https://purge.jsdelivr.net/gh/NokhXyr/MC-Images@main/<Dépôt>/<fichier>`

Règles de ce dépôt :

- Uniquement les images des mods Minecraft de NokhXyr qu'une page publique utilise réellement. Pas
  d'aperçus de travail, pas de captures de revue, pas de sources.
- Noms de fichiers en minuscules avec des tirets, sans espaces.
- Chaque fichier sous 2 Mo : CurseForge et Modrinth gèrent mal les images plus lourdes.
- Ne jamais renommer ou supprimer un fichier qu'une page publiée charge encore : mettez d'abord la
  page à jour.
- Aucune information personnelle dans une image ou ses métadonnées (nom, adresse, IP de serveur,
  chemin local).

## Licence

Tous droits réservés. Les images appartiennent à NokhXyr et aux mods qu'elles présentent. Ce
dépôt est public uniquement pour que les pages puissent les afficher ; il n'accorde aucun droit de
réutilisation. Voir [LICENSE](LICENSE).

## Credits

Author: NokhXyr
