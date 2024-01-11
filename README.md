## ==> Exo 1 commands : 

- docker pull docsseo91/stardocker:v1

## ==> Exo 2 commands :

(Lignes de commandes modifiés avec username en fonction de l'erreur rencontré dans l'exo 3 concernant le manque de droits de gestion)

- docker build -t 25032047/firstbasicwebsite .

- docker run -d -p 80:80 25032047/firstbasicwebsite


## ==> Exo 3 commands :

- docker login ... 
(Je devais faire cette ligne pour me connecter et pouvoir push l'image)

- docker image push 25032047/firstbasicwebsite
(Je suis obligé de mettre le username devant l'image sinon je ne peut pas push faute de droits, je ne connais pas la raison, j'ai modifié les lignes de commande de l'exo 2 en conséquence)


## ==> Exo 4 commands :

- docker build -t firstnodewebsite .

- docker run -d -p 3000:3000 firstnodewebsite


## ==> Exo 5 commands :

- docker build . -t firstsqlimage

- docker run -d --rm -p 5432:5432 -e POSTGRES_PASSWORD=postgres -e POSTGRES_USER=postgres --name workingfirstsqlimage firstsqlimage

- docker exec -it workingfirstsqlimage sh

- psql -h localhost -U postgres

- postgres=# SELECT nom from personnes where age > 30;

------
Une partie du retour console de la requête SQL effectuée :
 Charlie
 Erik
 Fanny
 George
 Karl
 Laura
 Mohamed
 Oscar
 Steve
 Tina
 Valerie
 William
 Xavier
 Zoé
 André
 Brigitte
 Danielle
 Flore
 Hugo
 Jocelyn
 Karim
 ... (plus d'info mais max taille terminal)


------


## Exo 6 commands :

(Je rencontre une erreur dans la récupération du fichier de base de données, voici l'erreur :
{"error":"database \"//workingfirstsqlimage/docker-entrypoint-initdb.d/db\" does not exist"})

- docker network create -d bridge nodenetwork

- docker build -t nodeapi .
- docker run -d -p 3000:3000 --network=nodenetwork nodeapi

- docker build . -t firstsqlimage
- docker run -d --rm -p 5432:5432 -e POSTGRES_PASSWORD=postgres -e POSTGRES_USER=postgres --name workingfirstsqlimage --network=nodenetwork firstsqlimage