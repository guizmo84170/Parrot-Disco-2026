# Câblage détaillé — Disco O4 Pro Mod

Schéma visuel : [`images/wiring.svg`](images/wiring.svg)

## Vue d'ensemble

| Depuis | Vers | Type de liaison | Détail |
|---|---|---|---|
| Batterie LiPo | ESC | Alim. directe | + / - |
| Batterie LiPo | Matek F405 (VBAT) | Alim. directe | + / - |
| Matek F405 (S1) | ESC | Signal PWM | Commande moteur |
| Matek F405 (S3) | Servo élevon gauche | Signal PWM | |
| Matek F405 (S4) | Servo élevon droit | Signal PWM | |
| Matek F405 (BEC 5V) | Servos (S3/S4) | Alim. | 5V régulé |
| Matek F405 (UART4) | DJI O4 Pro Air Unit | UART TX/RX + 5V + GND | Câble unique : RC + OSD/MSP + alimentation |
| Matek F405 (UART6) | Module GPS | UART TX/RX | |

## Détail par liaison

### Alimentation principale
- Batterie → ESC : câble d'alimentation direct, dimensionné selon l'ampérage moteur
- Batterie → FC (VBAT) : via le connecteur d'alimentation de la Matek F405

### UART4 — DJI O4 Pro
Câble unique DJI regroupant :
- **5V** : alimente l'O4 Air Unit depuis le BEC de la FC
- **GND** : masse commune
- **TX/RX** : liaison bidirectionnelle pour la RC (protocole DJI) et l'OSD/télémétrie (MSP)

Configuration côté INAV : **Ports → UART4 → activer "Serial RX"** (ou le protocole RC utilisé par ton firmware O4) et **MSP** si tu veux l'OSD.

### UART6 — GPS
Liaison standard GPS : TX/RX + alimentation (5V ou 3.3V selon le module — à vérifier sur ta doc GPS). Configuration : **Ports → UART6 → GPS**, puis dans **Configuration → activer le GPS** et sélectionner le bon protocole (UBLOX généralement).

### Servos (S3 / S4)
- Alimentés par le BEC 5V de la FC
- Mixés en mode **Flying Wing** dans INAV (Mixer) pour combiner aileron + profondeur sur chaque élevon

### Moteur (S1)
Signal PWM standard vers l'ESC. Vérifier le sens de rotation et calibrer l'ESC si nécessaire (min/max throttle).

## ⚠️ Points de vigilance

- **Charge du BEC** : l'O4 Air Unit + 2 servos sont tous alimentés par le même BEC 5V de la FC. Vérifie sa capacité en courant (datasheet Matek F405) pour éviter tout brownout en vol.
- **Masses communes** : toutes les masses (FC, ESC, O4, GPS) doivent être reliées entre elles, même si certaines liaisons semblent indépendantes.
- **Fixation mécanique** : le connecteur UART4 vers l'O4 doit être bien sécurisé (colle chaude, gaine thermo, attache) pour éviter toute déconnexion due aux vibrations en vol.
- **Vérification avant premier vol** : toujours tester les servos et le sens du mixer élevons au sol avant de voler (mode Angle/Horizon activé, hélice démontée).

## Ressources

- [INAV Wiki — Serial Ports](https://github.com/iNavFlight/inav/wiki)
- [INAV Wiki — Flying Wing Setup](https://github.com/iNavFlight/inav/wiki)
