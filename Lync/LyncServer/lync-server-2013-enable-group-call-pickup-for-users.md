---
title: 'Lync Server 2013: habilitar la atención de llamadas grupales para los usuarios'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Group Call Pickup for users
ms:assetid: 20ec5f41-6ba2-4156-82ed-b91d05b62a6d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945620(v=OCS.15)
ms:contentKeyID: 51541457
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69b17ab937d5dd095565e912b26129706b047e69
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136257"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-group-call-pickup-for-users-in-lync-server-2013"></a>Habilitar la atención de llamadas grupales para los usuarios en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-01-30_

Use la herramienta del kit de recursos de SEFAUtil para habilitar la atención de llamadas grupales para los usuarios. Los usuarios deben tener asignado un número de grupo con el tipo GroupPickup en la tabla de órbitas de estacionamiento de llamadas para tener habilitada la recepción de llamadas de grupo. Puede asignar un número de grupo de atención de llamadas y habilitar la recogida de llamadas de grupo al mismo tiempo mediante el parámetro/enablegrouppickup al ejecutar SEFAUtil. exe.

<div>

## <a name="to-enable-group-call-pickup-for-a-user"></a>Para habilitar la recepción de llamadas de grupo para un usuario

1.  Inicie sesión en el equipo donde instaló la herramienta SEFAUtil con derechos de administrador.

2.  En la línea de comandos, ejecute:
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    Por ejemplo:
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199

</div>

<div>

## <a name="see-also"></a>Vea también


[Asignar números de llamada de llamada de grupo a los usuarios en Lync Server 2013](lync-server-2013-assign-group-call-pickup-numbers-to-users.md)  
[Deshabilitar la atención de llamadas grupales para los usuarios en Lync Server 2013](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

