---
title: 'Lync Server 2013: habilitar la recogida de llamadas grupales para los usuarios y asignar un número de grupo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable Group Call Pickup for users and assign a group number
ms:assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945650(v=OCS.15)
ms:contentKeyID: 51541517
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b9523a76eb9cd23dd4c8ee531520341aaf82f508
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835316"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-group-call-pickup-for-users-in-lync-server-2013-and-assign-a-group-number"></a>Habilitar la recogida de llamadas grupales para los usuarios en Lync Server 2013 y asignar un número de grupo

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-01-30_

Después de agregar los números del grupo de recogida de llamadas a la tabla de llamadas en órbita, asigne los números de grupo a los usuarios y habilite la recogida de llamadas grupales. Use la herramienta del kit de recursos de activación de características de extensión secundaria (SEFAUtil) para asignar números de grupo y habilitar la recogida de llamadas grupales.

<div>


> [!NOTE]  
> En una implementación híbrida, no asigne un grupo de recogida de llamadas grupal a los usuarios alojados en línea. Los usuarios alojados en Internet no pueden participar en la recogida de llamadas grupales. Es decir, otros usuarios no pueden contestar las llamadas y no pueden responder llamadas a otros usuarios.



</div>

<div>

## <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a>Para asignar un número de grupo y habilitar la recogida de llamadas grupales para un usuario

1.  Inicie sesión como administrador en el equipo en el que haya instalado la herramienta SEFAUtil.

2.  En la línea de comandos, ejecute:
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    Por ejemplo, para asignar el número de grupo 199 a un usuario:
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199 

</div>

<div>

## <a name="see-also"></a>Vea también


[Deshabilitar la recogida de llamadas grupales para los usuarios en Lync Server 2013](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

