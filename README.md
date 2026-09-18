# Maquette — Rapport de chantier

Comparaison de directions visuelles pour les écrans du projet ServiceDesk P-20260810-0001
(module BRD « Rapports & temps chantier », v0.5.1). Zéro code de production, zéro branchement
réel — pour choisir une direction avant de construire.

## Lancer en local

Depuis la racine du dépôt :

```bash
python3 -m http.server 8420 --directory maquette/rapport-chantier
```

Puis ouvrir http://localhost:8420 dans un navigateur. Fonctionne aussi en ouvrant
`index.html` directement dans un navigateur (double-clic), sauf l'onglet « Direction 1 »
de `raj.html` qui charge un `<iframe>` local et préfère un vrai serveur.

## Contenu

| Fichier | Écran | Directions comparées |
|---|---|---|
| `sdt.html` | Saisie du temps — homme de chantier | Minimaliste · Guidée pas-à-pas · Grille dense |
| `raj.html` | Rapport journalier — contremaître | Existant (PR #753, copié tel quel) · Tableau de bord · Grille dense |
| `bureau.html` | Suivi au bureau (desktop) | Liste + filtres · Par exception · Grille consolidée |
| `raj-existant-pr753.html` | Copie non modifiée de la maquette du contremaître déjà livrée (PR #753 / E-20260910-0005) — chargée en `<iframe>` par `raj.html` | — |

## Sources

- BRD `Action Progex — Module Rapports & temps chantier` v0.5.1 (Somcraft `647ccfa8-…`), domaines RAJ/SDT/TMP.
- Formulaire papier réel « Rapport de chantier — Civil », chantier 166 — Port-Daniel, scans du 29 et 30 juin 2026.
- Maquette contremaître existante, PR GitHub #753, branche `docs/E-20260910-0005-maquette-rapport-chantier-contremaitre`.

## Point ouvert

Le champ « P ou T » du formulaire papier est marqué **à valider avec Progex** partout où il
apparaît (SDT, RAJ). Son sens n'a jamais été confirmé — même le module OCR en production le
documente comme tel (`site_report_labor_entries.pt_indicator`).
