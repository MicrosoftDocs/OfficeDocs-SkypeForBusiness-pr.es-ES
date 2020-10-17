---
title: 'Lync Server 2013: asignar una directiva de voz por usuario'
description: 'Lync Server 2013: asignar una directiva de voz por usuario.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user voice policy
ms:assetid: 9ee47ee7-1030-43b8-a4dc-bf685ea24659
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688155(v=OCS.15)
ms:contentKeyID: 49733758
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7ea0b171e10302b4c466187c54324cc2548e821
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563566"
---
# <a name="assign-a-per-user-voice-policy-in-lync-server-2013"></a><span data-ttu-id="316b8-103">Asignar una directiva de voz por usuario en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="316b8-103">Assign a per-user voice policy in Lync Server 2013</span></span>

 


<span data-ttu-id="316b8-104">Las directivas de voz globales y de nivel de sitio se asignan automáticamente a todas las cuentas de usuario de Lync Server 2013 que están habilitadas para Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="316b8-104">Global and site-level voice policies are automatically assigned to all Lync Server 2013 user accounts that are enabled for Enterprise Voice.</span></span> <span data-ttu-id="316b8-105">También puede asignar directivas de voz a usuarios específicos mediante el panel de control de Lync Server 2013 o el shell de administración de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="316b8-105">You can also assign voice policies to specific users by using either the Lync Server 2013 Control Panel or the Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="316b8-106">Use los procedimientos de este tema para asignar explícitamente directivas por usuario a los usuarios de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="316b8-106">Use the procedures in this topic to explicitly assign per-user policies to Lync Server users.</span></span>

## <a name="to-assign-a-user-specific-voice-policy-using-the-lync-server-control-panel"></a><span data-ttu-id="316b8-107">Para asignar una directiva de voz específica del usuario mediante el panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="316b8-107">To assign a user-specific voice policy using the Lync Server Control Panel</span></span>

1.  <span data-ttu-id="316b8-108">Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="316b8-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="316b8-109">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="316b8-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="316b8-110">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="316b8-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="316b8-111">En la barra de navegación izquierda, haga clic en  \*\*Usuarios \*\* y, a continuación, busque en la cuenta de usuario que desea configurar.</span><span class="sxs-lookup"><span data-stu-id="316b8-111">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>

4.  <span data-ttu-id="316b8-112">En la tabla donde se enumeran los resultados de la búsqueda, haga clic en la cuenta de usuario, en \*\*Editar \*\* y, a continuación, en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="316b8-112">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="316b8-113">En **Editar usuario de Lync Server** en **Directiva de voz**, seleccione la directiva de usuario que desea aplicar.</span><span class="sxs-lookup"><span data-stu-id="316b8-113">In **Edit Lync Server User** under **Voice policy**, select the user policy that you want to apply.</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="316b8-114">La configuración <STRONG> &lt; automática &gt; </STRONG> aplica el servidor predeterminado o la configuración de directiva global.</span><span class="sxs-lookup"><span data-stu-id="316b8-114">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default server or global policy settings.</span></span>



## <a name="assign-per-user-voice-policies"></a><span data-ttu-id="316b8-115">Asignar directivas de voz por usuario</span><span class="sxs-lookup"><span data-stu-id="316b8-115">Assign per-user voice policies</span></span>

<span data-ttu-id="316b8-116">Puede asignar directivas de voz por usuario con Windows PowerShell y el cmdlet **Grant-CsVoicePolicy** .</span><span class="sxs-lookup"><span data-stu-id="316b8-116">You can assign per-user voice policies by using Windows PowerShell and the **Grant-CsVoicePolicy** cmdlet.</span></span> <span data-ttu-id="316b8-117">Puede ejecutar este cmdlet desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="316b8-117">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="316b8-118">Para obtener información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, lea esta entrada de blog de Lync Server Windows PowerShell: [Inicio rápido: administración de Microsoft Lync Server 2010 mediante PowerShell remoto](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="316b8-118">To learn about using remote Windows PowerShell to connect to Lync Server, read this Lync Server Windows PowerShell blog post: [Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span>

### <a name="assign-a-per-user-voice-policy-to-a-single-user"></a><span data-ttu-id="316b8-119">Asignar una directiva de voz por usuario a un solo usuario</span><span class="sxs-lookup"><span data-stu-id="316b8-119">Assign a per-user voice policy to a single user</span></span>

  - <span data-ttu-id="316b8-120">El siguiente comando permite asignar la directiva de voz por usuario RedmondVoicePolicy al usuario Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="316b8-120">The following command assigns the per-user voice policy RedmondVoicePolicy to the user Ken Myer.</span></span>
    
        Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

## <a name="assign-a-per-user-voice-policy-to-multiple-users"></a><span data-ttu-id="316b8-121">Asignar una directiva de voz por usuario a varios usuarios</span><span class="sxs-lookup"><span data-stu-id="316b8-121">Assign a per-user voice policy to multiple users</span></span>

  - <span data-ttu-id="316b8-122">Este comando asigna la directiva de voz por usuario FinanceVoicePolicy a todos los usuarios que tengan cuentas en el OU Finance de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="316b8-122">This command assigns the per-user voice policy FinanceVoicePolicy to all the users who have accounts in the Finance OU in Active Directory.</span></span> <span data-ttu-id="316b8-123">Para obtener más información sobre el parámetro OU usado en este comando, consulte la documentación del cmdlet [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="316b8-123">For more information on the OU parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -OU "ou=Finance,ou=North America,dc=litwareinc,dc=com" | Grant-CsVoicePolicy -PolicyName "FinanceVoicePolicy"

## <a name="unassign-a-per-user-voice-policy"></a><span data-ttu-id="316b8-124">Cancelar la asignación de una directiva de voz por usuario</span><span class="sxs-lookup"><span data-stu-id="316b8-124">Unassign a per-user voice policy</span></span>

  - <span data-ttu-id="316b8-p105">Este comando desasigna cualquier directiva de voz por usuario previamente asignada a Ken Myer. Una vez desasignada la directiva por usuario, Ken Myer pasará automáticamente a ser administrado mediante la directiva global (o, de existir, por la directiva de su sitio local). Las directivas de sitio tienen prioridad sobre la directiva global.</span><span class="sxs-lookup"><span data-stu-id="316b8-p105">The following command unassigns any per-user voice policy previously assigned to Ken Myer. After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy. A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="316b8-128">Para obtener más información, consulte el tema de ayuda para el cmdlet [Grant-CsVoicePolicy](https://technet.microsoft.com/library/gg398828\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="316b8-128">For more information, see the help topic for the [Grant-CsVoicePolicy](https://technet.microsoft.com/library/gg398828\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="316b8-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="316b8-129">See Also</span></span>


[<span data-ttu-id="316b8-130">Deshabilitar a un usuario para la telefonía IP empresarial en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="316b8-130">Disable a user for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-disable-a-user-for-enterprise-voice.md)  


[<span data-ttu-id="316b8-131">Shell de administración de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="316b8-131">Lync Server 2013 Management Shell</span></span>](lync-server-2013-lync-server-management-shell.md)

