---
title: 'Lync Server 2013: deshabilitar la recogida de llamadas grupales para usuarios'
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
ms.openlocfilehash: f7e47b5c3b12997bd05f3721555a5dfdfe692bbc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762208"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disable-group-call-pickup-for-users-in-lync-server-2013"></a>Deshabilitar la recogida de llamadas grupales para los usuarios en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-01-30_

Use el siguiente procedimiento para deshabilitar la recogida de llamadas grupales para un usuario.

<div>


> [!NOTE]  
> Al deshabilitar la recogida de llamadas grupales para un usuario, el número del grupo de recogida de llamadas que se asignó al usuario no se conserva. Si posteriormente deseas volver a habilitar la recogida de llamadas grupales para ese usuario, debes asignar el número del grupo de recogida de llamadas de nuevo con el parámetro/enablegrouppickup.



</div>

<div>

## <a name="to-disable-group-call-pickup-for-a-user"></a>Para deshabilitar la recogida de llamadas grupales para un usuario

1.  Inicie sesión como administrador en el equipo en el que haya instalado la herramienta SEFAUtil.

2.  En la línea de comandos, ejecute:
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /disablegrouppickup
    
    Por ejemplo:
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /disablegrouppickup

</div>

<div>

## <a name="see-also"></a>Vea también


[Asignar números de recogida de llamadas grupales a los usuarios de Lync Server 2013](lync-server-2013-assign-group-call-pickup-numbers-to-users.md)  
[Habilitar la recogida de llamadas grupales para los usuarios en Lync Server 2013](lync-server-2013-enable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

