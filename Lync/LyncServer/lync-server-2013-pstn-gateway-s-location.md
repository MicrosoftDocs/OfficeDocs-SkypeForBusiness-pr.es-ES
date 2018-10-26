---
title: 'Lync Server 2013: Ubicación de la puerta de enlace RTC'
TOCTitle: Ubicación de la puerta de enlace RTC
ms:assetid: 49693a35-fad3-49ee-a71e-c7e4537b79aa
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ994031(v=OCS.15)
ms:contentKeyID: 52061676
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ubicación de la puerta de enlace RTC en Lync Server 2013

 

_**Última modificación del tema:** 2013-03-09_

Las llamadas enrutadas a través de puertas de enlace RTC y PBX podrían necesitar restricciones de enrutamiento según ubicación en función de la ubicación de dichos sistemas. El enrutamiento según ubicación se puede habilitar en la granularidad para cada tronco.

El enrutamiento según ubicación presenta el siguiente conjunto de reglas cuando se habilita en un tronco:

  - Cuando el enrutamiento según ubicación se habilita para cada tronco, las reglas definen el tronco que se aplicará solo para llamadas enrutadas a través de dicho tronco.

  - Para impedir la omisión de tarifa RTC donde las llamadas se originan en un sitio de red distinto que el sitio de red en el que se encuentra la puerta de enlace RTC, el enrutamiento según ubicación presenta la asociación de un sitio de red a un tronco determinado. Esto define el sitio de red que permite que las llamadas se enruten hacia determinado tronco.

Los troncos se pueden habilitar para el enrutamiento según ubicación de dos maneras:

  - El tronco se define para una puerta de enlace RTC que da salida a llamadas al RTC. Las llamadas entrantes enrutadas por un tronco de este tipo se enrutarán solo a los extremos ubicados dentro del mismo sitio de red que el tronco.

  - El tronco se define para un par de Servidor de mediación que no da salida a llamadas al RTC y usuarios de servicios con teléfonos heredados en una ubicación estática (p. ej., teléfonos de PBX). Para esta configuración específica, todas las llamadas entrantes enrutadas por un tronco de este tipo se considerarán como originarias del mismo sitio de red que el tronco. Las llamadas de usuarios de PBX tendrán la misma aplicación de enrutamiento según ubicación que los usuarios de Lync que se encuentran en el mismo sitio de red que el tronco. Si dos sistemas PBX ubicados en sitios de red independientes se conectan a través de Lync Server, el enrutamiento según ubicación permitirá enrutamiento de un extremo de PBX en un sitio de red a otro extremo de PBX en el otro sitio de red. Este escenario no se bloqueará mediante el enrutamiento según ubicación. Además de este escenario y de una forma similar que un usuario de Lync en la misma ubicación, los extremos conectados a un par de Servidor de mediación con esta configuración podrán hacer o recibir llamadas hacia y desde otro par de Servidor de mediación que no enrute llamadas al RTC (un extremo conectado a otro PBX) independientemente del sitio de red al que se asocia el par de Servidor de mediación. Todas las llamadas entrantes, llamadas salientes, transferencias de llamadas y reenvíos de llamadas en los que participan los extremos de RTC estarán sujetas al enrutamiento según ubicación para usar solo puertas de enlace RTC que se definan como locales para dicho par de Servidor de mediación.

## Vea también

#### Otros recursos

[Instrucciones para el enrutamiento basado en ubicación en Lync Server 2013](lync-server-2013-guidance-for-location-based-routing.md)

