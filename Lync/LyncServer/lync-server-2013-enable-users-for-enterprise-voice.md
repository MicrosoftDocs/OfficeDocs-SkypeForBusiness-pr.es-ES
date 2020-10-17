---
title: 'Lync Server 2013: habilitar a los usuarios para la telefonía IP empresarial'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable users for Enterprise Voice
ms:assetid: f252b23b-9641-4160-aa81-bf06dc2eced3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413011(v=OCS.15)
ms:contentKeyID: 48185800
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d03f47cbe637e2c6fe6a0466b73a3588b842d6e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501047"
---
# <a name="enable-users-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="d792d-102">Habilitar a los usuarios para la telefonía IP empresarial en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d792d-102">Enable users for Enterprise Voice in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d792d-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="d792d-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="d792d-104">Después de instalar los archivos de uno o varios servidores de mediación, configurar el enrutamiento de llamadas salientes y, opcionalmente, implementar una o más características avanzadas de Enterprise Voice, puede usar los siguientes procedimientos para permitir que un usuario realice llamadas mediante la telefonía IP empresarial:</span><span class="sxs-lookup"><span data-stu-id="d792d-104">After you install files for one or more Mediation Servers, configure outbound call routing, and optionally deploy one or more advanced Enterprise Voice features, you can use the following procedures to enable a user to make calls by using Enterprise Voice:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d792d-105">De los procedimientos siguientes, solo el primero se puede realizar mediante el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d792d-105">Of the following procedures, only the first can be performed by using Lync Server Control Panel.</span></span> <span data-ttu-id="d792d-106">Para el resto de los procedimientos, solo puede usar el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d792d-106">For the remaining procedures, you can use only Lync Server Management Shell.</span></span>



</div>

  - <span data-ttu-id="d792d-107">Habilitar la cuenta de usuario para la telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="d792d-107">Enable the user account for Enterprise Voice.</span></span>

  - <span data-ttu-id="d792d-108">(Opcional) Asignar a la cuenta de usuario una directiva de voz específica para el usuario.</span><span class="sxs-lookup"><span data-stu-id="d792d-108">(Optional) Assign the user account a user-specific voice policy.</span></span>

  - <span data-ttu-id="d792d-109">(Opcional) Asignar a la cuenta de usuario un plan de marcado específico para el usuario.</span><span class="sxs-lookup"><span data-stu-id="d792d-109">(Optional) Assign the user account a user-specific dial plan.</span></span>

<div>

## <a name="to-enable-a-user-account-for-enterprise-voice"></a><span data-ttu-id="d792d-110">Para habilitar una cuenta de usuario para telefonía IP empresarial</span><span class="sxs-lookup"><span data-stu-id="d792d-110">To enable a user account for Enterprise Voice</span></span>

1.  <span data-ttu-id="d792d-111">Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="d792d-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d792d-112">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d792d-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d792d-113">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="d792d-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d792d-114">En la barra de navegación izquierda, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="d792d-114">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="d792d-115">En el cuadro **Buscar usuarios**, escriba la primera parte del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de línea de la cuenta de usuario que desee habilitar y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="d792d-115">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>

5.  <span data-ttu-id="d792d-116">En la tabla, haga clic en la cuenta de usuario que desee habilitar para la telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="d792d-116">In the table, click the user account that you want to enable for Enterprise Voice.</span></span>

6.  <span data-ttu-id="d792d-117">En el menú **Editar**, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="d792d-117">On the **Edit** menu, click **Show details**.</span></span>

7.  <span data-ttu-id="d792d-118">En la página **Editar usuario de Lync Server**, en **Telefonía**, haga clic en **Telefonía IP empresarial**.</span><span class="sxs-lookup"><span data-stu-id="d792d-118">On the **Edit Lync Server User** page, under **Telephony**, click **Enterprise Voice**.</span></span>

8.  <span data-ttu-id="d792d-119">Haga clic en **URI de línea** y, a continuación, escriba un número de teléfono exclusivo y normalizado (por ejemplo, tel:+14255550200).</span><span class="sxs-lookup"><span data-stu-id="d792d-119">Click **Line URI**, and then type a unique, normalized phone number (for example, tel:+14255550200).</span></span>

9.  <span data-ttu-id="d792d-120">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="d792d-120">Click **Commit**.</span></span>

<span data-ttu-id="d792d-121">Para terminar de habilitar a un usuario para la telefonía IP empresarial, asegúrese de que el usuario tiene asignada una directiva de voz y un plan de marcado, ya sea global (asignado de forma predeterminada) o específico del usuario.</span><span class="sxs-lookup"><span data-stu-id="d792d-121">To finish enabling a user for Enterprise Voice, be sure that the user is assigned a voice policy and a dial plan, whether global (assigned by default) or user-specific.</span></span>

<span data-ttu-id="d792d-122">De manera predeterminada, a todos los usuarios se les asigna una directiva de voz global y un plan de marcado.</span><span class="sxs-lookup"><span data-stu-id="d792d-122">By default, all users are assigned a global voice policy and dial plan.</span></span> <span data-ttu-id="d792d-123">Si ya hubiera una directiva de voz o un plan de marcado a nivel de sitio para el sitio en el que se hospeda la cuenta de usuario, se aplicarán automáticamente al usuario.</span><span class="sxs-lookup"><span data-stu-id="d792d-123">If a voice policy or dial plan exists at the site level for the site on which the user account is homed, those site policies will automatically apply to the user.</span></span> <span data-ttu-id="d792d-124">Para aplicar una directiva de voz o plan de marcado por usuario a un usuario, deberá ejecutar los cmdlets **Grant-CsVoicePolicy** y **Grant-CsDialPlan**.</span><span class="sxs-lookup"><span data-stu-id="d792d-124">To apply a per-user voice policy or dial plan to a user, you must run the **Grant-CsVoicePolicy** and **Grant-CsDialPlan** cmdlets.</span></span> <span data-ttu-id="d792d-125">Para obtener más información, consulte la documentación del [Shell de administración de Lync Server 2013](lync-server-2013-lync-server-management-shell.md) .</span><span class="sxs-lookup"><span data-stu-id="d792d-125">For details, see the [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) documentation.</span></span>

</div>

<div>

## <a name="voice-policy-assignment"></a><span data-ttu-id="d792d-126">Asignación de directivas de voz</span><span class="sxs-lookup"><span data-stu-id="d792d-126">Voice Policy Assignment</span></span>

<span data-ttu-id="d792d-127">Las directivas de voz globales y de nivel de sitio se asignan automáticamente a todas las cuentas de usuario habilitadas para la telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="d792d-127">Global and site-level voice policies are automatically assigned to all user accounts that are enabled for Enterprise Voice.</span></span> <span data-ttu-id="d792d-128">También puede crear directivas de voz aplicables a usuarios o grupos específicos.</span><span class="sxs-lookup"><span data-stu-id="d792d-128">You can also create voice policies that apply to specific users or groups.</span></span> <span data-ttu-id="d792d-129">Estas directivas por usuario deben estar explícitamente asignadas a los usuarios o grupos.</span><span class="sxs-lookup"><span data-stu-id="d792d-129">These per-user policies must be explicitly assigned to the users or groups.</span></span> <span data-ttu-id="d792d-130">Si desea usar la Directiva de voz global o del sitio para todos los usuarios que están habilitados para telefonía IP empresarial, puede omitir esta sección y seguir marcando la sección asignación de plan más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="d792d-130">If you want to use the global or site voice policy for all users who are enabled for Enterprise Voice, you can skip this section and continue to Dial Plan Assignment section later in this topic.</span></span>

<div>

## <a name="to-assign-a-user-specific-voice-policy"></a><span data-ttu-id="d792d-131">Para asignar una directiva de voz específica del usuario</span><span class="sxs-lookup"><span data-stu-id="d792d-131">To assign a user-specific voice policy</span></span>

1.  <span data-ttu-id="d792d-132">Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="d792d-132">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d792d-133">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="d792d-133">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="d792d-134">Para asignar una directiva de voz de usuario existente a un usuario, ejecute lo siguiente en el símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="d792d-134">To assign an existing user voice policy to a user, run the following at the command prompt:</span></span>
    
        Grant-CsVoicePolicy -Identity <UserIdParameter> -PolicyName <String>
    
    <span data-ttu-id="d792d-135">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d792d-135">For example:</span></span>
    
        Grant-CsVoicePolicy -Identity "Bob Kelly" -PolicyName VoicePolicyJapan
    
    <span data-ttu-id="d792d-136">En este ejemplo, al usuario con el nombre para mostrar Bob Kelly se le asigna la Directiva de voz con el nombre **VoicePolicyJapan**.</span><span class="sxs-lookup"><span data-stu-id="d792d-136">In this example, the user with the display name Bob Kelly is assigned the voice policy with the name **VoicePolicyJapan**.</span></span>

<span data-ttu-id="d792d-137">Para obtener información detallada sobre cómo asignar una directiva de voz específica del usuario o acerca de la ejecución del cmdlet **Grant-CsVoicePolicy** , consulte la documentación del [Shell de administración de Lync Server 2013](lync-server-2013-lync-server-management-shell.md) .</span><span class="sxs-lookup"><span data-stu-id="d792d-137">For details about assigning a user-specific voice policy or about running the **Grant-CsVoicePolicy** cmdlet, see the [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) documentation.</span></span>

</div>

</div>

<span id="BKMK_DialPlanAssignment"></span>

<div>

## <a name="dial-plan-assignment"></a><span data-ttu-id="d792d-138">Asignación de planes de marcado</span><span class="sxs-lookup"><span data-stu-id="d792d-138">Dial Plan Assignment</span></span>

<span data-ttu-id="d792d-139">Para completar la configuración de cuentas de usuario para los usuarios de Telefonía IP empresarial o para los usuarios de conferencias de acceso telefónico local, asigne un plan de marcado.</span><span class="sxs-lookup"><span data-stu-id="d792d-139">To complete user account configuration for either users of Enterprise Voice or users of dial-in conferencing, the user must be assigned a dial plan.</span></span> <span data-ttu-id="d792d-140">Las cuentas de usuario emplearán automáticamente el plan de marcado global o, si existe, el plan de marcado del sitio, en los casos en los que no se asigne explícitamente un plan de marcado creado particularmente para el usuario.</span><span class="sxs-lookup"><span data-stu-id="d792d-140">User accounts will automatically use the global dial plan or, if one exists, the site-level dial plan, when you do not explicitly assign an existing per-user dial plan.</span></span> <span data-ttu-id="d792d-141">Si desea usar el plan de marcado global o del sitio para todos los usuarios que están habilitados para telefonía IP empresarial, puede omitir esta sección.</span><span class="sxs-lookup"><span data-stu-id="d792d-141">If you want to use the global or site dial plan for all users who are enabled for Enterprise Voice, you can skip this section.</span></span>

<div>

## <a name="to-assign-a-dial-plan"></a><span data-ttu-id="d792d-142">Para asignar un plan de marcado</span><span class="sxs-lookup"><span data-stu-id="d792d-142">To assign a dial plan</span></span>

1.  <span data-ttu-id="d792d-143">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="d792d-143">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d792d-144">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="d792d-144">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="d792d-145">Para asignar un plan de marcado específico del usuario, ejecute lo siguiente en el símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="d792d-145">To assign a user-specific dial plan, run the following at the command prompt:</span></span>
    
        Grant-CsDialPlan -Identity <UserIdParameter> -PolicyName <String>
    
    <span data-ttu-id="d792d-146">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d792d-146">For example:</span></span>
    
        Grant-CsDialPlan -Identity "Bob Kelly" -PolicyName DialPlanJapan
    
    <span data-ttu-id="d792d-147">En este ejemplo, al usuario con el nombre para mostrar Bob Kelly se le asigna el plan de marcado del usuario con el nombre **DialPlanJapan**.</span><span class="sxs-lookup"><span data-stu-id="d792d-147">In this example, the user with the display name Bob Kelly is assigned the user dial plan with the name **DialPlanJapan**.</span></span>

<span data-ttu-id="d792d-148">Para obtener información detallada acerca de la asignación de un plan de marcado de usuario o de la ejecución del cmdlet **Grant-CsDialPlan** , consulte la documentación del [Shell de administración de Lync Server 2013](lync-server-2013-lync-server-management-shell.md) .</span><span class="sxs-lookup"><span data-stu-id="d792d-148">For details about assigning a user dial plan or about running the **Grant-CsDialPlan** cmdlet, see the [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) documentation.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d792d-149">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d792d-149">See Also</span></span>


[<span data-ttu-id="d792d-150">Deshabilitar a un usuario para la telefonía IP empresarial en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d792d-150">Disable a user for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-disable-a-user-for-enterprise-voice.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

