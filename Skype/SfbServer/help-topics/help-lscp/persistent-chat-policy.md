---
title: Directiva de chat persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.PersistentChatPolicy
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eb9e95b9-f69d-4545-970f-9dfdd93b0eff
description: Puede usar la página Directiva de chat persistente del grupo Chat persistente para administrar directivas en un nivel global, de grupo, de sitio o de usuario, además de configurar la directiva global predeterminada y crear una o varias directivas de sitio y usuario adicionales para su implementación. Si el servidor de chat persistente está habilitado para un usuario por directiva, el entorno del servidor de chat persistente aparece en el cliente.
ms.openlocfilehash: 957956ce8537dd9f3ce08dd0919c7392a0c20810
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "41686193"
---
# <a name="persistent-chat-policy"></a><span data-ttu-id="2ad6c-104">Directiva de chat persistente</span><span class="sxs-lookup"><span data-stu-id="2ad6c-104">Persistent Chat Policy</span></span>
 
<span data-ttu-id="2ad6c-105">Puede usar la página **Directiva de chat persistente** del grupo **Chat persistente** para administrar directivas en un nivel global, de grupo, de sitio o de usuario, además de configurar la directiva global predeterminada y crear una o varias directivas de sitio y usuario adicionales para su implementación.</span><span class="sxs-lookup"><span data-stu-id="2ad6c-105">You can use the **Persistent Chat Policy** page of the **Persistent Chat** group to manage policies at a global, pool, site, or user level, including configuring the default global policy and creating one or more additional user and site policies for your deployment.</span></span> <span data-ttu-id="2ad6c-106">Si el servidor de chat persistente está habilitado para un usuario por directiva, el entorno del servidor de chat persistente aparece en el cliente.</span><span class="sxs-lookup"><span data-stu-id="2ad6c-106">If Persistent Chat Server is enabled for a user by policy, then the Persistent Chat Server environment appears in their client.</span></span>
  
<span data-ttu-id="2ad6c-107">La directiva global se crea automáticamente al implementar un servidor de chat persistente, y puede configurarse, pero no eliminarse.</span><span class="sxs-lookup"><span data-stu-id="2ad6c-107">The global policy is created automatically when you deploy Persistent Chat Server, and it can be configured, but not deleted.</span></span> <span data-ttu-id="2ad6c-108">Puesto que la directiva global se aplica a todos los usuarios, no es necesario establecerla para cada usuario.</span><span class="sxs-lookup"><span data-stu-id="2ad6c-108">Because the global policy applies to all users, it doesn't have to be set per user.</span></span>
  
<span data-ttu-id="2ad6c-109">Puede crear y configurar varias directivas de sitio y de usuario que, junto con la directiva global, permitan a los usuarios usar el servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="2ad6c-109">You can create and configure multiple site and user policies which, together with the global policy, enable users for Persistent Chat Server.</span></span> <span data-ttu-id="2ad6c-110">Las directivas del servidor de chat persistente del sitio y del grupo invalidan la Directiva del servidor de chat persistente global, pero solo para los usuarios de ese sitio.</span><span class="sxs-lookup"><span data-stu-id="2ad6c-110">Pool and site Persistent Chat Server policies override the global Persistent Chat Server policy, but only for users of that site.</span></span> <span data-ttu-id="2ad6c-111">Las directivas de usuario reemplazan a las directivas globales, de grupo y de sitio para los usuarios que tengan asignada esa directiva de usuario.</span><span class="sxs-lookup"><span data-stu-id="2ad6c-111">User policies override both global, pool, and site policies for the users to whom the user policy is assigned.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2ad6c-112">Para configurar y usar el servidor de chat persistente, primero debe usar topología Builder para agregar la compatibilidad con el servidor de chat persistente a la topología y, a continuación, publicar la topología.</span><span class="sxs-lookup"><span data-stu-id="2ad6c-112">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="2ad6c-113">Para obtener más información, consulte [Agregar un servidor de chat persistente a su topología de 2015 de Skype empresarial Server](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="2ad6c-113">For details, see [Add Persistent Chat Server to your Skype for Business Server 2015 topology](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md).</span></span> 
  
## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="2ad6c-114">Tareas que puede realizar</span><span class="sxs-lookup"><span data-stu-id="2ad6c-114">Tasks that you can perform</span></span>

<span data-ttu-id="2ad6c-115">En la página **Directiva de chat persistente** puede realizar las siguientes tareas: habilitar y administrar la directiva de servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="2ad6c-115">You can perform the following tasks on the **Persistent Chat Policy** page: enable Persistent Chat Server policy; manage Persistent Chat Server policy.</span></span>
  
## <a name="to-configure-the-global-policy-for-persistent-chat"></a><span data-ttu-id="2ad6c-116">Para configurar la directiva global para el chat persistente</span><span class="sxs-lookup"><span data-stu-id="2ad6c-116">To configure the Global Policy for Persistent Chat</span></span>

1. <span data-ttu-id="2ad6c-117">Inicie sesión en cualquier equipo de la implementación interna con una cuenta de usuario asignada a los roles CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="2ad6c-117">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="2ad6c-118">En el menú **Inicio** , seleccione el panel de control de Skype empresarial Server o abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador.</span><span class="sxs-lookup"><span data-stu-id="2ad6c-118">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="2ad6c-119">En el panel de control de Skype empresarial Server, haga clic en **chat persistente**y, a continuación, en **Directiva de chat persistente**.</span><span class="sxs-lookup"><span data-stu-id="2ad6c-119">In Skype for Business Server Control Panel, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="2ad6c-120">Haga clic en **Global** en la lista de directivas, en **Editar** y, luego, en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="2ad6c-120">Click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="2ad6c-121">En **Editar directiva de chat persistente - Global**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2ad6c-121">In **Edit Persistent Chat Policy - Global**, do the following:</span></span>
    
   - <span data-ttu-id="2ad6c-122">En **Nombre**, especifique un nuevo nombre para la directiva global si no desea usar el valor predeterminado de Global.</span><span class="sxs-lookup"><span data-stu-id="2ad6c-122">In **Name**, specify a new name for the global policy, if you do not want to use the default of Global.</span></span>
    
   - <span data-ttu-id="2ad6c-123">En **Descripción**, proporcione detalles sobre cuál es la Directiva de usuario (por ejemplo, la directiva global de _centralSiteName_).</span><span class="sxs-lookup"><span data-stu-id="2ad6c-123">In **Description**, provide details about what the user policy is (for example, Global policy for  _centralSiteName_).</span></span>
    
   - <span data-ttu-id="2ad6c-124">Para controlar el chat persistente de todos los sitios y usuarios que no se controlan específicamente mediante una directiva de sitio o una directiva de usuario, Active o desactive la casilla de verificación **Habilitar conversación persistente** .</span><span class="sxs-lookup"><span data-stu-id="2ad6c-124">To control Persistent Chat for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="2ad6c-125">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="2ad6c-125">Click **Commit**.</span></span>
    
## <a name="to-create-a-persistent-chat-policy-for-a-site"></a><span data-ttu-id="2ad6c-126">Para crear una directiva de chat persistente para un sitio</span><span class="sxs-lookup"><span data-stu-id="2ad6c-126">To create a Persistent Chat policy for a site</span></span>

<span data-ttu-id="2ad6c-127">Para cada sitio que haya implementado, puede crear una directiva de chat persistente específica de un sitio.</span><span class="sxs-lookup"><span data-stu-id="2ad6c-127">For each site you have deployed, you can create a site-specific Persistent Chat policy.</span></span>
  
<span data-ttu-id="2ad6c-128">La configuración de la directiva de sitio reemplaza la directiva global, pero solo para el sitio específico que abarca la directiva de sitio.</span><span class="sxs-lookup"><span data-stu-id="2ad6c-128">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span>
  
1. <span data-ttu-id="2ad6c-129">Inicie sesión en cualquier equipo de la implementación interna con una cuenta de usuario asignada a los roles CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="2ad6c-129">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="2ad6c-130">En el menú **Inicio** , seleccione el panel de control de Skype empresarial Server o abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador.</span><span class="sxs-lookup"><span data-stu-id="2ad6c-130">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="2ad6c-131">En la barra de navegación izquierda, haga clic en **Chat persistente** y, luego, en **Directiva de chat persistente**.</span><span class="sxs-lookup"><span data-stu-id="2ad6c-131">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="2ad6c-132">Haga clic en **Nuevo** y en **Directiva de sitio**.</span><span class="sxs-lookup"><span data-stu-id="2ad6c-132">Click **New**, and then click **Site policy**.</span></span>
    
5. <span data-ttu-id="2ad6c-133">En **Seleccionar un sitio**, haga clic en el sitio al que se va a aplicar la directiva.</span><span class="sxs-lookup"><span data-stu-id="2ad6c-133">In **Select a Site**, click the site to which the policy is to be applied.</span></span>
    
6. <span data-ttu-id="2ad6c-134">En **Nueva directiva de chat persistente**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2ad6c-134">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="2ad6c-135">En **Nombre**, especifique un nombre para la nueva directiva de sitio (por ejemplo, Redmond).</span><span class="sxs-lookup"><span data-stu-id="2ad6c-135">In **Name**, specify a name for the new site policy (for example, Redmond).</span></span>
    
   - <span data-ttu-id="2ad6c-136">En **Descripción**, dé detalles sobre lo que es la directiva del sitio (por ejemplo, directiva de salón de chat de Redmond).</span><span class="sxs-lookup"><span data-stu-id="2ad6c-136">In **Description**, provide details about what the site policy is (for example, chat room policy for Redmond).</span></span>
    
   - <span data-ttu-id="2ad6c-137">Para controlar el chat persistente para todos los sitios no controlados específicamente con una directiva de sitio, active o desactive la casilla **Habilitar chat persistente**.</span><span class="sxs-lookup"><span data-stu-id="2ad6c-137">To control Persistent Chat for all sites not specifically controlled through a site policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
7. <span data-ttu-id="2ad6c-138">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="2ad6c-138">Click **Commit**.</span></span>
    
## <a name="to-create-a-user-policy-for-persistent-chat"></a><span data-ttu-id="2ad6c-139">Para crear una directiva de usuario para el chat persistente</span><span class="sxs-lookup"><span data-stu-id="2ad6c-139">To create a user policy for Persistent Chat</span></span>

<span data-ttu-id="2ad6c-140">En el panel de control de Skype empresarial Server, puede definir directivas de usuario que se pueden asignar a los usuarios de **los usuarios**.</span><span class="sxs-lookup"><span data-stu-id="2ad6c-140">In the Skype for Business Server Control Panel, you define user policies that can be assigned to users in **Users**.</span></span>
  
<span data-ttu-id="2ad6c-141">La directiva de usuario reemplaza la directiva global y las directivas de sitio, pero solo para los usuarios específicos que tienen asignada dicha directiva.</span><span class="sxs-lookup"><span data-stu-id="2ad6c-141">The user policy overrides the global policy and site policies, but only for the specific users who are assigned the user policy.</span></span>
  
1. <span data-ttu-id="2ad6c-142">Inicie sesión en cualquier equipo de la implementación interna con una cuenta de usuario asignada a los roles CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="2ad6c-142">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="2ad6c-143">En el menú **Inicio** , seleccione el panel de control de Skype empresarial Server o abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador.</span><span class="sxs-lookup"><span data-stu-id="2ad6c-143">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="2ad6c-144">En la barra de navegación izquierda, haga clic en **Chat persistente** y, luego, en **Directiva de chat persistente**.</span><span class="sxs-lookup"><span data-stu-id="2ad6c-144">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="2ad6c-145">Haga clic en **Nuevo** y, luego, en **Directiva de usuario**.</span><span class="sxs-lookup"><span data-stu-id="2ad6c-145">Click **New**, and then click **User policy**.</span></span>
    
5. <span data-ttu-id="2ad6c-146">En **Nueva directiva de chat persistente**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2ad6c-146">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="2ad6c-147">En **Nombre**, especifique un nombre para la nueva directiva de usuario.</span><span class="sxs-lookup"><span data-stu-id="2ad6c-147">In **Name**, specify a name for the new user policy.</span></span>
    
   - <span data-ttu-id="2ad6c-148">En **Descripción**, proporcione detalles sobre qué es la Directiva de usuario (por ejemplo, la Directiva de chat persistente para un usuario específico).</span><span class="sxs-lookup"><span data-stu-id="2ad6c-148">In **Description**, provide details about what the user policy is (for example, Persistent Chat policy for specific user).</span></span>
    
   - <span data-ttu-id="2ad6c-149">Para controlar el chat persistente para todos los usuarios que no se controlan específicamente mediante una directiva de usuario, Active o desactive la casilla de verificación **Habilitar conversación persistente** .</span><span class="sxs-lookup"><span data-stu-id="2ad6c-149">To control Persistent Chat for all users who are not specifically controlled through a user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="2ad6c-150">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="2ad6c-150">Click **Commit**.</span></span>
    
## <a name="to-apply-a-persistent-chat-user-policy-to-a-user-account"></a><span data-ttu-id="2ad6c-151">Para aplicar una directiva de usuario de chat persistente a una cuenta de usuario</span><span class="sxs-lookup"><span data-stu-id="2ad6c-151">To apply a Persistent Chat user policy to a user account</span></span>

<span data-ttu-id="2ad6c-152">Si se ha habilitado un usuario para Skype empresarial Server, puede aplicar las directivas apropiadas a determinados usuarios para habilitarlos o deshabilitarlos para el servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="2ad6c-152">If a user has been enabled for Skype for Business Server, you can apply appropriate policies to specific users to enable or disable them for Persistent Chat Server.</span></span>
  
<span data-ttu-id="2ad6c-153">Use el procedimiento de este tema para aplicar una directiva de usuario de chat persistente creada previamente a una o más cuentas de usuario o grupos de usuarios.</span><span class="sxs-lookup"><span data-stu-id="2ad6c-153">Use the procedure in this topic to apply a previously created Persistent Chat user policy to one or more user accounts or user groups.</span></span>
  
1. <span data-ttu-id="2ad6c-154">Inicie sesión en cualquier equipo de la implementación interna con una cuenta de usuario asignada a los roles CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="2ad6c-154">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="2ad6c-155">En el menú **Inicio** , seleccione el panel de control de Skype empresarial Server o abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador.</span><span class="sxs-lookup"><span data-stu-id="2ad6c-155">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="2ad6c-156">En la barra de navegación izquierda, haga clic en **Usuarios** y, luego, busque la cuenta de usuario que desea configurar.</span><span class="sxs-lookup"><span data-stu-id="2ad6c-156">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>
    
4. <span data-ttu-id="2ad6c-157">En la tabla donde se enumeran los resultados de la búsqueda, haga clic en la cuenta de usuario, en **Editar** y, luego, en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="2ad6c-157">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="2ad6c-158">En **Editar usuario de Lync Server** en **Directiva de chat persistente**, seleccione la Directiva de usuario de chat persistente que desea aplicar.</span><span class="sxs-lookup"><span data-stu-id="2ad6c-158">In **Edit Lync Server User** under **Persistent Chat policy**, select the Persistent Chat user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="2ad6c-159">La \*\* \<configuración\> automática\*\* aplica la Directiva vigente predeterminada.</span><span class="sxs-lookup"><span data-stu-id="2ad6c-159">The **\<Automatic\>** settings apply the default effective policy.</span></span> <span data-ttu-id="2ad6c-160">El servidor aplica automáticamente esta configuración.</span><span class="sxs-lookup"><span data-stu-id="2ad6c-160">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="2ad6c-161">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="2ad6c-161">Click **Commit**.</span></span>
    

