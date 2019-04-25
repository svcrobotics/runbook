# Runbook

https://fr.wikipedia.org/wiki/Runbook

## OVERVIEW (vue d'ensemble)

> Vue d'ensemble du service: qu'est-ce que c'est, pourquoi l'avons-nous, qui sont les contacts principaux, comment signaler les bogues, les liens vers les documents de conception et autres informations pertinentes.
>
> 

## BUILD (construire)

> Comment construire le logiciel qui rend le service. Où le télécharger, où se trouve le référentiel de code source, étapes pour construire et créer un paquet ou d’autres mécanismes de distribution. S'il s'agit d'un logiciel que vous modifiez de quelque manière que ce soit (projet open source auquel vous contribuez ou un projet local), incluez des instructions pour démarrer un nouveau développeur. Idéalement, le résultat final est un package qui peut être copié sur d’autres machines pour l’installation.

## COMMON TASKS (taches courantes)

> Instructions pas à pas pour des tâches courantes telles que le provisioning (ajout / modification / suppression), les problèmes courants et leurs solutions, etc.

## PAGER PLAYBOOK (troubleshooting)

> Une liste de toutes les alertes que votre système de surveillance peut générer pour ce service et un énoncé détaillé «Que faire pour quand…» pour chacune d’elles.
>
> ## DEPLOY (déployer)

> Comment déployer le logiciel. Comment créer un serveur à partir de zéro: configuration requise pour la mémoire RAM / disque, la version et la configuration du système d'exploitation, les packages à installer, etc. Si cela est automatisé avec un outil de gestion de la configuration tel que cfengine / puppet / chef (et il devrait l'être), dites-le.



## DISASTER RECOVERY PLAN (DR)

> Plans et procédures de reprise après sinistre. Si une machine de service venait à mourir, comment basculeriez-vous sur le disque de rechange chaud / froid?



## SLA: Service Level Agreement

> Le contrat (social ou réel) que vous établissez avec vos clients. Généralement, des objectifs tels que l’objectif Uptime (combien de 9), RPO (objectif de point de récupération) et RTO (objectif de temps de récupération).

