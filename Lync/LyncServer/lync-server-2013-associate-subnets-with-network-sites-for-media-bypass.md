---
title: Asociar subredes a sitios de red para el desvío de medios
TOCTitle: Asociar subredes a sitios de red para el desvío de medios
ms:assetid: 5bc632b7-1446-470f-b332-48ea0ca4d1fd
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398401(v=OCS.15)
ms:contentKeyID: 48275385
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Asociar subredes a sitios de red para el desvío de medios

 

_**Última modificación del tema:** 2012-09-12_


> [!NOTE]
> En este tema se da por supuesto que ha realizado la configuración global de desvío de medios, así como una región de red y los sitios de red para el desvío de medios.



Todas las subredes de la red debe estar asociadas con un sitio de red específico. Por este motivo la información de las subredes se usa para determinar el sitio de red en el que se encuentra un extremo. Cuando se conocen las ubicaciones de ambas partes de una sesión, el desvío de medios puede determinar si envía medios para su procesamiento.

El desvío de medios no tiene requisitos especiales para asociar subredes con sitios de red. Para crear una asociación entre las subredes y los sitios de red de su topología, siga los procedimientos de [Asociar una subred a un sitio de red en Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).

## Pasos siguientes: Crear perfiles de directivas de ancho de banda

Una vez asociadas las subredes con sitios de red para el desvío de medios, deberá crear uno o varios perfiles de directiva de ancho de banda que particionen las subredes entre las que tienen buena conectividad y aquellas cuyo propósito no es el desvío de medios. Todas las subredes de una región de red que poseen sitios de red sin restricciones de ancho de banda tienen buena conectividad y, por lo tanto, pueden usar el desvío de medios.

Para ver los procedimientos para configurar perfiles de directivas de ancho de banda, consulte [Crear perfiles de directivas de ancho de banda en Lync Server 2013](lync-server-2013-create-bandwidth-policy-profiles.md).

