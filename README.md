# Projet Final Docker

Projet Final Docker

Date : 11/12/2024

Fait par : KADI Soulaymane, HOMBOURGER Tomy, BERNARD Jonathan, AHMADI Rateb, FIGAROLI Romain

# Explication du projet 

Dans ce projet, j'ai travaillé sur la conteneurisation de plusieurs applications web et leur mise à disposition via un reverse proxy Nginx, le tout orchestré avec un docker-compose

Une partie essentielle du projet a été la configuration de Nginx comme reverse proxy. J'ai créé un fichier de configuration dans lequel j'ai défini les règles pour rediriger les requêtes des utilisateurs vers les bonnes applications. Certaines applications, comme le site HTML5, sont directement accessibles, tandis que d'autres passent par le reverse proxy.

# Environnement de travail 

## Multipass avec un dossier “tp-final”

![image](https://github.com/user-attachments/assets/88f785c6-e156-466f-a70f-488ecb115b1c)

 

Initialisation de toutes les applications grâce à la commande ```git clone```

![image](https://github.com/user-attachments/assets/fb45d3b1-9a13-4462-a1a9-dfa204b2717d)


Arborescence du projet : 

 ![image](https://github.com/user-attachments/assets/427d98cd-981f-4393-8b69-986cace68cee)


# Configuration des fichiers

## Optimisation des images (Dockerfile)

Ajout du python:3.10-alpine pour chaque image et ajout des &&

 ![image](https://github.com/user-attachments/assets/2d71cbdb-9c99-4f2a-8640-8ec2d3f3cf6d)


Config du fichier Appseed

 ![image](https://github.com/user-attachments/assets/c38979a2-55e7-4794-9fcd-465c9273024d)

```# Configuration du reverse proxy NGINX pour Django

# Définir les upstreams pour chaque application Django
upstream django_argon_dashboard {
    server django_argon_dashboard:8000;
}

upstream django_coreui {
    server django_coreui:8001;
}

upstream django_datta_able {
    server django_datta_able:8002;
}

upstream django_material_dashboard {
    server django_material_dashboard:8003;
}

upstream django_pixel {
    server django_pixel:8004;
}

upstream django_soft_ui_design {
    server django_soft_ui_design:8005;
}

# Serveur statique pour le HTML5
server {
    listen 8080;
    server_name html5;

    root /usr/share/nginx/html;
    index index.html;

    location / {
        try_files $uri /index.html;
    }
}

server {
    listen 80;
    server_name 192.168.1.197;  

    location /django_argon_dashboard/ {
        rewrite ^/django_argon_dashboard/(.*)$ /$1 break; 
        proxy_pass http://django_argon_dashboard;
        proxy_set_header Host $host;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
    }

    # Proxy pour Django CoreUI
    location /django_coreui/ {
        rewrite ^/django_coreui/(.*)$ /$1 break;  # Réécriture de l'URL
        proxy_pass http://django_coreui;
        proxy_set_header Host $host;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
    }

    # Proxy pour Django Datta Able
    location /django_datta_able/ {
        rewrite ^/django_datta_able/(.*)$ /$1 break;  # Réécriture de l'URL
        proxy_pass http://django_datta_able;
        proxy_set_header Host $host;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
    }

    # Proxy pour Django Material Dashboard
    location /django_material_dashboard/ {
        rewrite ^/django_material_dashboard/(.*)$ /$1 break;  # Réécriture de l'URL
        proxy_pass http://django_material_dashboard;
        proxy_set_header Host $host;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
    }

    # Proxy pour Django Pixel
    location /django_pixel/ {
        rewrite ^/django_pixel/(.*)$ /$1 break;  # Réécriture de l'URL
        proxy_pass http://django_pixel;
        proxy_set_header Host $host;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
    }

    # Proxy pour Django Soft UI Design  
    location /django_soft_ui_design/ {
        rewrite ^/django_soft_ui_design/(.*)$ /$1 break;  # Réécriture de l'URL
        proxy_pass http://django_soft_ui_design;
        proxy_set_header Host $host;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
    }
}

```
Config du fichier docker-compose.yml
 
![image](https://github.com/user-attachments/assets/ca584a10-55a9-403f-bfd2-40c862a2bffe)






# Test et vérification

## Test de l’image sur un navigateur

 ![image](https://github.com/user-attachments/assets/4a522158-51c2-457d-b784-e8cda80bab4a)


## Test de l’image avec la commande curl 

 ![image](https://github.com/user-attachments/assets/6f39c511-8815-4b6d-91ab-cc72cdfd2a77)

![image](https://github.com/user-attachments/assets/98be5b12-2bc0-4c06-bae7-babe85c576ca)

 




Test de l’image qui ne passe par le Reverse Proxy :

 ![image](https://github.com/user-attachments/assets/6b86b964-69c6-40f3-a104-5239718c8f53)


## Logs : 

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
