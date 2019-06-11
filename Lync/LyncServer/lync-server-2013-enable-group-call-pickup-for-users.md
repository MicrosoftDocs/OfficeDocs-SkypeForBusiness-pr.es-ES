---
title: 'Lync Server 2013: habilitar la recogida de llamadas grupales para los usuarios'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable Group Call Pickup for users
ms:assetid: 20ec5f41-6ba2-4156-82ed-b91d05b62a6d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945620(v=OCS.15)
ms:contentKeyID: 51541457
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b54abf04c7c0d892e5cc58938866592f96cc1776
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835313"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-group-call-pickup-for-users-in-lync-server-2013"></a>Habilitar la recogida de llamadas grupales para los usuarios en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-01-30_

Use la herramienta del kit de recursos de SEFAUtil para habilitar la recogida de llamadas grupales para los usuarios. Los usuarios deben tener asignado un número de grupo con el tipo GroupPickup en la tabla llamada de la órbita de la llamada para tener habilitada la recopilación de llamadas de grupo. Para asignar un número de grupo de recogida de llamadas y habilitar la recogida de llamadas grupales al mismo tiempo, use el parámetro/enablegrouppickup cuando ejecute SEFAUtil. exe.

<div>

## <a name="to-enable-group-call-pickup-for-a-user"></a>Para habilitar la recogida de llamadas grupales para un usuario

1.  Inicie sesión como administrador en el equipo en el que haya instalado la herramienta SEFAUtil.

2.  En la línea de comandos, ejecute:
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    Por ejemplo:
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199

</div>

<div>

## <a name="see-also"></a>Vea también


[Asignar números de recogida de llamadas grupales a los usuarios de Lync Server 2013](lync-server-2013-assign-group-call-pickup-numbers-to-users.md)  
[Deshabilitar la recogida de llamadas grupales para los usuarios en Lync Server 2013](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

