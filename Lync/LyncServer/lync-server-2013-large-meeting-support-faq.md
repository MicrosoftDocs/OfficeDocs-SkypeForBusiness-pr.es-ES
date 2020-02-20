---
title: 'Lync Server 2013: preguntas más frecuentes sobre la compatibilidad con reuniones grandes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server large meeting support FAQ
ms:assetid: 34b4fb6a-e35c-47e8-8ab1-f8331741fed2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204804(v=OCS.15)
ms:contentKeyID: 48183837
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8b00c7d2713bed543dd42812d0d7c31bf75cd1d8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146343"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="large-meeting-support-faq-for-lync-server-2013"></a>Preguntas más frecuentes de soporte de reuniones grandes para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-22_

Las siguientes secciones ofrecen respuestas a preguntas habituales para crear y ejecutar reuniones grandes.

<div>

## <a name="q-how-many-users-can-participate-in-a-large-meeting"></a>P: ¿Cuántos usuarios pueden participar en una reunión grande?

El modelo de usuario de Lync Server especifica los límites de 250 usuarios en un grupo compartido o 1000 usuarios en un grupo dedicado a reuniones grandes, pero estos números solo representan el número de usuarios que se probaron y solo para el conjunto específico de hardware que usamos en nuestras pruebas. En función de nuestra prueba, se recomiendan dichos límites para tamaños máximos. Sin embargo, se controla el número real de participantes permitidos en las reuniones de la organización mediante la configuración de una o varias directivas de conferencia (que se configuran mediante cmdlets de Windows PowerShell en el shell de administración de Lync Server o mediante el uso de Lync Server Panel de control). El número que especifica en una directiva de conferencia puede ser cualquier número entero de 32 bits comprendido entre 1 y 4.294.967.295, pero el tamaño recomendado se encuentra entre 2 y 250 participantes, inclusive; y el valor predeterminado es 250.

</div>

<div>

## <a name="q-how-many-meetings-or-other-workloads-can-i-have-in-a-pool-that-is-dedicated-to-large-meetings"></a>P: ¿Cuántas reuniones u otras cargas de trabajo puedo tener en un grupo de servidores que está dedicado a reuniones grandes?

Para garantizar la mejor experiencia de usuario en reuniones grandes de hasta 1000 participantes, se recomienda hospedar únicamente una única reunión grande cada vez en un grupo de servidores dedicado a reuniones grandes. También se recomienda no permitir que se ejecute cualquier otra carga de trabajo en dicho grupo de servidores cuando la reunión grande se encuentre en curso.

</div>

<div>

## <a name="q-should-the-organizers-of-large-meeting-be-homed-on-the-dedicated-pool"></a>P: ¿Deberían los organizadores de reuniones grandes hospedarse en el grupo de servidores dedicado?

No. Se recomienda no hospedar ningún usuario distinto del personal dedicado que administra la programación de reuniones grandes en el grupo de servidores dedicado. Esto evita que tráfico de comunicaciones en tiempo real provoque problemas con reuniones grandes que se hospedan en el grupo de servidores. Debería programar reuniones grandes en el grupo de servidores dedicado con una cuenta de usuario del personal de programación de reuniones grandes. Debería agregar la cuenta de usuario del organizador de reuniones (el usuario que solicita una reunión grande) como moderador para las reuniones grandes.

</div>

<div>

## <a name="q-what-media-modalities-can-i-use-in-a-large-meeting"></a>P: ¿Qué modalidades de medios puedo usar en una reunión grande?

Las reuniones grandes con un máximo de 1000 usuarios pueden incluir audio, video, uso compartido de PowerPoint, pizarras y sondeo de presencia.

</div>

<div>

## <a name="q-can-i-use-group-instant-messaging-im-in-large-meetings"></a>P: ¿Puedo usar la mensajería instantánea de grupo (MI) en reuniones grandes?

Sí. Sin embargo, los números grandes de mensajes instantáneos, especialmente cuando se envían por un gran número de participantes de reunión, pueden afectar a la experiencia del usuario debido a problemas con el desplazamiento de texto rápido en la ventana de MI. La entrega de una gran cantidad de mensajes instantáneos de un máximo de 1000 usuarios también puede introducir cargas de servidor importantes, que pueden afectar al rendimiento. Por lo general, la mensajería instantánea solo es necesaria para las\&preguntas y respuestas (Q como).

</div>

<div>

## <a name="can-users-join-large-meetings-by-dialing-in-from-a-phone"></a>¿Pueden los usuarios unirse a reuniones grandes marcando desde un teléfono?

Sí. Si el grupo de servidores de Lync Server 2013 se ha implementado correctamente y está habilitado para las conferencias de acceso telefónico local, los usuarios podrán unirse a las reuniones grandes marcando en. Nuestra prueba ha mostrado que hasta un máximo de un 15% de los 1000 usuarios pueden unirse a la reunión grande por un período de 10 minutos.

</div>

<div>

## <a name="q-can-i-host-large-meetings-in-a-virtual-topology"></a>P: ¿Puedo hospedar reuniones grandes en una topología virtual?

No hemos probado reuniones grandes en una topología virtual, por lo que no admitimos el uso de máquinas virtuales para hospedar un grupo de servidores dedicados para reuniones grandes.

</div>

</div>

<span> </span>

</div>

</div>

</div>

