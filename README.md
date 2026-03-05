# 🤖 PAMI - Coupe de France de Robotique 2026 - Carte Électronique (PCB)

![Status](https://img.shields.io/badge/Status-En_Développement-orange)
![Version](https://img.shields.io/badge/Version-V1.0-blue)

Bienvenue sur le dépôt dédié à la conception de la carte électronique (PCB) des **PAMI** (Petits Actionneurs Mobiles Intelligents) de notre équipe pour la Coupe de France de Robotique 2026.

Ce dépôt centralise les schémas, le routage, les fichiers de fabrication (Gerber) et la nomenclature (BOM) de la carte mère du robot.

---

## ⚙️ Spécifications Matérielles (Hardware)

### ⚡ Architecture Électronique & Puissance
La carte mère est conçue autour d'un microcontrôleur ESP32 et intègre toute la distribution de puissance, le contrôle moteur et les interfaces capteurs/IHM.

* **Cerveau :** Microcontrôleur ESP32 (Modèle précis à déterminer).
* **Programmation & Debug :** Port USB-C intégré à la carte.
* **Alimentation Générale :** Entrée Batterie avec coupure de sécurité matérielle via un **Bouton d'Arrêt d'Urgence (BAU)**.
* **Drivers Moteurs DC :** 2x TB67H420FTG (Contrôle indépendant des moteurs gauche/droit).

### 🏎️ Motorisation & Cinématique (Rappel de la cible)
* **Moteurs :** 2x CHW-4632-370 ABHL 6V (Moteurs CC à balais avec réducteur à vis sans fin).
* **Rapport de réduction :** 1:32 (Renvoi d'angle à 90° - 185 RPM à vide).
* **Vitesse de croisière estimée :** ~27 cm/s (avec des roues de 40 mm).
* **Couple de décrochage (Stall Torque) :** > 2.9 Kg.cm par moteur.
* **Odométrie :** Encodeurs magnétiques à effet Hall (Quadratrure Phase A/B), offrant ~352 tics par tour de roue.

### 📡 Capteurs & Actionneurs Auxiliaires
* **Évitement (Adversaires/Obstacles) :** Interface pour capteur LIDAR.
* **Actionneurs secondaires :** Connectique pour 2x Servomoteurs.

### 🕹️ Interface Homme-Machine (IHM) intégrée
* **Affichage Équipe :** 1x LED RGB.
* **Indicateurs de Statut (Batterie, Erreurs, etc.) :** 4x LEDs standards.
* **Configuration (Changement couleur équipe) :** 1x Bouton poussoir utilisateur.

---

## 📂 Architecture du Dépôt

```text
📦 PAMI-PCB-2026
 ┣ 📂 hardware/               # Projet KiCad (Schémas et Routage)
 ┣ 📂 fabrication/            # Fichiers générés pour l'usinage/assemblage (Générés en fin de projet)
 ┣ 📂 docs/                   # Documentation technique
 ┗ 📜 README.md