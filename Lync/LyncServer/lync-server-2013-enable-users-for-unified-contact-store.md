---
title: 'Lync Server 2013: habilitar usuarios para el almacenamiento de contactos unificado'
description: 'Lync Server 2013: habilite a los usuarios para el almacén de contactos unificados.'
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
ms.openlocfilehash: 2249249d314e13d840b276e46f1fe38ad271664a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572736"
---
# <a name="enable-users-for-unified-contact-store-in-lync-server-2013"></a><span data-ttu-id="288a8-103">Habilitar a los usuarios para el almacén de contactos unificados en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="288a8-103">Enable users for unified contact store in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="288a8-104">_**Última modificación del tema:** 2012-10-07_</span><span class="sxs-lookup"><span data-stu-id="288a8-104">_**Topic Last Modified:** 2012-10-07_</span></span>

<span data-ttu-id="288a8-105">Al implementar Lync Server 2013 y publicar la topología, el almacén de contactos unificado está habilitado para todos los usuarios de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="288a8-105">When you deploy Lync Server 2013 and publish the topology, unified contact store is enabled for all users by default.</span></span> <span data-ttu-id="288a8-106">No es necesario realizar ninguna acción adicional para habilitar el almacén de contactos unificado después de implementar Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="288a8-106">You do not need to take any additional action to enable unified contact store after you deploy Lync Server 2013.</span></span> <span data-ttu-id="288a8-107">Sin embargo, puede usar el cmdlet **Set-CsUserServicesPolicy** para personalizar qué usuarios tienen disponible el almacén de contactos unificados.</span><span class="sxs-lookup"><span data-stu-id="288a8-107">However, you can use the **Set-CsUserServicesPolicy** cmdlet to customize which users have unified contact store available.</span></span> <span data-ttu-id="288a8-108">Puede habilitar esta característica globalmente, por sitio, por inquilino o por individuos o grupos de individuos.</span><span class="sxs-lookup"><span data-stu-id="288a8-108">You can enable this feature globally, by site, by tenant, or by individuals or groups of individuals.</span></span>

<div>

## <a name="to-enable-users-for-unified-contact-store"></a><span data-ttu-id="288a8-109">Procedimiento para habilitar usuarios para el almacén de contactos unificados</span><span class="sxs-lookup"><span data-stu-id="288a8-109">To enable users for unified contact store</span></span>

1.  <span data-ttu-id="288a8-110">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="288a8-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="288a8-111">Siga uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="288a8-111">Do any of the following:</span></span>
    
      - <span data-ttu-id="288a8-112">Para habilitar el almacén de contactos Unificado de forma global para todos los usuarios de Lync Server, en la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="288a8-112">To enable unified contact store globally for all Lync Server users, at the command line, type:</span></span>
        
            Set-CsUserServicesPolicy -Identity global -UcsAllowed $True
    
      - <span data-ttu-id="288a8-113">Para habilitar el almacén de contactos unificados para los usuarios de un sitio específico, en la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="288a8-113">To enable unified contact store for the users at a specific site, at the command line, type:</span></span>
        
            New-CsUserServicesPolicy -Identity site:<site name> -UcsAllowed $True
        
        <span data-ttu-id="288a8-114">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="288a8-114">For example:</span></span>
        
            New-CsUserServicesPolicy -Identity site:Redmond -UcsAllowed $True
    
      - <span data-ttu-id="288a8-115">Para habilitar el almacén de contactos unificados por arrendatario, en la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="288a8-115">To enable unified contact store by tenant, at the command line, type:</span></span>
        
            Set-CsUserServicesPolicy -Tenant <tenantId> -UcsAllowed $True
        
        <span data-ttu-id="288a8-116">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="288a8-116">For example:</span></span>
        
            Set-CsUserServicesPolicy -Tenant "38aad667-af54-4397-aaa7-e94c79ec2308" -UcsAllowed $True
    
      - <span data-ttu-id="288a8-117">Para habilitar el almacén de contactos unificados para los usuarios especificados, en la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="288a8-117">To enable unified contact store for specific users, at the command line, type:</span></span>
        
            New-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $True
            Grant-CsUserServicesPolicy -Identity "<user display name>" -PolicyName <"policy name">
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="288a8-118">También puede usar alias de usuario o URI de SIP en lugar del nombre para mostrar del usuario.</span><span class="sxs-lookup"><span data-stu-id="288a8-118">You can also use user alias or SIP URI instead of the user display name.</span></span>

        
        </div>
        
        <span data-ttu-id="288a8-119">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="288a8-119">For example:</span></span>
        
            New-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $True
            Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "UCS Enabled Users"
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="288a8-p102">En el ejemplo anterior, el primer comando crea una nueva directiva por usuario denominada <EM>Usuarios habilitados para UC</EM> con el indicador UcsAllowed establecido en Verdadero. El segundo comando asigna la directiva al usuario con el nombre para mostrar Ken Myer, lo cual significa que Ken Myer ahora está habilitado para el almacén de contactos unificados.</span><span class="sxs-lookup"><span data-stu-id="288a8-p102">In the preceding example, the first command creates a new per-user policy named <EM>UCS Enabled Users</EM> with the UcsAllowed flag set to True. The second command assigns the policy to the user with the display name Ken Myer, which means that Ken Myer is now enabled for unified contact store.</span></span>

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

