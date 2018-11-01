---
title: Consideraciones sobre interoperabilidad para las conferencias de vídeo
TOCTitle: Consideraciones sobre interoperabilidad para las conferencias de vídeo
ms:assetid: 31ead3b5-ed95-42d4-96e2-7d9403d5c026
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204790(v=OCS.15)
ms:contentKeyID: 48274866
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Consideraciones sobre interoperabilidad para las conferencias de vídeo

 

_**Última modificación del tema:** 2012-10-02_

Esta sección describe la experiencia de usuario durante la fase de coexistencia de migración, cuando hay interoperabilidad entre los clientes heredados y un grupo de servidores de Lync Server 2013 o clientes de Lync Server 2013 y un grupo de servidores heredado.

## Grupo de servidores de Lync Server 2013

Los usuarios probarán el siguiente comportamiento cuando se use un cliente heredado en un grupo de servidores de Lync Server 2013:

  - Para llamadas de dos participantes, la resolución de vídeo es la misma que en el grupo de servidores heredado.

  - Para conferencias de varios participantes, las características de resolución de vídeo y conferencia de vídeo son las mismas que en el grupo de servidores heredado. La vista de galería y la alta resolución no están disponibles.

## Grupos de servidores heredados

Los usuarios probarán el siguiente comportamiento cuando se usa un cliente de Lync Server 2013 en un grupo de servidores heredado:

  - Para llamadas de dos participantes, los clientes de Lync Server 2013 pueden usar nuevas características como las siguientes:
    
      - H.264 está disponible si ambos participantes usan clientes de Lync Server 2013.
    
      - El cliente de Lync Server 2013 usa el valor predeterminado para TotalReceiveVideoBitRateKb, puesto que el servidor heredado no envía esta información con aprovisionamiento en banda.

  - Para conferencias de varios participantes, las características de resolución de vídeo y conferencia de vídeo son las mismas que las que tiene un cliente heredado en el grupo de servidores heredado.


> [!NOTE]
> Cuando un servidor heredado hospeda un cliente de Lync Server 2013, es posible configurar un ancho de banda de videoconferencia de manera que todos los usuarios del grupo de servidores reciban solo vídeo de baja resolución, pero envíen vídeo de alta resolución. Un ejemplo de esto es cuando MaxVideoRateAllowed se establece en CIF-250K en la configuración multimedia y VideoBitRateKb se establece en 2000 kbps en la directiva de conferencia. El efecto neto en esta situación es que la resolución alta no es posible para usuarios del grupo de servidores.<BR>Debido a que MaxVideoRateAllowed ya no se usa para clientes de Lync Server 2013, no puede evitar que clientes de Lync Server 2013 soliciten vídeo de alta resolución. En su lugar, establezca VideoBitRateKb en la directiva de conferencia para todos los usuarios del grupo de servidores al mismo valor que MaxVideoRateAllowed (es decir, CIF se establece en 250 kbps, o VGA se establece en 600 kbps, o HD se establece en 1500 kbps).


