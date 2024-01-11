Exo 1 commands : 

- docker pull docsseo91/stardocker:v1

Exo 2 commands :

- docker build -t 25032047/firstbasicwebsite .
- docker run -d -p 80:80 25032047/firstbasicwebsite


Exo 3 commands :

- docker login ... (je donne pas mes logs :)
- docker image push 25032047/firstbasicwebsite
(je suis obligé de mettre le username devant l'image sinon je ne peut pas push, je sais pas pourquoi, j'ai modifié les lignes de l'exo 2 enc conséquence)


Exo 4 commands :

- docker build -t firstnodewebsite .
- docker run -d -p 3000:3000 firstnodewebsite


Exo 5 commands :

docker build . -t firstsqlimage
docker run -d --rm -p 5432:5432 -e POSTGRES_PASSWORD=postgres -e POSTGRES_USER=postgres --name workingfirstsqlimage firstsqlimage

docker exec -it workingfirstsqlimage sh
psql -h localhost -U postgres

postgres=# SELECT nom from personnes where age > 30;

    nom
-----------
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


 Exo 6 commands :