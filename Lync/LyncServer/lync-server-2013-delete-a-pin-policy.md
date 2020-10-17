---
title: 'Lync Server 2013: eliminar una directiva de PIN'
description: 'Lync Server 2013: eliminar una directiva de PIN.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a PIN policy
ms:assetid: 7c378927-2e41-418e-9721-327021bd2e45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521020(v=OCS.15)
ms:contentKeyID: 48184609
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03e0f1d9c22e367693f846a31b1ad2232f048965
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566576"
---
# <a name="delete-a-pin-policy-in-lync-server-2013"></a><span data-ttu-id="eec53-103">Eliminar una directiva de PIN en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eec53-103">Delete a PIN policy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eec53-104">_**Última modificación del tema:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="eec53-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="eec53-105">Siga estos pasos para eliminar una directiva de número de identificación personal (PIN).</span><span class="sxs-lookup"><span data-stu-id="eec53-105">Follow these steps to delete a personal identification number (PIN) policy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="eec53-106">No puede eliminar la directiva global de PIN.</span><span class="sxs-lookup"><span data-stu-id="eec53-106">You cannot delete the global PIN policy.</span></span>



</div>

<div>

## <a name="to-delete-a-pin-policy-in-lync-server-2013-control-panel"></a><span data-ttu-id="eec53-107">Para eliminar una directiva de PIN en el panel de control de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eec53-107">To delete a PIN policy in Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="eec53-108">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que se encuentra en la red en el que se implementó Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eec53-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="eec53-109">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="eec53-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="eec53-110">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="eec53-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="eec53-111">En la barra de navegación izquierda, haga clic en **Seguridad** y, a continuación, en **Directiva de PIN**.</span><span class="sxs-lookup"><span data-stu-id="eec53-111">In the left navigation bar, click **Security** and then click **PIN Policy**.</span></span>

4.  <span data-ttu-id="eec53-112">En la página **Directiva de PIN**, escriba en el campo de búsqueda el nombre completo o parcial de la directiva que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="eec53-112">On the **PIN Policy** page, and in the search field, type all or part of the name of the policy you want to delete.</span></span>

5.  <span data-ttu-id="eec53-113">En la lista de directivas, seleccione la directiva que desee, haga clic en **Editar** y, a continuación, en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="eec53-113">In the list of policies, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>

6.  <span data-ttu-id="eec53-114">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="eec53-114">Click **OK**.</span></span>

</div>

<div>

## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="eec53-115">Eliminación de directivas de PIN mediante cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="eec53-115">Removing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="eec53-116">Puede eliminar directivas de PIN mediante Windows PowerShell y el cmdlet Remove-CsPinPolicy.</span><span class="sxs-lookup"><span data-stu-id="eec53-116">You can delete PIN policies by using Windows PowerShell and the Remove-CsPinPolicy cmdlet.</span></span> <span data-ttu-id="eec53-117">Puede ejecutar este cmdlet desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="eec53-117">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="eec53-118">Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server 2010 mediante PowerShell remoto" en [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="eec53-118">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specific-pin-policy"></a><span data-ttu-id="eec53-119">Para quitar una directiva de PIN específica</span><span class="sxs-lookup"><span data-stu-id="eec53-119">To remove a specific PIN policy</span></span>

  - <span data-ttu-id="eec53-120">Este comando elimina la Directiva de PIN con la RedmondPinPolicy de identidad:</span><span class="sxs-lookup"><span data-stu-id="eec53-120">This command removes the PIN policy with the Identity RedmondPinPolicy:</span></span>
    
        Remove-CsPinPolicy -Identity "RedmondPinPolicy"

</div>

<div>

## <a name="to-remove-all-the-pin-policies-applied-to-the-site-scope"></a><span data-ttu-id="eec53-121">Para quitar todas las directivas de PIN que se aplican al ámbito del sitio</span><span class="sxs-lookup"><span data-stu-id="eec53-121">To remove all the PIN policies applied to the site scope</span></span>

  - <span data-ttu-id="eec53-122">Este comando elimina todas las Directivas de PIN configuradas en el ámbito del sitio:</span><span class="sxs-lookup"><span data-stu-id="eec53-122">This command removes all the PIN policies configured at the site scope:</span></span>
    
        Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy

</div>

<div>

## <a name="to-remove-all-the-pin-policies-that-allow-the-use-of-common-patterns"></a><span data-ttu-id="eec53-123">Para quitar todas las directivas de PIN que permiten el uso de patrones comunes</span><span class="sxs-lookup"><span data-stu-id="eec53-123">To remove all the PIN policies that allow the use of common patterns</span></span>

  - <span data-ttu-id="eec53-124">Y este elimina todas las Directivas de PIN que permiten el uso de patrones comunes:G</span><span class="sxs-lookup"><span data-stu-id="eec53-124">And this one removes all the PIN policies that allow the use of common patterns:G</span></span>
    
        et-CsPinPolicy | Where-Object {$_.AllowCommonPatterns -eq $True} | Remove-CsPinPolicy

</div>

<span data-ttu-id="eec53-125">Para obtener más información, consulte el tema de ayuda del cmdlet [Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsPinPolicy) .</span><span class="sxs-lookup"><span data-stu-id="eec53-125">For more information, see the help topic for the [Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsPinPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

