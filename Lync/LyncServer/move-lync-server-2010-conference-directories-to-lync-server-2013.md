---
title: Mover los directorios de conferencia de Lync Server 2010 a Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move Conference Directories
ms:assetid: 659867e0-ce91-4a95-9787-b1c1566460a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727126(v=OCS.15)
ms:contentKeyID: 62387565
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6712e22ffcdc2eaea9ae39be961bb50316beed5b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034570"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-conference-directories"></a>Mover directorios de conferencia

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-05-28_

Antes de retirar un grupo de servidores, debe realizar el siguiente procedimiento para cada directorio de conferencia del grupo de servidores de Lync Server 2010.

<div>

## <a name="to-move-a-conference-directory-to-lync-server-2013"></a>Para mover un directorio de conferencia a Lync Server 2013

1.  Abra el Shell de administración de Lync Server.

2.  Para obtener la identidad de los directorios de conferencia de su organización, ejecute el siguiente comando:
    
        Get-CsConferenceDirectory
    
    El comando anterior devuelve todos los directorios de conferencia de la organización. Por ello, es posible que desee limitar los resultados al grupo de servidores que se está retirando. Por ejemplo, si va a retirar el grupo de servidores con el nombre de dominio completo (FQDN) pool01.contoso.net, use este comando para limitar los datos devueltos a los directorios de conferencia de ese grupo:
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
    
    Este comando devuelve sólo los directorios de conferencia en los que la propiedad ServiceID contiene el FQDN pool01.contoso.net.

3.  Para mover los directorios de conferencia, ejecute el siguiente comando para cada directorio de conferencia del Grupo:
    
        Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
    
    Por ejemplo, para mover el directorio de conferencia 3 Use este comando, especificando un grupo de servidores de Lync Server 2013 como TargetPool:
    
        Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
    
    Si desea mover todos los directorios de conferencia de un grupo de servidores, use un comando similar al siguiente:
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"

Consulte el documento "desinstalar Microsoft Lync Server 2010 y quitar roles de servidor" (del [http://go.microsoft.com/fwlink/p/?linkId=246227](http://go.microsoft.com/fwlink/p/?linkid=246227)que se puede descargar) para obtener instrucciones detalladas paso a paso sobre cómo retirar los grupos de Lync 2010.

Al mover los directorios de conferencia, es posible que se produzca el siguiente error:

    WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
    WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
    Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
    This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.

Este error suele producirse cuando el shell de administración de Lync Server requiere un conjunto actualizado de permisos de Active Directory para poder completar una tarea. Para solucionar el problema, cierre la instancia actual del shell de administración, abra una nueva instancia del shell y vuelva a ejecutar el comando para mover el directorio de conferencia.

</div>

</div>

<span> </span>

</div>

</div>

</div>

