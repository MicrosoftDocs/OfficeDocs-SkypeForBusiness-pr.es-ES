---
title: 'Lync Server 2013: preguntas más frecuentes sobre la ayuda de reuniones grandes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync Server large meeting support FAQ
ms:assetid: 34b4fb6a-e35c-47e8-8ab1-f8331741fed2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204804(v=OCS.15)
ms:contentKeyID: 48183837
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c8355374a773afe3d6da22c886a2b103b13abd3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834948"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="large-meeting-support-faq-for-lync-server-2013"></a>Preguntas más frecuentes sobre la compatibilidad con reuniones grandes para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-22_

En las siguientes secciones se proporcionan respuestas a las preguntas más frecuentes sobre la creación y la ejecución de reuniones grandes.

<div>

## <a name="q-how-many-users-can-participate-in-a-large-meeting"></a>P: ¿Cuántos usuarios pueden participar en una reunión de gran tamaño?

El modelo de usuario de Lync Server especifica los límites de usuarios de 250 en un grupo compartido o los usuarios de 1000 de un grupo dedicado a reuniones grandes, pero estos números solo representan el número de usuarios que probamos y solo para el conjunto específico de hardware que usamos en nuestras pruebas. Según nuestras pruebas, recomendamos esos límites para el tamaño máximo. Sin embargo, puede controlar la cantidad real de participantes permitidos en las reuniones de su organización mediante la configuración de una o más directivas de conferencia (que puede configurar con los cmdlets de Windows PowerShell en el shell de administración de Lync Server o con el servidor de Lync). Panel de control). El número que especifique en una directiva de conferencia puede ser cualquier número entero de 32 entre 1 y 4.294.967.295, pero el tamaño recomendado es de entre 2 y 250 participantes, ambos inclusive; y el valor predeterminado es 250.

</div>

<div>

## <a name="q-how-many-meetings-or-other-workloads-can-i-have-in-a-pool-that-is-dedicated-to-large-meetings"></a>P: ¿cuántas reuniones u otras cargas de trabajo puedo tener en un grupo dedicado a reuniones grandes?

Para garantizar la mejor experiencia del usuario en reuniones de gran tamaño de hasta 1000 participantes, le recomendamos que aloje una sola reunión de gran tamaño a la vez en un grupo dedicado a reuniones grandes. También recomendamos no permitir que se ejecuten otras cargas de trabajo en ese grupo cuando la reunión de gran tamaño está en curso.

</div>

<div>

## <a name="q-should-the-organizers-of-large-meeting-be-homed-on-the-dedicated-pool"></a>P: ¿deberían los organizadores de una reunión grande estar alojados en el grupo dedicado?

No. Le recomendamos que no se a ningún usuario que no sea el personal dedicado que administra la programación de reuniones grandes en el grupo dedicado. Esto evita que otro tráfico de comunicaciones en tiempo real cause problemas con reuniones grandes hospedadas en el grupo. Debe programar reuniones grandes en el grupo dedicado usando una cuenta de usuario del gran personal de programación de reuniones. Debe agregar la cuenta de usuario del organizador de la reunión (el usuario que solicita una reunión grande) como moderador de la reunión grande.

</div>

<div>

## <a name="q-what-media-modalities-can-i-use-in-a-large-meeting"></a>P: ¿Qué es lo que las modalidades de medios puedo usar en una reunión grande?

Las reuniones grandes con hasta 1000 usuarios pueden incluir audio, vídeo, uso compartido de PowerPoint, pizarras y sondeo de presencia.

</div>

<div>

## <a name="q-can-i-use-group-instant-messaging-im-in-large-meetings"></a>P: ¿Puedo usar la mensajería instantánea grupal (mi) en reuniones grandes?

Sí. Sin embargo, un gran número de mensajes instantáneos, especialmente cuando los envía un gran número de participantes de la reunión, puede afectar la experiencia del usuario debido a problemas con el desplazamiento de texto rápido en la ventana de mensajes instantáneos. Ofrecer una gran cantidad de mensajes instantáneos a un máximo de 1000 usuarios también puede presentar cargas de servidor significativas, lo cual puede afectar al rendimiento. Por lo general, la mensajería instantánea solo es necesaria para preguntas\&y respuestas (Q como).

</div>

<div>

## <a name="can-users-join-large-meetings-by-dialing-in-from-a-phone"></a>¿Los usuarios pueden unirse a reuniones grandes al marcar desde un teléfono?

Sí. Si el grupo de 2013 de Lync Server se ha implementado correctamente y está habilitado para las conferencias de acceso telefónico local, los usuarios podrán unirse a las reuniones grandes al marcar. Nuestras pruebas han demostrado que hasta el 15% de los usuarios de 1000 pueden unirse a la reunión de gran tamaño durante un período de 10 minutos.

</div>

<div>

## <a name="q-can-i-host-large-meetings-in-a-virtual-topology"></a>P: ¿puedo hospedar reuniones grandes en una topología virtual?

No hemos probado las reuniones grandes en una topología virtual, por lo que no admitimos el uso de máquinas virtuales para hospedar un grupo dedicado para reuniones grandes.

</div>

</div>

<span> </span>

</div>

</div>

</div>

