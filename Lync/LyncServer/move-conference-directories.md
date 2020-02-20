---
title: Mover directorios de conferencia
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Move conference directories
ms:assetid: 71a28308-1f3b-4717-b535-2f4bfe3499a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204994(v=OCS.15)
ms:contentKeyID: 48184463
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eae2d3b588cafb09fd2eaea821b998b546fd0211
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148669"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-conference-directories"></a>Mover directorios de conferencia

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-04_

Antes de retirar un grupo de servidores, debe realizar el siguiente procedimiento para cada directorio de conferencia del grupo de servidores de Office Communications Server 2007 R2.

<div>

## <a name="to-move-a-conference-directory-to-lync-server-2013"></a>Para mover un directorio de conferencia a Lync Server 2013

1.  Abra el Shell de administración de Lync Server.

2.  Para obtener la identidad de los directorios de conferencia de su organización, ejecute los comandos siguientes:
    
        Get-CsConferenceDirectory
    
    Debido a que este cmdlet devuelve todos los directorios de conferencia de su organización, es posible que desee limitar los resultados solo a los grupos que desea retirar. Por ejemplo, si desea retirar un grupo con el nombre de dominio completo (FQDN) pool01.contoso.net:
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
    
    Este cmdlet devuelve todos los directorios de conferencia en los que el Id. de servicio contiene el FQDN pool01.contoso.net.

3.  Para mover directorios de conferencia, ejecute lo siguiente para cada directorio de conferencia del grupo:
    
        Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
    
    Por ejemplo:
    
        Move-CsConferenceDirectory -Identity 3 -TargetPool pool02.contoso.net

<div>


> [!NOTE]  
> Puede experimentar un error, que se muestra a continuación, debido a que el shell de administración de Lync Server requiere un conjunto actualizado de permisos de Active Directory. Para solucionar el error, cierre la ventana actual y abra un nuevo shell de administración de Lync Server y ejecute el comando de nuevo.



</div>

![Salida de error de Move-CsConferenceDirectory](images/JJ204994.4748b9e8-9651-4527-afe1-cbdc6d5ce4a8(OCS.15).jpg "Salida de error de Move-CsConferenceDirectory")

</div>

</div>

<span> </span>

</div>

</div>

</div>

