# README

Ce ver Discord rejoint tous les serveurs qu'il trouve. Il recherche les invitations, rejoint les serveurs et collectes les donnees suivante :  
Actuellement : 
- Nom de serveur
- Code identifiant du serveur
- Nom de tous les membres du serveur
- Identifiants de tous les membres du seveur
A venir :
- Tous les messages des serveurs associes a leurs utilisateurs
- Statut de connexion en live des utilisateurs sur les serveurs

## Principe general

L'ensemble du programme sera  en 3 parties :
- Le ver (en gros deterre.py)
- Le serveur (la partie django)
- L'analyseur (une future partie)

Le ver : 
- Recolte les datas sur discord et fait des requetes POST vers l'API django pour ajouter ce qu'il trouve en DB 

Le serveur  : 
- Recoit les appels API et fait les modifications en DB 
- A une interface d'admin pour pourvoir modifier / acceder aux data quand on le souhaite
- Recoit des appels API GET et fournit les data de la DB 

L'analyseur : 
- Fait des appels GET vers le serveur
- Analyse et recoupe les datas
- Genere des graphiques
- *Cette pqrtie n'est pas encore live*

## How to ...?

**Lancer le serveur :**
``` bash
cd siteweb/
python3 manage.py runserver
```

**Pour creer un utilisateur admin :**
``` bash
cd siteweb/
python3 manage.py createsuperuser
```  

**Pour effectuer des migrations (update du model de donee) :**
``` bash
python3 manage.py makemigrations
python3 manage.py migrate
```

**Pour lancer le ver**
- Ayez un compte discord avec un `DISCORD_TOKEN` qui permet d'utiliser les API
- Lancez le serveur
- Puis : 
``` bash
# Setup env
export DISCORD_TOKEN=<your_token>
# or edit ver/.env

python3 ver/deterre-v2.py
```
- Enfin lancez un premier lien d'invitation sur le serveur d'origin ou se trouve votre ver... Et c'est partit !

# Contributeurs 

- VictorLuc4
- Dadoo-A