# Parrot Disco – DJI O4 Pro + Matek F405 Mod

🇬🇧 [Read in English](README.md) | 🇫🇷 Français

![Disco modifié](docs/images/Hero.png)

Modification complète du Parrot Disco : suppression du chuck d'origine, intégration d'un système vidéo **DJI O4 Pro** et d'un contrôleur de vol **Matek F405**, avec pièces 3D imprimées sur-mesure.

## 🎯 Présentation du projet

- **Pourquoi ce mod ?** Remplacement de l'électronique propriétaire Parrot par une stack moderne, open et réparable (vidéo longue portée O4 Pro + contrôleur de vol INAV).
- **Gains** : suppression du chuck (poids/encombrement), vidéo numérique longue portée, réglages de vol personnalisables via INAV.
- **Statut** : ✅ Fonctionnel

## ✈️ Résultat

[Vidéo du premier vol]([LIEN_VIDEO](https://youtu.be/oAaKVsJd3Pc?si=X5Niqoi7fkNdR0t8))

## 🛠️ Matériel utilisé

| Composant | Référence | Lien d'achat |
|---|---|---|
| Système vidéo | DJI O4 Pro | [LIEN](https://www.lacameraembarquee.fr/dji-o4-air-unit-goggles/17819-dji-o4-air-unit-pro-6941565997449.html) |
| Contrôleur de vol | Matek F405 | [LIEN](https://www.drone-fpv-racer.com/controleur-de-vol-f405-wing-v2-matek-11770.html) |
| Récepteur RC | DJI O4 Pro | [LIEN](https://www.lacameraembarquee.fr/dji-o4-air-unit-goggles/17819-dji-o4-air-unit-pro-6941565997449.html) |
| ESC | 20A | [LIEN](https://www.amazon.fr/HAWKS-WORK-ESC-R%C3%A9gulateur-%C3%A9lectrique/dp/B0B25DLFZ2) |
| Batterie | 3S 2200mAh | [LIEN](https://www.lacameraembarquee.fr/batteries-fpv/15885-batterie-lipo-cnhl-black-series-3s-2200mah-40c.html) |
| Autre (connecteurs, câblage, etc.) | | [LIEN] |
| GPS M10 | | [LIEN](https://www.drone-fpv-racer.com/module-gps-m10-glonass-tbs-12411.html) |
| Câbles Dupont | | |
| Insert laiton pour impression 3D | | |
| Vis 2.5mm | | |
| Ventilateur 30mmx30mm 5V | | |

## 🖨️ Pièces imprimées 3D

Toutes les pièces sont disponibles en téléchargement/achat sur :

- **Cults3D** : [LIEN](https://cults3d.com/fr/mod%C3%A8le-3d/jeu/parrot-disco-2026-mod-full-fpv)

| Pièce | Fonction | Matériau conseillé | Fichier |
|---|---|---|---|
| Support O4 Pro | Fixation VTX | PETG/PLA | `stl/support_o4pro.stl` |
| Support Matek F405 | Fixation FC + amortissement vibrations | PETG/PLA | `stl/support_fc.stl` |
| Support Caméra | Fixation caméra | PLA/PETG | `stl/support_camera.stl` |

**Paramètres d'impression recommandés**  :
- Hauteur de couche : 0.2 mm
- Remplissage : 20–30%
- Parois : 3
- Support : *(oui/non selon pièce)*
- PLA

## 🔌 Câblage

![Schéma de câblage](docs/images/wiring.svg)

Détail des connexions FC ↔ O4 Pro ↔ récepteur : voir [`docs/wiring.md`](docs/wiring.md)

## ⚙️ Réglages INAV

Fichier de configuration exportable directement dans le INAV Configurator :

📄 [`inav/disco_o4pro.txt`](inav/disco_o4pro.txt) — *(dump complet via CLI `diff all`)*

Points clés de configuration :
- **Mixer** : profil fixed-wing, type *(à préciser : DIFFERENTIAL_THRUST, etc.)*
- **Modes de vol** : *(ANGLE, NAV_ALTHOLD, RTH, etc.)*
- **Failsafe** : *(réglages spécifiques recommandés)*
- **PID** : valeurs ajustées pour la masse/inertie du Disco modifié

> ⚠️ Ces réglages sont un point de départ, pas une config universelle. Ajuste selon ton propre montage et fais tes tests en conditions sûres.

## 📋 Guide de montage

1. Démontage du C.H.U.C.K d'origine
2. Impression et préparation des supports 3D
3. Installation Matek F405 + câblage
4. Installation DJI O4 Pro
5. Flash et configuration INAV
6. Calibration (accéléromètre, compas, ESC)
7. Tests au sol avant premier vol

Détails complets : [`docs/guide-montage.md`](docs/guide-montage.md)

## ⚠️ Avertissement

Ce mod implique de voler avec un firmware et un matériel non homologués par Parrot. À réaliser en connaissance de cause, dans le respect de la réglementation drone en vigueur (DGAC / réglementation locale), et jamais au-dessus de personnes ou zones sensibles.

## 📬 Contact / Commander

- Pièces imprimées prêtes à l'emploi : me faire la demande par Email
- Questions techniques : Email

