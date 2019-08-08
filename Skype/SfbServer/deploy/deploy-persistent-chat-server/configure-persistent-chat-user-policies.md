---
title: Configurar las directivas de usuario del chat persistente de Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5862480-95f8-4d76-a2b5-940cd995e93c
description: 'Resumen: Lea este tema para obtener información sobre cómo crear directivas de usuario iniciales para el servidor de chat persistente en Skype empresarial Server 2015. Las directivas de usuario de chat persistente determinan si los usuarios tienen permitido el acceso a salones de chat.'
ms.openlocfilehash: 83d6b49372f695be1a4db516eda6c7be357beed3
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239761"
---
# <a name="configure-persistent-chat-user-policies-in-skype-for-business-server-2015"></a><span data-ttu-id="c6560-104">Configurar las directivas de usuario del chat persistente de Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="c6560-104">Configure Persistent Chat user policies in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="c6560-105">**Resumen:** Lea este tema para obtener información sobre cómo crear directivas de usuario iniciales para el servidor de chat persistente en Skype empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="c6560-105">**Summary:** Read this topic to learn how to create initial user policies for Persistent Chat Server in Skype for Business Server 2015.</span></span> <span data-ttu-id="c6560-106">Las directivas de usuario de chat persistente determinan si los usuarios tienen permitido el acceso a salones de chat.</span><span class="sxs-lookup"><span data-stu-id="c6560-106">Persistent Chat user policies determine whether or not users are allowed access to chat rooms.</span></span>
  
<span data-ttu-id="c6560-107">Puede administrar directivas de usuario del servidor de chat persistentes en los siguientes niveles: global, sitio o usuario.</span><span class="sxs-lookup"><span data-stu-id="c6560-107">You can manage Persistent Chat Server user policies at the following levels: global, site, or user.</span></span> <span data-ttu-id="c6560-108">Inicialmente, debe configurar la directiva global para habilitar la configuración de chat persistente para todos los usuarios de la implementación y, a continuación, crear directivas de usuario y de sitio adicionales para controlar si el chat persistente está activado para usuarios y sitios específicos.</span><span class="sxs-lookup"><span data-stu-id="c6560-108">Initially, you configure the global policy to enable Persistent Chat settings for all users in your deployment, and then create additional user and site policies to control whether Persistent Chat is turned on for specific users and sites.</span></span>
  
<span data-ttu-id="c6560-109">Este tema incluye las secciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="c6560-109">This topic contains the following sections:</span></span>
  
- <span data-ttu-id="c6560-110">Configurar la directiva global</span><span class="sxs-lookup"><span data-stu-id="c6560-110">Configure the global policy</span></span>
    
- <span data-ttu-id="c6560-111">Crear una directiva de sitio</span><span class="sxs-lookup"><span data-stu-id="c6560-111">Create a site policy</span></span>
    
- <span data-ttu-id="c6560-112">Crear una directiva de usuario</span><span class="sxs-lookup"><span data-stu-id="c6560-112">Create a user policy</span></span>
    
- <span data-ttu-id="c6560-113">Aplicar una directiva a un usuario o a un grupo de usuarios</span><span class="sxs-lookup"><span data-stu-id="c6560-113">Apply a policy to a user or user group</span></span>
    
> [!NOTE] 
> <span data-ttu-id="c6560-114">Chat persistente está disponible en Skype empresarial Server 2015, pero ya no es compatible con Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c6560-114">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="c6560-115">La misma funcionalidad está disponible en Teams.</span><span class="sxs-lookup"><span data-stu-id="c6560-115">The same functionality is available in Teams.</span></span> <span data-ttu-id="c6560-116">Para obtener más información, consulte [Introducción a la actualización de Microsoft Teams](/microsoftteams/upgrade-start-here).</span><span class="sxs-lookup"><span data-stu-id="c6560-116">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="c6560-117">Si necesita usar una conversación persistente, puede elegir entre migrar los usuarios que tienen esta funcionalidad a teams o continuar usando Skype empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="c6560-117">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>

## <a name="configure-the-global-policy"></a><span data-ttu-id="c6560-118">Configurar la directiva global</span><span class="sxs-lookup"><span data-stu-id="c6560-118">Configure the global policy</span></span>

<span data-ttu-id="c6560-119">Para configurar la directiva global:</span><span class="sxs-lookup"><span data-stu-id="c6560-119">To configure the global policy:</span></span>
  
1. <span data-ttu-id="c6560-120">Inicie sesión en cualquier equipo de la implementación interna con una cuenta de usuario asignada a los roles CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="c6560-120">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="c6560-121">En el menú **Inicio** , seleccione el panel de control de Skype empresarial Server o abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador.</span><span class="sxs-lookup"><span data-stu-id="c6560-121">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="c6560-122">En el panel de control de Skype empresarial Server, haga clic en **chat persistente**y, a continuación, en **Directiva de chat persistente**.</span><span class="sxs-lookup"><span data-stu-id="c6560-122">In Skype for Business Server Control Panel, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="c6560-123">Haga clic en **Global** en la lista de directivas, en **Editar** y, luego, en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="c6560-123">Click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="c6560-124">En **Editar directiva de chat persistente - Global**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c6560-124">In **Edit Persistent Chat Policy - Global**, do the following:</span></span> 
    
   - <span data-ttu-id="c6560-125">En **Nombre**, especifique un nuevo nombre para la directiva global si no desea usar el valor predeterminado de Global.</span><span class="sxs-lookup"><span data-stu-id="c6560-125">In **Name**, specify a new name for the global policy, if you do not want to use the default of Global.</span></span>
    
   - <span data-ttu-id="c6560-126">En **Descripción**, proporcione detalles sobre cuál es la Directiva de usuario (por ejemplo, la directiva global de _centralSiteName_).</span><span class="sxs-lookup"><span data-stu-id="c6560-126">In **Description**, provide details about what the user policy is (for example, Global policy for  _centralSiteName_).</span></span>
    
   - <span data-ttu-id="c6560-127">Para controlar el chat persistente de todos los sitios y usuarios que no se controlan específicamente mediante una directiva de sitio o una directiva de usuario, Active o desactive la casilla de verificación **Habilitar conversación persistente** .</span><span class="sxs-lookup"><span data-stu-id="c6560-127">To control Persistent Chat for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="c6560-128">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="c6560-128">Click **Commit**.</span></span>
    
## <a name="create-a-site-policy"></a><span data-ttu-id="c6560-129">Crear una directiva de sitio</span><span class="sxs-lookup"><span data-stu-id="c6560-129">Create a site policy</span></span>

<span data-ttu-id="c6560-130">Para cada sitio que ha implementado, puede crear una directiva de chat persistente específica para el sitio.</span><span class="sxs-lookup"><span data-stu-id="c6560-130">For each site that you have deployed, you can create a site-specific Persistent Chat policy.</span></span> <span data-ttu-id="c6560-131">La configuración de la directiva de sitio reemplaza la directiva global, pero solo para el sitio específico que abarca la directiva de sitio.</span><span class="sxs-lookup"><span data-stu-id="c6560-131">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span> <span data-ttu-id="c6560-132">Para crear una directiva de sitio:</span><span class="sxs-lookup"><span data-stu-id="c6560-132">To create a site policy:</span></span>
  
1. <span data-ttu-id="c6560-133">Inicie sesión en cualquier equipo de la implementación interna con una cuenta de usuario asignada a los roles CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="c6560-133">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="c6560-134">En el menú **Inicio** , seleccione el panel de control de Skype empresarial Server o abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador.</span><span class="sxs-lookup"><span data-stu-id="c6560-134">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="c6560-135">En la barra de navegación izquierda, haga clic en **Chat persistente** y, luego, en **Directiva de chat persistente**.</span><span class="sxs-lookup"><span data-stu-id="c6560-135">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="c6560-136">Haga clic en **Nuevo** y en **Directiva de sitio**.</span><span class="sxs-lookup"><span data-stu-id="c6560-136">Click **New**, and then click **Site policy**.</span></span>
    
5. <span data-ttu-id="c6560-137">En **Seleccionar un sitio**, haga clic en el sitio al que se va a aplicar la directiva.</span><span class="sxs-lookup"><span data-stu-id="c6560-137">In **Select a Site**, click the site to which the policy is to be applied.</span></span>
    
6. <span data-ttu-id="c6560-138">En **Nueva directiva de chat persistente**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c6560-138">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="c6560-139">En **Nombre**, especifique un nombre para la nueva directiva de sitio (por ejemplo, Redmond).</span><span class="sxs-lookup"><span data-stu-id="c6560-139">In **Name**, specify a name for the new site policy (for example, Redmond).</span></span>
    
   - <span data-ttu-id="c6560-140">En **Descripción**, dé detalles sobre lo que es la directiva del sitio (por ejemplo, directiva de salón de chat de Redmond).</span><span class="sxs-lookup"><span data-stu-id="c6560-140">In **Description**, provide details about what the site policy is (for example, chat room policy for Redmond).</span></span>
    
   - <span data-ttu-id="c6560-141">Para controlar el chat persistente para todos los sitios no controlados específicamente con una directiva de sitio, active o desactive la casilla **Habilitar chat persistente**.</span><span class="sxs-lookup"><span data-stu-id="c6560-141">To control Persistent Chat for all sites not specifically controlled through a site policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
7. <span data-ttu-id="c6560-142">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="c6560-142">Click **Commit**.</span></span>
    
## <a name="create-a-user-policy"></a><span data-ttu-id="c6560-143">Crear una directiva de usuario</span><span class="sxs-lookup"><span data-stu-id="c6560-143">Create a user policy</span></span>

<span data-ttu-id="c6560-144">Puede crear directivas de usuario específicas que reemplazan la directiva global y todas las directivas de sitio que abarcan al usuario.</span><span class="sxs-lookup"><span data-stu-id="c6560-144">You can create user-specific policies that override the global policy and any site policies to which the user belongs.</span></span> <span data-ttu-id="c6560-145">Para crear una directiva de usuario:</span><span class="sxs-lookup"><span data-stu-id="c6560-145">To create a user policy:</span></span>
  
1. <span data-ttu-id="c6560-146">Inicie sesión en cualquier equipo de la implementación interna con una cuenta de usuario asignada a los roles CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="c6560-146">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="c6560-147">En el menú **Inicio** , seleccione el panel de control de Skype empresarial Server o abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador.</span><span class="sxs-lookup"><span data-stu-id="c6560-147">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="c6560-148">En la barra de navegación izquierda, haga clic en **Chat persistente** y, luego, en **Directiva de chat persistente**.</span><span class="sxs-lookup"><span data-stu-id="c6560-148">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="c6560-149">Haga clic en **Nuevo** y, luego, en **Directiva de usuario**.</span><span class="sxs-lookup"><span data-stu-id="c6560-149">Click **New**, and then click **User policy**.</span></span>
    
5. <span data-ttu-id="c6560-150">En **Nueva directiva de chat persistente**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c6560-150">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="c6560-151">En **Nombre**, especifique un nombre para la nueva directiva de usuario.</span><span class="sxs-lookup"><span data-stu-id="c6560-151">In **Name**, specify a name for the new user policy.</span></span>
    
   - <span data-ttu-id="c6560-152">En **Descripción**, proporcione detalles sobre qué es la Directiva de usuario (por ejemplo, la Directiva de chat persistente para un usuario específico).</span><span class="sxs-lookup"><span data-stu-id="c6560-152">In **Description**, provide details about what the user policy is (for example, Persistent Chat policy for specific user).</span></span>
    
   - <span data-ttu-id="c6560-153">Para controlar el chat persistente para todos los usuarios que no se controlan específicamente mediante una directiva de usuario, Active o desactive la casilla de verificación **Habilitar conversación persistente** .</span><span class="sxs-lookup"><span data-stu-id="c6560-153">To control Persistent Chat for all users who are not specifically controlled through a user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="c6560-154">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="c6560-154">Click **Commit**.</span></span>
    
## <a name="apply-a-policy-to-a-user-account"></a><span data-ttu-id="c6560-155">Aplicar una directiva a una cuenta de usuario</span><span class="sxs-lookup"><span data-stu-id="c6560-155">Apply a policy to a user account</span></span>

<span data-ttu-id="c6560-156">Después de crear políticas, puede aplicarlas a una cuenta de usuario de esta manera:</span><span class="sxs-lookup"><span data-stu-id="c6560-156">After you create policies, you can apply them to a user account as follows:</span></span>
  
1. <span data-ttu-id="c6560-157">En una cuenta de usuario asignada al rol CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="c6560-157">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="c6560-158">En el menú **Inicio** , seleccione el panel de control de Skype empresarial Server o abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador.</span><span class="sxs-lookup"><span data-stu-id="c6560-158">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="c6560-159">En la barra de navegación izquierda, haga clic en **Usuarios** y, luego, busque la cuenta de usuario que desea configurar.</span><span class="sxs-lookup"><span data-stu-id="c6560-159">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>
    
4. <span data-ttu-id="c6560-160">En la tabla donde se enumeran los resultados de la búsqueda, haga clic en la cuenta de usuario, en **Editar** y, luego, en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="c6560-160">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="c6560-161">En **Editar usuario de Skype empresarial Server** en **Directiva de chat persistente**, seleccione la Directiva de usuario de chat persistente que desea aplicar.</span><span class="sxs-lookup"><span data-stu-id="c6560-161">In **Edit Skype for Business Server User** under **Persistent Chat policy**, select the Persistent Chat user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c6560-162">La \*\* \<configuración\> automática\*\* aplica la Directiva vigente predeterminada.</span><span class="sxs-lookup"><span data-stu-id="c6560-162">The **\<Automatic\>** settings apply the default effective policy.</span></span> <span data-ttu-id="c6560-163">El servidor aplica automáticamente esta configuración.</span><span class="sxs-lookup"><span data-stu-id="c6560-163">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="c6560-164">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="c6560-164">Click **Commit**.</span></span>
    

