---
title: 'Lync Server 2013: asignar una directiva de acceso de usuario externo a un usuario habilitado para Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign an external user access policy to a Lync enabled user
ms:assetid: 736fcaad-9f95-4896-b767-e199d86a00a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398551(v=OCS.15)
ms:contentKeyID: 48184483
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 96b578028b7e5d68d902557fddeb9dd5e2a61a9e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030103"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assign-an-external-user-access-policy-to-a-lync-enabled-user-in-lync-server-2013"></a><span data-ttu-id="353c2-102">Asignar una directiva de acceso de usuario externo a un usuario habilitado para Lync en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="353c2-102">Assign an external user access policy to a Lync enabled user in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="353c2-103">_**Última modificación del tema:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="353c2-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="353c2-104">Si un usuario se ha habilitado para Lync Server, puede configurar la Federación SIP, la Federación XMPP, el acceso de usuarios remotos y la conectividad de mensajería instantánea pública en el panel de control de Lync Server, mediante la aplicación de las directivas apropiadas a usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="353c2-104">If a user has been enabled for Lync Server, you can configure SIP federation, XMPP federation, remote user access, and public instant messaging (IM) connectivity in the Lync Server Control Panel by applying the appropriate policies to specific users.</span></span> <span data-ttu-id="353c2-105">Por ejemplo, si ha creado una directiva para admitir el acceso de usuarios remotos, debe aplicarla al usuario antes de que el usuario pueda conectarse a Lync Server desde una ubicación remota y colaborar con usuarios internos desde la ubicación remota.</span><span class="sxs-lookup"><span data-stu-id="353c2-105">For example, if you created a policy to support remote user access, you must apply it to the user before the user can connect to Lync Server from a remote location and collaborate with internal users from the remote location.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="353c2-106">Para permitir el acceso de usuarios externos, debe habilitar la compatibilidad para cada tipo de acceso de usuarios externos que desee permitir y configurar las directivas adecuadas y otras opciones para controlar su uso.</span><span class="sxs-lookup"><span data-stu-id="353c2-106">To support external user access, you must enable support for each type of external user access you want to support, and configure the appropriate policies and other options to control its use.</span></span> <span data-ttu-id="353c2-107">Para obtener más información, consulte Configuración de la <A href="lync-server-2013-configuring-support-for-external-user-access.md">compatibilidad para el acceso de usuarios externos en Lync server 2013</A> en la documentación de implementación o administración de la <A href="lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md">Federación y el acceso externo a Lync Server 2013</A> en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="353c2-107">For details, see <A href="lync-server-2013-configuring-support-for-external-user-access.md">Configuring support for external user access in Lync Server 2013</A> in the Deployment documentation or <A href="lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md">Managing federation and external access to Lync Server 2013</A> in the Operations documentation.</span></span>



</div>

<span data-ttu-id="353c2-108">Use el procedimiento descrito en este tema para aplicar una directiva de acceso de usuarios externos creada previamente a una o varias cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="353c2-108">Use the procedure in this topic to apply a previously created external user access policy to one or more user accounts.</span></span>

<div>

## <a name="to-apply-an-external-user-policy-to-a-user-account"></a><span data-ttu-id="353c2-109">Para aplicar una directiva de usuario externo a una cuenta de usuario</span><span class="sxs-lookup"><span data-stu-id="353c2-109">To apply an external user policy to a user account</span></span>

1.  <span data-ttu-id="353c2-110">Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="353c2-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="353c2-111">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="353c2-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="353c2-112">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="353c2-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="353c2-113">En la barra de navegación izquierda, haga clic en  \*\*Usuarios \*\* y, a continuación, busque en la cuenta de usuario que desea configurar.</span><span class="sxs-lookup"><span data-stu-id="353c2-113">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>

4.  <span data-ttu-id="353c2-114">En la tabla donde se enumeran los resultados de la búsqueda, haga clic en la cuenta de usuario, en **Editar** y, a continuación, en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="353c2-114">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="353c2-115">En **Editar usuario de Lync Server** en **Directiva de acceso externo**, seleccione la directiva de usuario que desea aplicar.</span><span class="sxs-lookup"><span data-stu-id="353c2-115">In **Edit Lync Server User** under **External access policy**, select the user policy that you want to apply.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="353c2-116">La <STRONG> &lt;configuración&gt; automática</STRONG> aplica el servidor predeterminado o la configuración de directiva global.</span><span class="sxs-lookup"><span data-stu-id="353c2-116">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default server or global policy settings.</span></span>

    
    </div>

</div>

<div>

## <a name="assigning-per-user-external-access-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="353c2-117">Asignación de directivas de acceso externo por usuario mediante cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="353c2-117">Assigning Per-User External Access Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="353c2-118">Las directivas de acceso externo por usuario se pueden asignar mediante Windows PowerShell y el cmdlet Grant-CsExternalAccessPolicy.</span><span class="sxs-lookup"><span data-stu-id="353c2-118">Per-user external access policies can be assigned by using Windows PowerShell and the Grant-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="353c2-119">Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="353c2-119">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="353c2-120">Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.</span><span class="sxs-lookup"><span data-stu-id="353c2-120">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-assign-a-per-user-external-access-policy-to-a-single-user"></a><span data-ttu-id="353c2-121">Para asignar una directiva de acceso externo por usuario a un solo usuario</span><span class="sxs-lookup"><span data-stu-id="353c2-121">To assign a per-user external access policy to a single user</span></span>

  - <span data-ttu-id="353c2-122">Este comando asigna la directiva de acceso externo por usuario RedmondExternalAccessPolicy al usuario Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="353c2-122">This command assigns the per-user external access policy RedmondExternalAccessPolicy to the user Ken Myer.</span></span>
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName "RedmondExternalAccessPolicy"

</div>

<div>

## <a name="to-assign-a-per-user-external-access-policy-to-multiple-users"></a><span data-ttu-id="353c2-123">Para asignar una directiva de acceso externo por usuario a varios usuarios</span><span class="sxs-lookup"><span data-stu-id="353c2-123">To assign a per-user external access policy to multiple users</span></span>

  - <span data-ttu-id="353c2-124">Este comando asigna la directiva de acceso externo por usuario USAExternalAccessPolicy a todos los usuarios que tienen cuentas en la unidad organizativa (OU) de los Estados Unidos en Active Directory.</span><span class="sxs-lookup"><span data-stu-id="353c2-124">This command assigns the per-user external access policy USAExternalAccessPolicy to all the users who have accounts in the UnitedStates OU in Active Directory.</span></span> <span data-ttu-id="353c2-125">Para obtener más información sobre el parámetro OU usado en este comando, consulte la documentación del cmdlet [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) .</span><span class="sxs-lookup"><span data-stu-id="353c2-125">For more information on the OU parameter used in this command, see the documentation for the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) cmdlet.</span></span>
    
        Get-CsUser -OU "ou=UnitedStates,dc=litwareinc,dc=com" | Grant-CsExternalAccessPolicy -PolicyName "USAExternalAccessPolicy"

</div>

<div>

## <a name="to-unassign-a-per-user-external-access-policy"></a><span data-ttu-id="353c2-126">Para cancelar la asignación de una directiva de acceso externo por usuario</span><span class="sxs-lookup"><span data-stu-id="353c2-126">To unassign a per-user external access policy</span></span>

  - <span data-ttu-id="353c2-p106">Este comando anula la asignación de una directiva de acceso externo por usuario que se había asignado a Ken Myer. Una vez anulada la asignación, el usuario Ken Myer será administrado por la directiva global o, si la hay, por su directiva de sitio local. Las directivas de sitio tienen preferencia sobre la directiva global.</span><span class="sxs-lookup"><span data-stu-id="353c2-p106">This command unassigns any per-user external access policy previously assigned to Ken Myer. After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy. A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName $Null

</div>

<span data-ttu-id="353c2-130">Para obtener más información, consulte el tema de ayuda para el cmdlet [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy) .</span><span class="sxs-lookup"><span data-stu-id="353c2-130">For more information, see the help topic for the [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

