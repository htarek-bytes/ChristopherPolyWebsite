# Tableau de bord d'administration — Christophe Poly

Ce site est équipé d'un **tableau de bord simplifié** qui permet de **modifier,
ajouter ou supprimer toutes les photos et tous les PDF** en quelques clics,
sans aucune compétence technique.

Il repose sur **Decap CMS** (gratuit, aucun serveur à gérer) et sur le système
d'identité de **Netlify** où le site est hébergé.

---

## 1. Où se trouve le tableau de bord ?

À l'adresse de votre site suivie de `/admin/` :

```
https://votre-site.netlify.app/admin/
```

*(par exemple `https://stalwart-kataifi-cc2c3c.netlify.app/admin/`)*

---

## 2. Activation (une seule fois, par un administrateur Netlify)

Ces deux réglages s'activent en **quelques minutes** dans le tableau de bord
Netlify. Ils ne sont à faire **qu'une seule fois**.

1. **Activer Netlify Identity**
   - Netlify → votre site → **Site configuration → Identity → Enable Identity**.

2. **Activer Git Gateway**
   - Toujours dans **Identity → Services → Git Gateway → Enable**.
   - C'est ce qui permet au tableau de bord d'enregistrer les changements.

3. **(Recommandé) Inscriptions sur invitation seulement**
   - **Identity → Registration → Invite only**, pour que personne d'autre ne
     puisse créer de compte.

4. **Inviter la personne qui gérera le site**
   - **Identity → Invite users** → entrez son courriel.
   - Elle recevra un courriel d'invitation : en cliquant sur le lien, elle
     choisit son mot de passe, puis arrive directement sur `/admin/`.

---

## 3. Utilisation au quotidien

Une fois connecté sur `/admin/`, on trouve deux sections :

### 📷 Photos du site
- Ouvrez **« Portraits & atelier »**.
- Cliquez sur une image, puis **« Choose an image »** pour téléverser une
  nouvelle photo, ou **utilisez le bouton Media** (en haut) pour ajouter /
  supprimer librement des photos.
- Cliquez **« Publish »** : le site se met à jour automatiquement en 1–2 minutes.

### 📄 Documents PDF
- Ouvrez **« PDF du portail commerçant »**.
- Remplacez le catalogue, les codes ou la brochure par un nouveau fichier PDF.
- Cliquez **« Publish »**.

### 💡 Astuce importante — remplacer une image ou un PDF existant
Pour qu'une nouvelle photo/PDF **remplace** l'ancienne partout sur le site,
téléversez le fichier en **gardant exactement le même nom** que l'original
(ex. `atelier1.jpg`, `CATA.FR_.26.2.pdf`). Le site utilise ces noms de
fichiers ; en conservant le même nom, le remplacement est automatique.

Pour simplement **ajouter** une nouvelle photo (nouveau nom), utilisez le
bouton **« Media »** en haut du tableau de bord : téléversez, et le fichier est
disponible immédiatement.

---

## 4. Fichiers techniques (ne pas supprimer)

| Fichier | Rôle |
|---|---|
| `admin/index.html` | Page du tableau de bord |
| `admin/config.yml` | Configuration (photos, PDF, français) |
| `_data/photos.json` | Références des photos gérées |
| `_data/documents.json` | Références des PDF gérés |

---

## 5. En cas de blocage

- **Impossible de se connecter** → vérifier que *Identity* et *Git Gateway*
  sont bien activés (étape 2).
- **Les changements n'apparaissent pas** → patienter 1–2 minutes (le temps que
  Netlify republie le site), puis rafraîchir la page.
- Pour toute question technique : contacter la personne qui gère l'hébergement
  Netlify.
