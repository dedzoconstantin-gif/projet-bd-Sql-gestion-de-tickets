# Implementation d'une Base de Données pour Support Technique

## 📝 Présentation du Projet
[cite_start]Ce projet a pour objectif de concevoir et d'implémenter une base de données relationnelle dédiée à la gestion des tickets de support et à la documentation des incidents.

### Objectifs principaux :
* [cite_start]**Centralisation** des tickets de support[cite: 6].
* [cite_start]**Suivi précis** des incidents et des délais de résolution[cite: 7, 8].
* [cite_start]**Traçabilité** complète via l'historique des interventions[cite: 9].

## 👥 Acteurs du Système
[cite_start]Le système définit quatre rôles principaux[cite: 15, 17]:
* [cite_start]**Utilisateur** : Soumet et consulte ses tickets[cite: 17].
* [cite_start]**Agent Support** : Traite et résout les incidents[cite: 17].
* [cite_start]**Responsable Support** : Analyse les performances et génère des rapports[cite: 17].
* [cite_start]**Administrateur** : Gère la configuration et les utilisateurs[cite: 17].

## 🛠️ Structure de la Base de Données (Modèle Conceptuel)
[cite_start]Le projet s'appuie sur plusieurs entités clés et leurs relations[cite: 71, 86]:
* [cite_start]**Utilisateur (1) ↔ (0..*) Ticket** : Un utilisateur peut créer plusieurs tickets[cite: 87].
* **Ticket (1) ↔ (0..*) Commentaire** : Permet le suivi détaillé de chaque incident[cite: 87].
* **Ticket (1) ↔ (0..*) Fichier Joint** : Possibilité d'attacher des documents justificatifs[cite: 87].
* **AgentSupport (0..*) ↔ (0..1) Ticket** : Un agent gère plusieurs tickets, mais un ticket est affecté à un seul agent[cite: 87].

## 🚀 Installation et Utilisation
Le script SQL se trouve dans le dossier principal. Pour l'exécuter :
1. [cite_start]Créez la base de données : `CREATE DATABASE GestionSupport;`[cite: 88].
2. [cite_start]Utilisez la base : `USE GestionSupport;`[cite: 89].
3. [cite_start]Exécutez le script de création des tables (Utilisateur, AgentSupport, Ticket, etc.)[cite: 91, 100, 123].

---
[cite_start]**Auteur** : DEDZO CONSTANTIN SRI [cite: 4]
