---
title: Configurar directivas de usuario de chat persistente en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e5862480-95f8-4d76-a2b5-940cd995e93c
description: 'Resumen: lea este tema para obtener información sobre cómo crear directivas de usuario iniciales para el servidor de chat persistente en Skype Empresarial Server 2015. Las directivas de usuario de chat persistente determinan si los usuarios tienen o no permiso de acceso a los salón de chat.'
ms.openlocfilehash: 531146a55b0282db191f503ef39e9be9e4d5f879
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802120"
---
# <a name="configure-persistent-chat-user-policies-in-skype-for-business-server-2015"></a><span data-ttu-id="9f2dd-104">Configurar directivas de usuario de chat persistente en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="9f2dd-104">Configure Persistent Chat user policies in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="9f2dd-105">**Resumen:** Lea este tema para obtener información sobre cómo crear directivas de usuario iniciales para el servidor de chat persistente en Skype Empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="9f2dd-105">**Summary:** Read this topic to learn how to create initial user policies for Persistent Chat Server in Skype for Business Server 2015.</span></span> <span data-ttu-id="9f2dd-106">Las directivas de usuario de chat persistente determinan si los usuarios tienen o no permiso de acceso a los salón de chat.</span><span class="sxs-lookup"><span data-stu-id="9f2dd-106">Persistent Chat user policies determine whether or not users are allowed access to chat rooms.</span></span>
  
<span data-ttu-id="9f2dd-107">Puede administrar las directivas de usuario del servidor de chat persistente en los siguientes niveles: global, de sitio o de usuario.</span><span class="sxs-lookup"><span data-stu-id="9f2dd-107">You can manage Persistent Chat Server user policies at the following levels: global, site, or user.</span></span> <span data-ttu-id="9f2dd-108">Inicialmente, se configura la directiva global para habilitar la configuración de chat persistente para todos los usuarios de la implementación y, a continuación, se crean directivas de usuario y de sitio adicionales para controlar si el chat persistente está activado para usuarios y sitios específicos.</span><span class="sxs-lookup"><span data-stu-id="9f2dd-108">Initially, you configure the global policy to enable Persistent Chat settings for all users in your deployment, and then create additional user and site policies to control whether Persistent Chat is turned on for specific users and sites.</span></span>
  
<span data-ttu-id="9f2dd-109">En este tema se presentan las siguientes secciones:</span><span class="sxs-lookup"><span data-stu-id="9f2dd-109">This topic contains the following sections:</span></span>
  
- <span data-ttu-id="9f2dd-110">Configurar la directiva global</span><span class="sxs-lookup"><span data-stu-id="9f2dd-110">Configure the global policy</span></span>
    
- <span data-ttu-id="9f2dd-111">Crear una directiva de sitio</span><span class="sxs-lookup"><span data-stu-id="9f2dd-111">Create a site policy</span></span>
    
- <span data-ttu-id="9f2dd-112">Crear una directiva de usuario</span><span class="sxs-lookup"><span data-stu-id="9f2dd-112">Create a user policy</span></span>
    
- <span data-ttu-id="9f2dd-113">Aplicar una directiva a un usuario o grupo de usuarios</span><span class="sxs-lookup"><span data-stu-id="9f2dd-113">Apply a policy to a user or user group</span></span>
    
> [!NOTE] 
> <span data-ttu-id="9f2dd-114">El chat persistente está disponible en Skype Empresarial Server 2015, pero ya no es compatible con Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="9f2dd-114">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="9f2dd-115">La misma funcionalidad está disponible en Teams.</span><span class="sxs-lookup"><span data-stu-id="9f2dd-115">The same functionality is available in Teams.</span></span> <span data-ttu-id="9f2dd-116">Para obtener más información, consulte [Introducción a la actualización de Microsoft Teams.](/microsoftteams/upgrade-start-here)</span><span class="sxs-lookup"><span data-stu-id="9f2dd-116">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="9f2dd-117">Si necesita usar el chat persistente, puede migrar usuarios que requieran esta funcionalidad a Teams o seguir usando Skype Empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="9f2dd-117">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>

## <a name="configure-the-global-policy"></a><span data-ttu-id="9f2dd-118">Configurar la directiva global</span><span class="sxs-lookup"><span data-stu-id="9f2dd-118">Configure the global policy</span></span>

<span data-ttu-id="9f2dd-119">Para configurar la directiva global:</span><span class="sxs-lookup"><span data-stu-id="9f2dd-119">To configure the global policy:</span></span>
  
1. <span data-ttu-id="9f2dd-120">Desde una cuenta de usuario que se asigne al rol CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="9f2dd-120">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="9f2dd-121">En el **menú Inicio,** seleccione el Panel de control de Skype Empresarial Server o abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador.</span><span class="sxs-lookup"><span data-stu-id="9f2dd-121">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="9f2dd-122">En el Panel de control de Skype Empresarial Server, haga clic en **Chat** persistente y, a continuación, haga clic en **Directiva de chat persistente.**</span><span class="sxs-lookup"><span data-stu-id="9f2dd-122">In Skype for Business Server Control Panel, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="9f2dd-123">Haga clic en **Global** en la lista de directivas, haga clic en **Editar** y, a continuación, en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="9f2dd-123">Click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="9f2dd-124">In **Editar directiva de chat persistente - Global**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9f2dd-124">In **Edit Persistent Chat Policy - Global**, do the following:</span></span> 
    
   - <span data-ttu-id="9f2dd-125">En **Nombre**, especifique un nombre nuevo para la directiva global, si no desea usar el nombre predeterminado (Global).</span><span class="sxs-lookup"><span data-stu-id="9f2dd-125">In **Name**, specify a new name for the global policy, if you do not want to use the default of Global.</span></span>
    
   - <span data-ttu-id="9f2dd-126">En **Descripción,** proporcione detalles sobre la directiva de usuario (por ejemplo, directiva global para  _centralSiteName_).</span><span class="sxs-lookup"><span data-stu-id="9f2dd-126">In **Description**, provide details about what the user policy is (for example, Global policy for  _centralSiteName_).</span></span>
    
   - <span data-ttu-id="9f2dd-127">Para controlar el chat persistente para todos los sitios y usuarios que no se controlan específicamente a través de una directiva de sitio o de usuario, active o desactive la casilla Habilitar **chat** persistente.</span><span class="sxs-lookup"><span data-stu-id="9f2dd-127">To control Persistent Chat for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="9f2dd-128">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="9f2dd-128">Click **Commit**.</span></span>
    
## <a name="create-a-site-policy"></a><span data-ttu-id="9f2dd-129">Crear una directiva de sitio</span><span class="sxs-lookup"><span data-stu-id="9f2dd-129">Create a site policy</span></span>

<span data-ttu-id="9f2dd-130">Para cada sitio que haya implementado, puede crear una directiva de chat persistente específica del sitio.</span><span class="sxs-lookup"><span data-stu-id="9f2dd-130">For each site that you have deployed, you can create a site-specific Persistent Chat policy.</span></span> <span data-ttu-id="9f2dd-131">La configuración de la directiva de sitio invalida la directiva global, pero solo en el caso del sitio específico que determina la directiva.</span><span class="sxs-lookup"><span data-stu-id="9f2dd-131">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span> <span data-ttu-id="9f2dd-132">Para crear una directiva de sitio:</span><span class="sxs-lookup"><span data-stu-id="9f2dd-132">To create a site policy:</span></span>
  
1. <span data-ttu-id="9f2dd-133">Desde una cuenta de usuario que se asigne al rol CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="9f2dd-133">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="9f2dd-134">En el **menú Inicio,** seleccione el Panel de control de Skype Empresarial Server o abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador.</span><span class="sxs-lookup"><span data-stu-id="9f2dd-134">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="9f2dd-135">En la barra de navegación izquierda, haga clic en **Chat persistente** y, a continuación, en **Directiva de chat persistente**.</span><span class="sxs-lookup"><span data-stu-id="9f2dd-135">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="9f2dd-136">Haga clic en **Nuevo** y en **Directiva de sitio**.</span><span class="sxs-lookup"><span data-stu-id="9f2dd-136">Click **New**, and then click **Site policy**.</span></span>
    
5. <span data-ttu-id="9f2dd-137">En **Seleccionar un sitio**, haga clic en el sitio al que se va a aplicar la directiva.</span><span class="sxs-lookup"><span data-stu-id="9f2dd-137">In **Select a Site**, click the site to which the policy is to be applied.</span></span>
    
6. <span data-ttu-id="9f2dd-138">En **Nueva directiva de chat persistente**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9f2dd-138">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="9f2dd-139">En **Nombre**, especifique un nombre para la nueva directiva de sitio (por ejemplo, Redmond).</span><span class="sxs-lookup"><span data-stu-id="9f2dd-139">In **Name**, specify a name for the new site policy (for example, Redmond).</span></span>
    
   - <span data-ttu-id="9f2dd-140">En **Descripción**, proporcione información detallada sobre la directiva de sitio (por ejemplo, directiva de salón de chat para Redmond).</span><span class="sxs-lookup"><span data-stu-id="9f2dd-140">In **Description**, provide details about what the site policy is (for example, chat room policy for Redmond).</span></span>
    
   - <span data-ttu-id="9f2dd-141">Para controlar el chat persistente para todos los sitios no controlados específicamente mediante una directiva de sitio, active o desactive la casilla **Habilitar chat persistente**.</span><span class="sxs-lookup"><span data-stu-id="9f2dd-141">To control Persistent Chat for all sites not specifically controlled through a site policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
7. <span data-ttu-id="9f2dd-142">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="9f2dd-142">Click **Commit**.</span></span>
    
## <a name="create-a-user-policy"></a><span data-ttu-id="9f2dd-143">Crear una directiva de usuario</span><span class="sxs-lookup"><span data-stu-id="9f2dd-143">Create a user policy</span></span>

<span data-ttu-id="9f2dd-144">Puede crear directivas específicas de usuario que invalide la directiva global y las directivas de sitio a las que pertenece el usuario.</span><span class="sxs-lookup"><span data-stu-id="9f2dd-144">You can create user-specific policies that override the global policy and any site policies to which the user belongs.</span></span> <span data-ttu-id="9f2dd-145">Para crear una directiva de usuario:</span><span class="sxs-lookup"><span data-stu-id="9f2dd-145">To create a user policy:</span></span>
  
1. <span data-ttu-id="9f2dd-146">Desde una cuenta de usuario que se asigne al rol CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="9f2dd-146">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="9f2dd-147">En el **menú Inicio,** seleccione el Panel de control de Skype Empresarial Server o abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador.</span><span class="sxs-lookup"><span data-stu-id="9f2dd-147">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="9f2dd-148">En la barra de navegación izquierda, haga clic en **Chat persistente** y, a continuación, en **Directiva de chat persistente**.</span><span class="sxs-lookup"><span data-stu-id="9f2dd-148">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="9f2dd-149">Haga clic en **Nuevo** y en **Directiva de usuario**.</span><span class="sxs-lookup"><span data-stu-id="9f2dd-149">Click **New**, and then click **User policy**.</span></span>
    
5. <span data-ttu-id="9f2dd-150">En **Nueva directiva de chat persistente**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9f2dd-150">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="9f2dd-151">En **Nombre**, especifique un nombre para la nueva directiva de usuario.</span><span class="sxs-lookup"><span data-stu-id="9f2dd-151">In **Name**, specify a name for the new user policy.</span></span>
    
   - <span data-ttu-id="9f2dd-152">En **Descripción,** proporcione detalles sobre la directiva de usuario (por ejemplo, directiva de chat persistente para un usuario específico).</span><span class="sxs-lookup"><span data-stu-id="9f2dd-152">In **Description**, provide details about what the user policy is (for example, Persistent Chat policy for specific user).</span></span>
    
   - <span data-ttu-id="9f2dd-153">Para controlar el chat persistente para todos los usuarios que no están controlados específicamente a través de una directiva de usuario, active o desactive la casilla Habilitar **chat** persistente.</span><span class="sxs-lookup"><span data-stu-id="9f2dd-153">To control Persistent Chat for all users who are not specifically controlled through a user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="9f2dd-154">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="9f2dd-154">Click **Commit**.</span></span>
    
## <a name="apply-a-policy-to-a-user-account"></a><span data-ttu-id="9f2dd-155">Aplicar una directiva a una cuenta de usuario</span><span class="sxs-lookup"><span data-stu-id="9f2dd-155">Apply a policy to a user account</span></span>

<span data-ttu-id="9f2dd-156">Después de crear directivas, puede aplicarlas a una cuenta de usuario de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="9f2dd-156">After you create policies, you can apply them to a user account as follows:</span></span>
  
1. <span data-ttu-id="9f2dd-157">Desde una cuenta de usuario que se asigne al rol CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="9f2dd-157">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="9f2dd-158">En el **menú Inicio,** seleccione el Panel de control de Skype Empresarial Server o abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador.</span><span class="sxs-lookup"><span data-stu-id="9f2dd-158">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="9f2dd-159">En la barra de navegación izquierda, haga clic en  **Usuarios** y, a continuación, busque en la cuenta de usuario que desea configurar.</span><span class="sxs-lookup"><span data-stu-id="9f2dd-159">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>
    
4. <span data-ttu-id="9f2dd-160">En la tabla donde se enumeran los resultados de la búsqueda, haga clic en la cuenta de usuario, en  **Editar** y, a continuación, en  **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="9f2dd-160">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="9f2dd-161">En **Editar usuario de Skype Empresarial Server** en la directiva de **chat** persistente, seleccione la directiva de usuario de chat persistente que desee aplicar.</span><span class="sxs-lookup"><span data-stu-id="9f2dd-161">In **Edit Skype for Business Server User** under **Persistent Chat policy**, select the Persistent Chat user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9f2dd-162">La **\<Automatic\>** configuración aplica la directiva efectiva predeterminada.</span><span class="sxs-lookup"><span data-stu-id="9f2dd-162">The **\<Automatic\>** settings apply the default effective policy.</span></span> <span data-ttu-id="9f2dd-163">Esta configuración se aplica automáticamente por el servidor.</span><span class="sxs-lookup"><span data-stu-id="9f2dd-163">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="9f2dd-164">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="9f2dd-164">Click **Commit**.</span></span>
    

