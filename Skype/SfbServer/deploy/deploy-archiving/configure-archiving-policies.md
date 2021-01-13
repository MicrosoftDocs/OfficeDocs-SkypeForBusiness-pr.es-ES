---
title: Configurar directivas de archivado para Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e8e48087-d4f0-4fe1-9e7e-f2b3e07f815f
description: 'Resumen: lea este tema para obtener información sobre cómo configurar directivas de archivado iniciales para usuarios de Skype Empresarial Server.'
ms.openlocfilehash: ab737305561aa20c873bbce6e0f075d17fedd0d6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820860"
---
# <a name="configure-archiving-policies-for-skype-for-business-server"></a><span data-ttu-id="d9648-103">Configurar directivas de archivado para Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="d9648-103">Configure archiving policies for Skype for Business Server</span></span>
 
<span data-ttu-id="d9648-104">**Resumen:** Lea este tema para obtener información sobre cómo configurar directivas de archivado iniciales para usuarios de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="d9648-104">**Summary:** Read this topic to learn how to configure initial archiving policies for Skype for Business Server users.</span></span>
  
<span data-ttu-id="d9648-105">En Skype Empresarial Server, se usan directivas para habilitar y deshabilitar el archivado para comunicaciones internas y externas para los usuarios que están en Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="d9648-105">In Skype for Business Server, you use policies to enable and disable archiving for internal communications and external communications for users who are homed on Skype for Business Server.</span></span> <span data-ttu-id="d9648-106">Esto incluye lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d9648-106">This includes the following:</span></span>
  
- <span data-ttu-id="d9648-107">Una directiva global que se crea de forma predeterminada al implementar Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="d9648-107">A global policy that is created by default when you deploy Skype for Business Server</span></span>
    
- <span data-ttu-id="d9648-108">Directivas de nivel de sitio opcionales que especifican cómo se implementa el archivado para un sitio específico</span><span class="sxs-lookup"><span data-stu-id="d9648-108">Optional site-level policies that specify how archiving is implemented for a specific site</span></span>
    
- <span data-ttu-id="d9648-109">Directivas opcionales de nivel de usuario que especifican cómo se implementa el archivado para usuarios específicos</span><span class="sxs-lookup"><span data-stu-id="d9648-109">Optional user-level policies that specify how archiving is implemented for specific users</span></span>
    
<span data-ttu-id="d9648-110">Las directivas de archivado se establecen inicialmente al implementar el archivado, pero puede cambiar, agregar y eliminar directivas después de la implementación.</span><span class="sxs-lookup"><span data-stu-id="d9648-110">You initially set up archiving policies when you deploy archiving, but you can change, add, and delete policies after deployment.</span></span> <span data-ttu-id="d9648-111">En el Panel de control de  Skype Empresarial Server, puede usar la página Directiva de archivado del grupo de archivado y supervisión para administrar directivas en los niveles global, de sitio y de usuario. </span><span class="sxs-lookup"><span data-stu-id="d9648-111">In Skype for Business Server Control Panel, you can use the **Archiving Policy** page of the **Archiving and Monitoring** group to manage policies at the global, site, and user levels.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d9648-112">Para controlar la implementación del archivado, debe especificar opciones, como archivar mensajería instantánea o conferencias, el uso del modo crítico y las opciones de depuración.</span><span class="sxs-lookup"><span data-stu-id="d9648-112">To control the implementation of archiving, you must specify options, such as whether to archive IM or conferencing, the use of critical mode, and purging options.</span></span> <span data-ttu-id="d9648-113">De forma predeterminada, no hay opciones habilitadas en la configuración de archivado global ni en ninguna configuración de archivado de sitio o grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="d9648-113">By default no options are enabled in the global archiving configuration or any site or pool archiving configuration.</span></span> <span data-ttu-id="d9648-114">Debe especificar todas las opciones adecuadas antes de habilitar el archivado para las comunicaciones internas o externas.</span><span class="sxs-lookup"><span data-stu-id="d9648-114">You should specify all appropriate options before enabling archiving for internal or external communications.</span></span> <span data-ttu-id="d9648-115">Para obtener más información, [consulte Configurar las opciones de archivado para Skype Empresarial Server.](configure-archiving-options.md)</span><span class="sxs-lookup"><span data-stu-id="d9648-115">For details, see [Configure archiving options for Skype for Business Server](configure-archiving-options.md).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="d9648-116">Si habilita la integración de Microsoft Exchange para su implementación, las directivas de retención de Exchange In-Place controlan si el archivado está habilitado para los usuarios que están en Exchange y tienen sus buzones en retención In-Place local.</span><span class="sxs-lookup"><span data-stu-id="d9648-116">If you enable Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange and have their mailboxes put on In-Place Hold.</span></span> 
  
<span data-ttu-id="d9648-117">Para obtener más información sobre cómo funcionan las directivas de archivado, incluida la jerarquía de las directivas globales, de sitio y de usuario, consulte [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span><span class="sxs-lookup"><span data-stu-id="d9648-117">For details about how archiving policies work, including the hierarchy for global, site, and user policies, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span> <span data-ttu-id="d9648-118">Para obtener más información sobre cómo administrar directivas después de la implementación, consulte Administrar directivas [de archivado en Skype Empresarial Server.](../../manage/archiving/policies.md)</span><span class="sxs-lookup"><span data-stu-id="d9648-118">For details about how to manage policies after deployment, see [Manage archiving policies in Skype for Business Server](../../manage/archiving/policies.md).</span></span>
  
## <a name="global-policy"></a><span data-ttu-id="d9648-119">Directiva global</span><span class="sxs-lookup"><span data-stu-id="d9648-119">Global policy</span></span>

<span data-ttu-id="d9648-120">Al implementar los servidores front-end, Skype Empresarial Server crea una directiva global para el archivado.</span><span class="sxs-lookup"><span data-stu-id="d9648-120">When you deploy your Front End Servers, Skype for Business Server creates a global policy for archiving.</span></span> <span data-ttu-id="d9648-121">De forma predeterminada, el archivado está deshabilitado en la directiva global.</span><span class="sxs-lookup"><span data-stu-id="d9648-121">By default, archiving is disabled in the global policy.</span></span> <span data-ttu-id="d9648-122">La directiva global controla si el archivado está habilitado para comunicaciones internas y externas para toda la implementación, a menos que configure directivas de sitio o de usuario, que invalidan la directiva global, o si usa la integración de Microsoft Exchange para algunos o todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="d9648-122">The global policy controls whether archiving is enabled for internal and external communications for your entire deployment, unless you set up site or user policies, which override the global policy, or if you use Microsoft Exchange integration for some or all of your users.</span></span> <span data-ttu-id="d9648-123">Si usa la integración de Microsoft Exchange, la directiva global no se aplica a ningún usuario que se encuentra en Exchange y que tiene los buzones en retención In-Place local.</span><span class="sxs-lookup"><span data-stu-id="d9648-123">If you use Microsoft Exchange integration, the global policy does not apply to any users who are homed on Exchange and have the mailboxes put on In-Place Hold.</span></span>
  
### <a name="configure-the-global-policy-for-archiving-for-skype-for-business-server-archiving-databases"></a><span data-ttu-id="d9648-124">Configurar la directiva global de archivado para las bases de datos de archivado de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="d9648-124">Configure the global policy for archiving for Skype for Business Server archiving databases</span></span>

1. <span data-ttu-id="d9648-125">Desde una cuenta de usuario asignada al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="d9648-125">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="d9648-126">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="d9648-126">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="d9648-127">En la barra de navegación izquierda, haga clic en **Configuración y archivado** y, a continuación, en **Directiva de archivado**.</span><span class="sxs-lookup"><span data-stu-id="d9648-127">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="d9648-128">En la página **Directiva de** archivado, haga clic **en Global**, **Editar** y, a continuación, en **Mostrar detalles.**</span><span class="sxs-lookup"><span data-stu-id="d9648-128">On the **Archiving Policy** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="d9648-129">En **Editar directiva de archivado - Global**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d9648-129">In **Edit Archiving Policy - Global**, do the following:</span></span>
    
   - <span data-ttu-id="d9648-130">En **Nombre**, si no desea usar el nombre predeterminado de Global, especifique un nombre nuevo para la directiva global.</span><span class="sxs-lookup"><span data-stu-id="d9648-130">In **Name**, if you do not want to use the default name of Global, specify a new name for the global policy.</span></span> 
    
   - <span data-ttu-id="d9648-131">En **Descripción,** proporcione información sobre cuál es la directiva (por ejemplo, Directiva global para  *divisionName*  .</span><span class="sxs-lookup"><span data-stu-id="d9648-131">In **Description**, provide information about what the policy is (for example, Global policy for  *divisionName*  .</span></span>
    
   - <span data-ttu-id="d9648-132">Para controlar el archivado de las comunicaciones internas de todos los usuarios y sitios que no se controlan específicamente mediante una directiva de sitio o de usuario, active o desactive la casilla **Archivar comunicaciones internas**.</span><span class="sxs-lookup"><span data-stu-id="d9648-132">To control archiving of internal communications for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="d9648-133">Para controlar el archivado de comunicaciones externas para todos los sitios y usuarios que no se controlan específicamente a través de una directiva de sitio o directiva de usuario, active o desactive la casilla Archivar **comunicaciones** externas.</span><span class="sxs-lookup"><span data-stu-id="d9648-133">To control archiving of external communications for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Archive external communications** check box.</span></span>
    
6. <span data-ttu-id="d9648-134">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="d9648-134">Click **Commit**.</span></span>
    
## <a name="site-policies"></a><span data-ttu-id="d9648-135">Directivas del sitio</span><span class="sxs-lookup"><span data-stu-id="d9648-135">Site policies</span></span>

<span data-ttu-id="d9648-136">Puede habilitar o deshabilitar el archivado para sitios específicos mediante la creación de una directiva de archivado para cada uno de esos sitios.</span><span class="sxs-lookup"><span data-stu-id="d9648-136">You can enable or disable archiving for specific sites by creating an archiving policy for each of those sites.</span></span> <span data-ttu-id="d9648-137">Las directiva de sitio anulan la directiva global pero las directivas de usuario anulan las directivas de sitio.</span><span class="sxs-lookup"><span data-stu-id="d9648-137">A site policy overrides the global policy, but user policies override site policies.</span></span> <span data-ttu-id="d9648-138">Las directivas de archivado solo se aplican si no usa la integración de Microsoft Exchange o, si usa la integración de Microsoft Exchange, pero tiene algunos usuarios que no están en Exchange y tienen sus buzones en retención In-Place local.</span><span class="sxs-lookup"><span data-stu-id="d9648-138">Archiving policies only apply if you do not use Microsoft Exchange integration or, if you do use Microsoft Exchange integration, but have some users who are not homed on Exchange and have their mailboxes put on In-Place Hold.</span></span>
  
### <a name="create-an-archiving-policy-for-a-site"></a><span data-ttu-id="d9648-139">Crear una directiva de archivado para un sitio</span><span class="sxs-lookup"><span data-stu-id="d9648-139">Create an archiving policy for a site</span></span>

1. <span data-ttu-id="d9648-140">Desde una cuenta de usuario asignada al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="d9648-140">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="d9648-141">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="d9648-141">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="d9648-142">En la barra de navegación izquierda, haga clic en **Configuración y archivado** y, a continuación, en **Directiva de archivado**.</span><span class="sxs-lookup"><span data-stu-id="d9648-142">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
    <span data-ttu-id="d9648-143">Para obtener más información sobre cómo funcionan las directivas de archivado, incluida la jerarquía de las directivas globales, de sitio y de usuario, consulte [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span><span class="sxs-lookup"><span data-stu-id="d9648-143">For details about how archiving policies work, including the hierarchy for global, site, and user policies, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span>
    
4. <span data-ttu-id="d9648-144">Haga clic en  **Nuevo** y en  **Directiva de sitio**.</span><span class="sxs-lookup"><span data-stu-id="d9648-144">Click **New**, and then click **Site policy**.</span></span>
    
5. <span data-ttu-id="d9648-145">En  **Seleccionar un sitio**, haga clic en el sitio al que se va a aplicar la directiva.</span><span class="sxs-lookup"><span data-stu-id="d9648-145">In **Select a site**, click the site to which the policy is to be applied.</span></span>
    
6. <span data-ttu-id="d9648-146">En  **Directiva de archivado nueva**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d9648-146">In **New Archiving Policy**, do the following:</span></span>
    
   - <span data-ttu-id="d9648-147">En  **Nombre**, especifique el nombre para la directiva de sitio.</span><span class="sxs-lookup"><span data-stu-id="d9648-147">In **Name**, specify the name for the site policy.</span></span> 
    
   - <span data-ttu-id="d9648-148">En **Descripción**, proporcione información sobre la función de la directiva de sitio (por ejemplo, directiva de archivado de usuarios externos para Redmond).</span><span class="sxs-lookup"><span data-stu-id="d9648-148">In **Description**, provide information about what the site policy is (for example, site policy for Redmond).</span></span>
    
   - <span data-ttu-id="d9648-149">Para controlar el archivado de comunicaciones internas para los sitios especificados, active o desactive la casilla  **Archivar comunicaciones internas**.</span><span class="sxs-lookup"><span data-stu-id="d9648-149">To control archiving of internal communications for the specified site, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="d9648-150">Para controlar el archivado de comunicaciones externas para los usuarios especificados, active o desactive la casilla  **Archivar comunicaciones externas**.</span><span class="sxs-lookup"><span data-stu-id="d9648-150">To control archiving of external communications for the specified site, select or clear the **Archive external communications** check box.</span></span>
    
7. <span data-ttu-id="d9648-151">Haga clic en  **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="d9648-151">Click **Commit**.</span></span>
    
## <a name="user-policies"></a><span data-ttu-id="d9648-152">Directivas de usuario</span><span class="sxs-lookup"><span data-stu-id="d9648-152">User policies</span></span>

<span data-ttu-id="d9648-153">Puede habilitar o deshabilitar el archivado para usuarios específicos creando y configurando una directiva de archivado para usuarios y, a continuación, aplicando la directiva a usuarios o grupos de usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="d9648-153">You can enable or disable archiving for specific users by creating and configuring an archiving policy for users, and then applying the policy to specific users or user groups.</span></span> <span data-ttu-id="d9648-154">Las directivas de usuario invalidan cualquier directiva global o de sitio.</span><span class="sxs-lookup"><span data-stu-id="d9648-154">User policies override any global policy or site policies.</span></span> <span data-ttu-id="d9648-155">Las directivas de archivado solo se aplican si no usa la integración de Microsoft Exchange o, si usa la integración de Microsoft Exchange, pero tiene algunos usuarios que no están en Exchange y tienen sus buzones en retención In-Place local.</span><span class="sxs-lookup"><span data-stu-id="d9648-155">Archiving policies only apply if you do not use Microsoft Exchange integration or, if you do use Microsoft Exchange integration, but have some users who are not homed on Exchange and have their mailboxes put on In-Place Hold.</span></span>
  
### <a name="configure-an-archiving-policy-for-users-homed-on-skype-for-business-server"></a><span data-ttu-id="d9648-156">Configurar una directiva de archivado para los usuarios que están en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="d9648-156">Configure an archiving policy for users homed on Skype for Business Server</span></span>

1. <span data-ttu-id="d9648-157">Desde una cuenta de usuario asignada al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="d9648-157">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="d9648-158">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="d9648-158">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="d9648-159">En la barra de navegación izquierda, haga clic en **Configuración y archivado** y, a continuación, en **Directiva de archivado**.</span><span class="sxs-lookup"><span data-stu-id="d9648-159">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="d9648-160">Haga clic en **Nuevo** y en **Directiva de usuario**.</span><span class="sxs-lookup"><span data-stu-id="d9648-160">Click **New**, and then click **User policy**.</span></span>
    
5. <span data-ttu-id="d9648-161">En **Nueva directiva de archivado**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d9648-161">In **New Archiving Policy**, do the following:</span></span>
    
   - <span data-ttu-id="d9648-162">En **Nombre**, escriba el nombre de la directiva de usuario.</span><span class="sxs-lookup"><span data-stu-id="d9648-162">In **Name**, specify the name for the user policy.</span></span> 
    
   - <span data-ttu-id="d9648-163">En **Descripción**, proporcione información sobre cuál es la directiva de usuario (por ejemplo, directiva de usuario para el departamento legal).</span><span class="sxs-lookup"><span data-stu-id="d9648-163">In **Description**, provide information about what the user policy is (for example, user policy for legal department).</span></span>
    
   - <span data-ttu-id="d9648-164">Para controlar el archivado de las comunicaciones internas para la directiva de usuario, seleccione o anule la selección de la casilla de verificación **Archivar comunicaciones internas**.</span><span class="sxs-lookup"><span data-stu-id="d9648-164">To control archiving of internal communications for the user policy, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="d9648-165">Para controlar el archivado de las comunicaciones externas para la directiva de usuario, seleccione o anule la selección de la casilla de verificación **Archivar comunicaciones externas**.</span><span class="sxs-lookup"><span data-stu-id="d9648-165">To control archiving of external communications for the user policy, select or clear the **Archive external communications** check box.</span></span>
    
6. <span data-ttu-id="d9648-166">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="d9648-166">Click **Commit**.</span></span>
    
<span data-ttu-id="d9648-167">Una directiva de usuario solo se aplica a los usuarios a los que asigne la directiva.</span><span class="sxs-lookup"><span data-stu-id="d9648-167">A user policy applies only to users to whom you assign the policy.</span></span>
### <a name="apply-a-skype-for-business-server-archiving-policy-to-a-user"></a><span data-ttu-id="d9648-168">Aplicar una directiva de archivado de Skype Empresarial Server a un usuario</span><span class="sxs-lookup"><span data-stu-id="d9648-168">Apply a Skype for Business Server archiving policy to a user</span></span>

1. <span data-ttu-id="d9648-169">Desde una cuenta de usuario asignada al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="d9648-169">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="d9648-170">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="d9648-170">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="d9648-171">En la barra de navegación izquierda, haga clic en **Usuarios** y, a continuación, busque la cuenta de usuario que quiera configurar.</span><span class="sxs-lookup"><span data-stu-id="d9648-171">In the left navigation bar, click **Users**, and then search for the user account that you want to configure.</span></span>
    
4. <span data-ttu-id="d9648-172">En la tabla donde se enumeran los resultados de la búsqueda, haga clic en la cuenta de usuario, en **Editar** y, a continuación, en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="d9648-172">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="d9648-173">En **Editar usuario de Skype Empresarial Server** en la directiva **de** archivado, seleccione la directiva de usuario de archivado que desee aplicar.</span><span class="sxs-lookup"><span data-stu-id="d9648-173">In **Edit Skype for Business Server user** under **Archiving policy**, select the archiving user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d9648-174">La **\<Automatic\>** configuración aplica la configuración de instalación predeterminada del servidor.</span><span class="sxs-lookup"><span data-stu-id="d9648-174">The **\<Automatic\>** settings apply the default server installation settings.</span></span> <span data-ttu-id="d9648-175">Esta configuración se aplica automáticamente por el servidor.</span><span class="sxs-lookup"><span data-stu-id="d9648-175">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="d9648-176">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="d9648-176">Click **Commit**.</span></span>
    

