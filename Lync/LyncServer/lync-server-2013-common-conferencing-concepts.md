---
title: 'Lync Server 2013: conceptos comunes de conferencias'
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
ms.openlocfilehash: 91d21526cfcd6d2c78cd67660136e8f7600d1841
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742780"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="common-conferencing-concepts-in-lync-server-2013"></a>Conceptos de conferencias comunes en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-19_

Varios conceptos son comunes a todos los tipos de conferencia. Se describen en las siguientes secciones.

<div>

## <a name="policies-and-bandwidth-management"></a>Directivas y administración de ancho de banda

Lync Server 2013 permite a los administradores establecer directivas para los tipos de reuniones que los usuarios pueden organizar. Esto le permite exigir las directivas de su organización y controlar el uso del ancho de banda. Puede definir una amplia variedad de políticas de reunión y asignarlas a usuarios individuales y a grupos de usuarios. También puede establecer las directivas que rigen las conversaciones de punto a punto. Para obtener más información sobre cómo configurar directivas de conferencia, consulte [directivas de conferencia en Lync Server 2013](lync-server-2013-conferencing-policies.md) en la documentación de operaciones. Para obtener más información sobre la administración de ancho de banda, vea [información general sobre el control de admisión de llamadas en Lync server 2013](lync-server-2013-overview-of-call-admission-control.md) y [configurar el ancho de banda de vídeo en Lync Server 2013](lync-server-2013-configuring-video-bandwidth.md).

</div>

<div>

## <a name="archiving-and-compliance-features"></a>Características de archivado y cumplimiento

Lync Server 2013 proporciona características que puede usar si su organización debe seguir las normas de cumplimiento. Puede usar las capacidades de archivado para archivar el contenido presentado en las reuniones, así como el contenido de las conversaciones de mensajería instantánea y las conferencias de mensajería instantánea. Para obtener más información, vea [planificación de archivado en Lync Server 2013](lync-server-2013-planning-for-archiving.md) en la documentación de planeación. Puede usar las características de cumplimiento del servidor de chat persistente para archivar conversaciones basadas en temas y en temas que se mantienen a lo largo del tiempo. Para obtener más información, vea [planeación de un servidor de chat persistente en Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) en la documentación de planeación.

</div>

<div>

## <a name="monitoring-feature"></a>Característica de supervisión

La característica servidor de supervisión puede capturar registros de detalles de llamadas (CDRs), que puede usar para realizar un seguimiento de los usuarios que se comunican con los otros usuarios de Lync Server 2013. Para obtener detalles sobre la implementación y la configuración de la supervisión, consulte [implementación de la supervisión en Lync Server 2013](lync-server-2013-deploying-monitoring.md).

</div>

<div>

## <a name="enabling-external-participation-in-conferences"></a>Habilitar la participación externa en conferencias

Puede aumentar enormemente los beneficios de su inversión en conferencias de 2013 de Lync Server al permitir que los usuarios externos también participen en conferencias cuando se inviten. Entre los usuarios externos se pueden incluir:

  - **A los usuarios**   remotos de su organización, cuando trabajan fuera de los firewalls y usan sus equipos portátiles u otros dispositivos de Lync Server 2013.

  - **Usuarios federados**   usuarios de empresas con las que trabaja y que también ejecutan Lync Server 2013. Si desea habilitar a sus usuarios para que se pongan en contacto fácilmente con estos otros usuarios, cree relaciones federadas con estas compañías.

  - **Usuarios anónimos**   cualquier otro usuario externo al que los usuarios hayan invitado específicamente para unirse a conferencias específicas. Un organizador de reuniones de su compañía puede enviar una invitación por correo electrónico a un usuario externo para una conferencia. El correo electrónico incluye un vínculo en el que el usuario externo puede hacer clic para unirse a la conferencia.

Para habilitar cualquiera de estos escenarios o todos ellos, debe implementar un servidor perimetral que le ayude a habilitar las comunicaciones seguras entre la implementación de Lync Server 2013 y los usuarios externos. La solución Lync Server 2013 que usa servidores perimetrales proporciona un medio de mayor calidad que otras soluciones, como una red privada virtual (VPN). Para obtener más información, consulte [planear el acceso de usuarios externos en Lync Server 2013](lync-server-2013-planning-for-external-user-access.md).

Además, tanto si implementa servidores perimetrales como si no, puede habilitar a los usuarios (es decir, dentro o fuera de su organización) llamar desde teléfonos RTC estándar para unirse a conferencias de audio locales. Esto se logra implementando las conferencias de acceso telefónico local de Lync Server 2013.

</div>

<div>

## <a name="compatibility-among-meeting-types-and-client-versions"></a>Compatibilidad entre los tipos de reunión y las versiones de cliente

Si va a tener Lync Server 2013 interopera con versiones anteriores de Office Communications Server y sus clientes, debe tener en cuenta los siguientes problemas:

  - Los usuarios que usen Lync Server 2013 no pueden programar conferencias de Live Meeting ni modificar las reuniones migradas de este tipo.

  - Los usuarios que usan Lync Server 2013 que necesitan asistir a conferencias de Live Meeting hospedadas en servidores que ejecutan Office Communications Server 2007 R2 deben tener el cliente de Live Meeting instalado en su equipo (además de Lync Server 2013) para asistir a estas reuniones.

  - Cuando se migran conferencias de Live Meeting a Lync Server 2013, el contenido de la reunión no se migra. Si se necesita este contenido, se debe volver a cargar.

</div>

</div>

<span> </span>

</div>

</div>

</div>

