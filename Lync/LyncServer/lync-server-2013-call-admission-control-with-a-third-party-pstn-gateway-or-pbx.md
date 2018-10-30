---
title: "Lync Server 2013: Admisión de llamadas con PBX o puerta de enlace RTC de terceros"
TOCTitle: Control de admisión de llamadas con un PBX o una puerta de enlace RTC de terceros
ms:assetid: 95dc4ceb-bcad-48ee-86ec-af911727f853
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398762(v=OCS.15)
ms:contentKeyID: 48276077
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Control de admisión de llamadas con un PBX o una puerta de enlace RTC de terceros en Lync Server 2013

 

_**Última modificación del tema:** 2012-10-20_

En este tema se explican ejemplos de cómo el servicio de control de admisión de llamadas puede implementarse en el vínculo entre la interfaz de puerta de enlace del servidor de mediación y una puerta de enlace la red telefónica conmutada (RTC) o central de conmutación (PBX) de terceros.

## Caso 1: Control de admisión de llamadas entre el servidor de mediación y una puerta de enlace RTC

El control de admisión de llamadas puede implementarse en el vínculo WAN de la interfaz de puerta de enlace del servidor de mediación con una puerta de enlace RTC o PBX de terceros.

**Caso 1: Control de admisión de llamadas entre el servidor de mediación y una puerta de enlace RTC**

![Caso 1: Control de admisión de llamadas (CAC) entre el servidor de mediación y la puerta de enlace RTC](images/Gg398762.4bebf9ee-2732-4ea6-bbe5-0269b2903d8c(OCS.15).jpg "Caso 1: Control de admisión de llamadas (CAC) entre el servidor de mediación y la puerta de enlace RTC")

En este ejemplo, el control de admisión de llamadas se aplica entre el servidor de mediación y una puerta de enlace RTC. Si un usuario del cliente de Lync realiza en el Sitio de red 1 una llamada RTC a través de la puerta de enlace RTC del Sitio de red 2, los medios se transmiten mediante el vínculo WAN. Por tanto, se llevan a cabo dos comprobaciones de control de admisión de llamadas para cada sesión RTC:

  - Entre la aplicación cliente Lync y el servidor de mediación

  - Entre el servidor de mediación y la puerta de enlace RTC

Esto funciona tanto para las llamadas RTC entrantes a un cliente en el Sitio de red 1 como para las llamadas RTC salientes desde una aplicación cliente en el Sitio de red 1.


> [!NOTE]
> Asegúrese de que la subred IP a la que pertenezca la puerta de enlace RTC esté configurada y asociada con el Sitio de red 2.<BR>Asegúrese de que la subred IP a la que pertenezcan ambas interfaces del servidor de mediación esté configurada y asociada con el Sitio de red 1.<BR>Para ver información detallada, consulte <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Asociar una subred a un sitio de red en Lync Server 2013</A>.



## Caso 2: Control de admisión de llamadas entre el servidor de mediación y una PBX de terceros con punto de terminación de medios (MTP, Media Termination Point)

Esta configuración es similar a la del Caso 1. En ambos casos, el servidor de mediación sabe en qué dispositivo terminan los medios en el extremo opuesto del vínculo WAN, y la dirección IP de la puerta de enlace RTC o de la PBX que tiene el MTP está configurada en el servidor de mediación como siguiente salto.

**Caso 2: Control de admisión de llamadas entre el servidor de mediación y una PBX de terceros con MTP**

![Caso 2: Control de admisión de llamadas (CAC) entre el servidor de mediación y la PBX con MTP](images/Gg398762.1c0b5263-c053-4cca-842f-85dd670760c8(OCS.15).jpg "Caso 2: Control de admisión de llamadas (CAC) entre el servidor de mediación y la PBX con MTP")

En este ejemplo, el control de admisión de llamadas se aplica entre el servidor de mediación y el MTP o la PBX. Si un usuario del cliente de Lync realiza en el Sitio de red 1 una llamada RTC a través de la PBX o el MTP del Sitio de red 2, los medios se transmiten mediante el vínculo WAN. Por tanto, se llevan a cabo dos comprobaciones de control de admisión de llamadas para cada sesión RTC:

  - Entre la aplicación cliente Lync y el servidor de mediación

  - Entre el servidor de mediación y la PBX o el MTP

Esto funciona tanto para las llamadas RTC entrantes a un cliente en el Sitio de red 1 como para las llamadas RTC salientes desde un cliente en el Sitio de red 1.


> [!NOTE]
> Asegúrese de que la subred IP a la que pertenezca el MTP esté configurada y asociada con el Sitio de red 2.<BR>Asegúrese de que la subred IP a la que pertenezcan ambas interfaces del servidor de mediación esté configurada y asociada con el Sitio de red 1.<BR>Para ver información detallada, consulte <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Asociar una subred a un sitio de red en Lync Server 2013</A>.



## Caso 3: Control de admisión de llamadas entre el servidor de mediación y una PBX de terceros sin MTP

El Caso 3 es ligeramente diferente a los dos primeros casos. Si no hay ningún MTP en la PBX de terceros, en el caso de una solicitud de sesión saliente enviada a la PBX de terceros, el servidor de mediación no sabe dónde terminarán los medios en el límite de la PBX. En tal caso, los medios se transmiten directamente entre el servidor de mediación y el dispositivo del extremo de terceros.

**Caso 3: Control de admisión de llamadas entre el servidor de mediación y una PBX de terceros sin MTP**

![Caso 3: Control de admisión de llamadas (CAC) entre el servidor de mediación y la PBX sin MTP](images/Gg398762.f4bcf800-3a68-4037-bb3f-adb2fdf50d32(OCS.15).jpg "Caso 3: Control de admisión de llamadas (CAC) entre el servidor de mediación y la PBX sin MTP")

En este ejemplo, si un usuario del cliente de Lync realiza una llamada a un usuario en el Sitio de red 1 a través de la PBX, el servidor de mediación solo podrá realizar comprobaciones de control de admisión de llamadas en la sección del proxy (entre la aplicación cliente Lync y el servidor de mediación). Dado que el servidor de mediación no tiene información sobre el dispositivo del extremo, durante el proceso de solicitud de la sesión, no pueden realizarse comprobaciones de control de admisión de llamadas en el vínculo WAN (entre el servidor de mediación y el extremo de terceros) antes del establecimiento de llamada. Sin embargo, una vez establecida la sesión, el servidor de mediación facilita la cantidad de ancho de banda usada en el tronco.

Para las llamadas realizadas desde el extremo de terceros, la información sobre el dispositivo del extremo está disponible en el momento de la solicitud de la sesión y la comprobación de control de admisión de llamadas puede realizarse en ambas partes del servidor de mediación.


> [!NOTE]
> Asegúrese de que la subred IP a la que pertenezca el dispositivo del extremo esté configurada y asociada con el Sitio de red 2.<BR>Asegúrese de que la subred IP a la que pertenezcan ambas interfaces del servidor de mediación esté configurada y asociada con el Sitio de red 1.<BR>Para ver información detallada, consulte <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Asociar una subred a un sitio de red en Lync Server 2013</A>.


