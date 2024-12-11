# Projet Final Docker

Projet Final Docker

Date : 11/12/2024

Fait par : KADI Soulaymane, HOMBOURGER Tomy, BERNARD Jonathan, AHMADI Rateb, FIGAROLI Romain


Sommaire :

Table des matières
Environnement de travail	2
Configuration des fichiers	3
Optimisation des images (Dockerfile)	3
Test et vérification	5
Test de l’image sur un navigateur	5
Test de l’image avec la commande curl	5
Test de l’image qui ne passe par le Reverse Proxy :	6
Repos Git	7
Schéma	8
Questions	8

















# Environnement de travail 

Multipass avec un dossier “tp-final”

![image](https://github.com/user-attachments/assets/88f785c6-e156-466f-a70f-488ecb115b1c)

 

Initialisation de toutes les applications grâce à la commande “Git clone”

![image](https://github.com/user-attachments/assets/fb45d3b1-9a13-4462-a1a9-dfa204b2717d)


Arborescence du projet : 

 ![image](https://github.com/user-attachments/assets/427d98cd-981f-4393-8b69-986cace68cee)


# Configuration des fichiers

Optimisation des images (Dockerfile)

Ajout du python:3.10-alpine pour chaque image et ajout des &&

 ![image](https://github.com/user-attachments/assets/2d71cbdb-9c99-4f2a-8640-8ec2d3f3cf6d)


Config du fichier Appseed

 ![image](https://github.com/user-attachments/assets/c38979a2-55e7-4794-9fcd-465c9273024d)


Config du fichier docker-compose.yml
 
![image](https://github.com/user-attachments/assets/ca584a10-55a9-403f-bfd2-40c862a2bffe)






# Test et vérification

Test de l’image sur un navigateur

 ![image](https://github.com/user-attachments/assets/4a522158-51c2-457d-b784-e8cda80bab4a)


Test de l’image avec la commande curl 

 ![image](https://github.com/user-attachments/assets/6f39c511-8815-4b6d-91ab-cc72cdfd2a77)

![image](https://github.com/user-attachments/assets/98be5b12-2bc0-4c06-bae7-babe85c576ca)

 




Test de l’image qui ne passe par le Reverse Proxy :

 ![image](https://github.com/user-attachments/assets/6b86b964-69c6-40f3-a104-5239718c8f53)


Logs : 

 ![image](https://github.com/user-attachments/assets/d8e0f2d4-7723-4c41-bf6f-b245a95e78f6)







# Repos Git

 ![image](https://github.com/user-attachments/assets/a5d1c704-5a95-4654-bcdc-6a69b0f3ba15)


Accessible via l’adresse : https://github.com/Soutshy/tp-final-docker









# Schéma 





![image](https://github.com/user-attachments/assets/0ef9c5a0-8346-4489-9c49-0b59064b1648)










# Questions 

Qu'est-ce que le devops ?
Le DevOps, c’est un ensemble de pratiques qui combinent le développement logiciel. Le but principal est d’améliorer la collaboration entre les équipes pour livrer des projets plus rapidement, tout en garantissant la qualité
En quoi le devops vous a aidé dans cette mission ?
Nous n’avons pas utilisé le DevOps

Votre chef de projet vous demande de comparer l'utilisation de Docker avec des machines virtuelles. Que répondrez-vous ?
Docker est plus léger que les machines virtuelles. Une VM embarque tout un système d’exploitation, ce qui consomme beaucoup de ressources



À l'aide de vos connaissances personnelles, citer un ou plusieurs autres outils similaires à docker qui pourrait aider votre équipe à livrer et maintenir ce projet client.
-	Kubernetes
-	PodMan
