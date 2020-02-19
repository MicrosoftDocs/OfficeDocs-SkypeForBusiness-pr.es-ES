---
title: 'Lync Server 2013: conceptos comunes de conferencia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Common conferencing concepts
ms:assetid: a21d4987-1c0a-44c8-8a39-9c17ffb57f3c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688158(v=OCS.15)
ms:contentKeyID: 49733762
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3117f07a3ffffe6b3c081b64a4ad4ba8ee6aee8a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138491"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="common-conferencing-concepts-in-lync-server-2013"></a>Conceptos comunes de conferencia en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-19_

Todos los tipos de conferencias tienen varios conceptos en común. Se describen en las siguientes secciones.

<div>

## <a name="policies-and-bandwidth-management"></a>Directivas y administración de ancho de banda

Lync Server 2013 permite a los administradores establecer directivas para los tipos de reuniones que los usuarios pueden organizar. Esto ayuda a aplicar las directivas de la organización y a controlar el uso de ancho de banda. Puede definirse una gran variedad de directivas de reunión y asignarlas a usuarios individuales y grupos de usuarios. También se pueden establecer las directivas que rigen las conversaciones de punto a punto. Para obtener más información sobre cómo establecer directivas de conferencia, consulte [directivas de conferencia en Lync Server 2013](lync-server-2013-conferencing-policies.md) en la documentación de operaciones. Para obtener más información acerca de la administración del ancho de banda, consulte [información general sobre el control de admisión de llamadas en Lync server 2013](lync-server-2013-overview-of-call-admission-control.md) y [configurar el ancho de banda de vídeo en Lync Server 2013](lync-server-2013-configuring-video-bandwidth.md).

</div>

<div>

## <a name="archiving-and-compliance-features"></a>Características de Archivado y Cumplimiento

Lync Server 2013 proporciona características que puede usar si su organización debe seguir las normas de cumplimiento. Pueden usarse las capacidades de archivado para archivar contenido presentado en las reuniones, así como el contenido de conversaciones y conferencias de mensajería instantánea (MI). Para obtener más información, consulte [planeación del archivado en Lync Server 2013](lync-server-2013-planning-for-archiving.md) en la documentación de planeación. Puede usar las características de cumplimiento de Servidor de Chat persistente para archivar conversaciones con varios participantes y basadas en temas que persistan durante mucho tiempo. Para obtener más información, consulte [Planning for persistent chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) en la documentación referente a la planeación.

</div>

<div>

## <a name="monitoring-feature"></a>Función de supervisión

La característica de servidor de supervisión puede capturar registros de detalles de llamadas (CDR), que puede usar para realizar un seguimiento de los usuarios que hablan a otros usuarios que usan Lync Server 2013. Para obtener más información sobre la implementación y la configuración de la supervisión, consulte [Deploying Monitoring in Lync Server 2013](lync-server-2013-deploying-monitoring.md).

</div>

<div>

## <a name="enabling-external-participation-in-conferences"></a>Habilitar la participación externa en conferencias

Puede aumentar en gran medida los beneficios de su inversión en conferencias de Lync Server 2013 al habilitar a los usuarios externos para que también participen en conferencias cuando se les invite. Entre los usuarios externos se pueden incluir:

  - **Usuarios remotos**   los propios usuarios de su organización, cuando trabajan fuera de los firewalls y están usando sus equipos portátiles u otros dispositivos de Lync Server 2013.

  - **Usuarios federados**   usuarios de empresas con las que trabaja y que también ejecutan Lync Server 2013. Para habilitar a sus usuarios para que se pongan en contacto fácilmente con estos usuarios, cree relaciones federadas con estas compañías.

  - **Usuarios anónimos**   todos los usuarios externos que han invitado específicamente a los usuarios a unirse a conferencias específicas. Un organizador de reuniones de su compañía puede enviar una invitación por correo electrónico a un usuario externo para una conferencia. El correo electrónico incluye un vínculo en el que el usuario externo puede hacer clic para unirse a la conferencia.

Para habilitar uno o todos estos escenarios, debe implementar un servidor perimetral que ayude a habilitar las comunicaciones seguras entre la implementación de Lync Server 2013 y los usuarios externos. La solución Lync Server 2013 con servidores perimetrales proporciona una mayor calidad de medios que otras soluciones, como una red privada virtual (VPN). Para obtener más información, consulte [planeación del acceso de usuarios externos en Lync Server 2013](lync-server-2013-planning-for-external-user-access.md).

Además, tanto si su organización implementa o no servidores perimetrales, puede habilitar usuarios (ya sean de dentro o de fuera de la organización) para que realicen marcados desde teléfonos RTC para unirse a conferencias de audio locales. Esto se logra mediante la implementación de la Conferencia de acceso telefónico local 2013 de Lync Server.

</div>

<div>

## <a name="compatibility-among-meeting-types-and-client-versions"></a>Compatibilidad entre tipos de reunión y versiones de cliente

Si va a hacer que Lync Server 2013 interopere con versiones anteriores de Office Communications Server y sus clientes, debe tener en cuenta los siguientes problemas:

  - Los usuarios que usan Lync Server 2013 no pueden programar conferencias de Live Meeting ni modificar ninguna reunión migrada de este tipo.

  - Los usuarios que usan Lync Server 2013 y deben asistir a conferencias de Live Meeting hospedadas en servidores que ejecutan Office Communications Server 2007 R2 deben tener el cliente de Live Meeting instalado en su equipo (además de Lync Server 2013) para asistir a estas reuniones.

  - Cuando se migran conferencias de Live Meeting a Lync Server 2013, el contenido de la reunión no se migra. Si necesita dicho contenido, deberá volver a cargarlo.

</div>

</div>

<span> </span>

</div>

</div>

</div>

