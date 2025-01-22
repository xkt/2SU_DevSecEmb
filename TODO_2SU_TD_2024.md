# % TODO_2SU_TD_2024

**à rendre pour le 10 février par mail**

Cours: [https://github.com/xkt/2SU_DevSecEmb](https://github.com/xkt/2SU_DevSecEmb)

**Output** : README au format pdf / documentez votre logique et vos résultats (notes, screenshots)

[Exemple de readme](https://github.com/DavidJacobson/EasyCTF-2015-writeup/blob/master/binary_exploitation.md#buffering---80-pts)

Astuce: si markdown => utilisez [pandoc](https://pandoc.org/) pour générer le pdf

Regardez les templates markdown pour pandoc par exemple eisvogel pour une belle présentation



# TD1 emily

Suivre le tuto [patching de binaire](https://web.archive.org/web/20210120032416/https://archive.emily.st/2015/01/27/reverse-engineering/)

<!-- https://archive.emily.st/2015/01/27/reverse-engineering/ -->

## Questions:

* Patcher le binaire. Quelle différence dans un environnement ARM?
* Comprendre le lien les attaques physiques / expliquez quelles sont les attaques par patching possibles sur une boucle for.
* Quelle défense est ce que je peux utiliser contre le patching? Utilisez openssl pour metter en oeuvre cette défense et la valider

Bonus: Effectuer la même manipulation avec avec un autre outil par ex: Ghidra ? quels sont les avantages / inconvénients ?


# TD2 binwalk

A l'aide de [binwalk](https://github.com/ReFirmLabs/binwalk) retrouvez le pingouin 
qui s'affiche lorsque vous lancez le binaire / [firmware](https://bootlin.com/pub/qemu/demos/arm/directfb/1.0/vmlinuz-qemu-arm-2.6.20)
dans Qemu.

[source](https://bootlin.com/blog/qemu-arm-directfb-demo/)

**WARNING**: utilisez un environnement virtualisé lorsque vous manupulez un binaire inconnu!

## Questions:

* Trouvez et modifiez le pingouin. Qu'est ce qui empêche de modifier le pinguoin directement?
* Qu'est ce que je peux faire pour contourner cette protection?
* Quelle propriété de sécurité est garantie? 

Bonus: Quelle propriété de sécurité *n'est pas* garantie? Que peut on faire pour obtenir cette garantie?


# TD3 speedrun

Suivre le tuto [bufferoverflow et rop speedrun](https://liveoverflow.com/speedrun-hacking-buffer-overflow-speedrun-001-dc27-2/)

**WARNING**: ne pas utiliser la commande nc pour vous connecter au serveur mais utiliser le binaire localement avec le lien en dessous.

Résumé: 

lien vers vidéo: [vidéo](https://www.youtube.com/watch?v=gBL6IzwIjuA)

lien vers dockerfile: [dockerfile](https://gist.github.com/LiveOverflow/b4502c5358a838d7ca9d92e8a2e8b5a0)

la commande pour le pull : 

```
docker build -t ubuntu18:ctf - < Dockerfile
```

lien vers binaire: [speedrun](https://github.com/o-o-overflow/dc2019q-speedrun-001/blob/master/service/speedrun-001)

<!-- https://media.defcon.org/DEF%20CON%2027/DEF%20CON%2027%20ctf/OOO%20DEF%20CON%2027%20CTF%20Quals/OOO%20DEF%20CON%2027%20CTF%20quals%20challenges/dc2019q-speedrun-001-master/service/ -->

Astuce trouver l'offset de l'overflow:

[pattern create generator](https://zerosum0x0.blogspot.com/2016/11/overflow-exploit-pattern-generator.html)

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


# TD3 bis (alternative au précédent) Fuzzing

Prendre les formes de code avec des bugs dans le cours ou trouver des équivalents
(github est votre ami)

* Buffer overflow
* Null pointer dereference
* Integer rollover / Signedness error
* Use after free
* Use unitialized
* Double free

Utiliser TD1 Emily comme base et [cifuzz](https://github.com/CodeIntelligenceTesting/cifuzz) / [sulley](https://github.com/OpenRCE/sulley) / [afl++](https://github.com/AFLplusplus/AFLplusplus) / [libfuzzer](https://aviii.hashnode.dev/the-art-of-fuzzing-a-step-by-step-guide-to-coverage-guided-fuzzing-with-libfuzzer) comme fuzzer pour retrouver les bugs.

Donnez une explication des crashs et de comment exploiter les différents bugs.

## Questions:

* En utilisant TD2 binwalk / qemu comme base (donc dans un environnement embarqué), est ce que les résultats seraient identiques? Pourquoi?
* Pourquoi le coverage guided fuzzing est plus efficace que le dumb fuzzing?
* Quel pouvoir donne le fuzzing? Est ce que l'ensemble des bugs sont exploitables et permettent de devenir root? Quelles sont les conditions nécessaires?

# TD4 Toolbox

Rechercher et tester sur github des projects qui permettent de se mettre en Man in The Middle sur les différentes interfaces:

* Usb
* Bluetooth
* Wifi
* NFC
* RJ45
* 3G
* Hardware

Astuce github / Joe Grand

## Questions:

* Quel sont les critères qui rendent une vulnérabilité critique ?
* Suivant ces critères quelle interface devrait être testée en premier? Pourquoi?
* Quels avantages, inconvénients ont les outils que vous avez choisi?

# Question générale en texte libre

Décrivez votre processus et raisonnement pour évaluer la sécurité d'un système embarqué au niveau matériel et logiciel.


# TD4 bis (alternative au précédent) Exploit Dev

See [Intro_ExploitDev.md](https://github.com/xkt/2SU_DevSecEmb/blob/master/Intro_ExploitDev.md) (en anglais)

## Questions:

* Est ce que les buffers overflows sont plus faciles à exploiter sur la stack ou sur la heap?
* Quelles défenses ou méthodes peuvent être utilisées pour trouver ou contrer ces bugs?
* Quels sont les limites de ces défenses? Quel est le risque qu'il reste ou reste t'il un vecteur d'attaque?
* Est ce qu'il existe un moyen infaillible de défendre contre cette catégorie de bugs?

<!-- pandoc .\TODO_2SU_TD_2021.md -o .\TODO_2SU_TD_2021.pdf --from markdown --template eisvogel --listings --variable urlcolor=cyan -->

