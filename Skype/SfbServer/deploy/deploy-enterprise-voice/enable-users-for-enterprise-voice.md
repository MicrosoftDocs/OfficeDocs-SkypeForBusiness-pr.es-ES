---
title: Habilitar a usuarios para Enterprise Voice en Skype para Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f252b23b-9641-4160-aa81-bf06dc2eced3
description: 'Resumen: Obtenga información sobre cómo habilitar a los usuarios realizar y recibir llamadas mediante el uso de Enterprise Voice en Skype para Business Server.'
ms.openlocfilehash: 9e1435c73a175ef40b4962ace41f4c7690f85953
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23883759"
---
# <a name="enable-users-for-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="5107a-103">Habilitar a usuarios para Enterprise Voice en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="5107a-103">Enable users for Enterprise Voice in Skype for Business Server</span></span>
 
<span data-ttu-id="5107a-104">**Resumen:** Obtenga información sobre cómo habilitar a los usuarios realizar y recibir llamadas mediante el uso de Enterprise Voice en Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="5107a-104">**Summary:** Learn how to enable users to make and receive calls by using Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="5107a-105">Después de implementar Enterprise Voice o llamar vía trabajo, puede usar los siguientes procedimientos para habilitar a un usuario realizar llamadas mediante el uso de Enterprise Voice:</span><span class="sxs-lookup"><span data-stu-id="5107a-105">After you deploy Enterprise Voice or Call Via Work, you can use the following procedures to enable a user to make calls by using Enterprise Voice:</span></span>
  
> [!NOTE]
> <span data-ttu-id="5107a-106">De los procedimientos siguientes, sólo la primera se puede realizar mediante el uso de Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="5107a-106">Of the following procedures, only the first can be performed by using Skype for Business Server Control Panel.</span></span> <span data-ttu-id="5107a-107">Para los restantes procedimientos, puede usar Skype sólo para el Shell de administración de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="5107a-107">For the remaining procedures, you can use only Skype for Business Server Management Shell.</span></span> 
  
- <span data-ttu-id="5107a-108">Habilitar la cuenta de usuario para Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="5107a-108">Enable the user account for Enterprise Voice.</span></span>
    
- <span data-ttu-id="5107a-109">(Opcional) Asignar a la cuenta de usuario una directiva de voz específica para el usuario.</span><span class="sxs-lookup"><span data-stu-id="5107a-109">(Optional) Assign the user account a user-specific voice policy.</span></span>
    
- <span data-ttu-id="5107a-110">(Opcional) Asignar a la cuenta de usuario un plan de marcado específico para el usuario.</span><span class="sxs-lookup"><span data-stu-id="5107a-110">(Optional) Assign the user account a user-specific dial plan.</span></span>
    
### <a name="to-enable-a-user-account-for-enterprise-voice"></a><span data-ttu-id="5107a-111">Para habilitar una cuenta de usuario para Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="5107a-111">To enable a user account for Enterprise Voice</span></span>

1. <span data-ttu-id="5107a-112">Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins, o como miembro del rol administrativo **CsVoiceAdministrator**, **CsServerAdministrator** o **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="5107a-112">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="5107a-113">Abra Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="5107a-113">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="5107a-114">En la barra de navegación izquierda, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="5107a-114">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="5107a-115">En el cuadro **Buscar usuarios**, escriba la primera parte del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de línea de la cuenta de usuario que desee habilitar y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="5107a-115">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="5107a-116">En la tabla, haga clic en la cuenta de usuario que desea habilitar para Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="5107a-116">In the table, click the user account that you want to enable for Enterprise Voice.</span></span>
    
6. <span data-ttu-id="5107a-117">En el menú **Editar**, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="5107a-117">On the **Edit** menu, click **Show details**.</span></span>
    
7. <span data-ttu-id="5107a-118">En la página **Editar Skype para usuarios del servidor de empresa** , en **telefonía**, haga clic en **Enterprise Voice**.</span><span class="sxs-lookup"><span data-stu-id="5107a-118">On the **Edit Skype for Business Server User** page, under **Telephony**, click **Enterprise Voice**.</span></span>
    
8. <span data-ttu-id="5107a-119">Haga clic en **URI de línea** y, a continuación, escriba un número de teléfono exclusivo y normalizado (por ejemplo, tel:+14255550200).</span><span class="sxs-lookup"><span data-stu-id="5107a-119">Click **Line URI**, and then type a unique, normalized phone number (for example, tel:+14255550200).</span></span>
    
9. <span data-ttu-id="5107a-120">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="5107a-120">Click **Commit**.</span></span>
    
<span data-ttu-id="5107a-121">Para terminar de habilitar un usuario para Enterprise Voice, asegúrese de que el usuario tiene asignada una directiva de voz y un plan de marcado, ya sea global (asignado de forma predeterminada) o específica del usuario. De forma predeterminada, todos los usuarios se les asigna una directiva de voz global y plan de marcado.</span><span class="sxs-lookup"><span data-stu-id="5107a-121">To finish enabling a user for Enterprise Voice, be sure that the user is assigned a voice policy and a dial plan, whether global (assigned by default) or user-specific.By default, all users are assigned a global voice policy and dial plan.</span></span> <span data-ttu-id="5107a-122">Si ya hubiera una directiva de voz o un plan de marcado a nivel de sitio para el sitio en el que se hospeda la cuenta de usuario, dichas directivas se aplicarán automáticamente al usuario.</span><span class="sxs-lookup"><span data-stu-id="5107a-122">If a voice policy or dial plan exists at the site level for the site on which the user account is homed, those site policies will automatically apply to the user.</span></span> <span data-ttu-id="5107a-123">Para aplicar una directiva de voz por usuario o plan a un usuario de marcado, debe ejecutar los cmdlets **Grant-CsVoicePolicy** y **Grant-CsDialPlan** .</span><span class="sxs-lookup"><span data-stu-id="5107a-123">To apply a per-user voice policy or dial plan to a user, you must run the **Grant-CsVoicePolicy** and **Grant-CsDialPlan** cmdlets.</span></span> <span data-ttu-id="5107a-124">Para obtener más información, consulte los siguientes procedimientos de este tema.</span><span class="sxs-lookup"><span data-stu-id="5107a-124">For details, see the following procedures in this topic.</span></span>
## <a name="voice-policy-assignment"></a><span data-ttu-id="5107a-125">Asignación de directivas de voz</span><span class="sxs-lookup"><span data-stu-id="5107a-125">Voice Policy Assignment</span></span>

<span data-ttu-id="5107a-126">Las directivas de voz global y de nivel de sitio se asignan automáticamente a todas las cuentas de usuario que están habilitadas para Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="5107a-126">Global and site-level voice policies are automatically assigned to all user accounts that are enabled for Enterprise Voice.</span></span> <span data-ttu-id="5107a-127">También puede crear directivas de voz aplicables a usuarios o grupos específicos.</span><span class="sxs-lookup"><span data-stu-id="5107a-127">You can also create voice policies that apply to specific users or groups.</span></span> <span data-ttu-id="5107a-128">Estas directivas por usuario deben estar explícitamente asignadas a los usuarios o grupos.</span><span class="sxs-lookup"><span data-stu-id="5107a-128">These per-user policies must be explicitly assigned to the users or groups.</span></span> <span data-ttu-id="5107a-129">Si desea usar la información global o sitio directiva de voz para todos los usuarios que están habilitados para Enterprise Voice, puede omitir esta sección y continuar con la sección [Asignación de Plan de marcado](enable-users-for-enterprise-voice.md#BKMK_DialPlanAssignment) más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="5107a-129">If you want to use the global or site voice policy for all users who are enabled for Enterprise Voice, you can skip this section and continue to [Dial Plan Assignment](enable-users-for-enterprise-voice.md#BKMK_DialPlanAssignment) section later in this topic.</span></span>
  
### <a name="to-assign-a-user-specific-voice-policy"></a><span data-ttu-id="5107a-130">Para asignar una directiva de voz específica del usuario</span><span class="sxs-lookup"><span data-stu-id="5107a-130">To assign a user-specific voice policy</span></span>

1. <span data-ttu-id="5107a-131">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="5107a-131">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="5107a-132">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="5107a-132">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="5107a-133">Para asignar una directiva de voz de usuario existente a un usuario, ejecute lo siguiente en el símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="5107a-133">To assign an existing user voice policy to a user, run the following at the command prompt:</span></span>
    
   ```
   Grant-CsVoicePolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    <span data-ttu-id="5107a-134">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="5107a-134">For example:</span></span>
    
   ```
   Grant-CsVoicePolicy -Identity "Bob Kelly" -PolicyName VoicePolicyJapan
   ```

    <span data-ttu-id="5107a-135">En este ejemplo, el usuario con el nombre para mostrar Bob Kelly es asignado la directiva de voz con el nombre **VoicePolicyJapan**.</span><span class="sxs-lookup"><span data-stu-id="5107a-135">In this example, the user with the display name Bob Kelly is assigned the voice policy with the name **VoicePolicyJapan**.</span></span>
    
## <a name="dial-plan-assignment"></a><span data-ttu-id="5107a-136">Asignación de planes de marcado</span><span class="sxs-lookup"><span data-stu-id="5107a-136">Dial Plan Assignment</span></span>
<span data-ttu-id="5107a-137"><a name="BKMK_DialPlanAssignment"> </a></span><span class="sxs-lookup"><span data-stu-id="5107a-137"></span></span>

<span data-ttu-id="5107a-138">Para completar la configuración de la cuenta de usuario para los usuarios de Enterprise Voice o los usuarios de conferencia de acceso telefónico, el usuario debe estar asignado un plan de marcado.</span><span class="sxs-lookup"><span data-stu-id="5107a-138">To complete user account configuration for either users of Enterprise Voice or users of dial-in conferencing, the user must be assigned a dial plan.</span></span> <span data-ttu-id="5107a-139">Las cuentas de usuario emplearán automáticamente el plan de marcado global o, si existe, el plan de marcado del sitio, en los casos en los que no se asigne explícitamente un plan de marcado creado particularmente para el usuario.</span><span class="sxs-lookup"><span data-stu-id="5107a-139">User accounts will automatically use the global dial plan or, if one exists, the site-level dial plan, when you do not explicitly assign an existing per-user dial plan.</span></span> <span data-ttu-id="5107a-140">Si desea usar la información global o sitio plan de marcado para todos los usuarios que están habilitados para Enterprise Voice, puede omitir esta sección.</span><span class="sxs-lookup"><span data-stu-id="5107a-140">If you want to use the global or site dial plan for all users who are enabled for Enterprise Voice, you can skip this section.</span></span>
  
### <a name="to-assign-a-user-specific-dial-plan"></a><span data-ttu-id="5107a-141">Asignar un plan de marcado específico de usuario</span><span class="sxs-lookup"><span data-stu-id="5107a-141">To assign a user-specific dial plan</span></span>

1. <span data-ttu-id="5107a-142">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="5107a-142">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="5107a-143">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="5107a-143">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="5107a-144">Para asignar un plan de marcado específico del usuario, ejecute lo siguiente en el símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="5107a-144">To assign a user-specific dial plan, run the following at the command prompt:</span></span>
    
   ```
   Grant-CsDialPlan -Identity <UserIdParameter> -PolicyName <String>
   ```

    <span data-ttu-id="5107a-145">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="5107a-145">For example:</span></span>
    
   ```
   Grant-CsDialPlan -Identity "Bob Kelly" -PolicyName DialPlanJapan
   ```

    <span data-ttu-id="5107a-146">En este ejemplo, el usuario con el nombre para mostrar Bob Kelly es asignado el plan de marcado de usuario con el nombre **DialPlanJapan**.</span><span class="sxs-lookup"><span data-stu-id="5107a-146">In this example, the user with the display name Bob Kelly is assigned the user dial plan with the name **DialPlanJapan**.</span></span>
    

