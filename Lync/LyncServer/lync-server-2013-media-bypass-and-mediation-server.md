---
title: 'Lync Server 2013: Omisión de medios y servidor de mediación'
TOCTitle: Omisión de medios y servidor de mediación
ms:assetid: 8ed35f95-05cd-4b5d-8470-442d2323df71
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398719(v=OCS.15)
ms:contentKeyID: 48275988
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Omisión de medios y servidor de mediación en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-21_

El desvío de medios es una funcionalidad de Lync Server que permite a un administrador configurar el enrutamiento de llamadas de modo que fluya directamente entre el extremo del usuario y la puerta de enlace de la red telefónica conmutada (RTC) sin atravesar el Servidor de mediación. El desvío de medios mejora la calidad de la llamada al reducir la latencia, la traducción innecesaria, la posibilidad de pérdida de paquetes y el número de puntos de errores potenciales. En los lugares donde un sitio remoto sin Servidor de mediación está conectado a un sitio central mediante uno o más vínculos WAN con ancho de banda restringido, el desvío de medios disminuye la necesidad de ancho de banda, al permitir que los medios de un cliente en un sitio remoto fluyan directamente hasta su puerta de enlace local, sin tener que pasar primero por el vínculo WAN hasta un Servidor de mediación del sitio central y volver. Esta reducción en el procesamiento de medios complementa también a la capacidad del Servidor de mediación para controlar varias puertas de enlace.

El desvío de medios y el control de admisión de llamadas (CAC) se excluyen mutuamente. Si se usa desvío de medios en una llamada, no se aplicará el CAC en esa llamada. Se asume que no hay vínculos relacionados con la llamada que tengan restringido el ancho de banda.

## Vea también

#### Conceptos

[Control de admisión de llamadas y servidor de mediación en Lync Server 2013](lync-server-2013-call-admission-control-and-mediation-server.md)  

#### Otros recursos

[Planificar la omisión de medios en Lync Server 2013](lync-server-2013-planning-for-media-bypass.md)

