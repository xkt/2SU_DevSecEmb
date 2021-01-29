% TODO_2SU_TD_2021

**à rendre pour le 12 février par discord en PV**

Cours: [https://github.com/xkt/2SU_DevSecEmb](https://github.com/xkt/2SU_DevSecEmb)

Discord : [https://discord.gg/QEHccwJa](https://discord.gg/QEHccwJa)

**Output** : README au format pdf / documentez votre logique et vos résultats (notes, screenshots)

[Exemple de readme](https://github.com/DavidJacobson/EasyCTF-2015-writeup/blob/master/binary_exploitation.md#buffering---80-pts)

Astuce: si markdown => utilisez [pandoc](https://pandoc.org/) pour générer le pdf



# TD1 binwalk

A l'aide de [binwalk](https://github.com/ReFirmLabs/binwalk) retrouvez le pingouin 
qui s'affiche lorsque vous lancez le binaire / [firmware](https://bootlin.com/pub/qemu/demos/arm/directfb/1.0/vmlinuz-qemu-arm-2.6.20)
dans Qemu.

[source](https://bootlin.com/blog/qemu-arm-directfb-demo/)

## Questions:

* Trouvez et modifiez le pingouin. Qu'est ce qui empêche de modifier le pinguoin directement?
* Qu'est ce que je peux faire pour contourner cette protection?
* Quelle propriété de sécurité est garantie? 

Bonus: Quelle propriété de sécurité *n'est pas* garantie? Que peut on faire pour obtenir cette garantie?


# TD2 emily

Suivre le tuto [patching de binaire](https://archive.emily.st/2015/01/27/reverse-engineering/)

## Questions:

* Patcher le binaire. Quelle différence dans un environnement ARM?
* Comprendre le lien les attaques physiques / expliquez quelles sont les attaques par patching possibles sur une boucle for.
* Qu'elle défense est ce que je peux utiliser contre le patching?

Bonus: Effectuer la même manipulation avec avec un autre outil par ex: Ghidra ? quels sont les avantages / inconvénients ?


# TD3 speedrun

Suivre le tuto [bufferoverflow et rop speedrun](https://liveoverflow.com/speedrun-hacking-buffer-overflow-speedrun-001-dc27-2/)

Résumé: 

lien vers vidéo: [vidéo](https://www.youtube.com/watch?v=gBL6IzwIjuA)

lien vers dockerfile: [dockerfile](https://gist.github.com/LiveOverflow/b4502c5358a838d7ca9d92e8a2e8b5a0)

la commande pour le pull : 

```
docker build -t ubuntu18:ctf - < Dockerfile
```

lien vers binaire: [speedrun](https://media.defcon.org/DEF%20CON%2027/DEF%20CON%2027%20ctf/OOO%20DEF%20CON%2027%20CTF%20Quals/OOO%20DEF%20CON%2027%20CTF%20quals%20challenges/dc2019q-speedrun-001-master/service/)

Astuce gdb :

```
handle signal ignore
handle signal noprint
```

## Questions:

* Devenez root. Qu'est ce qu'un attaquant peut faire une fois root?
* Qu'est ce que je dois prendre en compte dans mon modèle d'attaque? 
* Comprendre le lien avec les bugs / cette méthode est-elle applicable dans le cas d'un use after free? Pourquoi?
* Qu'est ce que je peux faire pour diminuer / contrer les bugs?

Bonus: Quelle différence si les canary et l'ASLR sont présents?


# TD4 PKI

Reproduire une arborescence de clés i.e un PKI en suivant les commandes dans le fichier commands dans PKI_template.zip

## Questions:

* Comprendre les éléments de la PKI en expliquant les différentes étapes avec vos mots / schémas.
* A quoi sert une PKI?
* Quels éléments de la PKI sont utilisés pour assurer l'authenticité des binaires sur un système embarqué? Comment?

Bonus: Expliquez / créez les commandes pour effectuer une révocation / renouvellement et une opération de CSR 


<!-- pandoc .\TODO_2SU_TD_2021.md -o .\TODO_2SU_TD_2021.pdf --from markdown --template eisvogel --listings --variable urlcolor=cyan -->