---
title: 'Lync Server 2013: administración de usuarios en una implementación híbrida'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Administering users in a hybrid deployment
ms:assetid: 6924ed7b-30a9-4be7-b952-90655625f2c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204967(v=OCS.15)
ms:contentKeyID: 48184381
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7804aacb226d06fbf239939658b6592d438a84f9
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "40971131"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="administering-users-in-a-hybrid-lync-server-2013-deployment"></a>Administración de usuarios en una implementación híbrida de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-05-29_

Puede administrar la configuración y las directivas de usuario para los usuarios migrados a Lync Online mediante las características de administración de usuarios disponibles en el portal en línea de Microsoft Office 365. Necesita iniciar sesión con una cuenta de administrador de inquilinos para realizar tareas administrativas.

<div>

## <a name="moving-users-back-to-on-premises"></a>Mover usuarios a local

<div class="">


> [!IMPORTANT]  
> Esta sección solo se aplica a los usuarios que se han creado y habilitado para Lync local y después se han movido de una implementación local a Lync Online. Si quiere mover los usuarios que se crearon en Lync Online (y nunca se habilitaron para Lync en una implementación local), vea <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">mover usuarios de Lync Online a Lync local en Lync Server 2013</A>.



</div>

  - Ejecute los siguientes cmdlets para mover un usuario de Lync Online de nuevo a Lync local:
    
       ```PowerShell
        $cred=Get-Credential
       ```
    
       ```PowerShell
        Move-CsUser -Identity username@contoso.com -Target localpool.contoso.com -Credential $cred -HostedMigrationOverrideUrl <URL>
       ```

El formato de la dirección URL especificada para el parámetro **HostedMigrationOverrideUrl** necesita ser la dirección URL al grupo donde se ejecuta el servicio de migración hospedado, con el siguiente formato:

Https://\<FQDN\>del grupo de/HostedMigration/hostedmigrationService.SVC. Para determinar la dirección URL al servicio de migración hospedado, vea la dirección URL del Panel de control de Lync Online para la cuenta del inquilino de Office 365.

**Para determinar la dirección URL al servicio de migración de hospedado de su inquilino Office 365**

1.  Inicie sesión en el inquilino de Office 365 como administrador.

2.  Abra el **centro de administración de Lync**.

3.  Con el **centro de administración de Lync** mostrado, seleccione y copie la dirección URL en la barra de direcciones hasta **Lync.com**. Una dirección URL de ejemplo es muy similar a la siguiente:
    
    `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`

4.  Sustituya **webdir** en la dirección URL por **admin**. Quedará como a continuación:
    
    `https://admin0a.online.lync.com`

5.  Anexe la cadena siguiente a la URL: **/MigraciónHospedada/ServicioDeMigraciónHospedada.svc**.
    
    La dirección URL resultante, que es el valor de **HostedMigrationOverrideUrl**, necesita ser como la siguiente:
    
    `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`

</div>

</div>

<span> </span>

</div>

</div>

</div>

