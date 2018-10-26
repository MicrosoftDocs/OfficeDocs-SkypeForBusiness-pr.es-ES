---
title: 'Lync Server 2013: Asignar el ámbito de directiva de ubicación'
TOCTitle: Asignar el ámbito de directiva de ubicación
ms:assetid: e4c66517-c593-4253-b900-7b4dd8bddf2f
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205360(v=OCS.15)
ms:contentKeyID: 48276964
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Asignar el ámbito de directiva de ubicación en Lync Server 2013

 

_**Última modificación del tema:** 2012-06-06_

Al igual que sucede con otras directivas de Lync Server, las directivas de ubicación se pueden asignar en múltiples niveles de ámbito: global, de sitio y de usuario. No obstante, las directivas de ubicación en el nivel de usuario se comportan de forma un poco diferente a las de otras directivas de Lync Server. Las directivas de ubicación por usuario no solo se pueden aplicar a objetos de extremo (tales como objetos de contacto de Usuario y Teléfono de área común), sino que también se pueden aplicar a sitios de red de Lync Server. Los sitios de red son agrupaciones de subredes de clientes asociadas con una ubicación geográfica (pero no es necesario que sean todas las subredes de un sitio central o sitio de sucursal completo). Los clientes conectados a las subredes de un sitio de red escogen automáticamente la directiva de ubicación asignada a dicho sitio de red. Si la directiva de ubicación en el nivel de usuario se asigna tanto a un usuario como a un sitio de red, la directiva de ubicación basada en sitio de la red sustituye a cualquier otra configuración de directiva de usuario.

Cada sitio de red tiene asignada una directiva de ubicación, y cada directiva tendrá asignados valores diferentes de Uso de RTC, URI de notificación y URI de conferencia.


> [!NOTE]
> El motivo de este comportamiento de ámbito de directiva especial es que, cuando un usuario hospedado en un grupo de usuarios de un sitio de oficina visita otro sitio y tiene que realizar una llamada de emergencia, se aplicará la configuración de enrutamiento de llamada E9-1-1 correspondiente a dicho sitio de red independientemente de a qué grupo de usuarios o sitio esté asignado el usuario.


