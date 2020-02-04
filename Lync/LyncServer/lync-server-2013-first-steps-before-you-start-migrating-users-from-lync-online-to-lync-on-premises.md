---
title: 'Lync Server 2013: primeros pasos antes de empezar a migrar usuarios de Lync Online a Lync local'
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
ms.openlocfilehash: 59ca20a994934a199504a4fb6a7dd5eec206c960
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742500"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="first-steps-before-you-start-migrating-users-from-lync-online-to-lync-on-premises-in-lync-server-2013"></a><span data-ttu-id="0c343-102">Primeros pasos antes de empezar a migrar usuarios de Lync Online a Lync local en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0c343-102">First steps before you start migrating users from Lync Online to Lync on-premises in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0c343-103">_**Última modificación del tema:** 2014-05-08_</span><span class="sxs-lookup"><span data-stu-id="0c343-103">_**Topic Last Modified:** 2014-05-08_</span></span>

<span data-ttu-id="0c343-104">Antes de empezar a mover usuarios de Lync Online a su entorno local, compruebe que se cumplen todas las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="0c343-104">Before you start moving Lync Online users to your on-premises environment, check that all of the following are true:</span></span>

  - <span data-ttu-id="0c343-105">El entorno local de Lync Server debe implementarse y validarse por completo.</span><span class="sxs-lookup"><span data-stu-id="0c343-105">Your Lync Server on-premises environment must be fully deployed and validated.</span></span> <span data-ttu-id="0c343-106">Para obtener más información, consulte [implementar Lync Server 2013](lync-server-2013-deploying-lync-server.md).</span><span class="sxs-lookup"><span data-stu-id="0c343-106">For more information, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md).</span></span>

  - <span data-ttu-id="0c343-107">El inquilino de Lync Online debe estar configurado para el acceso remoto de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0c343-107">Your Lync Online tenant must be configured for remote PowerShell Access.</span></span>
    
    <span data-ttu-id="0c343-108">Para ello, primero Instale el módulo Lync Online para Windows PowerShell, que puede obtener aquí: [http://go.microsoft.com/fwlink/p/?LinkId=391911](http://go.microsoft.com/fwlink/p/?linkid=391911).</span><span class="sxs-lookup"><span data-stu-id="0c343-108">To do this, first install the Lync Online module for Windows PowerShell, which you can get here: [http://go.microsoft.com/fwlink/p/?LinkId=391911](http://go.microsoft.com/fwlink/p/?linkid=391911).</span></span>
    
    <span data-ttu-id="0c343-109">Después de instalar el módulo, puede establecer una sesión remota escribiendo los cmdlets siguientes en el shell de administración de Lync Server:</span><span class="sxs-lookup"><span data-stu-id="0c343-109">After you install the module, you can establish a remote session by typing the following cmdlets in the Lync Server Management Shell:</span></span>
    
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
    
    <span data-ttu-id="0c343-110">Para obtener más información sobre cómo establecer una sesión PowerShell remota con Lync Online, consulte [conectarse a Lync Online mediante Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="0c343-110">For more information about how to establish a remote PowerShell session with Lync Online, see [Connecting to Lync Online by using Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
  
    <span data-ttu-id="0c343-111">Para obtener más información sobre el uso del módulo de PowerShell Lync Online, vea [usar Windows PowerShell para administrar Lync Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="0c343-111">For more information about using the Lync Online PowerShell module, see [Using Windows PowerShell to manage Lync Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

  - <span data-ttu-id="0c343-112">Su Lync Online debe estar configurado para el espacio de direcciones SIP compartido.</span><span class="sxs-lookup"><span data-stu-id="0c343-112">Your Lync Online must be configured for Shared SIP Address Space.</span></span> <span data-ttu-id="0c343-113">Para ello, inicie en primer lugar una sesión remota de PowerShell con Lync Online.</span><span class="sxs-lookup"><span data-stu-id="0c343-113">To do this, first start a remote Powershell session with Lync Online.</span></span> <span data-ttu-id="0c343-114">Luego, ejecute el cmdlet siguiente:</span><span class="sxs-lookup"><span data-stu-id="0c343-114">Then run the following cmdlet:</span></span>
    
        Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True

<span data-ttu-id="0c343-115">Una vez que haya terminado estos pasos, puede pasar a [migrar usuarios de Lync Online a Lync local en Lync Server 2013](lync-server-2013-migrating-lync-online-users-to-lync-on-premises.md).</span><span class="sxs-lookup"><span data-stu-id="0c343-115">After you’ve finished these steps, you can move on to [Migrating Lync Online users to Lync on-premises in Lync Server 2013](lync-server-2013-migrating-lync-online-users-to-lync-on-premises.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

