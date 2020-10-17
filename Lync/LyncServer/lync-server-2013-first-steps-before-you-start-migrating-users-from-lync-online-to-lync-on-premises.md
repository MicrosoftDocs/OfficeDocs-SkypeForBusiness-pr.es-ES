---
title: 'Lync Server 2013: primeros pasos antes de empezar a migrar usuarios de Lync Online a Lync local'
description: 'Lync Server 2013: primeros pasos antes de empezar a migrar usuarios de Lync Online a Lync local.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: First steps before you start migrating users from Lync Online to Lync on-premises
ms:assetid: 98245b04-ded4-4186-8da3-ba1c554b5c39
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689118(v=OCS.15)
ms:contentKeyID: 62258123
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 408820e461c0a9f7c0beaaaae3a502802048d3f5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564206"
---
# <a name="first-steps-before-you-start-migrating-users-from-lync-online-to-lync-on-premises-in-lync-server-2013"></a>Primeros pasos antes de empezar a migrar usuarios de Lync Online a Lync local en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-05-08_

Antes de empezar a mover usuarios de Lync Online a su entorno local, compruebe que se cumplen todas las condiciones siguientes:

  - El entorno local de Lync Server debe implementarse y validarse por completo. Para obtener más información, consulte [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md).

  - El inquilino de Lync Online debe estar configurado para el acceso remoto a PowerShell.
    
    Para ello, primero Instale el módulo Lync Online para Windows PowerShell, que puede obtener aquí: [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?linkid=391911) .
    
    Después de instalar el módulo, puede establecer una sesión remota si escribe los siguientes cmdlets en el shell de administración de Lync Server:
    
       ```PowerShell
        Import-Module LyncOnlineConnector
       ```  
    
       ```PowerShell
        $cred = Get-Credential
       ``` 
    
       ```PowerShell
        $CSSession = New-CsOnlineSession -Credential $cred
       ```
    
       ```PowerShell
        Import-PSSession $CSSession -AllowClobber
       ```
    
    Para obtener más información sobre cómo establecer una sesión de PowerShell remota con Lync Online, consulte [conectarse a Lync Online mediante Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).
  
    Para obtener más información sobre el uso del módulo Lync Online PowerShell, vea [using Windows PowerShell to Manage Lync Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).

  - Su Lync Online debe estar configurado para el espacio de direcciones SIP compartido. Para ello, inicie primero una sesión remota de PowerShell con Lync Online. A continuación, ejecute el siguiente cmdlet:
    
        Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True

Una vez que haya terminado estos pasos, puede pasar a [migrar a los usuarios de Lync Online a Lync local en Lync Server 2013](lync-server-2013-migrating-lync-online-users-to-lync-on-premises.md).

</div>

<span> </span>

</div>

</div>

</div>

