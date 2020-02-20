---
title: 'Lync Server 2013: nuevas características de la aplicación de grupo de respuesta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New Response Group application features
ms:assetid: 569544b4-fa97-429b-97e6-568afab6c19b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398373(v=OCS.15)
ms:contentKeyID: 48184196
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f2538c6698875a0a96ce4e7dc7a46aa7cb9ed8e1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153570"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="new-response-group-application-features-in-lync-server-2013"></a>Nuevas características de aplicación de grupo de respuesta en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-29_

La aplicación de grupo de respuesta permite enrutar y poner en cola llamadas entrantes para personas designadas para fines especiales, como el servicio al cliente, un servicio de asistencia interno o un teléfono general de asistencia para un departamento.

Las siguientes características de la aplicación de grupo de respuesta son nuevas en Lync Server 2013:

  - **Rol de administrador**
    
    Lync Server 2013 presenta un nuevo rol de administrador de grupo de respuesta. Ahora hay dos funciones de administración para los grupos de respuesta: administrador del grupo de respuesta y administrador del grupo de respuesta. Mientras que los administradores de grupos de respuesta pueden seguir configurando cualquier elemento para cualquier grupo de respuesta, los administradores pueden configurar únicamente determinados elementos sólo para los grupos de respuesta de los que son propietarios.
    
    Esta mejora en el modelo de administración beneficia la escalabilidad del grupo de respuesta, especialmente en los escenarios de grandes implementaciones.

  - **Alta disponibilidad**
    
    La compatibilidad de alta disponibilidad para la aplicación de grupo de respuesta, en forma de reflejo de SQL Server, está habilitada como parte de la configuración general e implementación de alta disponibilidad para Lync Server 2013. Si configura para alta disponibilidad y pierde la conectividad con el servidor back-end principal, el aprovechamiento del servidor reflejado no afecta a las funciones del grupo de respuesta.
    
    La compatibilidad con la creación de reflejos de SQL Server para la aplicación de grupo de respuesta no se puede habilitar o configurar de forma individual fuera de la configuración general de alta disponibilidad de Lync Server 2013.

  - **Recuperación ante desastres**
    
    La compatibilidad de recuperación ante desastres para la aplicación de grupo de respuesta está habilitada como parte de la configuración e implementación de los grupos de servidores front-end emparejados, que forman parte de la configuración general de recuperación ante desastres de Lync Server 2013. Además, los cmdlets de importación y exportación de grupos de respuesta admiten el proceso de conmutación por error al grupo de copia de seguridad y el proceso de conmutación por recuperación al grupo principal o a un nuevo grupo. Si se produce una interrupción en el grupo principal, los grupos de respuesta pueden conmutarse por error al grupo de copia de seguridad y luego conmutarse por recuperación al grupo principal o a un nuevo grupo cuando finalice la interrupción.

<div id="sectionSection0" class="section">

</div>

<div>

## <a name="see-also"></a>Vea también


[Planeación de grupos de respuesta en Lync Server 2013](lync-server-2013-planning-for-response-groups.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

