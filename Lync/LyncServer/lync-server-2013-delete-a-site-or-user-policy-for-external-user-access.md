---
title: 'Lync Server 2013: Eliminar un sitio o una directiva de usuario para el acceso de usuarios externos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a site or user policy for external user access
ms:assetid: 6d907507-825b-4354-9c03-337a459f72de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521013(v=OCS.15)
ms:contentKeyID: 48184455
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b928fcb1347fdbc89099a5b0dc649deefffa19e6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742550"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-site-or-user-policy-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="49d93-102">Eliminar un sitio o una directiva de usuario para el acceso de usuarios externos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="49d93-102">Delete a site or user policy for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="49d93-103">_**Última modificación del tema:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="49d93-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="49d93-104">Puede eliminar cualquier sitio o Directiva de usuario que aparezca en el panel de control de Lync Server en la página **Directiva de acceso externo** .</span><span class="sxs-lookup"><span data-stu-id="49d93-104">You can delete any site or user policy that is listed in Lync Server Control Panel on the **External Access Policy** page.</span></span> <span data-ttu-id="49d93-105">Eliminar la directiva global no la elimina realmente, pero solo la restablece a la configuración predeterminada, que no incluye compatibilidad con ninguna de las opciones de acceso de usuarios externos.</span><span class="sxs-lookup"><span data-stu-id="49d93-105">Deleting the global policy does not actually delete it, but only resets it to the default settings, which do not include support for any external user access options.</span></span> <span data-ttu-id="49d93-106">Para obtener más información sobre cómo restablecer la directiva global, vea [restablecer la directiva global para el acceso de usuarios externos en Lync Server 2013](lync-server-2013-reset-the-global-policy-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="49d93-106">For details about resetting the global policy, see [Reset the global policy for external user access in Lync Server 2013](lync-server-2013-reset-the-global-policy-for-external-user-access.md).</span></span>

<div>

## <a name="to-delete-a-site-or-user-policy-for-external-user-access"></a><span data-ttu-id="49d93-107">Para eliminar un sitio o una directiva de usuario para el acceso de usuarios externos</span><span class="sxs-lookup"><span data-stu-id="49d93-107">To delete a site or user policy for external user access</span></span>

1.  <span data-ttu-id="49d93-108">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="49d93-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="49d93-109">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="49d93-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="49d93-110">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="49d93-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="49d93-111">Haga clic en **acceso externo de usuarios**, haga clic en **Directiva de acceso externo**.</span><span class="sxs-lookup"><span data-stu-id="49d93-111">Click **External User Access**, click **External Access Policy**.</span></span>

4.  <span data-ttu-id="49d93-112">En la pestaña **Directiva de acceso externo** , haga clic en el sitio o la Directiva de usuario que desea eliminar, haga clic en **Editar**y, a continuación, haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="49d93-112">On the **External Access Policy** tab, click the site or user policy you want to delete, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="49d93-113">Cuando se le pida que confirme la eliminación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="49d93-113">When prompted to confirm the deletion, click **OK**.</span></span>

</div>

<div>

## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="49d93-114">Quitar directivas de PIN mediante cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="49d93-114">Removing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="49d93-115">Las directivas de acceso externo se pueden eliminar mediante Windows PowerShell y el cmdlet Remove-CsExternalAccessPolicy.</span><span class="sxs-lookup"><span data-stu-id="49d93-115">External access policies can be deleted by using Windows PowerShell and the Remove-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="49d93-116">Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="49d93-116">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="49d93-117">Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.</span><span class="sxs-lookup"><span data-stu-id="49d93-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specific-external-access-policy"></a><span data-ttu-id="49d93-118">Para quitar una directiva de acceso externo específica</span><span class="sxs-lookup"><span data-stu-id="49d93-118">To remove a specific external access policy</span></span>

  - <span data-ttu-id="49d93-119">Este comando quita la Directiva de acceso externo aplicada al sitio de Redmond:</span><span class="sxs-lookup"><span data-stu-id="49d93-119">This command removes the external access policy applied to the Redmond site:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-external-access-policies-applied-to-the-per-user-scope"></a><span data-ttu-id="49d93-120">Para quitar todas las directivas de acceso externo que se aplican al ámbito de cada usuario</span><span class="sxs-lookup"><span data-stu-id="49d93-120">To remove all the external access policies applied to the per-user scope</span></span>

  - <span data-ttu-id="49d93-121">Este comando quita todas las directivas de acceso externo configuradas en el ámbito de cada usuario:</span><span class="sxs-lookup"><span data-stu-id="49d93-121">This command removes all the external access policies configured at the per-user scope:</span></span>
    
        Get-CsExternalAccessPolicy -Filter "tag:*" | Remove-CsExternalAccessPolicy

</div>

<div>

## <a name="to-remove-all-the-external-access-policies-where-outside-user-access-is-disabled"></a><span data-ttu-id="49d93-122">Para quitar todas las directivas de acceso externas donde el acceso de usuarios externos está deshabilitado</span><span class="sxs-lookup"><span data-stu-id="49d93-122">To remove all the external access policies where outside user access is disabled</span></span>

  - <span data-ttu-id="49d93-123">Este comando elimina todas las directivas de acceso externas donde se ha deshabilitado el acceso de usuarios externos:</span><span class="sxs-lookup"><span data-stu-id="49d93-123">This command deletes all the external access policies where outside user access has been disabled:</span></span>
    
        Get-CsExternalAccessPolicy | Where-Object {$_.EnableOutsideAccess -eq $False} | Remove-CsExternalAccessPolicy

</div>

<span data-ttu-id="49d93-124">Para obtener más información, consulte el tema de ayuda para el cmdlet [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) .</span><span class="sxs-lookup"><span data-stu-id="49d93-124">For more information, see the help topic for the [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

