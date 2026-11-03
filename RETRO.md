# RETRO : Dodge the Creeps 

- **Dates** : 03 novembre 2026
- **Temps passé (estimé)**: 4h
- **Moteur / version**: Godot 4
- **Statut** : Terminé

## 1. Objectif initial vs résultat

- **Ce que je voulais faire** : Suivre le tuto pour apprendre les base de godot et du game dev
- **Ce que j'ai réellement livré**: Le jeu complet (joueurs, mobs, score, HUD, game over/restart, musique)
- **Écarts de scope**: Aucun

## 2. Ce qui a bien marché

- Le découpage en scènes (`Player`, `Mob`, `HUD`, `Main`) : chaque scène est testable seule.
- Les signaux pour communiquer (`hit`, `start_game`)

## 3. Ce qui a cassé / ce qui a été pénible

| Problème | Cause racine | Comment je l'ai résolu |
| Le joueurs se déplaçais que d'un px lors d'un déplacement `up` | Erreur de fonction `is_action_just_pressed` | Remplacement par `is_action_pressed` |

## 4. Ce que je n'ai pas compris
- Revoir les notion de delta et de PI pour les orientations et calculs de vitesse

## 5. Architecture : bilan

- **Ce qui a tenu la route** : séparation `Main` (orchestration) / `Player` / `Mob` / `HUD`, communication par signaux.
- **Ce qui a mal vieilli** : `Main` fait tout (spawn, score, game over) : il deviendrait ingérable avec plus de features.
- **Écart entre ARCHITECTURE.md et le code final** : Pas de ARCHITECTURE.md (Premier projet suivi de tuto).
- **Ce que je referais autrement** : Organisation des fichiers

## 6. Utilisation de l'IA

- **Où elle a aidé** (explication, relecture, debug) : Explication de concepts avec example
- **Où j'ai été tenté de déléguer** : Pas de besoin 
- **Code que je ne saurais pas réécrire seul** : Aucun

## 7. Concept appris 

- Scènes et instanciation (`preload` + `instantiate`)
- Signaux (déclaration, connexion éditeur et code)
- `Area2D` + détection de collision par signal
- Groupes de nodes
- `Path2D` / `PathFollow2D` pour le spawn
- Séparation UI (`CanvasLayer`) / gameplay

## 8. Actions pour le prochain projet

- Écrire l'architecture complète **avant** de toucher à l'éditeur
- Ne pas mettre toute la logique dans `Main` : prévoir dès le départ un script par responsabilité

## 9. Notes libres 
