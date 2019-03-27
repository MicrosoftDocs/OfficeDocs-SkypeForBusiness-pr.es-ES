---
title: Configure las directivas de archivado para Skype para Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8e48087-d4f0-4fe1-9e7e-f2b3e07f815f
description: 'Resumen: Lea este tema para obtener información sobre cómo configurar las directivas de archivado iniciales de Skype para los usuarios de Business Server.'
ms.openlocfilehash: 88840d10cbd7a71b32b5079a8600018b97e8b0c3
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30876453"
---
# <a name="configure-archiving-policies-for-skype-for-business-server"></a><span data-ttu-id="c26b5-103">Configure las directivas de archivado para Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="c26b5-103">Configure archiving policies for Skype for Business Server</span></span>
 
<span data-ttu-id="c26b5-104">**Resumen:** Lea este tema para obtener información sobre cómo configurar las directivas de archivado iniciales de Skype para los usuarios de Business Server.</span><span class="sxs-lookup"><span data-stu-id="c26b5-104">**Summary:** Read this topic to learn how to configure initial archiving policies for Skype for Business Server users.</span></span>
  
<span data-ttu-id="c26b5-105">En Skype para Business Server, use las directivas para habilitar y deshabilitar el archivado de comunicaciones internas y comunicaciones externas para los usuarios que están hospedados en Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="c26b5-105">In Skype for Business Server, you use policies to enable and disable archiving for internal communications and external communications for users who are homed on Skype for Business Server.</span></span> <span data-ttu-id="c26b5-106">Entre estas directivas se incluyen:</span><span class="sxs-lookup"><span data-stu-id="c26b5-106">This includes the following:</span></span>
  
- <span data-ttu-id="c26b5-107">Una directiva global que se crea de forma predeterminada al implementar Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="c26b5-107">A global policy that is created by default when you deploy Skype for Business Server</span></span>
    
- <span data-ttu-id="c26b5-108">Directivas de sitio opcionales, que especifican cómo se implementa el archivado para un sitio específico</span><span class="sxs-lookup"><span data-stu-id="c26b5-108">Optional site-level policies that specify how archiving is implemented for a specific site</span></span>
    
- <span data-ttu-id="c26b5-109">Directivas opcionales de nivel de usuario que especifican cómo se implementa el archivado para usuarios específicos</span><span class="sxs-lookup"><span data-stu-id="c26b5-109">Optional user-level policies that specify how archiving is implemented for specific users</span></span>
    
<span data-ttu-id="c26b5-110">Las directivas de archivado se configuran inicialmente al implementar el archivado, pero es posible cambiar, agregar y eliminar directivas después de la implementación.</span><span class="sxs-lookup"><span data-stu-id="c26b5-110">You initially set up archiving policies when you deploy archiving, but you can change, add, and delete policies after deployment.</span></span> <span data-ttu-id="c26b5-111">En Skype para el Panel de Control de servidor empresarial, puede usar la página **Directiva de archivado** del grupo **de archivado y supervisión** para administrar las directivas a nivel global, sitio y los niveles de usuario.</span><span class="sxs-lookup"><span data-stu-id="c26b5-111">In Skype for Business Server Control Panel, you can use the **Archiving Policy** page of the **Archiving and Monitoring** group to manage policies at the global, site, and user levels.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c26b5-112">Para controlar la implementación del archivado, es necesario especificar opciones, como por ejemplo, si archivar la mensajería instantánea (MI) o las conferencias, el uso del modo crítico y las opciones de purga.</span><span class="sxs-lookup"><span data-stu-id="c26b5-112">To control the implementation of archiving, you must specify options, such as whether to archive IM or conferencing, the use of critical mode, and purging options.</span></span> <span data-ttu-id="c26b5-113">De manera predeterminada, no hay opciones habilitadas en la configuración del archivado global ni en ninguna otra configuración de archivado de sitio o de grupo.</span><span class="sxs-lookup"><span data-stu-id="c26b5-113">By default no options are enabled in the global archiving configuration or any site or pool archiving configuration.</span></span> <span data-ttu-id="c26b5-114">Es preciso especificar todas las opciones correspondientes antes de habilitar el archivado para las comunicaciones internas o externas.</span><span class="sxs-lookup"><span data-stu-id="c26b5-114">You should specify all appropriate options before enabling archiving for internal or external communications.</span></span> <span data-ttu-id="c26b5-115">Para obtener información detallada, vea [Configurar opciones de Skype para Business Server de archivado](configure-archiving-options.md).</span><span class="sxs-lookup"><span data-stu-id="c26b5-115">For details, see [Configure archiving options for Skype for Business Server](configure-archiving-options.md).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="c26b5-116">Si habilita la integración de Microsoft Exchange para la implementación, el control de las directivas de retención de Exchange local si el archivado está habilitado para los usuarios que están ubicados en Exchange y disponer sus buzones en suspensión en contexto.</span><span class="sxs-lookup"><span data-stu-id="c26b5-116">If you enable Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange and have their mailboxes put on In-Place Hold.</span></span> 
  
<span data-ttu-id="c26b5-117">Para obtener información detallada acerca de las directivas de archivado cómo funciona, incluida la jerarquía para globales, de sitio y las directivas de usuario, consulte [Plan para el archivado en Skype para Business Server](../../plan-your-deployment/archiving/archiving.md).</span><span class="sxs-lookup"><span data-stu-id="c26b5-117">For details about how archiving policies work, including the hierarchy for global, site, and user policies, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span> <span data-ttu-id="c26b5-118">Para obtener información detallada sobre cómo administrar las directivas después de la implementación, vea [administrar las directivas de archivado en Skype para Business Server](../../manage/archiving/policies.md).</span><span class="sxs-lookup"><span data-stu-id="c26b5-118">For details about how to manage policies after deployment, see [Manage archiving policies in Skype for Business Server](../../manage/archiving/policies.md).</span></span>
  
## <a name="global-policy"></a><span data-ttu-id="c26b5-119">Directiva global</span><span class="sxs-lookup"><span data-stu-id="c26b5-119">Global policy</span></span>

<span data-ttu-id="c26b5-120">Al implementar los servidores Front-End, Skype para Business Server crea una directiva global para el archivado.</span><span class="sxs-lookup"><span data-stu-id="c26b5-120">When you deploy your Front End Servers, Skype for Business Server creates a global policy for archiving.</span></span> <span data-ttu-id="c26b5-121">De forma predeterminada, el archivado se deshabilita en la directiva global.</span><span class="sxs-lookup"><span data-stu-id="c26b5-121">By default, archiving is disabled in the global policy.</span></span> <span data-ttu-id="c26b5-122">La directiva global controla si el archivado está habilitado para las comunicaciones internas y externas de toda la implementación, a menos que la configuración de directivas de usuario o de sitio, que reemplaza la directiva global, o si utiliza la integración de Microsoft Exchange para algunos o todos los de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="c26b5-122">The global policy controls whether archiving is enabled for internal and external communications for your entire deployment, unless you set up site or user policies, which override the global policy, or if you use Microsoft Exchange integration for some or all of your users.</span></span> <span data-ttu-id="c26b5-123">Si utiliza la integración de Microsoft Exchange, la directiva global no se aplica a todos los usuarios que están ubicados en Exchange y disponer los buzones de correo en retención en contexto.</span><span class="sxs-lookup"><span data-stu-id="c26b5-123">If you use Microsoft Exchange integration, the global policy does not apply to any users who are homed on Exchange and have the mailboxes put on In-Place Hold.</span></span>
  
### <a name="configure-the-global-policy-for-archiving-for-skype-for-business-server-archiving-databases"></a><span data-ttu-id="c26b5-124">Configurar la directiva global para el archivado de Skype para bases de datos de archivado de Business Server</span><span class="sxs-lookup"><span data-stu-id="c26b5-124">Configure the global policy for archiving for Skype for Business Server archiving databases</span></span>

1. <span data-ttu-id="c26b5-125">Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="c26b5-125">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="c26b5-126">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="c26b5-126">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="c26b5-127">En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, después, en **Directiva de archivado**.</span><span class="sxs-lookup"><span data-stu-id="c26b5-127">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="c26b5-128">En la página **Directiva de archivado**, haga clic en **Global**, **Editar** y, luego, en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="c26b5-128">On the **Archiving Policy** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="c26b5-129">En **Editar directiva de archivado: global**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c26b5-129">In **Edit Archiving Policy - Global**, do the following:</span></span>
    
   - <span data-ttu-id="c26b5-130">En **Nombre**, si no desea usar el nombre predeterminado "global", especifique un nombre nuevo para la directiva global.</span><span class="sxs-lookup"><span data-stu-id="c26b5-130">In **Name**, if you do not want to use the default name of Global, specify a new name for the global policy.</span></span> 
    
   - <span data-ttu-id="c26b5-131">En **Descripción**, proporcione información acerca de la directiva (por ejemplo, la directiva Global para *divisionName* .</span><span class="sxs-lookup"><span data-stu-id="c26b5-131">In **Description**, provide information about what the policy is (for example, Global policy for  *divisionName*  .</span></span>
    
   - <span data-ttu-id="c26b5-132">Para controlar el archivado de las comunicaciones internas de todos los usuarios y sitios que no se controlan específicamente por medio de una directiva de sitio o de usuario, active o desactive la casilla **Archivar comunicaciones internas**.</span><span class="sxs-lookup"><span data-stu-id="c26b5-132">To control archiving of internal communications for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="c26b5-133">Para controlar el archivado de las comunicaciones externas de todos los usuarios y sitios que no se controlan específicamente por medio de una directiva de sitio o de usuario, active o desactive la casilla **Archivar comunicaciones externas**.</span><span class="sxs-lookup"><span data-stu-id="c26b5-133">To control archiving of external communications for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Archive external communications** check box.</span></span>
    
6. <span data-ttu-id="c26b5-134">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="c26b5-134">Click **Commit**.</span></span>
    
## <a name="site-policies"></a><span data-ttu-id="c26b5-135">Directivas de sitio</span><span class="sxs-lookup"><span data-stu-id="c26b5-135">Site policies</span></span>

<span data-ttu-id="c26b5-136">Puede habilitar o deshabilitar el archivado de sitios específicos si crea y configura una directiva de archivado para cada uno de esos sitios.</span><span class="sxs-lookup"><span data-stu-id="c26b5-136">You can enable or disable archiving for specific sites by creating an archiving policy for each of those sites.</span></span> <span data-ttu-id="c26b5-137">Las directivas de sitio invalidan las directivas globales, pero las directivas de usuario invalidan las directivas de sitio.</span><span class="sxs-lookup"><span data-stu-id="c26b5-137">A site policy overrides the global policy, but user policies override site policies.</span></span> <span data-ttu-id="c26b5-138">Las directivas de archivado sólo se aplican si no utiliza la integración de Microsoft Exchange o, si utiliza la integración de Microsoft Exchange, pero han algunos usuarios que no están ubicados en Exchange y tengan sus buzones de correo, poner en suspensión en contexto.</span><span class="sxs-lookup"><span data-stu-id="c26b5-138">Archiving policies only apply if you do not use Microsoft Exchange integration or, if you do use Microsoft Exchange integration, but have some users who are not homed on Exchange and have their mailboxes put on In-Place Hold.</span></span>
  
### <a name="create-an-archiving-policy-for-a-site"></a><span data-ttu-id="c26b5-139">Crear una directiva de archivado para un sitio</span><span class="sxs-lookup"><span data-stu-id="c26b5-139">Create an archiving policy for a site</span></span>

1. <span data-ttu-id="c26b5-140">Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="c26b5-140">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="c26b5-141">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="c26b5-141">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="c26b5-142">En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, después, en **Directiva de archivado**.</span><span class="sxs-lookup"><span data-stu-id="c26b5-142">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
    <span data-ttu-id="c26b5-143">Para obtener información detallada acerca de las directivas de archivado cómo funciona, incluida la jerarquía para globales, de sitio y las directivas de usuario, consulte [Plan para el archivado en Skype para Business Server](../../plan-your-deployment/archiving/archiving.md).</span><span class="sxs-lookup"><span data-stu-id="c26b5-143">For details about how archiving policies work, including the hierarchy for global, site, and user policies, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span>
    
4. <span data-ttu-id="c26b5-144">Haga clic en **Nuevo** y en **Directiva de sitio**.</span><span class="sxs-lookup"><span data-stu-id="c26b5-144">Click **New**, and then click **Site policy**.</span></span>
    
5. <span data-ttu-id="c26b5-145">En **Seleccionar un sitio**, haga clic en el sitio al que se aplicará la directiva.</span><span class="sxs-lookup"><span data-stu-id="c26b5-145">In **Select a site**, click the site to which the policy is to be applied.</span></span>
    
6. <span data-ttu-id="c26b5-146">En **Directiva de archivado nueva**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c26b5-146">In **New Archiving Policy**, do the following:</span></span>
    
   - <span data-ttu-id="c26b5-147">En **Nombre**, especifique el nombre para la directiva de sitio.</span><span class="sxs-lookup"><span data-stu-id="c26b5-147">In **Name**, specify the name for the site policy.</span></span> 
    
   - <span data-ttu-id="c26b5-148">En **Descripción**, proporcione información sobre la directiva de sitio (por ejemplo, directiva de sitio para Redmond).</span><span class="sxs-lookup"><span data-stu-id="c26b5-148">In **Description**, provide information about what the site policy is (for example, site policy for Redmond).</span></span>
    
   - <span data-ttu-id="c26b5-149">Para controlar el archivado de las comunicaciones internas para los sitios especificados, active o desactive la casilla **Archivar comunicaciones internas**.</span><span class="sxs-lookup"><span data-stu-id="c26b5-149">To control archiving of internal communications for the specified site, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="c26b5-150">Para controlar el archivado de las comunicaciones externas para los usuarios especificados, active o desactive la casilla **Archivar comunicaciones externas**.</span><span class="sxs-lookup"><span data-stu-id="c26b5-150">To control archiving of external communications for the specified site, select or clear the **Archive external communications** check box.</span></span>
    
7. <span data-ttu-id="c26b5-151">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="c26b5-151">Click **Commit**.</span></span>
    
## <a name="user-policies"></a><span data-ttu-id="c26b5-152">Directivas de usuario</span><span class="sxs-lookup"><span data-stu-id="c26b5-152">User policies</span></span>

<span data-ttu-id="c26b5-153">Puede habilitar o deshabilitar el archivado para determinados usuarios si crea y configura una directiva de archivado para usuarios y, después, aplica la directiva a usuarios o grupos de usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="c26b5-153">You can enable or disable archiving for specific users by creating and configuring an archiving policy for users, and then applying the policy to specific users or user groups.</span></span> <span data-ttu-id="c26b5-154">Las directivas de usuario invalidan las directivas de sitio o las directivas globales.</span><span class="sxs-lookup"><span data-stu-id="c26b5-154">User policies override any global policy or site policies.</span></span> <span data-ttu-id="c26b5-155">Las directivas de archivado sólo se aplican si no utiliza la integración de Microsoft Exchange o, si utiliza la integración de Microsoft Exchange, pero han algunos usuarios que no están ubicados en Exchange y tengan sus buzones de correo, poner en suspensión en contexto.</span><span class="sxs-lookup"><span data-stu-id="c26b5-155">Archiving policies only apply if you do not use Microsoft Exchange integration or, if you do use Microsoft Exchange integration, but have some users who are not homed on Exchange and have their mailboxes put on In-Place Hold.</span></span>
  
### <a name="configure-an-archiving-policy-for-users-homed-on-skype-for-business-server"></a><span data-ttu-id="c26b5-156">Configurar una directiva de archivado para los usuarios alojados en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="c26b5-156">Configure an archiving policy for users homed on Skype for Business Server</span></span>

1. <span data-ttu-id="c26b5-157">Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="c26b5-157">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="c26b5-158">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="c26b5-158">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="c26b5-159">En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, después, en **Directiva de archivado**.</span><span class="sxs-lookup"><span data-stu-id="c26b5-159">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="c26b5-160">Haga clic en **Nuevo** y, luego, en **Directiva de usuario**.</span><span class="sxs-lookup"><span data-stu-id="c26b5-160">Click **New**, and then click **User policy**.</span></span>
    
5. <span data-ttu-id="c26b5-161">En **Directiva de archivado nueva**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c26b5-161">In **New Archiving Policy**, do the following:</span></span>
    
   - <span data-ttu-id="c26b5-162">En **Nombre**, escriba el nombre de la directiva de usuario.</span><span class="sxs-lookup"><span data-stu-id="c26b5-162">In **Name**, specify the name for the user policy.</span></span> 
    
   - <span data-ttu-id="c26b5-163">En **Descripción**, proporcione información sobre la directiva de usuario (por ejemplo, directiva de usuario para el departamento legal).</span><span class="sxs-lookup"><span data-stu-id="c26b5-163">In **Description**, provide information about what the user policy is (for example, user policy for legal department).</span></span>
    
   - <span data-ttu-id="c26b5-164">Para controlar el archivado de las comunicaciones internas para la directiva de usuario, active o desactive la casilla **Archivar comunicaciones internas**.</span><span class="sxs-lookup"><span data-stu-id="c26b5-164">To control archiving of internal communications for the user policy, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="c26b5-165">Para controlar el archivado de las comunicaciones externas para la directiva de usuario, active o desactive la casilla **Archivar comunicaciones externas**.</span><span class="sxs-lookup"><span data-stu-id="c26b5-165">To control archiving of external communications for the user policy, select or clear the **Archive external communications** check box.</span></span>
    
6. <span data-ttu-id="c26b5-166">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="c26b5-166">Click **Commit**.</span></span>
    
<span data-ttu-id="c26b5-167">Una directiva de usuario solo se aplica a los usuarios a los que asigne la directiva.</span><span class="sxs-lookup"><span data-stu-id="c26b5-167">A user policy applies only to users to whom you assign the policy.</span></span>
### <a name="apply-a-skype-for-business-server-archiving-policy-to-a-user"></a><span data-ttu-id="c26b5-168">Aplicar un Skype para Business Server directiva a un usuario de archivado</span><span class="sxs-lookup"><span data-stu-id="c26b5-168">Apply a Skype for Business Server archiving policy to a user</span></span>

1. <span data-ttu-id="c26b5-169">Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="c26b5-169">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="c26b5-170">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="c26b5-170">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="c26b5-171">En la barra de navegación izquierda, haga clic en **Usuarios** y, luego, busque la cuenta de usuario que desea configurar.</span><span class="sxs-lookup"><span data-stu-id="c26b5-171">In the left navigation bar, click **Users**, and then search for the user account that you want to configure.</span></span>
    
4. <span data-ttu-id="c26b5-172">En la tabla donde se enumeran los resultados de la búsqueda, haga clic en la cuenta de usuario, en **Editar** y, luego, en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="c26b5-172">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="c26b5-173">En **Editar Skype para usuario Business Server** en **Directiva de archivado**, seleccione la directiva de usuario de archivado que desea aplicar.</span><span class="sxs-lookup"><span data-stu-id="c26b5-173">In **Edit Skype for Business Server user** under **Archiving policy**, select the archiving user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c26b5-174">La \*\* \<automática\> \*\* configuración aplica la configuración predeterminada de la instalación de servidor.</span><span class="sxs-lookup"><span data-stu-id="c26b5-174">The **\<Automatic\>** settings apply the default server installation settings.</span></span> <span data-ttu-id="c26b5-175">El servidor aplica automáticamente esta configuración.</span><span class="sxs-lookup"><span data-stu-id="c26b5-175">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="c26b5-176">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="c26b5-176">Click **Commit**.</span></span>
    

