---
title: 'Lync Server 2013: aplicar una directiva de archivado a los usuarios'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Applying an Archiving policy to users
ms:assetid: 624a7d3e-389d-403a-97e5-f7bb17023ef3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521004(v=OCS.15)
ms:contentKeyID: 48184290
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d1cf0db76b888b9774a16f7a6353ccf1b399eb3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737590"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="applying-an-archiving-policy-to-users-in-lync-server-2013"></a><span data-ttu-id="e36be-102">Aplicar una directiva de archivado a los usuarios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e36be-102">Applying an Archiving policy to users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e36be-103">_**Última modificación del tema:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="e36be-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="e36be-104">Si se ha habilitado un usuario para Lync Server 2013 y ha creado una o más directivas de usuario para archivar para usuarios alojados en Lync Server 2013, puede implementar la compatibilidad de archivado para usuarios específicos aplicando las directivas apropiadas a esos usuarios o grupos de usuarios.</span><span class="sxs-lookup"><span data-stu-id="e36be-104">If a user has been enabled for Lync Server 2013 and you have created one or more user policies for archiving for users homed on Lync Server 2013, you can implement archiving support for specific users by applying the appropriate policies to those users or user groups.</span></span> <span data-ttu-id="e36be-105">Por ejemplo, si crea una directiva para admitir el archivado de comunicaciones internas, puede aplicarla a al menos un usuario o grupo de usuarios para admitir el archivado de las comunicaciones de Lync Server 2013 del usuario.</span><span class="sxs-lookup"><span data-stu-id="e36be-105">For example, if you create a policy to support archiving of internal communications, you can apply it to at least one user or user group to support archiving of the user’s Lync Server 2013 communications.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e36be-106">Si habilitó la integración de Microsoft Exchange para su implementación, las directivas de retención local de Exchange controlan si el archivado está habilitado para los usuarios alojados en Exchange 2013 y si sus buzones se colocan en conservación local.</span><span class="sxs-lookup"><span data-stu-id="e36be-106">If you enabled Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="e36be-107">Para obtener más información, consulte <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">configurar directivas para archivar en Lync Server 2013 al usar la integración de Exchange Server</A> en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="e36be-107">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="e36be-108">Debe especificar todas las opciones apropiadas en las configuraciones de archivado antes de habilitar el archivado.</span><span class="sxs-lookup"><span data-stu-id="e36be-108">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span> <span data-ttu-id="e36be-109">Para obtener más información, vea <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">administrar las opciones de configuración de archivado en Lync Server 2013 para su organización, sitios y grupos</A> en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="e36be-109">For details, see <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</A> in the Operations documentation.</span></span>



</div>

<span data-ttu-id="e36be-110">Use el procedimiento de este tema para aplicar una directiva de usuario de archivado creada previamente a una o más cuentas de usuario o grupos de usuarios.</span><span class="sxs-lookup"><span data-stu-id="e36be-110">Use the procedure in this topic to apply a previously created Archiving user policy to one or more user accounts or user groups.</span></span>

<div>

## <a name="to-apply-an-archiving-user-policy-to-a-user-account"></a><span data-ttu-id="e36be-111">Para aplicar una directiva de usuario de archivado a una cuenta de usuario</span><span class="sxs-lookup"><span data-stu-id="e36be-111">To apply an archiving user policy to a user account</span></span>

1.  <span data-ttu-id="e36be-112">Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="e36be-112">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e36be-113">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e36be-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e36be-114">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e36be-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e36be-115">En la barra de navegación izquierda, haga clic en **Usuarios** y, luego, busque la cuenta de usuario que desea configurar.</span><span class="sxs-lookup"><span data-stu-id="e36be-115">In the left navigation bar, click **Users**, and then search for the user account that you want to configure.</span></span>

4.  <span data-ttu-id="e36be-116">En la tabla donde se enumeran los resultados de la búsqueda, haga clic en la cuenta de usuario, en **Editar** y, luego, en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="e36be-116">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="e36be-117">En **Editar usuario de Lync Server** , en **Directiva de archivado**, seleccione la Directiva de usuario de archivado que desea aplicar.</span><span class="sxs-lookup"><span data-stu-id="e36be-117">In **Edit Lync Server User** under **Archiving policy**, select the archiving user policy that you want to apply.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e36be-118">La <STRONG> &lt;configuración&gt; automática</STRONG> aplica la configuración predeterminada de la instalación del servidor.</span><span class="sxs-lookup"><span data-stu-id="e36be-118">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default server installation settings.</span></span> <span data-ttu-id="e36be-119">El servidor aplica automáticamente esta configuración.</span><span class="sxs-lookup"><span data-stu-id="e36be-119">These settings are applied automatically by the server.</span></span>

    
    </div>

6.  <span data-ttu-id="e36be-120">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="e36be-120">Click **Commit**.</span></span>

</div>

<div>

## <a name="assigning-a-per-user-archiving-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="e36be-121">Asignar una directiva de archivado por usuario mediante cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e36be-121">Assigning a Per-User Archiving Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="e36be-122">Las directivas de archivado por usuario se pueden asignar mediante Windows PowerShell y el cmdlet **Grant-CsArchivingPolicy** .</span><span class="sxs-lookup"><span data-stu-id="e36be-122">Per-user archiving policies can be assigned by using Windows PowerShell and the **Grant-CsArchivingPolicy** cmdlet.</span></span> <span data-ttu-id="e36be-123">Puede ejecutar este cmdlet desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e36be-123">You can run this cmdlet from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="e36be-124">Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.</span><span class="sxs-lookup"><span data-stu-id="e36be-124">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-assign-a-per-user-archiving-policy-to-a-single-user"></a><span data-ttu-id="e36be-125">Para asignar una directiva de archivado por usuario a un solo usuario</span><span class="sxs-lookup"><span data-stu-id="e36be-125">To assign a per-user archiving policy to a single user</span></span>

  - <span data-ttu-id="e36be-126">El siguiente comando permite asignar la directiva de archivado por usuario RedmondArchivingPolicy al usuario Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="e36be-126">The following command assigns the per-user archiving policy RedmondArchivingPolicy to the user Ken Myer.</span></span>
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"

</div>

<div>

## <a name="to-assign-a-per-user-archiving-policy-to-multiple-users"></a><span data-ttu-id="e36be-127">Para asignar una directiva de archivado por usuario a varios usuarios</span><span class="sxs-lookup"><span data-stu-id="e36be-127">To assign a per-user archiving policy to multiple users</span></span>

  - <span data-ttu-id="e36be-128">Este comando asigna el RedmondArchivingPolicy de directiva de archivado por usuario a todos los usuarios que tienen cuentas alojadas en el registro de la agrupación de atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="e36be-128">This command assigns the per-user archiving policy RedmondArchivingPolicy to all users who have accounts homed on the Registrar pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="e36be-129">Para obtener más información sobre el parámetro de filtro usado en este comando, consulte la documentación del cmdlet [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) .</span><span class="sxs-lookup"><span data-stu-id="e36be-129">For details about the Filter parameter used in this command, see the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) cmdlet documentation.</span></span>
    
        Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"

</div>

<div>

## <a name="to-assign-a-per-user-archiving-policy"></a><span data-ttu-id="e36be-130">Para asignar una directiva de archivado por usuario</span><span class="sxs-lookup"><span data-stu-id="e36be-130">To assign a per-user archiving policy</span></span>

  - <span data-ttu-id="e36be-131">El comando siguiente elimina la asignación de cualquier directiva de archivado por usuario previamente asignada a Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="e36be-131">The following command unassigns any per-user archiving policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="e36be-132">Después de quitar la asignación de la directiva por usuario, se usará automáticamente la directiva global o la directiva del sitio local, si existe, para administrar a Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="e36be-132">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="e36be-133">La directiva de sitio tiene prioridad sobre la directiva global.</span><span class="sxs-lookup"><span data-stu-id="e36be-133">A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null

</div>

<span data-ttu-id="e36be-134">Para obtener más información, consulte la documentación del cmdlet [Grant-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsArchivingPolicy) .</span><span class="sxs-lookup"><span data-stu-id="e36be-134">For details, see the [Grant-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsArchivingPolicy) cmdlet documentation.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e36be-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="e36be-135">See Also</span></span>


[<span data-ttu-id="e36be-136">Administrar el archivado de comunicaciones internas y externas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e36be-136">Managing the Archiving of internal and external communications in Lync Server 2013</span></span>](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)  
[<span data-ttu-id="e36be-137">Asignación de directivas por usuario en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e36be-137">Assigning per-user policies in Lync Server 2013</span></span>](lync-server-2013-assigning-per-user-policies.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

