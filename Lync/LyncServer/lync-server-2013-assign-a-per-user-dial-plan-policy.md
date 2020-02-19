---
title: 'Lync Server 2013: asignar una directiva de plan de marcado por usuario'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user dial plan policy
ms:assetid: 9fea861f-7770-4cae-9b1f-2a960595bfc9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688156(v=OCS.15)
ms:contentKeyID: 49733760
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8bd4d46e2cd41c972258a84a1e8fb34549dc8b4e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134446"
---
# <a name="assign-a-per-user-dial-plan-policy-in-lync-server-2013"></a><span data-ttu-id="0bad0-102">Asignar una directiva de plan de marcado por usuario en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0bad0-102">Assign a per-user dial plan policy in Lync Server 2013</span></span>

 


<span data-ttu-id="0bad0-p101">Para completar la configuración de cuentas de usuario para los usuarios de Telefonía IP empresarial o para los usuarios de conferencias de acceso telefónico local, asigne un plan de marcado. Las cuentas de usuario emplearán automáticamente el plan de marcado global o, si existe, el plan de marcado del sitio, en los casos en los que no se asigne explícitamente un plan de marcado creado particularmente para el usuario. Si desea usar el plan de marcado global o del sitio para todos los usuarios habilitados para Enterprise Voice, puede omitir esta sección.</span><span class="sxs-lookup"><span data-stu-id="0bad0-p101">To complete user account configuration for either users of Enterprise Voice or users of dial-in conferencing, the user must be assigned a dial plan. User accounts will automatically use the global dial plan or, if one exists, the site-level dial plan when you do not explicitly assign an existing per-user dial plan. If you want to use the global or site dial plan for all users that are enabled for Enterprise Voice, you can skip this section.</span></span>

## <a name="to-assign-a-dial-plan-by-using-the-lync-server-2013-control-panel"></a><span data-ttu-id="0bad0-106">Para asignar un plan de marcado mediante el panel de control de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0bad0-106">To assign a dial plan by using the Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="0bad0-107">Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="0bad0-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="0bad0-108">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0bad0-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="0bad0-109">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="0bad0-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="0bad0-110">En la barra de navegación izquierda, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="0bad0-110">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="0bad0-111">En el cuadro \*\*Buscar usuarios \*\*, escriba la primera parte del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de línea de la cuenta de usuario que desee habilitar y, a continuación, haga clic en \*\*Buscar \*\*.</span><span class="sxs-lookup"><span data-stu-id="0bad0-111">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>

5.  <span data-ttu-id="0bad0-112">En la tabla, haga clic en la cuenta de usuario que desee asignar un plan de marcado.</span><span class="sxs-lookup"><span data-stu-id="0bad0-112">In the table, click the user account that you want to assign a dial plan.</span></span>

6.  <span data-ttu-id="0bad0-113">En el menú **Editar**, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="0bad0-113">On the **Edit** menu, click **Show details**.</span></span>

7.  <span data-ttu-id="0bad0-114">En la página **Editar usuario de Lync Server**, en **Telefonía**, haga clic en **Telefonía IP empresarial**.</span><span class="sxs-lookup"><span data-stu-id="0bad0-114">On the **Edit Lync Server User** page, under **Telephony**, click **Enterprise Voice**.</span></span>

8.  <span data-ttu-id="0bad0-115">Haga clic en **Directiva de plan de marcado** y luego seleccione el plan de marcado que desee.</span><span class="sxs-lookup"><span data-stu-id="0bad0-115">Click **Dial plan policy**, and then choose the desired dial plan.</span></span>

9.  <span data-ttu-id="0bad0-116">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="0bad0-116">Click **Commit**.</span></span>

<span data-ttu-id="0bad0-117">Para obtener más información sobre cómo configurar planes de marcado, consulte el tema [Configuring dial Plans in Lync Server 2013](lync-server-2013-configuring-dial-plans.md) .</span><span class="sxs-lookup"><span data-stu-id="0bad0-117">For details about configuring dial plans, see the [Configuring dial plans in Lync Server 2013](lync-server-2013-configuring-dial-plans.md) topic.</span></span>

## <a name="assign-a-per-user-dial-plan-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="0bad0-118">Asignar un plan de marcado por usuario mediante cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0bad0-118">Assign a Per-User Dial Plan by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="0bad0-119">Puede asignar planes de marcado por usuario con Windows PowerShell y el cmdlet **Grant-CsdialPlan** .</span><span class="sxs-lookup"><span data-stu-id="0bad0-119">You can assign per-user dial plans with Windows PowerShell and the **Grant-CsdialPlan** cmdlet.</span></span> <span data-ttu-id="0bad0-120">Puede ejecutar este cmdlet desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0bad0-120">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="0bad0-121">Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.</span><span class="sxs-lookup"><span data-stu-id="0bad0-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a><span data-ttu-id="0bad0-122">Para asignar un plan de marcado por usuario a un solo usuario</span><span class="sxs-lookup"><span data-stu-id="0bad0-122">To assign a per-user dial plan to a single user</span></span>

  - <span data-ttu-id="0bad0-123">El siguiente comando permite asignar el plan de marcado RedmondDialPlan al usuario Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="0bad0-123">The following command assigns the per-user dial plan RedmondDialPlan to the user Ken Myer.</span></span>
    
        Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"

## <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a><span data-ttu-id="0bad0-124">Para asignar un plan de marcado por usuario a varios usuarios</span><span class="sxs-lookup"><span data-stu-id="0bad0-124">To assign a per-user dial plan to multiple users</span></span>

  - <span data-ttu-id="0bad0-125">Este comando asigna el plan de marcado por usuario RedmondDialPlan a todos los usuarios que trabajen en la ciudad de Redmond.</span><span class="sxs-lookup"><span data-stu-id="0bad0-125">This command assigns the per-user dial plan RedmondDialPlan to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="0bad0-126">Para obtener más información sobre el parámetro LdapFilter usado en este comando, consulte la documentación del cmdlet [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="0bad0-126">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"

## <a name="to-unassign-a-per-user-dial-plan"></a><span data-ttu-id="0bad0-127">Para cancelar la asignación de un plan de marcado por usuario</span><span class="sxs-lookup"><span data-stu-id="0bad0-127">To unassign a per-user dial plan</span></span>

  - <span data-ttu-id="0bad0-p105">Este comando desasigna cualquier plan de marcado por usuario previamente asignado a Ken Myer. Una vez desasignado el plan de marcado por usuario, Ken Myer será administrado automáticamente utilizando el plan de marcado global, su plan de marcado de sitio local (si es que existe uno) o el plan de marcado de ámbito de servicio asignado a este registrador o puerta de enlace de RTC. Los planes de marcado de ámbito de servicio tienen prioridad sobre cualquier plan de marcado de sitio local, y los planes de marcado de sitio local tienen prioridad sobre cualquier plan de marcado global.</span><span class="sxs-lookup"><span data-stu-id="0bad0-p105">The following command unassigns any per-user dial plan previously assigned to Ken Myer. After the per-user dial plan is unassigned, Ken Myer will automatically be managed by using the global dial plan, his local site dial plan (if one exists), or the service-scope dial plan assigned to his Registrar or PSTN gateway. A service scope dial plan takes precedence over any site dial plan, and a site dial plan takes precedence over the global dial plan.</span></span>
    
        Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="0bad0-131">Para obtener más información, consulte el tema de ayuda para el cmdlet [Grant-CsDialPlan](https://technet.microsoft.com/library/gg398547\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="0bad0-131">For more information, see the help topic for the [Grant-CsDialPlan](https://technet.microsoft.com/library/gg398547\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="0bad0-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="0bad0-132">See Also</span></span>


[<span data-ttu-id="0bad0-133">Configurar planes de marcado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0bad0-133">Configuring dial plans in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-plans.md)  
[<span data-ttu-id="0bad0-134">Cuentas de usuario habilitadas para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0bad0-134">User accounts enabled for Lync Server 2013</span></span>](lync-server-2013-user-accounts-enabled-for-lync-server.md)

