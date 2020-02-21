---
title: Requisitos previos y derechos de usuario para la configuración de llamada de grupo
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Group Call Pickup configuration prerequisites and user rights
ms:assetid: 8757b1d3-751d-49c3-b1b8-b678f663f18e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945641(v=OCS.15)
ms:contentKeyID: 51541495
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1d0127ff5c196c14dc7844c6958ced9ae5478113
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213246"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="group-call-pickup-configuration-prerequisites-and-user-rights-in-lync-server-2013"></a>Requisitos previos de configuración de llamada de grupo y derechos de usuario en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-01-30_

La recogida de llamadas grupales es una característica de administración de llamadas que se instala de forma predeterminada al implementar la telefonía IP empresarial. En este tema se describe lo que necesita tener en su ubicación antes de poder configurar la atención de llamadas grupales y los derechos de usuario necesarios para realizar tareas de configuración.

En esta sección se da por sentado que ha leído la documentación de planeación relacionada con la recogida de llamadas de grupo (consulte [Planning for Group Call pickup in Lync Server 2013](lync-server-2013-planning-for-group-call-pickup.md)).

<div>

## <a name="group-call-pickup-configuration-prerequisites"></a>Requisitos previos de configuración de llamada de grupo

La recogida de llamadas de grupo requiere los siguientes componentes:

  - Servicio de aplicación

  - Aplicación Estacionamiento de llamadas

Estos componentes se instalan automáticamente al implementar la telefonía IP empresarial.

</div>

<div>

## <a name="group-call-pickup-configuration-user-rights"></a>Derechos de usuario de configuración de llamada de grupo

Puede usar las siguientes herramientas administrativas para configurar la recogida de llamadas de Grupo:

  - Shell de administración de Communications Server

  - Herramienta del kit de recursos de SEFAUtil

Use el shell de administración de Lync Server para crear y administrar grupos de recogida de llamadas en la tabla de órbitas de estacionamiento de llamadas. Use la herramienta del kit de recursos de SEFAUtil para asignar un grupo de atención de llamadas y habilitar la atención de llamadas grupales para los usuarios o para deshabilitar la atención de llamadas grupales para los usuarios.

La configuración de la recogida de llamadas de grupo requiere cualquiera de los siguientes roles administrativos, en función de la tarea:

  - **CsVoiceAdministrator:** Este rol de administrador puede crear, configurar y administrar todas las configuraciones y directivas relacionadas con la voz.

  - **CsUserAdministrator:** Este rol de administrador puede habilitar la recepción de llamadas grupales para los usuarios. De igual modo, permite el acceso de vista de solo lectura a todas las configuraciones de voz.

  - **CsServerAdministrator:** Este rol de administrador puede administrar, supervisar y solucionar problemas de servidores y servicios.

  - **CsAdministrator:** Este rol de administrador puede realizar todas las tareas de CsVoiceAdministrator, CsServerAdministrator y CsUserAdministrator.

<div>


> [!NOTE]
> Para obtener más información sobre los derechos administrativos, consulte <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> en la documentación referente a la planeación.



</div>

</div>

<div>

## <a name="see-also"></a>Consulta también


[Implementar la telefonía IP empresarial en Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md)  


[Planeación de características de administración de llamadas en Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

