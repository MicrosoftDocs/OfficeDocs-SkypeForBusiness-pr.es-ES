---
title: 'Lync Server 2013: Habilitar usuarios para el almacenamiento de contactos unificado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable users for unified contact store
ms:assetid: 7b46a01f-beb5-4a33-adb0-35f0502b168d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205024(v=OCS.15)
ms:contentKeyID: 48184599
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3df3cbd4d71a1decc3607263f2e98b159dc29b2e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735870"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-users-for-unified-contact-store-in-lync-server-2013"></a><span data-ttu-id="01450-102">Habilitar usuarios para el almacenamiento de contactos unificado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01450-102">Enable users for unified contact store in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="01450-103">_**Última modificación del tema:** 2012-10-07_</span><span class="sxs-lookup"><span data-stu-id="01450-103">_**Topic Last Modified:** 2012-10-07_</span></span>

<span data-ttu-id="01450-104">Al implementar Lync Server 2013 y publicar la topología, el almacén de contactos unificado está habilitado para todos los usuarios de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="01450-104">When you deploy Lync Server 2013 and publish the topology, unified contact store is enabled for all users by default.</span></span> <span data-ttu-id="01450-105">No es necesario realizar ninguna acción adicional para habilitar el almacén de contactos unificado después de implementar Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="01450-105">You do not need to take any additional action to enable unified contact store after you deploy Lync Server 2013.</span></span> <span data-ttu-id="01450-106">Pero, puede usar el cmdlet **Set-CsUserServicesPolicy** para personalizar qué usuarios tienen disponible el almacén de contactos unificado.</span><span class="sxs-lookup"><span data-stu-id="01450-106">However, you can use the **Set-CsUserServicesPolicy** cmdlet to customize which users have unified contact store available.</span></span> <span data-ttu-id="01450-107">Puede habilitar esta característica globalmente, por sitio, por inquilino, por individuo o por grupos de individuos.</span><span class="sxs-lookup"><span data-stu-id="01450-107">You can enable this feature globally, by site, by tenant, or by individuals or groups of individuals.</span></span>

<div>

## <a name="to-enable-users-for-unified-contact-store"></a><span data-ttu-id="01450-108">Para habilitar usuarios para el almacén de contactos unificado</span><span class="sxs-lookup"><span data-stu-id="01450-108">To enable users for unified contact store</span></span>

1.  <span data-ttu-id="01450-109">Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="01450-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="01450-110">Siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="01450-110">Do any of the following:</span></span>
    
      - <span data-ttu-id="01450-111">Para habilitar el almacén de contactos unificado globalmente para todos los usuarios de Lync Server, en la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="01450-111">To enable unified contact store globally for all Lync Server users, at the command line, type:</span></span>
        
            Set-CsUserServicesPolicy -Identity global -UcsAllowed $True
    
      - <span data-ttu-id="01450-112">Para habilitar el almacén de contactos unificado para los usuarios de un sitio específico, en la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="01450-112">To enable unified contact store for the users at a specific site, at the command line, type:</span></span>
        
            New-CsUserServicesPolicy -Identity site:<site name> -UcsAllowed $True
        
        <span data-ttu-id="01450-113">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="01450-113">For example:</span></span>
        
            New-CsUserServicesPolicy -Identity site:Redmond -UcsAllowed $True
    
      - <span data-ttu-id="01450-114">Para habilitar el almacén de contactos unificado por inquilino, en la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="01450-114">To enable unified contact store by tenant, at the command line, type:</span></span>
        
            Set-CsUserServicesPolicy -Tenant <tenantId> -UcsAllowed $True
        
        <span data-ttu-id="01450-115">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="01450-115">For example:</span></span>
        
            Set-CsUserServicesPolicy -Tenant "38aad667-af54-4397-aaa7-e94c79ec2308" -UcsAllowed $True
    
      - <span data-ttu-id="01450-116">Para habilitar el almacén de contactos unificado para usuarios específicos, en la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="01450-116">To enable unified contact store for specific users, at the command line, type:</span></span>
        
            New-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $True
            Grant-CsUserServicesPolicy -Identity "<user display name>" -PolicyName <"policy name">
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="01450-117">También puede usar alias de usuario o URI de SIP en lugar del nombre para mostrar del usuario.</span><span class="sxs-lookup"><span data-stu-id="01450-117">You can also use user alias or SIP URI instead of the user display name.</span></span>

        
        </div>
        
        <span data-ttu-id="01450-118">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="01450-118">For example:</span></span>
        
            New-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $True
            Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "UCS Enabled Users"
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="01450-p102">En el ejemplo anterior, el primer comando crea una directiva por usuario denominada <EM>Usuarios habilitados para UCS</EM> con el indicador UcsAllowed establecido en True. El segundo comando asigna la directiva al usuario con el nombre para mostrar Ken Myer, lo que significa que Ken Myer ahora está habilitado para el almacén de contactos unificado.</span><span class="sxs-lookup"><span data-stu-id="01450-p102">In the preceding example, the first command creates a new per-user policy named <EM>UCS Enabled Users</EM> with the UcsAllowed flag set to True. The second command assigns the policy to the user with the display name Ken Myer, which means that Ken Myer is now enabled for unified contact store.</span></span>

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

