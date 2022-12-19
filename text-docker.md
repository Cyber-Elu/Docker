Git repo pour le TP Docker
#J'utilise Curl pendant cette partie car Mozilla ne fonctionne pas sur ma VM

#Lancement du container nginx avec l'option de volume qui pointe sur le fichier index.html créé :

docker run --name Test2 -v /home/elu/Git/DevOps/TP_Docker/Web:/usr/share/nginx/html -d -p 80:80 nginx

#On test si le container renvoi bien le fichier

curl localhost:80

#On éteint le container avec

docker stop test

#On supprime le container avec

docker rm test

#On utilise la commande cp pour faire la même action qu'avec l'option -v

docker cp ./index.html test:/usr/share/nginx/html

#On test à nouveau si ça fonctionne 

curl localhost:80
