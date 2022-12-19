# Git repo pour le TP Docker

# J'utilise Curl pendant cette partie car Mozilla ne fonctionne pas sur ma VM

Lancement du container nginx avec l'option de volume qui pointe sur le fichier index.html créé :

```bash
docker run --name Test2 -v /home/elu/Git/DevOps/TP_Docker/Web:/usr/share/nginx/html -d -p 80:80 nginx
```

On test si le container renvoi bien le fichier

```bash
curl localhost:80
```

On éteint le container avec

```bash
docker stop test
```

On supprime le container avec

```bash
docker rm test
```

On utilise la commande cp pour faire la même action qu'avec l'option -v

```bash
docker cp ./index.html test:/usr/share/nginx/html
```

On test à nouveau si ça fonctionne 

```bash
curl localhost:80
```

# Question 6

On créer un dockerfile, on précise l'image nginx:latest puis on execute grace a la commande 

```bash
docker build -t test .
```

Pour la demarrer 

```bash
docker run -d test
```

La méthode via volume ou cp permet la mise en place d'image qui ne peut pas etre versionné

La méthode via dockerfile permet de mettre en place l'images dans un premier temps et ensuite de pouvoir l'executer simplement sans plus de mise en place
