---
title: 'Lync Server 2013: administración de usuarios en una implementación híbrida'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Administering users in a hybrid deployment
ms:assetid: 6924ed7b-30a9-4be7-b952-90655625f2c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204967(v=OCS.15)
ms:contentKeyID: 48184381
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c6cfa255eddc998047f5b404d59b7e6622fbaae
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204379"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="administering-users-in-a-hybrid-lync-server-2013-deployment"></a>Administración de usuarios en una implementación híbrida de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-05-29_

Puede administrar la configuración y las directivas de usuario para los usuarios migrados a Lync Online mediante las características de administración de usuarios disponibles en el portal de Microsoft Office 365 online. Debe iniciar sesión con la cuenta de administrador de inquilinos para realizar tareas de administración.

<div>

## <a name="moving-users-back-to-on-premises"></a>Mover a usuarios localmente

<div class="">


> [!IMPORTANT]  
> Esta sección solo se aplica a los usuarios que se crearon y habilitaron para Lync local y, a continuación, se movieron de una implementación local a Lync Online. Si quiere mover usuarios que se crearon en Lync Online (y que nunca se habilitaron para Lync en una implementación local), vea <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">mover usuarios de Lync Online a Lync local en Lync Server 2013</A>.



</div>

  - Ejecute los siguientes cmdlets para mover un usuario de Lync Online de nuevo a Lync local:
    
       ```PowerShell
        $cred=Get-Credential
       ```
    
       ```PowerShell
        Move-CsUser -Identity username@contoso.com -Target localpool.contoso.com -Credential $cred -HostedMigrationOverrideUrl <URL>
       ```

El formato de la dirección URL especificada para el parámetro **HostedMigrationOverrideUrl** debe ser la dirección URL del grupo en el que se está ejecutando el servicio de migración hospedado, en el siguiente formato:

Https://\<FQDN\>del grupo de servidores de/HostedMigration/hostedmigrationService.SVC. Para determinar la dirección URL del servicio de migración hospedado, vea la dirección URL del panel de control de Lync Online para su cuenta de inquilino de Office 365.

**Para determinar la dirección URL del servicio de migración hospedado de su inquilino de Office 365**

1.  Inicie sesión en su inquilino de Office 365 como administrador.

2.  Abra el **centro de administración de Lync**.

3.  Con el **centro de administración de Lync** mostrado, seleccione y copie la dirección URL en la barra de direcciones hasta **Lync.com**. Una dirección URL de ejemplo tiene un aspecto similar al siguiente:
    
    `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`

4.  Reemplace **webdir** en la dirección URL con **admin**, lo que dará como resultado lo siguiente:
    
    `https://admin0a.online.lync.com`

5.  Anexe la cadena siguiente a la dirección URL: **/HostedMigration/hostedmigrationservice.SVC**.
    
    La dirección URL resultante, que es el valor de **HostedMigrationOverrideUrl**, debe ser similar a la siguiente:
    
    `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`

</div>

</div>

<span> </span>

</div>

</div>

</div>

