---
title: Configurar las directivas de usuario del chat persistente de Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5862480-95f8-4d76-a2b5-940cd995e93c
description: 'Resumen: Lea este tema para obtener información sobre cómo crear directivas de usuario inicial para el servidor de Chat persistente en Skype para Business Server 2015. Las directivas de usuario de charla persistentes determinan si los usuarios pueden acceder a salones de chat.'
ms.openlocfilehash: 84bc1236bf8fd08063f55c9a0c3b0d63ff4eb280
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33894510"
---
# <a name="configure-persistent-chat-user-policies-in-skype-for-business-server-2015"></a><span data-ttu-id="2c03c-104">Configurar las directivas de usuario del chat persistente de Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="2c03c-104">Configure Persistent Chat user policies in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="2c03c-105">**Resumen:** Lea este tema para obtener información sobre cómo crear directivas de usuario inicial para el servidor de Chat persistente en Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="2c03c-105">**Summary:** Read this topic to learn how to create initial user policies for Persistent Chat Server in Skype for Business Server 2015.</span></span> <span data-ttu-id="2c03c-106">Las directivas de usuario de charla persistentes determinan si los usuarios pueden acceder a salones de chat.</span><span class="sxs-lookup"><span data-stu-id="2c03c-106">Persistent Chat user policies determine whether or not users are allowed access to chat rooms.</span></span>
  
<span data-ttu-id="2c03c-107">Puede administrar las directivas de usuario del servidor de Chat persistente en los siguientes niveles: global, sitio o usuario.</span><span class="sxs-lookup"><span data-stu-id="2c03c-107">You can manage Persistent Chat Server user policies at the following levels: global, site, or user.</span></span> <span data-ttu-id="2c03c-108">Inicialmente, configurar la directiva global para habilitar la configuración de Chat persistente para todos los usuarios de la implementación y, a continuación, crear las directivas de sitio y de usuario para controlar si Chat persistente está activado para determinados usuarios y sitios.</span><span class="sxs-lookup"><span data-stu-id="2c03c-108">Initially, you configure the global policy to enable Persistent Chat settings for all users in your deployment, and then create additional user and site policies to control whether Persistent Chat is turned on for specific users and sites.</span></span>
  
<span data-ttu-id="2c03c-109">Este tema incluye las secciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="2c03c-109">This topic contains the following sections:</span></span>
  
- <span data-ttu-id="2c03c-110">Configurar la directiva global</span><span class="sxs-lookup"><span data-stu-id="2c03c-110">Configure the global policy</span></span>
    
- <span data-ttu-id="2c03c-111">Crear una directiva de sitio</span><span class="sxs-lookup"><span data-stu-id="2c03c-111">Create a site policy</span></span>
    
- <span data-ttu-id="2c03c-112">Crear una directiva de usuario</span><span class="sxs-lookup"><span data-stu-id="2c03c-112">Create a user policy</span></span>
    
- <span data-ttu-id="2c03c-113">Aplicar una directiva a un usuario o a un grupo de usuarios</span><span class="sxs-lookup"><span data-stu-id="2c03c-113">Apply a policy to a user or user group</span></span>
    
> [!NOTE] 
> <span data-ttu-id="2c03c-114">Chat persistente está disponible en Skype para Business Server 2015, pero ya no se admite en Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="2c03c-114">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="2c03c-115">La misma funcionalidad está disponible en los equipos.</span><span class="sxs-lookup"><span data-stu-id="2c03c-115">The same functionality is available in Teams.</span></span> <span data-ttu-id="2c03c-116">Para obtener más información, vea [viaje de Skype para la empresa a los equipos de Microsoft](/microsoftteams/journey-skypeforbusiness-teams).</span><span class="sxs-lookup"><span data-stu-id="2c03c-116">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="2c03c-117">Si necesita usar chat en grupo, las opciones son para migrar los usuarios que requieren esta funcionalidad a los equipos, o para continuar usando Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="2c03c-117">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>

## <a name="configure-the-global-policy"></a><span data-ttu-id="2c03c-118">Configurar la directiva global</span><span class="sxs-lookup"><span data-stu-id="2c03c-118">Configure the global policy</span></span>

<span data-ttu-id="2c03c-119">Para configurar la directiva global:</span><span class="sxs-lookup"><span data-stu-id="2c03c-119">To configure the global policy:</span></span>
  
1. <span data-ttu-id="2c03c-120">Inicie sesión en cualquier equipo de la implementación interna con una cuenta de usuario asignada a los roles CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="2c03c-120">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="2c03c-121">Desde el menú **Inicio** , seleccione el Skype para el Panel de Control de servidor empresarial o abra una ventana del explorador y, a continuación, escriba la dirección URL de administración.</span><span class="sxs-lookup"><span data-stu-id="2c03c-121">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="2c03c-122">En Skype para el Panel de Control de servidor empresarial, haga clic en **Chat persistente**y, a continuación, haga clic en **Directiva de Chat persistente**.</span><span class="sxs-lookup"><span data-stu-id="2c03c-122">In Skype for Business Server Control Panel, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="2c03c-123">Haga clic en **Global** en la lista de directivas, en **Editar** y, luego, en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="2c03c-123">Click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="2c03c-124">En **Editar directiva de chat persistente - Global**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2c03c-124">In **Edit Persistent Chat Policy - Global**, do the following:</span></span> 
    
   - <span data-ttu-id="2c03c-125">En **Nombre**, especifique un nuevo nombre para la directiva global si no desea usar el valor predeterminado de Global.</span><span class="sxs-lookup"><span data-stu-id="2c03c-125">In **Name**, specify a new name for the global policy, if you do not want to use the default of Global.</span></span>
    
   - <span data-ttu-id="2c03c-126">En **Descripción**, proporcione información detallada acerca de la directiva de usuario (por ejemplo, directiva Global de _centralSiteName_).</span><span class="sxs-lookup"><span data-stu-id="2c03c-126">In **Description**, provide details about what the user policy is (for example, Global policy for  _centralSiteName_).</span></span>
    
   - <span data-ttu-id="2c03c-127">Para controlar el Chat persistente para todos los sitios y los usuarios no controlados específicamente mediante una directiva de sitio o usuario, active o desactive la casilla de verificación **Habilitar Chat persistente** .</span><span class="sxs-lookup"><span data-stu-id="2c03c-127">To control Persistent Chat for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="2c03c-128">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="2c03c-128">Click **Commit**.</span></span>
    
## <a name="create-a-site-policy"></a><span data-ttu-id="2c03c-129">Crear una directiva de sitio</span><span class="sxs-lookup"><span data-stu-id="2c03c-129">Create a site policy</span></span>

<span data-ttu-id="2c03c-130">Para cada sitio que ha implementado, puede crear una directiva de chat persistente específica para el sitio.</span><span class="sxs-lookup"><span data-stu-id="2c03c-130">For each site that you have deployed, you can create a site-specific Persistent Chat policy.</span></span> <span data-ttu-id="2c03c-131">La configuración de la directiva de sitio reemplaza la directiva global, pero solo para el sitio específico que abarca la directiva de sitio.</span><span class="sxs-lookup"><span data-stu-id="2c03c-131">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span> <span data-ttu-id="2c03c-132">Para crear una directiva de sitio:</span><span class="sxs-lookup"><span data-stu-id="2c03c-132">To create a site policy:</span></span>
  
1. <span data-ttu-id="2c03c-133">Inicie sesión en cualquier equipo de la implementación interna con una cuenta de usuario asignada a los roles CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="2c03c-133">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="2c03c-134">Desde el menú **Inicio** , seleccione el Skype para el Panel de Control de servidor empresarial o abra una ventana del explorador y, a continuación, escriba la dirección URL de administración.</span><span class="sxs-lookup"><span data-stu-id="2c03c-134">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="2c03c-135">En la barra de navegación izquierda, haga clic en **Chat persistente** y, luego, en **Directiva de chat persistente**.</span><span class="sxs-lookup"><span data-stu-id="2c03c-135">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="2c03c-136">Haga clic en **Nuevo** y en **Directiva de sitio**.</span><span class="sxs-lookup"><span data-stu-id="2c03c-136">Click **New**, and then click **Site policy**.</span></span>
    
5. <span data-ttu-id="2c03c-137">En **Seleccionar un sitio**, haga clic en el sitio al que se va a aplicar la directiva.</span><span class="sxs-lookup"><span data-stu-id="2c03c-137">In **Select a Site**, click the site to which the policy is to be applied.</span></span>
    
6. <span data-ttu-id="2c03c-138">En **Nueva directiva de chat persistente**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2c03c-138">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="2c03c-139">En **Nombre**, especifique un nombre para la nueva directiva de sitio (por ejemplo, Redmond).</span><span class="sxs-lookup"><span data-stu-id="2c03c-139">In **Name**, specify a name for the new site policy (for example, Redmond).</span></span>
    
   - <span data-ttu-id="2c03c-140">En **Descripción**, dé detalles sobre lo que es la directiva del sitio (por ejemplo, directiva de salón de chat de Redmond).</span><span class="sxs-lookup"><span data-stu-id="2c03c-140">In **Description**, provide details about what the site policy is (for example, chat room policy for Redmond).</span></span>
    
   - <span data-ttu-id="2c03c-141">Para controlar el chat persistente para todos los sitios no controlados específicamente con una directiva de sitio, active o desactive la casilla **Habilitar chat persistente**.</span><span class="sxs-lookup"><span data-stu-id="2c03c-141">To control Persistent Chat for all sites not specifically controlled through a site policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
7. <span data-ttu-id="2c03c-142">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="2c03c-142">Click **Commit**.</span></span>
    
## <a name="create-a-user-policy"></a><span data-ttu-id="2c03c-143">Crear una directiva de usuario</span><span class="sxs-lookup"><span data-stu-id="2c03c-143">Create a user policy</span></span>

<span data-ttu-id="2c03c-144">Puede crear directivas de usuario específicas que reemplazan la directiva global y todas las directivas de sitio que abarcan al usuario.</span><span class="sxs-lookup"><span data-stu-id="2c03c-144">You can create user-specific policies that override the global policy and any site policies to which the user belongs.</span></span> <span data-ttu-id="2c03c-145">Para crear una directiva de usuario:</span><span class="sxs-lookup"><span data-stu-id="2c03c-145">To create a user policy:</span></span>
  
1. <span data-ttu-id="2c03c-146">Inicie sesión en cualquier equipo de la implementación interna con una cuenta de usuario asignada a los roles CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="2c03c-146">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="2c03c-147">Desde el menú **Inicio** , seleccione el Skype para el Panel de Control de servidor empresarial o abra una ventana del explorador y, a continuación, escriba la dirección URL de administración.</span><span class="sxs-lookup"><span data-stu-id="2c03c-147">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="2c03c-148">En la barra de navegación izquierda, haga clic en **Chat persistente** y, luego, en **Directiva de chat persistente**.</span><span class="sxs-lookup"><span data-stu-id="2c03c-148">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="2c03c-149">Haga clic en **Nuevo** y, luego, en **Directiva de usuario**.</span><span class="sxs-lookup"><span data-stu-id="2c03c-149">Click **New**, and then click **User policy**.</span></span>
    
5. <span data-ttu-id="2c03c-150">En **Nueva directiva de chat persistente**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2c03c-150">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="2c03c-151">En **Nombre**, especifique un nombre para la nueva directiva de usuario.</span><span class="sxs-lookup"><span data-stu-id="2c03c-151">In **Name**, specify a name for the new user policy.</span></span>
    
   - <span data-ttu-id="2c03c-152">En **Descripción**, proporcione información detallada acerca de la directiva de usuario (por ejemplo, directiva de Chat persistente para usuario específico).</span><span class="sxs-lookup"><span data-stu-id="2c03c-152">In **Description**, provide details about what the user policy is (for example, Persistent Chat policy for specific user).</span></span>
    
   - <span data-ttu-id="2c03c-153">Para controlar el Chat persistente para todos los usuarios que no se controlan específicamente a través de una directiva de usuario, active o desactive la casilla de verificación **Habilitar Chat persistente** .</span><span class="sxs-lookup"><span data-stu-id="2c03c-153">To control Persistent Chat for all users who are not specifically controlled through a user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="2c03c-154">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="2c03c-154">Click **Commit**.</span></span>
    
## <a name="apply-a-policy-to-a-user-account"></a><span data-ttu-id="2c03c-155">Aplicar una directiva a una cuenta de usuario</span><span class="sxs-lookup"><span data-stu-id="2c03c-155">Apply a policy to a user account</span></span>

<span data-ttu-id="2c03c-156">Después de crear políticas, puede aplicarlas a una cuenta de usuario de esta manera:</span><span class="sxs-lookup"><span data-stu-id="2c03c-156">After you create policies, you can apply them to a user account as follows:</span></span>
  
1. <span data-ttu-id="2c03c-157">En una cuenta de usuario asignada al rol CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="2c03c-157">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="2c03c-158">Desde el menú **Inicio** , seleccione el Skype para el Panel de Control de servidor empresarial o abra una ventana del explorador y, a continuación, escriba la dirección URL de administración.</span><span class="sxs-lookup"><span data-stu-id="2c03c-158">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="2c03c-159">En la barra de navegación izquierda, haga clic en **Usuarios** y, luego, busque la cuenta de usuario que desea configurar.</span><span class="sxs-lookup"><span data-stu-id="2c03c-159">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>
    
4. <span data-ttu-id="2c03c-160">En la tabla donde se enumeran los resultados de la búsqueda, haga clic en la cuenta de usuario, en **Editar** y, luego, en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="2c03c-160">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="2c03c-161">En **Editar Skype para usuarios de empresa Server** en **Directiva de Chat persistente**, seleccione la directiva de usuario de Chat persistente que se desea aplicar.</span><span class="sxs-lookup"><span data-stu-id="2c03c-161">In **Edit Skype for Business Server User** under **Persistent Chat policy**, select the Persistent Chat user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="2c03c-162">La \*\* \<automática\> \*\* configuración aplica la directiva en vigor de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="2c03c-162">The **\<Automatic\>** settings apply the default effective policy.</span></span> <span data-ttu-id="2c03c-163">El servidor aplica automáticamente esta configuración.</span><span class="sxs-lookup"><span data-stu-id="2c03c-163">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="2c03c-164">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="2c03c-164">Click **Commit**.</span></span>
    

