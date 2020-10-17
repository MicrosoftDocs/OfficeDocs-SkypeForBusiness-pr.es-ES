---
title: 'Lync Server 2013: Planeación del control de admisión de llamadas'
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
ms.openlocfilehash: a7c101ab49d16b01dd35d4fc498f002747cd31cd
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48497817"
---
# <a name="planning-for-call-admission-control-in-lync-server-2013"></a>Planeación del control de admisión de llamadas en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-21_

Para las aplicaciones de comunicaciones unificadas (UC) basadas en IP, como la telefonía, el vídeo y el uso compartido de aplicaciones, el ancho de banda disponible de las redes de empresa no se considera normalmente un factor limitante dentro de los entornos de LAN; sin embargo, en los vínculos WAN que conectan sitios entre sí, el ancho de banda de red puede restringirse. Cuando una entrada de tráfico de red produce una suscripción excesiva en un vínculo WAN, los mecanismos actuales como la puesta en cola, el almacenamiento en búfer y la pérdida de paquetes se usan para solucionar la congestión. El tráfico adicional normalmente se retrasa hasta que la congestión de la red mejora o, si es necesario, se elimina el tráfico. Para el tráfico de datos convencional en estas situaciones, el cliente receptor puede recuperar. Para el tráfico en tiempo real como las comunicaciones unificadas, la congestión de la red no se puede solucionar de este modo porque el tráfico de las comunicaciones unificadas es sensible a la latencia y a la pérdida de paquetes. La congestión en la WAN puede ocasionar una baja Calidad de la experiencia (QoE) para los usuarios finales. Para el tráfico en tiempo real en condiciones de congestión, es mejor denegar llamadas que permitir conexiones de baja calidad.

El servicio de control de admisión de llamadas (CAC) determina si hay suficiente ancho de banda de red para establecer una sesión en tiempo real con una calidad aceptable. En Lync Server 2013, el CAC controla el tráfico en tiempo real solo para audio y vídeo, pero no afecta al tráfico de datos. Si la ruta de acceso WAN predeterminada no tiene el ancho de banda necesario, CAC puede intentar enrutar la llamada a través de una ruta de acceso de Internet o de la RTC. El CAC solo está disponible en Lync Server.

En esta sección se describen las funciones de control de admisión de llamadas y explica cómo planear para CAC.

<div>


> [!NOTE]  
> Lync Server tiene tres características avanzadas de telefonía IP empresarial: el control de admisión de llamadas (CAC), los servicios de emergencia (E9-1-1) y la omisión de medios. Para obtener información general sobre la planeación de información común a las tres características, consulte <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">configuración de red para las características avanzadas de telefonía IP empresarial en Lync Server 2013</A>.



</div>

<div>

## <a name="in-this-section"></a>En esta sección

  - [Información general sobre el control de admisión de llamadas en Lync Server 2013](lync-server-2013-overview-of-call-admission-control.md)

  - [Definición de los requisitos para el control de admisión de llamadas en Lync Server 2013](lync-server-2013-defining-your-requirements-for-call-admission-control.md)

  - [Ejemplo: recopilar los requisitos para el control de admisión de llamadas en Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)

  - [Componentes y topologías para CAC en Lync Server 2013](lync-server-2013-components-and-topologies-for-cac.md)

  - [Procedimientos recomendados para el control de admisión de llamadas en Lync Server 2013](lync-server-2013-best-practices-for-call-admission-control.md)

  - [Lista de comprobación para la implementación del control de admisión de llamadas en Lync Server 2013](lync-server-2013-deployment-checklist-for-call-admission-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

