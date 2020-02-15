---
title: 'Lync Server 2013: habilitar la atención de llamadas grupales para los usuarios y asignar un número de grupo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Group Call Pickup for users and assign a group number
ms:assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945650(v=OCS.15)
ms:contentKeyID: 51541517
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c541d5a82becf253ebbbb2bbab6d1c69e9fb7016
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42033779"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-group-call-pickup-for-users-in-lync-server-2013-and-assign-a-group-number"></a>Habilitar la atención de llamadas grupales para los usuarios en Lync Server 2013 y asignar un número de grupo

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-01-30_

Después de agregar los números del grupo de atención de llamadas a la tabla de órbitas de estacionamiento de llamadas, debe asignar los números de grupo a los usuarios y habilitar la recepción de llamadas de grupo para ellos. Use la herramienta de kit de recursos de activación de la característica de extensión secundaria (SEFAUtil) para asignar números de grupo y habilitar la atención de llamadas grupales.

<div>


> [!NOTE]  
> En una implementación híbrida, no asigne un grupo de recogida de llamadas de grupo a los usuarios hospedados en línea. Los usuarios hospedados en línea no pueden participar en la recogida de llamadas de grupo. Es decir, otros usuarios no pueden contestar a sus llamadas y no pueden responder llamadas a otros usuarios.



</div>

<div>

## <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a>Para asignar un número de grupo y habilitar la atención de llamadas grupales para un usuario

1.  Inicie sesión en el equipo donde instaló la herramienta SEFAUtil con derechos de administrador.

2.  En la línea de comandos, ejecute:
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    Por ejemplo, para asignar el número de grupo 199 a un usuario:
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199 

</div>

<div>

## <a name="see-also"></a>Vea también


[Deshabilitar la atención de llamadas grupales para los usuarios en Lync Server 2013](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

