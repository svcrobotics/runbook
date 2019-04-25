# Enregistrez une session terminal sous Linux avec TermRecord

par    Sandstorm  · Publié 7 mai 2014 · Mis à jour 3 août 2014

2-3 minutes

------

​     **F**aire  un tutoriel pour aider les autres c'est pas mal, mais parfois les mots  ne suffisent pas pour être bien clair. Et lorsque l'on balance des  commandes dans un terminal Linux, le lecteur n'a qu'à s'accrocher ! Pas  toujours évident. Et bien je viens de découvrir un outil fort sympa, en  python, permettant d'enregistrer une session terminal pour pouvoir la  relire plus tard : il s'agit de TermRecord. Cet outil va permettre  d'enregistrer ce qui se passe dans le terminal dans un fichier... html  ! Voici donc un petit topo sur le logiciel : comment ça s'installe,  comment ça fonctionne etc...

***Installation de TermRecord***

TermRecord  est codé en python. Il faut donc disposer de python sur sa machine,  ainsi que de pip pour pouvoir l'installer. Si vous ne disposez pas de  cela, la commande suivante devrait vous installer à la fois python et  pip (si vous êtes sous ubuntu/debian) :

> sudo apt-get install python-pip

Ensuite, on installe tout simplement TermRecord :

> sudo pip install TermRecord

Et voilà ! C'est installé. 

***Fonctionnement de TermRecord***

TermRecord a la particularité d'enregistrer la séquence terminal dans un fichier html.

Pour lancer un enregistrement, ouvrez un terminal, puis tapez :

> TermRecord -o /tmp/session.html

Tout  ce que vous saisirez ensuite sera enregistré, ainsi que les retours qui  s'affichent dans le terminal. Lorsque vous avez terminé, il suffit de  taper *exit* et l'enregistrement s'arrête.

Ensuite, vous n'avez qu'à ouvrir le fichier html, et vous obtiendrez ça :

[![TermRecord](https://www.justegeek.fr/wp-content/uploads/2014/08/xTermRecord_1-350x189.png.pagespeed.ic.REYAp695F2.png)](https://www.justegeek.fr/wp-content/uploads/2014/08/TermRecord_1.png)

[![TermRecord](https://www.justegeek.fr/wp-content/uploads/2014/08/xTermRecord_2-350x184.png.pagespeed.ic.EzZBIKv_uO.jpg)](https://www.justegeek.fr/wp-content/uploads/2014/08/TermRecord_2.png)

La  page html vous permet de mettre en pause l'enregistrement, puis de le  redémarrer. Vous pouvez également modifier la vitesse de lecture etc...  Envie de voir le rendu ? C'est [ici](https://www.justegeek.fr/pages/TermRecord.html). Vraiment  très pratique comme outil. Il convient également de préciser que  TermRecord fonctionne aussi sous Mac OS X, mais je ne donnerai pas ici  la procédure car je n'ai pas eu le temps de le mettre en place sous Mac  OS X.

​            

