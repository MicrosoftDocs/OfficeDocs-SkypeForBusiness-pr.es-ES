---
title: 'Lync Server 2013: Delegación'
TOCTitle: Delegación
ms:assetid: 89e76e5c-3cfb-4504-8d0d-7509c8ba9815
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ994045(v=OCS.15)
ms:contentKeyID: 52061666
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Delegación en Lync Server 2013

 

_**Última modificación del tema:** 2013-03-09_

Las funciones de delegación en Lync se ven afectadas por el enrutamiento según ubicación de la siguiente manera:

  - Cuando un delegado habilitado para el enrutamiento según ubicación hace una llamada por parte de un administrador, la directiva de voz del delegado se usa para autorizar la llamada y la directiva de enrutamiento de voz del sitio del delegado se usará para enrutar la llamada

  - Para las llamadas RTC entrantes a un administrador, se aplican las mismas reglas aplicables para reenvío de llamadas o llamadas simultáneas tal como se describe en los temas Transferencias y reenvíos de llamadas y Llamadas simultáneas.

  - Cuando un delegado establece un extremo RTC como destino de llamadas simultáneas, para una llamada entrante al administrador, la directiva de enrutamiento de voz del sitio asociado al tronco entrante se usará para enrutar la llamada al extremo RTC del delegado.

  - Para la delegación, se recomienda que el administrador y sus delegados asociados se ubiquen normalmente en el mismo sitio de red.

## Vea también

#### Otros recursos

[Escenarios para el enrutamiento basado en ubicación en Lync Server 2013](lync-server-2013-scenarios-for-location-based-routing.md)

