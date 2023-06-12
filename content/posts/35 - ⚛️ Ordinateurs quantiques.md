---
title: "35 - ⚛️ Ordinateurs quantiques"
date: 2023-06-12T12:00:00+02:00
author: ["Bob", "Chocobo futé"]
draft: false
---

**En voila un sujet intéressante, aujourd'hui au programme : les ordinateurs quantiques ⚛️**

![](/img/35.jpg)

- Contrairement aux ordinateurs classiques, qui utilisent des bits pour représenter et manipuler de l'information, les ordinateurs quantiques utilisent des qubits (bits quantiques).

- Les qubits peuvent exister simultanément dans plusieurs états, grâce à un phénomène appelé superposition quantique. Cela permet aux ordinateurs quantiques d'effectuer des calculs sur un grand nombre de combinaisons simultanément.

- Les qubits peuvent prendre plusieurs formes, aujourd'hui, on utilise de plus en plus la technologie des ions piégés.

- Les ordinateurs quantiques ont le potentiel de résoudre certains problèmes de manière beaucoup plus efficace que les ordinateurs classiques. Par exemple, ils pourraient être utilisés pour résoudre rapidement des problèmes de factorisation d'entiers, ce qui a des implications significatives pour la cryptographie.

- La technologie des ordinateurs quantiques est encore en développement et présente de nombreux défis. Les qubits sont extrêmement sensibles aux interférences et aux erreurs, ce qui peut entraîner des résultats incohérents. Les scientifiques travaillent sur des méthodes pour corriger ces erreurs et créer des qubits plus stables.

- Les ordinateurs quantiques sont souvent maintenus à des températures extrêmement basses, proches du zéro absolu, pour réduire les effets des interférences et des perturbations de l'environnement.

- Les ordinateurs ont été théorisés par Richard Feynman en 1959 dans le but de comprendre les phénomènes quantiques. Les applications informatiques sont arrivées plus tard.

- Plusieurs entreprises et institutions de recherche, telles que IBM, Google, Microsoft et des laboratoires gouvernementaux, travaillent sur le développement de l'informatique quantique.

- Ces entreprises proposent généralement des plateformes pour que vous et moi puissiez exécuter du code sur des ordinateurs quantique.

- Voici un exemple que j'ai fais en code en Q# pour les ordinateurs de Microsoft :
```qs
open Microsoft.Quantum.Measurement;

operation CreateEntangledPair () : Unit {
    use qubitArray = Qubit[2];
    let q = qubitArray[0];
    let r = qubitArray[1];
    
    H(q);
    CNOT(q, r);
    
    let result = MultiM(qubitArray);
    Message($"Result: {result}");
}
```

## Les détails de Chocobo futé

![](/img/35_1.jpg)
