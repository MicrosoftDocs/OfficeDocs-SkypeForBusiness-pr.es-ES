---
title: 'Lync Server 2013: Restablecer la directiva global para el acceso de usuarios externos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Reset the global policy for external user access
ms:assetid: 8207e1b1-de9e-461f-975f-fcc5c526849a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182545(v=OCS.15)
ms:contentKeyID: 48184675
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 327a658bcd75c05e291798598e53947b23c0c12f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823269"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reset-the-global-policy-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="f9cb0-102">Restablecer la directiva global para el acceso de usuarios externos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f9cb0-102">Reset the global policy for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f9cb0-103">_**Última modificación del tema:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="f9cb0-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="f9cb0-104">No puede eliminar completamente una directiva global.</span><span class="sxs-lookup"><span data-stu-id="f9cb0-104">You cannot completely delete a global policy.</span></span> <span data-ttu-id="f9cb0-105">El uso de la opción **eliminar** en la directiva global solo restablece la directiva global a la configuración predeterminada, que no incluye compatibilidad con las opciones de acceso de usuarios externos.</span><span class="sxs-lookup"><span data-stu-id="f9cb0-105">Using the **Delete** option on the global policy only resets the global policy to the default settings, which do not include support for any external user access options.</span></span>

<div>

## <a name="to-reset-the-global-policy-to-the-default-settings"></a><span data-ttu-id="f9cb0-106">Para restablecer la configuración predeterminada de la directiva global</span><span class="sxs-lookup"><span data-stu-id="f9cb0-106">To reset the global policy to the default settings</span></span>

1.  <span data-ttu-id="f9cb0-107">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="f9cb0-107">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f9cb0-108">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f9cb0-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f9cb0-109">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f9cb0-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f9cb0-110">En la barra de navegación izquierda, haga clic en **acceso de usuarios externos**, haga clic en **Directiva de acceso externo**.</span><span class="sxs-lookup"><span data-stu-id="f9cb0-110">In the left navigation bar, click **External User Access**, click **External Access Policy**.</span></span>

4.  <span data-ttu-id="f9cb0-111">En la pestaña **Directiva de acceso externo** , haga clic en la directiva global, haga clic en **Editar**y, a continuación, haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="f9cb0-111">On the **External Access Policy** tab, click the global policy, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="f9cb0-112">Cuando se le pida que confirme la eliminación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f9cb0-112">When prompted to confirm the deletion, click **OK**.</span></span> <span data-ttu-id="f9cb0-113">En la parte superior de la página aparece un mensaje que le informa de que se ha restablecido la directiva global.</span><span class="sxs-lookup"><span data-stu-id="f9cb0-113">A message appears at the top of the page informing you that the global policy has been reset.</span></span>

</div>

<div>

## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="f9cb0-114">Restablecer la Directiva de acceso externo global mediante cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f9cb0-114">Resetting the Global External Access Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="f9cb0-115">La Directiva de acceso externo global se puede restablecer mediante Windows PowerShell y el cmdlet Remove-CsExternalAccessPolicy.</span><span class="sxs-lookup"><span data-stu-id="f9cb0-115">The global external access policy can be reset by using Windows PowerShell and the Remove-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="f9cb0-116">Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f9cb0-116">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="f9cb0-117">Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.</span><span class="sxs-lookup"><span data-stu-id="f9cb0-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-reset-the-global-external-access-policy"></a><span data-ttu-id="f9cb0-118">Para restablecer la Directiva de acceso externo global</span><span class="sxs-lookup"><span data-stu-id="f9cb0-118">To reset the global external access policy</span></span>

  - <span data-ttu-id="f9cb0-119">Este comando restablece la Directiva de acceso externo global:</span><span class="sxs-lookup"><span data-stu-id="f9cb0-119">This command resets the global external access policy:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity "global"

</div>

<span data-ttu-id="f9cb0-120">Para obtener más información, consulte el tema de ayuda para el cmdlet [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) .</span><span class="sxs-lookup"><span data-stu-id="f9cb0-120">For more information, see the help topic for the [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

