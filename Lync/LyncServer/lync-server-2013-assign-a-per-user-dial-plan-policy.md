---
title: 'Lync Server 2013: asignar una directiva de plan de marcado por usuario'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign a per-user dial plan policy
ms:assetid: 9fea861f-7770-4cae-9b1f-2a960595bfc9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688156(v=OCS.15)
ms:contentKeyID: 49733760
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7f9bca09515daba6db7e072625d5b4a217d37cd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850746"
---
# <a name="assign-a-per-user-dial-plan-policy-in-lync-server-2013"></a><span data-ttu-id="fef7a-102">Asignar una directiva de plan de marcado por usuario en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fef7a-102">Assign a per-user dial plan policy in Lync Server 2013</span></span>

 


<span data-ttu-id="fef7a-103">Para completar la configuración de la cuenta de usuario para los usuarios de telefonía IP empresarial o para usuarios de conferencias de acceso telefónico local, el usuario debe tener asignado un plan de marcado.</span><span class="sxs-lookup"><span data-stu-id="fef7a-103">To complete user account configuration for either users of Enterprise Voice or users of dial-in conferencing, the user must be assigned a dial plan.</span></span> <span data-ttu-id="fef7a-104">Las cuentas de usuario usarán automáticamente el plan de marcado global o, si existe alguno, el plan de marcado de nivel de sitio cuando no se asigne de forma explícita un plan de marcado por usuario existente.</span><span class="sxs-lookup"><span data-stu-id="fef7a-104">User accounts will automatically use the global dial plan or, if one exists, the site-level dial plan when you do not explicitly assign an existing per-user dial plan.</span></span> <span data-ttu-id="fef7a-105">Si desea usar el plan de marcado global o de sitio para todos los usuarios habilitados para telefonía IP empresarial, puede omitir esta sección.</span><span class="sxs-lookup"><span data-stu-id="fef7a-105">If you want to use the global or site dial plan for all users that are enabled for Enterprise Voice, you can skip this section.</span></span>

## <a name="to-assign-a-dial-plan-by-using-the-lync-server-2013-control-panel"></a><span data-ttu-id="fef7a-106">Para asignar un plan de marcado mediante el panel de control de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fef7a-106">To assign a dial plan by using the Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="fef7a-107">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="fef7a-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="fef7a-108">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fef7a-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="fef7a-109">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="fef7a-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="fef7a-110">En la barra de navegación izquierda, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="fef7a-110">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="fef7a-111">En el cuadro **Buscar usuarios**, escriba la primera parte del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de línea de la cuenta de usuario que desee habilitar y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="fef7a-111">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>

5.  <span data-ttu-id="fef7a-112">En la tabla, haga clic en la cuenta de usuario a la que desea asignar un plan de marcado.</span><span class="sxs-lookup"><span data-stu-id="fef7a-112">In the table, click the user account that you want to assign a dial plan.</span></span>

6.  <span data-ttu-id="fef7a-113">En el menú **Editar**, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="fef7a-113">On the **Edit** menu, click **Show details**.</span></span>

7.  <span data-ttu-id="fef7a-114">En la página **Editar usuario de Lync Server** , en telefonía, haga clic en **telefonía** **IP empresarial**.</span><span class="sxs-lookup"><span data-stu-id="fef7a-114">On the **Edit Lync Server User** page, under **Telephony**, click **Enterprise Voice**.</span></span>

8.  <span data-ttu-id="fef7a-115">Haga clic en **Directiva de plan de marcado**y elija el plan de marcado que quiera.</span><span class="sxs-lookup"><span data-stu-id="fef7a-115">Click **Dial plan policy**, and then choose the desired dial plan.</span></span>

9.  <span data-ttu-id="fef7a-116">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="fef7a-116">Click **Commit**.</span></span>

<span data-ttu-id="fef7a-117">Para obtener más información sobre la configuración de planes de marcado, consulte el tema sobre [Cómo configurar planes de marcado en Lync Server 2013](lync-server-2013-configuring-dial-plans.md) .</span><span class="sxs-lookup"><span data-stu-id="fef7a-117">For details about configuring dial plans, see the [Configuring dial plans in Lync Server 2013](lync-server-2013-configuring-dial-plans.md) topic.</span></span>

## <a name="assign-a-per-user-dial-plan-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="fef7a-118">Asignar un plan de marcado por usuario mediante cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fef7a-118">Assign a Per-User Dial Plan by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="fef7a-119">Puede asignar planes de marcado por usuario con Windows PowerShell y el cmdlet **Grant-CsdialPlan** .</span><span class="sxs-lookup"><span data-stu-id="fef7a-119">You can assign per-user dial plans with Windows PowerShell and the **Grant-CsdialPlan** cmdlet.</span></span> <span data-ttu-id="fef7a-120">Puede ejecutar este cmdlet desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fef7a-120">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="fef7a-121">Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.</span><span class="sxs-lookup"><span data-stu-id="fef7a-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a><span data-ttu-id="fef7a-122">Para asignar un plan de marcado por usuario a un único usuario</span><span class="sxs-lookup"><span data-stu-id="fef7a-122">To assign a per-user dial plan to a single user</span></span>

  - <span data-ttu-id="fef7a-123">El comando siguiente asigna el plan de marcado por usuario RedmondDialPlan al usuario Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="fef7a-123">The following command assigns the per-user dial plan RedmondDialPlan to the user Ken Myer.</span></span>
    
        Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"

## <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a><span data-ttu-id="fef7a-124">Para asignar un plan de marcado por usuario a varios usuarios</span><span class="sxs-lookup"><span data-stu-id="fef7a-124">To assign a per-user dial plan to multiple users</span></span>

  - <span data-ttu-id="fef7a-125">Este comando asigna el plan de marcado por usuario RedmondDialPlan a todos los usuarios que trabajan en la ciudad de Redmond.</span><span class="sxs-lookup"><span data-stu-id="fef7a-125">This command assigns the per-user dial plan RedmondDialPlan to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="fef7a-126">Para obtener más información sobre el parámetro LdapFilter que se usa en este comando, consulte la documentación del cmdlet [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="fef7a-126">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"

## <a name="to-unassign-a-per-user-dial-plan"></a><span data-ttu-id="fef7a-127">Para quitar la asignación de un plan de marcado por usuario</span><span class="sxs-lookup"><span data-stu-id="fef7a-127">To unassign a per-user dial plan</span></span>

  - <span data-ttu-id="fef7a-128">El comando siguiente elimina la asignación de cualquier plan de marcado por usuario previamente asignado a Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="fef7a-128">The following command unassigns any per-user dial plan previously assigned to Ken Myer.</span></span> <span data-ttu-id="fef7a-129">Después de que el plan de marcado por usuario esté sin asignar, Ken Myer se administrará automáticamente con el plan de marcado global, su plan de marcado de sitio local (si existe alguno) o el plan de marcado de ámbito de servicio asignado a su registrador o puerta de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="fef7a-129">After the per-user dial plan is unassigned, Ken Myer will automatically be managed by using the global dial plan, his local site dial plan (if one exists), or the service-scope dial plan assigned to his Registrar or PSTN gateway.</span></span> <span data-ttu-id="fef7a-130">Un plan de marcado de ámbito de servicio tiene prioridad sobre cualquier plan de marcado del sitio, y un plan de marcado del sitio tiene prioridad sobre el plan de marcado global.</span><span class="sxs-lookup"><span data-stu-id="fef7a-130">A service scope dial plan takes precedence over any site dial plan, and a site dial plan takes precedence over the global dial plan.</span></span>
    
        Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="fef7a-131">Para obtener más información, consulte el tema de ayuda para el cmdlet [Grant-CsDialPlan](https://technet.microsoft.com/en-us/library/gg398547\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="fef7a-131">For more information, see the help topic for the [Grant-CsDialPlan](https://technet.microsoft.com/en-us/library/gg398547\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="fef7a-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="fef7a-132">See Also</span></span>


[<span data-ttu-id="fef7a-133">Configurar planes de marcado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fef7a-133">Configuring dial plans in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-plans.md)  
[<span data-ttu-id="fef7a-134">Cuentas de usuario habilitadas para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fef7a-134">User accounts enabled for Lync Server 2013</span></span>](lync-server-2013-user-accounts-enabled-for-lync-server.md)

