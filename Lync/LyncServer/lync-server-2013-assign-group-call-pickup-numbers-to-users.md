---
title: 'Lync Server 2013: asignar números de llamada de llamadas de grupo a los usuarios'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign Group Call Pickup numbers to users
ms:assetid: b8e79275-8e7e-4799-b908-f34f61df22f0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945647(v=OCS.15)
ms:contentKeyID: 51541508
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ced3de74542edc65de68ab5f803934aa671575cc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499487"
---
# <a name="assign-group-call-pickup-numbers-to-users-in-lync-server-2013"></a>Asignar números de llamada de llamada de grupo a los usuarios en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-01-30_

Después de agregar los números del grupo de recogida de llamadas de grupo a la tabla de órbitas de estacionamiento de llamadas, puede asignar los grupos a los usuarios. Use la herramienta de kit de recursos de activación de característica de extensión secundaria (SEFAUtil) para asignar grupos de recogida de llamadas a los usuarios.

<div>


> [!NOTE]  
> En una implementación híbrida, no asigne un grupo de recogida de llamadas de grupo a los usuarios hospedados en línea. Los usuarios hospedados en línea no pueden participar en la recogida de llamadas de grupo. Es decir, otros usuarios no pueden contestar a sus llamadas y no pueden responder llamadas a otros usuarios.



</div>

<div>

## <a name="to-assign-a-group-call-pickup-group-to-a-user"></a>Para asignar un grupo de recogida de llamadas grupales a un usuario

1.  Inicie sesión en el equipo donde instaló la herramienta SEFAUtil con derechos de administrador.

2.  En la línea de comandos, ejecute:
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    Por ejemplo:
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199

</div>

<div>

## <a name="see-also"></a>Vea también


[Habilitar la atención de llamadas grupales para los usuarios en Lync Server 2013](lync-server-2013-enable-group-call-pickup-for-users.md)  
[Deshabilitar la atención de llamadas grupales para los usuarios en Lync Server 2013](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

