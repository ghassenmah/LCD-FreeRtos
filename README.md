# LCD-FreeRtos

Projet STM32 : Affichage Distance et Luminosité sur LCD en basant sur  FreeRTOS 
Description:
Ce projet utilise un microcontrôleur STM32 pour afficher la distance mesurée par un capteur ultrason (HC-SR04) et la luminosité captée par un capteur LDR sur un écran LCD 16x2. Le projet est conçu avec FreeRTOS, permettant de gérer plusieurs tâches en temps réel :

Mesure de distance avec un capteur ultrason.
Lecture de la luminosité via un convertisseur analogique-numérique (ADC).
Affichage des données sur un écran LCD connecté via I²C.

Architecture logicielle:
Le projet est structuré en plusieurs tâches FreeRTOS :

Tâche de lecture LDR :

Lit les valeurs du LDR via l'ADC.
Envoie les données dans une file de message FreeRTOS pour le partage avec d'autres tâches.
Tâche de lecture ultrason :

Déclenche le capteur ultrason et calcule la distance en fonction du temps d'écho.
Envoie la distance dans une file de message FreeRTOS.
Tâche d'affichage LCD :

Lit les valeurs des capteurs depuis les files FreeRTOS.
Affiche les données sur l'écran LCD.
