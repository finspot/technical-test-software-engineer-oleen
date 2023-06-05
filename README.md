# Test technique - Dévelopeur fullstack Oleen

## Objectif

L'objectif de ce test technique est d'évaluer 

- ta capacité à résoudre des problèmes
- tes compétences en programmation et algorithmique
- tes compétences en front-end
- ta créativité

## Sujet

Au cours de l'expérience Pretto, un client va régulièrement prendre contact avec son conseiller. Pour cela, il doit prendre rendez-vous sur son espace client via une interface similaire à celle ci

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/444761f3-6f00-4aee-8940-f7f3e43c8e68/Untitled.png)

Cette grille est généré à partir de plusieurs points de données:

- La liste d’évènements prévu dans son calendrier.
    
    *Exemple*
    
    ```yaml
    - name: "RDV #1"
    	start: 2020-02-01T08:00:00Z
    	end: 2020-02-01T08:30:00Z
    - name: "RDV #2"
    	start: 2020-02-01T08:45:00Z
    	end: 2020-02-01T09:15:00Z
    ```
    

- Les horaires de travail du conseiller. Il s'agit des plages horaires sur lesquels le conseiller est joignable (ou non)
    
    
    ```yaml
    - allowDayAndTime: # horaires de travail
      # day est compris dans [1..7]
      # start/end : [00:00 .. 23:59]
    	- day: 1 # lundi
    		start: "08:00"
    		end: "12:00"
    	- day: 1 # lundi
    		start: "13:00"
    		end: "17:30"
    	- day: 2 # mardi
    		start: "08:30"
    		end: "13:00"
    	- day: 2 # mardi
    		start: "14:00"
    		end: "18:00"
    	- ...
    - blockSlot: # vacances
    	- start: 2020-07-01
    		end: 2020-07-07
      - ...
    - allowSlot: # permanences du samedi
    	- start: "2021-03-06T08:00:00Z"
    		end: "2021-03-06T16:00:00Z"
    ```
    
- Les contraintes du rendez vous :
    - La durée. Elle varie avec l'avancement du client dans le parcours. Certains durent **30 minutes**, d'autres **15 minutes.**
    - La durée du temps de préparation. Il est nécessaire de réserver quelques minutes de battement pour permettre au conseiller de relire la fiche client. Juste avant le rendez-vous, il faut réserver **5 ou 15 minutes en amont** selon le type de rendez-vous.
    - L’heure de départ. Les rendez-vous commencent **toujours à pile, et-quart, et-demi et moins-le-quart.**

## Exercice - Partie 1

Créer un programme permettant de calculer les disponibilités d'un expert. 

1. Vous pouvez utiliser le langage de programmation de votre choix.
2.  N'hésitez pas à laisser des commentaires, écrire des tests unitaires et laisser un minimum de documentation pour lancer votre programme.
3. Ne restez pas bloqué à cause d'une contrainte qui vous pose problème, soyez libre d'ignorer une difficulté pour avancer. Mieux vaut une solution partielle qui fonctionne bien qu'une solution complète qui fonctionne mal. J’ai volontairement omis l'attendu de chaque jeux de tests parce que ça fait aussi parti du job de déterminer comment le service va fonctionner.

[Jeux de tests faciles ](https://www.notion.so/Jeux-de-tests-faciles-69f65c25f5354ca9a70d862ecc82a45c?pvs=21)

[Jeux de test moins faciles](https://www.notion.so/Jeux-de-test-moins-faciles-a4d8020c996549deaf5224e05e262d2b?pvs=21)

[Jeux de test encore moins facile](https://www.notion.so/Jeux-de-test-encore-moins-facile-2e1ebd07fb87491e8ec214ee902fb9a3?pvs=21)

## Exercice - Partie 2

Créer une application frontend en utilisant React qui reproduit le Figma ce dessous 
**(TODO: faire un figma de display des slots disponibles)**

Bonus: Créer une application backend avec l’algorithme de la partie précédente et faire communiquer les 2 applications
