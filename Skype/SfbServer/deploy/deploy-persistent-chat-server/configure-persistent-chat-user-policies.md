---
title: Configurar las directivas de usuario del chat persistente de Skype Empresarial Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5862480-95f8-4d76-a2b5-940cd995e93c
description: 'Resumen: Leer este tema para aprender a crear directivas de usuario inicial para servidor de Chat persistente en Skype para Business Server 2015. Las directivas de usuario persistentes de charla determinan si los usuarios tienen acceso a salones de chat.'
ms.openlocfilehash: 01ed6eb048f1949c93260c554eb58d0c76c5259f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="configure-persistent-chat-user-policies-in-skype-for-business-server-2015"></a><span data-ttu-id="23abf-104">Configurar las directivas de usuario del chat persistente de Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="23abf-104">Configure Persistent Chat user policies in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="23abf-105">**Resumen:** Lea este tema para aprender a crear directivas de usuario inicial para servidor de Chat persistente en Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="23abf-105">**Summary:** Read this topic to learn how to create initial user policies for Persistent Chat Server in Skype for Business Server 2015.</span></span> <span data-ttu-id="23abf-106">Las directivas de usuario persistentes de charla determinan si los usuarios tienen acceso a salones de chat.</span><span class="sxs-lookup"><span data-stu-id="23abf-106">Persistent Chat user policies determine whether or not users are allowed access to chat rooms.</span></span>
  
<span data-ttu-id="23abf-107">Puede administrar las directivas de usuario de servidor de charla persistente en los siguientes niveles: global, sitio o usuario.</span><span class="sxs-lookup"><span data-stu-id="23abf-107">You can manage Persistent Chat Server user policies at the following levels: global, site, or user.</span></span> <span data-ttu-id="23abf-108">Inicialmente, configurar la directiva global para habilitar la configuración de Chat persistentes para todos los usuarios en la implementación y luego crear directivas de sitios y de usuario para controlar si la charla persistente está activado para sitios y usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="23abf-108">Initially, you configure the global policy to enable Persistent Chat settings for all users in your deployment, and then create additional user and site policies to control whether Persistent Chat is turned on for specific users and sites.</span></span>
  
<span data-ttu-id="23abf-109">Este tema incluye las secciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="23abf-109">This topic contains the following sections:</span></span>
  
- <span data-ttu-id="23abf-110">Configurar la directiva global</span><span class="sxs-lookup"><span data-stu-id="23abf-110">Configure the global policy</span></span>
    
- <span data-ttu-id="23abf-111">Crear una directiva de sitio</span><span class="sxs-lookup"><span data-stu-id="23abf-111">Create a site policy</span></span>
    
- <span data-ttu-id="23abf-112">Crear una directiva de usuario</span><span class="sxs-lookup"><span data-stu-id="23abf-112">Create a user policy</span></span>
    
- <span data-ttu-id="23abf-113">Aplicar una directiva a un usuario o a un grupo de usuarios</span><span class="sxs-lookup"><span data-stu-id="23abf-113">Apply a policy to a user or user group</span></span>
    
## <a name="configure-the-global-policy"></a><span data-ttu-id="23abf-114">Configurar la directiva global</span><span class="sxs-lookup"><span data-stu-id="23abf-114">Configure the global policy</span></span>

<span data-ttu-id="23abf-115">Para configurar la directiva global:</span><span class="sxs-lookup"><span data-stu-id="23abf-115">To configure the global policy:</span></span>
  
1. <span data-ttu-id="23abf-116">En una cuenta de usuario asignada al rol CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="23abf-116">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="23abf-117">Desde el menú **Inicio** , seleccione el Skype para Panel de Control de servidor de Business o abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin.</span><span class="sxs-lookup"><span data-stu-id="23abf-117">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="23abf-118">En Skype para Business Server Control Panel, haga clic en **Charla persistente**y, a continuación, haga clic en **Directiva de Chat persistentes**.</span><span class="sxs-lookup"><span data-stu-id="23abf-118">In Skype for Business Server Control Panel, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="23abf-119">Haga clic en **Global** en la lista de directivas, en **Editar** y, luego, en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="23abf-119">Click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="23abf-120">En **Editar directiva de chat persistente - Global**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="23abf-120">In **Edit Persistent Chat Policy - Global**, do the following:</span></span> 
    
   - <span data-ttu-id="23abf-121">En **Nombre**, especifique un nuevo nombre para la directiva global si no desea usar el valor predeterminado de Global.</span><span class="sxs-lookup"><span data-stu-id="23abf-121">In **Name**, specify a new name for the global policy, if you do not want to use the default of Global.</span></span>
    
   - <span data-ttu-id="23abf-122">En **Descripción**, proporcione detalles acerca de la directiva de usuario (por ejemplo, la directiva Global para _centralSiteName_).</span><span class="sxs-lookup"><span data-stu-id="23abf-122">In **Description**, provide details about what the user policy is (for example, Global policy for  _centralSiteName_).</span></span>
    
   - <span data-ttu-id="23abf-123">Para controlar la charla persistente para todos los sitios y los usuarios que no específicamente se controla a través de una directiva de sitio o usuario, active o desactive la casilla de verificación **Habilitar Chat persistente** .</span><span class="sxs-lookup"><span data-stu-id="23abf-123">To control Persistent Chat for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="23abf-124">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="23abf-124">Click **Commit**.</span></span>
    
## <a name="create-a-site-policy"></a><span data-ttu-id="23abf-125">Crear una directiva de sitio</span><span class="sxs-lookup"><span data-stu-id="23abf-125">Create a site policy</span></span>

<span data-ttu-id="23abf-126">Para cada sitio que ha implementado, puede crear una directiva de chat persistente específica para el sitio.</span><span class="sxs-lookup"><span data-stu-id="23abf-126">For each site that you have deployed, you can create a site-specific Persistent Chat policy.</span></span> <span data-ttu-id="23abf-127">La configuración de la directiva de sitio reemplaza la directiva global, pero solo para el sitio específico que abarca la directiva de sitio.</span><span class="sxs-lookup"><span data-stu-id="23abf-127">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span> <span data-ttu-id="23abf-128">Para crear una directiva de sitio:</span><span class="sxs-lookup"><span data-stu-id="23abf-128">To create a site policy:</span></span>
  
1. <span data-ttu-id="23abf-129">En una cuenta de usuario asignada al rol CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="23abf-129">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="23abf-130">Desde el menú **Inicio** , seleccione el Skype para Panel de Control de servidor de Business o abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin.</span><span class="sxs-lookup"><span data-stu-id="23abf-130">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="23abf-131">En la barra de navegación izquierda, haga clic en **Chat persistente** y, luego, en **Directiva de chat persistente**.</span><span class="sxs-lookup"><span data-stu-id="23abf-131">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="23abf-132">Haga clic en **Nuevo** y en **Directiva de sitio**.</span><span class="sxs-lookup"><span data-stu-id="23abf-132">Click **New**, and then click **Site policy**.</span></span>
    
5. <span data-ttu-id="23abf-133">En **Seleccionar un sitio**, haga clic en el sitio al que se va a aplicar la directiva.</span><span class="sxs-lookup"><span data-stu-id="23abf-133">In **Select a Site**, click the site to which the policy is to be applied.</span></span>
    
6. <span data-ttu-id="23abf-134">En **Nueva directiva de chat persistente**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="23abf-134">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="23abf-135">En **Nombre**, especifique un nombre para la nueva directiva de sitio (por ejemplo, Redmond).</span><span class="sxs-lookup"><span data-stu-id="23abf-135">In **Name**, specify a name for the new site policy (for example, Redmond).</span></span>
    
   - <span data-ttu-id="23abf-136">En **Descripción**, dé detalles sobre lo que es la directiva del sitio (por ejemplo, directiva de salón de chat de Redmond).</span><span class="sxs-lookup"><span data-stu-id="23abf-136">In **Description**, provide details about what the site policy is (for example, chat room policy for Redmond).</span></span>
    
   - <span data-ttu-id="23abf-137">Para controlar el chat persistente para todos los sitios no controlados específicamente con una directiva de sitio, active o desactive la casilla **Habilitar chat persistente**.</span><span class="sxs-lookup"><span data-stu-id="23abf-137">To control Persistent Chat for all sites not specifically controlled through a site policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
7. <span data-ttu-id="23abf-138">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="23abf-138">Click **Commit**.</span></span>
    
## <a name="create-a-user-policy"></a><span data-ttu-id="23abf-139">Crear una directiva de usuario</span><span class="sxs-lookup"><span data-stu-id="23abf-139">Create a user policy</span></span>

<span data-ttu-id="23abf-140">Puede crear directivas de usuario específicas que reemplazan la directiva global y todas las directivas de sitio que abarcan al usuario.</span><span class="sxs-lookup"><span data-stu-id="23abf-140">You can create user-specific policies that override the global policy and any site policies to which the user belongs.</span></span> <span data-ttu-id="23abf-141">Para crear una directiva de usuario:</span><span class="sxs-lookup"><span data-stu-id="23abf-141">To create a user policy:</span></span>
  
1. <span data-ttu-id="23abf-142">En una cuenta de usuario asignada al rol CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="23abf-142">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="23abf-143">Desde el menú **Inicio** , seleccione el Skype para Panel de Control de servidor de Business o abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin.</span><span class="sxs-lookup"><span data-stu-id="23abf-143">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="23abf-144">En la barra de navegación izquierda, haga clic en **Chat persistente** y, luego, en **Directiva de chat persistente**.</span><span class="sxs-lookup"><span data-stu-id="23abf-144">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="23abf-145">Haga clic en **Nuevo** y, luego, en **Directiva de usuario**.</span><span class="sxs-lookup"><span data-stu-id="23abf-145">Click **New**, and then click **User policy**.</span></span>
    
5. <span data-ttu-id="23abf-146">En **Nueva directiva de chat persistente**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="23abf-146">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="23abf-147">En **Nombre**, especifique un nombre para la nueva directiva de usuario.</span><span class="sxs-lookup"><span data-stu-id="23abf-147">In **Name**, specify a name for the new user policy.</span></span>
    
   - <span data-ttu-id="23abf-148">En **Descripción**, proporcione detalles acerca de la directiva de usuario (por ejemplo, la directiva persistente de charla para un usuario específico).</span><span class="sxs-lookup"><span data-stu-id="23abf-148">In **Description**, provide details about what the user policy is (for example, Persistent Chat policy for specific user).</span></span>
    
   - <span data-ttu-id="23abf-149">Para controlar la charla persistente para todos los usuarios que no están controlados específicamente a través de una directiva de usuario, active o desactive la casilla de verificación **Habilitar Chat persistente** .</span><span class="sxs-lookup"><span data-stu-id="23abf-149">To control Persistent Chat for all users who are not specifically controlled through a user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="23abf-150">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="23abf-150">Click **Commit**.</span></span>
    
## <a name="apply-a-policy-to-a-user-account"></a><span data-ttu-id="23abf-151">Aplicar una directiva a una cuenta de usuario</span><span class="sxs-lookup"><span data-stu-id="23abf-151">Apply a policy to a user account</span></span>

<span data-ttu-id="23abf-152">Después de crear políticas, puede aplicarlas a una cuenta de usuario de esta manera:</span><span class="sxs-lookup"><span data-stu-id="23abf-152">After you create policies, you can apply them to a user account as follows:</span></span>
  
1. <span data-ttu-id="23abf-153">En una cuenta de usuario asignada al rol CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="23abf-153">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="23abf-154">Desde el menú **Inicio** , seleccione el Skype para Panel de Control de servidor de Business o abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin.</span><span class="sxs-lookup"><span data-stu-id="23abf-154">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="23abf-155">En la barra de navegación izquierda, haga clic en **Usuarios** y, luego, busque la cuenta de usuario que desea configurar.</span><span class="sxs-lookup"><span data-stu-id="23abf-155">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>
    
4. <span data-ttu-id="23abf-156">En la tabla donde se enumeran los resultados de la búsqueda, haga clic en la cuenta de usuario, en **Editar** y, finalmente, en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="23abf-156">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="23abf-157">En **Editar Skype para usuarios de servidores de empresa** en **charla persistente de la política**, seleccione la directiva de usuario persistentes de charla que desea aplicar.</span><span class="sxs-lookup"><span data-stu-id="23abf-157">In **Edit Skype for Business Server User** under **Persistent Chat policy**, select the Persistent Chat user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="23abf-158">La ** \<automática\> ** configuración aplica la directiva efectiva de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="23abf-158">The **\<Automatic\>** settings apply the default effective policy.</span></span> <span data-ttu-id="23abf-159">El servidor aplica esta configuración automáticamente.</span><span class="sxs-lookup"><span data-stu-id="23abf-159">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="23abf-160">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="23abf-160">Click **Commit**.</span></span>
    

