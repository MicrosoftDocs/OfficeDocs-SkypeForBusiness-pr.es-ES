---
title: 'Lync Server 2013: configuración del grupo de respuesta'
description: 'Lync Server 2013: configuración del grupo de respuesta.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Response Group
ms:assetid: c56db929-cb21-4af0-be3f-c8f807b78a5a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205249(v=OCS.15)
ms:contentKeyID: 48185359
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 92674bb971ec5216051d75d788dc58b9c7ca641c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547936"
---
# <a name="configuring-response-group-in-lync-server-2013"></a>Configuración del grupo de respuesta en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-30_

El grupo de respuesta es una característica de Enterprise Voice que enruta y pone en cola las llamadas entrantes a grupos de personas, denominados *agentes*, como un servicio de asistencia o un servicio de atención al cliente.

Los componentes que necesita el grupo de respuesta se instalan y se habilitan automáticamente en el servidor front-end o servidor Standard Edition al implementar Enterprise Voice. Para que el grupo de respuesta esté disponible para los usuarios, debe configurar los grupos de agentes; a continuación, las colas y, por último, los flujos de trabajo. Además, un administrador de grupo de respuesta puede delegar la configuración de un flujo de trabajo existente a un administrador de grupo de respuesta, que puede modificar y volver a configurar el flujo de trabajo y sus grupos de agentes y colas asociados.

Esta sección le guiará a través de la configuración del grupo de respuesta 2013 de Lync Server. Se da por hecho que ya ha leído las secciones de planeación relacionadas con el grupo de respuesta y que ha implementado un servidor Enterprise Edition o un servidor Standard Edition con telefonía IP empresarial.

<div>


> [!TIP]  
> Para obtener información detallada sobre cómo crear un grupo de respuesta mediante el shell de administración de Lync Server, incluido un script de ejemplo, consulte "creación del primer grupo de respuesta con el shell de administración de Lync Server" en <A href="https://go.microsoft.com/fwlink/p/?linkid=204108">https://go.microsoft.com/fwlink/p/?linkId=204108</A> .



</div>

<div>

## <a name="in-this-section"></a>En esta sección

  - [Permisos y requisitos previos de configuración de grupos de respuesta en Lync Server 2013](lync-server-2013-response-group-configuration-permissions-and-prerequisites.md)

  - [Proceso de implementación del grupo de respuesta en Lync Server 2013](lync-server-2013-deployment-process-for-response-group.md)

  - [Información general sobre los escenarios de creación de flujos de trabajo en Lync Server 2013](lync-server-2013-overview-of-workflow-creation-scenarios.md)

  - [Crear grupos de agentes de grupo de respuesta Lync Server 2013](lync-server-2013-create-response-group-agent-groups.md)

  - [Crear colas de grupo de respuesta en Lync Server 2013](lync-server-2013-create-response-group-queues.md)

  - [Opcional Definir el horario comercial del grupo de respuesta en Lync Server 2013](lync-server-2013-optional-define-response-group-business-hours.md)

  - [Opcional Definir conjuntos de días festivos para grupos de respuesta en Lync Server 2013](lync-server-2013-optional-define-response-group-holiday-sets.md)

  - [Crear flujos de trabajo de grupo de respuesta en Lync Server 2013](lync-server-2013-create-response-group-workflows.md)

  - [Opcional Comprobar la implementación del grupo de respuesta en Lync Server 2013](lync-server-2013-optional-verify-response-group-deployment.md)

</div>

<div>

## <a name="see-also"></a>Consulte también


[Planeación de características de administración de llamadas en Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

