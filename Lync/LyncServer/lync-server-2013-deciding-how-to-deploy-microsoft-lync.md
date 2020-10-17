---
title: 'Lync Server 2013: decidir cómo implementar Microsoft Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deciding how to deploy Microsoft Lync
ms:assetid: 6ca677d3-745d-4935-8f05-19274a8bccf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204979(v=OCS.15)
ms:contentKeyID: 48184423
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f31a765d6b682e504839aa24962356f5524801d0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516527"
---
# <a name="deciding-how-to-deploy-lync-server-2013"></a>Decidir cómo implementar Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-03_

Al planear Lync, la primera decisión importante es cómo implementar Microsoft Lync: como Lync Server 2013 local o Lync Online con Microsoft 365 u Office 365 en la nube.

  - **Lync Server 2013 local** : esta opción proporciona el conjunto completo de características de Lync y proporciona la máxima flexibilidad para la configuración, personalización y funcionamiento de la implementación. La organización se encarga de instalar todos los servidores en el sitio y de su mantenimiento. Una implementación local proporciona el conjunto completo de características de Lync Server.

  - **Lync Online en la nube** Lync Online está diseñado para organizaciones que quieren obtener el costo y la agilidad de las reuniones de mensajería instantánea, presencia y reuniones basadas en la nube sin sacrificar las capacidades de clase empresarial de Lync Server. Con Lync Online, Microsoft implementa y mantiene la infraestructura de servidor necesaria y controla el mantenimiento continuo, las revisiones y las actualizaciones. Algunas de las características disponibles en una implementación local no están disponibles en Lync Online.

El tipo de implementación que más le convenga dependerá de las cargas de trabajo que desee implementar y de la situación financiera y geográfica de su organización.

<div>

## <a name="lync-server"></a>Lync Server

Se recomienda implementar Lync Server si se necesitan las características siguientes:

  - Capacidades completas de la **telefonía IP empresarial**     Si planea implementar una solución de telefonía IP completa para reemplazar su PBX o usa características avanzadas de llamada, se necesita una implementación local de Lync Server. La implementación local admite la conectividad directa con troncos y sistemas PBX, además de características telefónicas avanzadas como los grupos de respuesta y el Estacionamiento de llamadas. Lync Online no admite estas características en este momento.

  - Controles de calidad de **medios**     Si desea disponer de todas las características de seguridad de calidad de medios, como el control de admisión de llamadas (CAC) y las características de calidad de servicio (QoS), querrá una implementación local.

  - **Chat persistente**     Si tiene que implementar chat persistente en su organización, debe elegir una implementación local.

  - Aplicaciones de servidor **de**     terceros Solo las implementaciones locales pueden funcionar con aplicaciones de terceros de confianza que usen la API administrada de comunicaciones unificadas de Microsoft (UCMA).

  - **Empresas multinacionales y multiregionales que necesitan soporte regional**     Si tiene centros de información en varios países o regiones y necesita que los servidores se implementen y administren de manera regional, es mejor que una implementación local, ya que proporciona este tipo de capacidades de administración regionales.

  - **Control completo de las directivas, informes y actualizaciones**     Con una implementación local de Lync Server, tiene acceso a todo el conjunto de directivas de servidor y cliente, la supervisión y otros informes, y el tiempo de las actualizaciones. Lync Online proporciona un subconjunto de los informes y la configuración de directivas, y proporciona una ventana limitada, aunque significativa, para aceptar actualizaciones.

</div>

<div>

## <a name="lync-online"></a>Lync Online

Si ninguno de los aspectos enumerados en la lista anterior le resulta fundamental, puede que desee escoger Lync Online para una administración e implementación más sencillas. Lync Online proporciona un conjunto de características de mensajería instantánea, presencia y Conferencia sólidas, y también habilita las llamadas de voz y vídeo a través de IP entre los usuarios de la organización.

</div>

</div>

<span> </span>

</div>

</div>

</div>
