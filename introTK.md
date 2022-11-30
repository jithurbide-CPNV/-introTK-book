---
title:      Cookbook tkinter
banner:     CFC - Informatique
author:     Julien Ithurbide
date:       21.11.2022
signature:  JIE
numbering:  regular
toc_levels: 1..3
newpage_on: h1:not(.toc-title)
hide_header_on_page: "page==1"
hide_footer_on_page: "page==1"
---


# Cookbook tkinter
{:.no_toc.title}


{:.lines-14}


![logo](images/logo.png)
{:.width-50.fright}


{:.page-break-before.toc-title}
# Table des matières

1. TOC
{:toc}

# Préface

Ce livre est destiné aux élèves de première année CFC en
informatique. Il a été créé afin d'avoir une référence sur 
l'utilisation de tkinter au sein du CPNV.

Ce livre n'est en aucun cas une référence pour python. Le langage est
bien plus complexe et avancé que ce que le livre présente. 
Il permettra cependant, d'avoir une bonne connaissance de la syntaxe, et de fonction de base du langage.

# Les bases

## La fenêtre

### Généralités

En premier lieu, il faut importer la bibliothèque tkinter.

```python
from tkinter import *
```

Puis, il faut créer la fenêtre principale.

```python
window = Tk()
```

A ce stade, si vous exécuter le programme rien ne se passe ou
presque. Une fenêtre s'ouvre et se ferme directement. Pour combler ce
problème, il faut dire à tkinter d'attendre un évènement système et ne
pas fermer le fenêtre. Pour cela, on démarre la boucle principale.

```python
window.mainloop()
```

Un fenêtre s'ouvre tel que celle-ci :


 ![](images/tk-win1){:.width-50}
 
 Résumé : Pour initialiser la bibliothèque et ouvrir une fenêtre il
 faut :
 
 
 ```python
from tkinter import *
window = Tk()
window.mainloop()
```
 
### Options avancées

Nous pouvons changer le titre, la couleur de fond, la taille de la
fenêtre.

Pour changer le titre, il faut utiliser la méthode suivante juste
après la déclaration de la fenêtre.

```python
window.title("introTK")
```

Pour change la couleur de fond, nous devons utiliser la méthode
"configure".


```python
window.configure(bg='blue')
```

Et pour finir, pour changer sa taille, il faut utiliser la méthode
"geometry".

```python
window.geometry("400x200")
```

Ce qui nous donne comme code final :


```python
from tkinter import *
window = Tk()
window.title("introTK")
window.configure(bg='blue')
window.geometry("400x200")
window.mainloop()
```

Et le résultat 

 ![](images/tk-win2){:.width-50}
 
## Placer des objets

### Le Label

Si l'on veut écrire du texte d'information dans une fenêtre, nous
pouvons utiliser un label.

Pour déclarer un label, il faut créer un variable entre la
configuration de la fenêtre et la boucle principale comme tel :

```python
mon_label = Label(window,text="Ceci est un label")
```

Ceci n'affiche pas encore le label sur la fenêtre. Il faut utiliser la
méthode pack.


```python
from tkinter import *
window = Tk()

mon_label = Label(window,text="Ceci est un label")
mon_label.pack()

window.mainloop()
```

