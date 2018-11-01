---
title: "Lync Server 2013 : Dév. du trafic mult. et contrôle d’admission des appels"
TOCTitle: Omisión de medios y control de admisión de llamadas
ms:assetid: 120b2a2b-5f97-4735-a2ee-0f849feb8c1d
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398203(v=OCS.15)
ms:contentKeyID: 48274482
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Omisión de medios y control de admisión de llamadas en Lync Server 2013

 

_**Última modificación del tema:** 2012-10-05_

El control de admisión de llamadas y el desvío de medios (CAC) funcionan conjuntamente para administrar el control del ancho de banda para medios telefónicos. El desvío de medios facilita el flujo de medios sobre vínculos con buenas conexiones; el CAC administra el tráfico en vínculos con restricciones de ancho de banda. Como el desvío de medios y el CAC son mutuamente exclusivos, deberá tener en cuenta a cada uno de ellos al realizar la planeación del otro. Se admiten las siguientes combinaciones:

  - Tanto el CAC como el desvío de medios están habilitados. El desvío de medios debe estar configurado con **Usar información de sitio y región**. La información de sitio y región es la misma que la usada para el CAC.
    
    Si habilita el CAC, no podrá seleccionar **Desviar siempre**, y viceversa, ya que las dos configuraciones son mutuamente exclusivas. Es decir, solo se aplicará una de las dos a una llamada RTC determinada. En primer lugar, se realiza una comprobación para determinar si se aplica el desvío de medios a la llamada. Si es así, no se usa el CAC. Es lógico, ya que si una llamada reúne las condiciones necesarias para el desvío, está usando, por definición, una conexión que no requiere control de admisión de llamadas. Si no puede aplicarse el desvío a la llamada (es decir, si los identificadores de desvío del cliente y de la puerta de enlace no coinciden), se aplicará el CAC a la llamada.

  - CAC no habilitado y desvío de medios configurado con **Desviar siempre**.
    
    En esta configuración, las subredes tanto del tronco como del cliente están asignadas a un solo identificador de desvío, y el sistema lo calcula.

  - CAC no habilitado y desvío de medios configurado con **Usar información de sitio y región**.
    
    Cuando **Uso de información de sitio y región** está habilitado, la determinación de desvío funciona básicamente del mismo modo, independientemente de si el CAC está habilitado o no. Es decir, para todas las llamadas RTC, la subred del cliente está asignada a un sitio en particular, y se extrae el identificador de desvío para dicha subred. Del mismo modo, la subred de la puerta de enlace está asignada a un sitio en particular, y se extrae el identificador de desvío para dicha subred. El desvío de la llamada solo se producirá si los dos identificadores de desvío son idénticos. Si no es así, el desvío de medios no tendrá lugar.
    
    Incluso aunque el CAC esté inhabilitado globalmente, es necesario definir la directiva de ancho de banda para cada uno de los sitios y vínculos si desea usar una configuración de sitio y región para controlar la decisión de desvío. El valor real de la restricción de ancho de banda o su modalidad no es relevante. El objetivo final es hacer que el sistema calcule automáticamente diferentes identificadores de desvío para asociarse con diferentes configuraciones regionales que no tienen una buena conexión. La definición de una restricción de ancho de banda significa por definición que un vínculo no tiene una buena conexión.

  - El CAC está habilitado y el desvío de medios no está habilitado. Esto se aplica únicamente cuando todas las puertas de enlace y los sistemas IP-PBX presentan una conexión deficiente o no reúnen otros requisitos para el desvío de medios. Para obtener más información acerca de los requisitos para el desvío de medios, consulte [Requisitos técnicos para la omisión de medios en Lync Server 2013](lync-server-2013-technical-requirements-for-media-bypass.md).

## Vea también

#### Conceptos

[Introducción general a la omisión de medios en Lync Server 2013](lync-server-2013-overview-of-media-bypass.md)  
[Modos de omisión de medios en Lync Server 2013](lync-server-2013-media-bypass-modes.md)  
[Requisitos técnicos para la omisión de medios en Lync Server 2013](lync-server-2013-technical-requirements-for-media-bypass.md)

