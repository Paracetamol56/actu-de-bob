---
title: "87 - ⚡ Microprocesseurs"
date: 2023-08-03T12:00:00+02:00
author: ["Bob"]
draft: false
---

**Les microprocesseurs ⚡**

![](/img/87.jpg)

- Lorsqu'on parle de microprocesseurs, on parle de CPU moderne composé de transistors gravé sur du silicium. Les premiers processeurs fonctionnaient à l'aide de tubes à vide et consommaient énormément d'énergie en plus d'être gros et lent.

- Pour réaliser une opération sur un microprocesseur, il vous faut lui envoyer une instruction en binaire. Les jeux d'instructions sont définis par les fabricants : Par exemple ARM (Advanced RISC Machine), x86 (32 bit inventé par Intel) ou encore amd64 (64 bit inventé par AMD).

- Les microprocesseurs ont subi une miniaturisation considérable depuis leur invention. Nous sommes passés de tubes à vides de plusieurs cm de diamètres à des transistors de quelques nanomètres s'approchant à grands pas de la taille de l'atome.

- La loi empirique de Moore, formulée par Gordon Moore en 1965, stipule que le nombre de transistors dans un microprocesseur double environ tous les deux ans, entraînant une augmentation de la puissance de calcul.

- Le cout de production d'un CPU est de quelques dollars de matières premières, d'électricité et d'eau. Mais la quasi-totalité de son prix sert à amortir les machines extrêmement sophistiquées et la recherche et développement.

- Le premier producteur de microprocesseurs au monde est l'entreprise TSMC basé à Taiwan et c'est la ressource économique la plus importante du pays. D'où l'importance stratégique du pays pour les États-Unis ou la Chine.  

- Les machines qui servent à fabriquer les microprocesseurs sont extrêmement complexes et onéreuses et ne sont fabriqués que par une seule entreprise : ASML aux Pays-Bas. L'entreprise ne produit que 10 machines par ans et du fait de son monopole, c'est de loin l'entreprise la plus importante au monde sur laquelle repose toute la société.

- Les machines d'ASML gravent le silicium grâce à un système de photolithographie. La lumière utilisée (EUV pour Extreme Ultra Violet) à une longueur d'onde tellement faible que le verre ne la laisse pas passer, on utilise donc des miroirs paraboliques.
## Q&A

**Tuto : Comment utiliser un microprocesseur ?**
Pour ce tuto, nous allons réaliser une addition de deux nombres avec le jeu d'instruction x86.
Comme expliqué plus haut, pour réaliser une opération, il faut envoyer au processeur du binaire correspondant aux instructions souhaité.
```assembly
; Code en ASM pour additionner deux nombres en x86
section .data
    num1 dd 10        ; Premier nombre (modifiable)
    num2 dd 20        ; Deuxième nombre (modifiable)
    result dd 0       ; Résultat de l'addition (initialisé à 0)

section .text
global main
main:
    ; Chargement du premier nombre dans EAX
    mov eax, [num1]

    ; Ajout du deuxième nombre à EAX
    add eax, [num2]

    ; Stockage du résultat dans la variable 'result'
    mov [result], eax

    ; Terminaison du programme
    mov eax, 1         ; Code de l'appel système pour exit
    xor ebx, ebx       ; Code de retour 0
    int 0x80           ; Appel système pour quitter le programme

; Représentation binaire des instructions
; mov eax, [num1] => 8B 05 00 00 00 00
; add eax, [num2] => 03 05 00 00 00 00
; mov [result], eax => 89 05 00 00 00 00
; mov eax, 1 / xor ebx, ebx / int 0x80 => B8 01 00 00 00 31 DB CD 80
```
Si vous voulez aller plus loin et exécuter le programme ci-dessus, écrivez-le dans un fichier `addition.asm` puis assembler le avec les commandes suivantes :
```bash
nasm -f elf32 addition.asm -o addition.o
ld -m elf_i386 -s -o addition addition.o
```
Exécutez le programme avec `./addition`
