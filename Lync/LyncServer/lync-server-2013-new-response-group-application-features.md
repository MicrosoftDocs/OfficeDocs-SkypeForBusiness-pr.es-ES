---
title: 'Lync Server 2013: Nuevas funciones de las aplicaciones de grupo de respuesta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: New Response Group application features
ms:assetid: 569544b4-fa97-429b-97e6-568afab6c19b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398373(v=OCS.15)
ms:contentKeyID: 48184196
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 33dd01cf7516f950e58dbc90ee09b06901bccf74
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826153"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-response-group-application-features-in-lync-server-2013"></a>Nuevas funciones de las aplicaciones de grupo de respuesta en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-29_

Con la aplicación de grupo de respuesta, puede enrutar y poner en cola las llamadas entrantes a personas designadas para fines especiales, como el servicio de atención al cliente, una asistencia interna o asistencia telefónica general para un departamento.

Las siguientes características de la aplicación de grupo de respuesta son nuevas en Lync Server 2013:

  - **Rol de administrador**
    
    Lync Server 2013 introduce un nuevo rol de administrador de grupo de respuesta. Ahora hay dos roles de administración para los grupos de respuesta: administrador de grupo de respuesta y administrador del grupo de respuesta. Mientras que los administradores de grupos de respuesta aún pueden configurar cualquier elemento para cualquier grupo de respuesta, los administradores solo pueden configurar determinados elementos, solo para los grupos de respuesta de los que son propietarios.
    
    Esta mejora en el modelo de administración beneficia la escalabilidad de grupos de respuesta, especialmente para escenarios de implementación grandes.

  - **Alta disponibilidad**
    
    La compatibilidad de alta disponibilidad para la aplicación de grupo de respuesta, en forma de reflejo de SQL Server, está habilitada como parte de la configuración general e implementación de la alta disponibilidad de Lync Server 2013. Si configura para alta disponibilidad y pierde conectividad con el servidor back-end principal, la funcionalidad de grupo de respuesta no se ve afectada por el uso del servidor de servicios de fondo reflejado.
    
    La compatibilidad con el reflejo de SQL Server para la aplicación de grupo de respuesta no se puede habilitar o configurar individualmente fuera de la configuración general de alta disponibilidad de Lync Server 2013.

  - **Recuperación ante desastres**
    
    La compatibilidad de recuperación ante desastres para la aplicación de grupo de respuesta está habilitada como parte de la configuración e implementación de las agrupaciones frontales emparejadas, que forman parte de la configuración general de recuperación ante desastres de Lync Server 2013. Además, los cmdlets de importación y exportación de grupos de respuesta admiten el proceso de conmutación por error para el grupo de copia de seguridad y el proceso de recuperación tras error al grupo principal o a un grupo nuevo. Si se produce una interrupción en el grupo principal, los grupos de respuesta pueden conmutar por error al grupo de copias de seguridad y, después, devolver el error al grupo principal o a un nuevo grupo cuando haya finalizado la interrupción.

<div id="sectionSection0" class="section">

</div>

<div>

## <a name="see-also"></a>Vea también


[Planificar para grupos de respuesta en Lync Server 2013](lync-server-2013-planning-for-response-groups.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

