# Site vitrine AlphaCompanion

Page statique (HTML/CSS pur, sans build) pour présenter AlphaCompanion et vendre les licences
premium (EF-CMP-10/EF-CMP-11). Volontairement séparée de la PWA (`src/`) : ce dossier ne passe pas
par `vite build` et n'est pas embarqué dans le bundle de l'application.

## Déploiement

N'importe quel hébergeur de fichiers statiques convient (Netlify, GitHub Pages, Vercel...) : il
suffit de pointer vers ce dossier `site-vitrine/`, aucune commande de build n'est nécessaire.

## TODO avant mise en ligne

1. **Paiement** — `index.html` contient un bouton « Acheter une licence » marqué
   `data-lien-paiement-todo`. Une fois le compte marchand CinetPay (ou autre) validé, remplacer le
   `href="#"` par le lien de paiement généré, avec `merci.html` comme URL de redirection après
   paiement réussi.
2. **Tarif** — le prix de la licence premium n'est pas encore fixé (absent du SRS). Remplacer
   « tarif à venir » dans `index.html` une fois décidé.
3. **Livraison de la clé** — après un paiement réussi, générer la clé avec
   `node tools/generate-license.mjs --cle-privee <chemin> --duree <ex: 1an>` (voir ce script) et
   l'envoyer par email à l'acheteur. Manuel pour l'instant ; automatisable plus tard via un webhook
   du prestataire de paiement.
4. **Lien retour vers l'app** — le bouton « Ouvrir AlphaCompanion » du plan gratuit pointe vers `/`
   ; à ajuster selon l'URL réelle de déploiement de la PWA une fois connue.
