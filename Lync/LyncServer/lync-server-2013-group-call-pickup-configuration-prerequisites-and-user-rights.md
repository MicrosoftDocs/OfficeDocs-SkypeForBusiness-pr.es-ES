---
title: Requisitos previos y derechos de usuario para la configuración de la llamada grupal
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
ms.openlocfilehash: 2ed2a44ccd1730de2ebede4b08c1a4d3d7e0da9d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763884"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="group-call-pickup-configuration-prerequisites-and-user-rights-in-lync-server-2013"></a>Requisitos previos y derechos de usuario para la configuración de la llamada grupal en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-01-30_

La recogida de llamada grupal es una característica de administración de llamadas que se instala de forma predeterminada al implementar la telefonía IP empresarial. En este tema se describe lo que debe tener en cuenta antes de poder configurar la recogida de llamadas grupales y los derechos de usuario que necesita para realizar las tareas de configuración.

En esta sección se presupone que ha leído la documentación de planificación relacionada con la recogida de llamadas grupales (consulte [planificación de la recogida de llamadas grupales en Lync Server 2013](lync-server-2013-planning-for-group-call-pickup.md)).

<div>

## <a name="group-call-pickup-configuration-prerequisites"></a>Requisitos previos de configuración de la llamada grupal

La recogida de llamadas grupales requiere los siguientes componentes:

  - Servicio de aplicaciones

  - Aplicación de estacionamiento de llamadas

Estos componentes se instalan automáticamente al implementar la telefonía IP empresarial.

</div>

<div>

## <a name="group-call-pickup-configuration-user-rights"></a>Configuración de la recogida de llamada grupal derechos de usuario

Use las siguientes herramientas administrativas para configurar la recogida de llamadas grupales:

  - Shell de administración de Communications Server

  - Herramienta del kit de recursos de SEFAUtil

Use el shell de administración de Lync Server para crear y administrar grupos de recogida de llamadas en la tabla de llamadas en órbita de estacionamiento. Use la herramienta del kit de recursos de SEFAUtil para asignar un grupo de recogida de llamadas y habilitar la recogida de llamadas grupales para los usuarios o para deshabilitar la recogida de llamadas grupales para los usuarios.

La configuración de la recogida de llamadas de grupo requiere cualquiera de los siguientes roles administrativos, en función de la tarea:

  - **CsVoiceAdministrator:** Esta función de administrador puede crear, configurar y administrar todas las configuraciones y directivas relacionadas con las voz.

  - **CsUserAdministrator:** Este rol de administrador puede habilitar la recogida de llamadas grupales para los usuarios. Esta función de administrador también tiene acceso de vista de solo lectura a todas las configuraciones de voz.

  - **CsServerAdministrator:** Esta función de administrador puede administrar, supervisar y solucionar problemas de servidores y servicios.

  - **CsAdministrator:** Esta función de administrador puede realizar todas las tareas de CsVoiceAdministrator, CsServerAdministrator y CsUserAdministrator.

<div>


> [!NOTE]
> Para obtener más información sobre los derechos administrativos, consulte <A href="lync-server-2013-planning-for-role-based-access-control.md">planificación de control de acceso basado en roles en Lync Server 2013</A> en la documentación de planeación.



</div>

</div>

<div>

## <a name="see-also"></a>Vea también


[Implementación de telefonía IP empresarial en Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md)  


[Planeamiento de las características de administración de llamadas en Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

