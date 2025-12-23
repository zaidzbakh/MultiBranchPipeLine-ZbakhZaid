
Objectif du Projet
Créer un pipeline CI/CD complet entre GitHub et Jenkins en utilisant ngrok pour exposer Jenkins localement. À chaque push sur GitHub, Jenkins doit automatiquement builder et tester le projet.

Architecture
GitHub → Webhook → ngrok → Jenkins local → Build automatique

Étapes Réalisées
1. Installation et Configuration Jenkins
Jenkins installé sur le port 8080

Plugins installés : GitHub Integration, Pipeline, Git

2. Configuration ngrok
Tunnel HTTP créé vers localhost:8080

URL ngrok générée : https://kara-ruffed-enterprisingly.ngrok-free.dev/

3. Webhook GitHub
   
Configuration du webhook pointant vers l'URL ngrok
Événement déclencheur : push
Statut : Fonctionnel



4. Multibranch Pipeline
   
Pipeline créé dans Jenkins
Branch source : Repository GitHub
Build configuration : Jenkinsfile



5. Projet de Test
Projet Java Maven simple créé

Jenkinsfile avec étapes : Build, Test, Package, Run

Preuves de Fonctionnement
Webhook GitHub Actif
<img width="1375" height="642" alt="webhook" src="https://github.com/user-attachments/assets/927b47a4-010c-43c6-9bd7-7515c8f60615" />
Le webhook est configuré et montre "Last delivery was successful".

PING Reçu dans Jenkins
<img width="861" height="102" alt="ping" src="https://github.com/user-attachments/assets/b1badcab-1f0f-4516-9dc7-e29925b11dfa" />
Jenkins a bien reçu le PING de test de GitHub.

Scan Réussi du Repository
<img width="940" height="676" alt="success" src="https://github.com/user-attachments/assets/e5a0f621-c6ca-4b4b-9ec8-59407bd972c5" />
Le scan du repository GitHub s'est terminé avec succès.

Résultats
Webhook fonctionnel : GitHub envoie des notifications à Jenkins
Jenkins écoute : Réception confirmée des webhooks
Pipeline opérationnel : Build déclenché automatiquement
Intégration complète : CI/CD entre GitHub et Jenkins

Problèmes Résolus
Erreur 403 CSRF : Désactivé la protection CSRF dans Jenkins

Timeout API GitHub : Reconfiguré les credentials et timeout

Fichiers indésirables : Nettoyé le repository des fichiers Eclipse

Conclusion
Le TP est réussi avec une intégration complète entre GitHub et Jenkins via ngrok. Le système fonctionne automatiquement : chaque push sur GitHub déclenche un build Jenkins. Cette configuration démontre les principes de base du CI/CD dans un environnement DevOps.
