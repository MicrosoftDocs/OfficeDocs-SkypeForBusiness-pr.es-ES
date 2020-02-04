---
title: 'Lync Server 2013: Planear el control de admisión de llamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for call admission control (CAC)
ms:assetid: ca367138-adf5-4119-bc40-5ddf335ed22f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398842(v=OCS.15)
ms:contentKeyID: 48185652
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de1f39b32503be758e10f3fbf712acdc07bd956b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725470"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-call-admission-control-in-lync-server-2013"></a>Planear el control de admisión de llamadas en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-21_

En el caso de las aplicaciones de comunicaciones unificadas (UC) que se basan en IP, como la telefonía, el vídeo y el uso compartido de aplicaciones, generalmente no se considera que el ancho de banda disponible de las redes empresariales sea un factor limitador dentro de entornos LAN. Sin embargo, en los vínculos WAN que conectan sitios entre sí, el ancho de banda de red puede restringirse. Cuando un flujo de tráfico de red sobrescribirá un vínculo WAN, se usarán mecanismos actuales como colas, almacenamiento en búfer y descartar paquetes para resolver la congestión. El tráfico adicional se retrasa generalmente hasta que la red se acelera o, si es necesario, se pierde el tráfico. Para el tráfico de datos convencionales en estas situaciones, el cliente receptor puede recuperarse. Para el tráfico en tiempo real, como las comunicaciones unificadas, la congestión de red no se puede resolver de esta manera, porque el tráfico de comunicaciones unificadas es sensible a la latencia y a la pérdida de paquetes. La congestión de la WAN puede dar lugar a una experiencia de calidad deficiente para los usuarios. Para el tráfico en tiempo real en condiciones congestionadas, es mejor denegar las llamadas que proporcionar conexiones de baja calidad.

El servicio de control de admisión de llamadas (CAC) determina si hay suficiente ancho de banda de red para establecer una sesión en tiempo real con una calidad aceptable. En Lync Server 2013, CAC controla el tráfico en tiempo real solo para audio y vídeo, pero no afecta al tráfico de datos. Si la ruta de acceso de WAN predeterminada no tiene el ancho de banda necesario, CAC puede intentar redirigir la llamada a través de una ruta de acceso de Internet o a través de la red telefónica conmutada (RTC). CAC solo está disponible en Lync Server.

En esta sección se describen las funciones del servicio de control de admisión de llamadas y explica cómo planificar para CAC.

<div>


> [!NOTE]  
> Lync Server tiene tres características avanzadas de Enterprise Voice: control de admisión de llamadas (CAC), servicios de emergencia (E9-1-1) y omisión de medios. Para obtener una descripción general de la información de planeación común para estas tres características, consulte <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">configuración de red para las características de telefonía avanzada empresarial de Lync Server 2013</A>.



</div>

<div>

## <a name="in-this-section"></a>En esta sección

  - [Información general sobre el control de admisión de llamadas en Lync Server 2013](lync-server-2013-overview-of-call-admission-control.md)

  - [Definición de los requisitos de la organización para el servicio de control de admisión de llamadas en Lync Server 2013](lync-server-2013-defining-your-requirements-for-call-admission-control.md)

  - [Ejemplo: recopilar los requisitos para el control de admisión de llamadas en Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)

  - [Componentes y topologías para CAC en Lync Server 2013](lync-server-2013-components-and-topologies-for-cac.md)

  - [Procedimientos recomendados para el servicio de control de admisión de llamadas en Lync Server 2013](lync-server-2013-best-practices-for-call-admission-control.md)

  - [Lista de comprobación para la implementación del control de admisión de llamadas en Lync Server 2013](lync-server-2013-deployment-checklist-for-call-admission-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

