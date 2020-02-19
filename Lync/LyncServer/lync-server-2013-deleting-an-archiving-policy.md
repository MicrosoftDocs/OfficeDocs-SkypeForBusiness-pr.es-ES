---
title: 'Lync Server 2013: eliminación de una directiva de archivado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting an Archiving policy
ms:assetid: 4739a691-41cc-4128-8bb8-6d5a4c02107a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520989(v=OCS.15)
ms:contentKeyID: 48184043
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b2cac48287063e61be00495077f51042b1810f65
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137559"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deleting-an-archiving-policy-in-lync-server-2013"></a><span data-ttu-id="f8b71-102">Eliminación de una directiva de archivado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f8b71-102">Deleting an Archiving policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f8b71-103">_**Última modificación del tema:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="f8b71-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="f8b71-104">Es posible eliminar directivas de usuario o de sitio.</span><span class="sxs-lookup"><span data-stu-id="f8b71-104">You can delete a user policy or site policy.</span></span> <span data-ttu-id="f8b71-105">Las directivas globales no se pueden quitar.</span><span class="sxs-lookup"><span data-stu-id="f8b71-105">The global policy cannot be removed.</span></span> <span data-ttu-id="f8b71-106">Si intenta eliminar la directiva global, Lync Server 2013 restablece automáticamente la Directiva a los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="f8b71-106">If you try to delete the global policy, Lync Server 2013 automatically resets the policy to the default values.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f8b71-107">Si habilitó la integración de Microsoft Exchange para su implementación, las directivas de Exchange controlan si el archivado está habilitado para los usuarios que están hospedados en Exchange 2013 y cuyos buzones se colocan en conservación local.</span><span class="sxs-lookup"><span data-stu-id="f8b71-107">If you enabled Microsoft Exchange integration for your deployment, Exchange policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="f8b71-108">Para obtener más información, consulte <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">configuración de directivas para archivar en Lync Server 2013 al usar la integración de Exchange Server</A> en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="f8b71-108">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-delete-a-user-or-site-policy-for-archiving"></a><span data-ttu-id="f8b71-109">Para eliminar una directiva de usuario o de sitio para archivado</span><span class="sxs-lookup"><span data-stu-id="f8b71-109">To delete a user or site policy for archiving</span></span>

1.  <span data-ttu-id="f8b71-110">Desde una cuenta de usuario asignada al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="f8b71-110">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f8b71-111">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f8b71-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f8b71-112">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f8b71-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f8b71-113">En la barra de navegación izquierda, haga clic en **Configuración y archivado** y, a continuación, en **Directiva de archivado**.</span><span class="sxs-lookup"><span data-stu-id="f8b71-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>

4.  <span data-ttu-id="f8b71-114">En la lista de directivas, haga clic en la directiva de usuario o sitio que desea eliminar, haga clic en **Editar** y, a continuación, en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="f8b71-114">In the list of archiving policies, click the user or site policy that you want to delete, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="f8b71-115">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="f8b71-115">Click **Commit**.</span></span>

</div>

<div>

## <a name="removing-archiving-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="f8b71-116">Eliminación de directivas de archivado con los cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f8b71-116">Removing Archiving Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="f8b71-117">Las directivas de archivado se pueden eliminar con Windows PowerShell y el cmdlet **Remove-CsArchivingPolicy** .</span><span class="sxs-lookup"><span data-stu-id="f8b71-117">Archiving policies can be deleted by using Windows PowerShell and the **Remove-CsArchivingPolicy** cmdlet.</span></span> <span data-ttu-id="f8b71-118">Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f8b71-118">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="f8b71-119">Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.</span><span class="sxs-lookup"><span data-stu-id="f8b71-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-archiving-policy"></a><span data-ttu-id="f8b71-120">Para quitar una directiva de archivado especificada</span><span class="sxs-lookup"><span data-stu-id="f8b71-120">To remove a specified archiving policy</span></span>

  - <span data-ttu-id="f8b71-p105">Como ejemplo, **Remove-CsArchivingPolicy** elimina la directiva con el sitio de identidad: Redmond. Tenga en cuenta que, cuando se elimina una directiva configurada en el ámbito de aplicación de sitio, los usuarios anteriormente administrados por la directiva del sitio, en su lugar, se regirán automáticamente por la directiva global de archivado. El comando siguiente quita el archivado aplicado en el sitio Redmond:</span><span class="sxs-lookup"><span data-stu-id="f8b71-p105">As an example, **Remove-CsArchivingPolicy** deletes the policy with the Identity site:Redmond. Note that, when a policy configured at the site scope is deleted, users previously managed by the site policy will automatically be governed by the global archiving policy instead. The following command removes the archiving applied to the Redmond site:</span></span>
    
        Remove-CsArchivingPolicy -Identity site:Redmond

</div>

<div>

## <a name="to-remove-all-the-archiving-policies-applied-to-the-per-user-scope"></a><span data-ttu-id="f8b71-124">Para quitar todas las directivas de archivado aplicadas al ámbito por usuario</span><span class="sxs-lookup"><span data-stu-id="f8b71-124">To remove all the archiving policies applied to the per-user scope</span></span>

  - <span data-ttu-id="f8b71-125">Este comando quita todas las directivas de archivado aplicadas al ámbito por usuario:</span><span class="sxs-lookup"><span data-stu-id="f8b71-125">This command removes all the archiving policies applied to the per-user scope:</span></span>
    
        Get-CsArchivingPolicy -Filter "tag:*" | Remove-CsArchivingPolicy

</div>

<div>

## <a name="to-remove-all-the-archiving-policies-that-disable-internal-archiving"></a><span data-ttu-id="f8b71-126">Para quitar todas las directivas de archivado que deshabilitan el archivado interno</span><span class="sxs-lookup"><span data-stu-id="f8b71-126">To remove all the archiving policies that disable internal archiving</span></span>

  - <span data-ttu-id="f8b71-127">Este comando quita todas las directivas de archivado donde se deshabilitó el archivado interno:</span><span class="sxs-lookup"><span data-stu-id="f8b71-127">This command removes all the archiving policies where internal archiving has been disabled:</span></span>
    
        Get-CsArchivingPolicy | Where-Object {$_.ArchiveInternal -eq $False} | Remove-CsArchivingPolicy

</div>

<span data-ttu-id="f8b71-128">Para obtener más información, consulte el tema de ayuda del cmdlet [Remove-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsArchivingPolicy) .</span><span class="sxs-lookup"><span data-stu-id="f8b71-128">For more information, see the help topic for the [Remove-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsArchivingPolicy) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f8b71-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="f8b71-129">See Also</span></span>


[<span data-ttu-id="f8b71-130">Administración del archivado de comunicaciones internas y externas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f8b71-130">Managing the Archiving of internal and external communications in Lync Server 2013</span></span>](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

