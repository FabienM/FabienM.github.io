---
layout: post
title: "SOAP, c'est mort"
date: "2014-05-11 21:20:00 +0200"
author: FabienM
version: 1.0.0
categories: [soa]
---
Entendu au bureau aujourd'hui, par quelqu'un de très expérimenté : 

> SOAP, c'est mort. Maintenant il y a REST et c'est beaucoup plus simple.

J'adore l'approche orientée ressources de REST. Néanmoins, je ne suis pas
d'accord avec cette affirmation.
SOAP est une technologie basée sur des contrats : le WSDL qui décrit les 
méthodes et les XSD qui décrivent les objet. Ça en fait un candidat
de choix lorsque deux systèmes très hétérogènes doivent communiquer.
Définir d'abord le contrat permet au producteur du service de ne plus
se préoccuper de ses consommateurs. Si ceux-ci respectent le contrat,
ça marchera.

Le REST est effectivement plus souple, généralement plus rapide à 
implémenter (ça se discute) et très souvent plus élégant. En revanche
cette souplesse apparente donne souvent lieu à des incompréhensions :

* sur les objets retournés et leurs attributs
* sur l'utilisation des routes et les conventions de nommages (POST /products ? POST /product ?)
* sur la bonne utilisation des méthodes de mise à jour : je suis certain que la distinction POST/PUT/PATCH reste incomprise d'une majorité de développeurs d'API

On peut palier à ces défauts en investissant sur la documentation.
C'est une très bonne idée, mais les standards peinent à émerger.

De plus REST est vraiment orienté ressource, je fais un blocage avec 
les requêtes REST qui déclenchent des traitements métiers complexes.
Finalement les deux systèmes sont complémentaires, dans un contexte 
d'ESB, j'ai tendance à me pencher vers SOAP par défaut car très souvent 
on lie des applications qui possèdent des définitions différentes 
d'un même type d'objet. La définition du contrat permet donc d'accorder 
tout le monde et "d'assurer" les mappings.
