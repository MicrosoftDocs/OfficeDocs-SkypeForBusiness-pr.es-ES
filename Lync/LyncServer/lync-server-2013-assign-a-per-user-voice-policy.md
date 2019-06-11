---
title: 'Lync Server 2013: asignar una directiva de voz por usuario'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign a per-user voice policy
ms:assetid: 9ee47ee7-1030-43b8-a4dc-bf685ea24659
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688155(v=OCS.15)
ms:contentKeyID: 49733758
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e74bebc202a9e8d9fbc7b925c14bbe030e4c577
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850703"
---
# <a name="assign-a-per-user-voice-policy-in-lync-server-2013"></a><span data-ttu-id="dde4a-102">Asignar una directiva de voz por usuario en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dde4a-102">Assign a per-user voice policy in Lync Server 2013</span></span>

 


<span data-ttu-id="dde4a-103">Las directivas de voz globales y de nivel de sitio se asignan automáticamente a todas las cuentas de usuario de Lync Server 2013 que están habilitadas para telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="dde4a-103">Global and site-level voice policies are automatically assigned to all Lync Server 2013 user accounts that are enabled for Enterprise Voice.</span></span> <span data-ttu-id="dde4a-104">También puede asignar directivas de voz a usuarios específicos mediante el panel de control de Lync Server 2013 o el shell de administración de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dde4a-104">You can also assign voice policies to specific users by using either the Lync Server 2013 Control Panel or the Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="dde4a-105">Use los procedimientos de este tema para asignar directivas de usuario explícitamente a los usuarios de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="dde4a-105">Use the procedures in this topic to explicitly assign per-user policies to Lync Server users.</span></span>

## <a name="to-assign-a-user-specific-voice-policy-using-the-lync-server-control-panel"></a><span data-ttu-id="dde4a-106">Para asignar una directiva de voz específica del usuario mediante el panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="dde4a-106">To assign a user-specific voice policy using the Lync Server Control Panel</span></span>

1.  <span data-ttu-id="dde4a-107">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="dde4a-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="dde4a-108">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="dde4a-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="dde4a-109">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="dde4a-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="dde4a-110">En la barra de navegación izquierda, haga clic en **Usuarios** y, luego, busque la cuenta de usuario que desea configurar.</span><span class="sxs-lookup"><span data-stu-id="dde4a-110">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>

4.  <span data-ttu-id="dde4a-111">En la tabla donde se enumeran los resultados de la búsqueda, haga clic en la cuenta de usuario, en **Editar** y, luego, en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="dde4a-111">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="dde4a-112">En **Editar usuario de Lync Server** en **Directiva de voz**, seleccione la Directiva de usuario que desea aplicar.</span><span class="sxs-lookup"><span data-stu-id="dde4a-112">In **Edit Lync Server User** under **Voice policy**, select the user policy that you want to apply.</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="dde4a-113">La <STRONG> &lt;configuración&gt; automática</STRONG> aplica el servidor predeterminado o la configuración de la directiva global.</span><span class="sxs-lookup"><span data-stu-id="dde4a-113">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default server or global policy settings.</span></span>



## <a name="assigning-a-per-user-voice-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="dde4a-114">Asignar una directiva de voz por usuario mediante cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="dde4a-114">Assigning a Per-User Voice Policy by using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="dde4a-115">Puede asignar directivas de voz por usuario mediante Windows PowerShell y el cmdlet **Grant-CsVoicePolicy** .</span><span class="sxs-lookup"><span data-stu-id="dde4a-115">You can assign per-user voice policies by using Windows PowerShell and the **Grant-CsVoicePolicy** cmdlet.</span></span> <span data-ttu-id="dde4a-116">Puede ejecutar este cmdlet desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dde4a-116">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="dde4a-117">Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.</span><span class="sxs-lookup"><span data-stu-id="dde4a-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-voice-policy-to-a-single-user"></a><span data-ttu-id="dde4a-118">Para asignar una directiva de voz por usuario a un solo usuario</span><span class="sxs-lookup"><span data-stu-id="dde4a-118">To assign a per-user voice policy to a single user</span></span>

  - <span data-ttu-id="dde4a-119">El comando siguiente asigna la Directiva de voz por usuario RedmondVoicePolicy al usuario Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="dde4a-119">The following command assigns the per-user voice policy RedmondVoicePolicy to the user Ken Myer.</span></span>
    
        Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

## <a name="to-assign-a-per-user-voice-policy-to-multiple-users"></a><span data-ttu-id="dde4a-120">Para asignar una directiva de voz por usuario a varios usuarios</span><span class="sxs-lookup"><span data-stu-id="dde4a-120">To assign a per-user voice policy to multiple users</span></span>

  - <span data-ttu-id="dde4a-121">Este comando asigna la Directiva de voz por usuario FinanceVoicePolicy a todos los usuarios que tienen cuentas en la OU de Finanzas de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="dde4a-121">This command assigns the per-user voice policy FinanceVoicePolicy to all the users who have accounts in the Finance OU in Active Directory.</span></span> <span data-ttu-id="dde4a-122">Para obtener más información sobre el parámetro de Uo que se usa en este comando, consulte la documentación del cmdlet [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="dde4a-122">For more information on the OU parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -OU "ou=Finance,ou=North America,dc=litwareinc,dc=com" | Grant-CsVoicePolicy -PolicyName "FinanceVoicePolicy"

## <a name="to-unassign-a-per-user-voice-policy"></a><span data-ttu-id="dde4a-123">Para cancelar la asignación de una directiva de voz por usuario</span><span class="sxs-lookup"><span data-stu-id="dde4a-123">To unassign a per-user voice policy</span></span>

  - <span data-ttu-id="dde4a-124">El comando siguiente elimina la asignación de cualquier directiva de voz por usuario asignada previamente a Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="dde4a-124">The following command unassigns any per-user voice policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="dde4a-125">Después de quitar la asignación de la directiva por usuario, se usará automáticamente la directiva global o la directiva del sitio local, si existe, para administrar a Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="dde4a-125">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="dde4a-126">La directiva de sitio tiene prioridad sobre la directiva global.</span><span class="sxs-lookup"><span data-stu-id="dde4a-126">A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="dde4a-127">Para obtener más información, consulte el tema de ayuda para el cmdlet [Grant-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398828\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="dde4a-127">For more information, see the help topic for the [Grant-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398828\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="dde4a-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="dde4a-128">See Also</span></span>


[<span data-ttu-id="dde4a-129">Deshabilitar un usuario de telefonía IP empresarial en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dde4a-129">Disable a user for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-disable-a-user-for-enterprise-voice.md)  


[<span data-ttu-id="dde4a-130">Shell de administración de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dde4a-130">Lync Server 2013 Management Shell</span></span>](lync-server-2013-lync-server-management-shell.md)

