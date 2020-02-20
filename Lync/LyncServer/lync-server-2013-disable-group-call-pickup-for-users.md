---
title: 'Lync Server 2013: deshabilitar la atención de llamadas grupales para los usuarios'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disable Group Call Pickup for users
ms:assetid: 91b06f9e-2840-45a2-bbb3-6a29179b9a9f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945638(v=OCS.15)
ms:contentKeyID: 51541492
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e3e015fd7fc3be36439fb240e2f3f50ed7bc8ec1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147513"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="disable-group-call-pickup-for-users-in-lync-server-2013"></a>Deshabilitar la atención de llamadas grupales para los usuarios en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-01-30_

Use el siguiente procedimiento para deshabilitar la atención de llamadas grupales para un usuario.

<div>


> [!NOTE]  
> Cuando se deshabilita la recepción de llamadas de grupo para un usuario, no se conserva el número del grupo de atención de llamadas que se asignó al usuario. Si, posteriormente, desea volver a habilitar la atención de llamadas grupales para ese usuario, debe asignar el número de grupo de recogida de llamadas de nuevo con el parámetro/enablegrouppickup.



</div>

<div>

## <a name="to-disable-group-call-pickup-for-a-user"></a>Para deshabilitar la recepción de llamadas de grupo para un usuario

1.  Inicie sesión en el equipo donde instaló la herramienta SEFAUtil con derechos de administrador.

2.  En la línea de comandos, ejecute:
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /disablegrouppickup
    
    Por ejemplo:
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /disablegrouppickup

</div>

<div>

## <a name="see-also"></a>Vea también


[Asignar números de llamada de llamada de grupo a los usuarios en Lync Server 2013](lync-server-2013-assign-group-call-pickup-numbers-to-users.md)  
[Habilitar la atención de llamadas grupales para los usuarios en Lync Server 2013](lync-server-2013-enable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

