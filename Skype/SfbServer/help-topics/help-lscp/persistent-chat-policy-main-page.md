---
title: Página principal de directiva de chat persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.PersistentChatPolicyMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0dc18d5c-82d6-4d39-afb1-efdb3ae6d2c7
description: Puede usar la página Directiva de chat persistente del grupo Chat persistente para administrar directivas en un nivel global, de grupo, de sitio o de usuario, además de configurar la directiva global predeterminada y crear una o varias directivas de sitio y usuario adicionales para su implementación. Si un usuario está habilitado para el servidor de Chat persistente mediante una directiva, el entorno de servidor de Chat persistente aparece en su cliente.
ms.openlocfilehash: 562de77408fea4f23beabf8b8ef70a3a6fc1caf0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929198"
---
# <a name="persistent-chat-policy-main-page"></a><span data-ttu-id="9ad1e-104">Página principal de directiva de chat persistente</span><span class="sxs-lookup"><span data-stu-id="9ad1e-104">Persistent Chat Policy Main Page</span></span>
 
<span data-ttu-id="9ad1e-105">Puede usar la página **Directiva de chat persistente** del grupo **Chat persistente** para administrar directivas en un nivel global, de grupo, de sitio o de usuario, además de configurar la directiva global predeterminada y crear una o varias directivas de sitio y usuario adicionales para su implementación.</span><span class="sxs-lookup"><span data-stu-id="9ad1e-105">You can use the **Persistent Chat Policy** page of the **Persistent Chat** group to manage policies at a global, pool, site, or user level, including configuring the default global policy and creating one or more additional user and site policies for your deployment.</span></span> <span data-ttu-id="9ad1e-106">Si un usuario está habilitado para el servidor de Chat persistente mediante una directiva, el entorno de servidor de Chat persistente aparece en su cliente.</span><span class="sxs-lookup"><span data-stu-id="9ad1e-106">If a user is enabled for Persistent Chat Server by policy, then the Persistent Chat Server environment appears in their client.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9ad1e-107">En la topología, las directivas de sitio del servidor de Chat persistente se aplican globalmente, por grupo de servidores del usuario, o por sitio del usuario o por usuario.</span><span class="sxs-lookup"><span data-stu-id="9ad1e-107">In the topology, Persistent Chat Server site policies apply globally, per user's pool, or per user's site, or per user.</span></span> 
  
<span data-ttu-id="9ad1e-108">La directiva global se crea automáticamente al implementar servidor de Chat persistente, y puede ser configurada, pero no elimina.</span><span class="sxs-lookup"><span data-stu-id="9ad1e-108">The global policy is created automatically when you deploy Persistent Chat Server, and it can be configured, but not deleted.</span></span> <span data-ttu-id="9ad1e-109">Debido a que la directiva global se aplica a todos los usuarios, no tiene que se establecerá por usuario.</span><span class="sxs-lookup"><span data-stu-id="9ad1e-109">Because the global policy applies to all users, it doesn't have to be set per user.</span></span>
  
<span data-ttu-id="9ad1e-110">Puede crear y configurar varias directivas de usuario y de sitio que, junto con la directiva global, permiten a los usuarios para el servidor de Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="9ad1e-110">You can create and configure multiple site and user policies which, together with the global policy, enable users for Persistent Chat Server.</span></span> <span data-ttu-id="9ad1e-111">Las directivas de servidor de Chat persistente de grupo de servidores y sitios reemplazan la directiva global del servidor de Chat persistente, pero sólo para los usuarios de ese sitio.</span><span class="sxs-lookup"><span data-stu-id="9ad1e-111">Pool and site Persistent Chat Server policies override the global Persistent Chat Server policy, but only for users of that site.</span></span> <span data-ttu-id="9ad1e-112">Las directivas de usuario reemplazan a las directivas globales, de grupo y de sitio para los usuarios que tengan asignada esa directiva de usuario.</span><span class="sxs-lookup"><span data-stu-id="9ad1e-112">User policies override both global, pool, and site policies for the users to whom the user policy is assigned.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9ad1e-113">Para configurar y usar el servidor de Chat persistente, debe primero usar el generador de topología para agregar compatibilidad con servidor de Chat persistente a la topología y, a continuación, publique la topología.</span><span class="sxs-lookup"><span data-stu-id="9ad1e-113">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="9ad1e-114">Para obtener información detallada, vea [Agregar servidor de Chat persistente a su Skype para topología empresarial Server 2015](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="9ad1e-114">For details, see [Add Persistent Chat Server to your Skype for Business Server 2015 topology](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md).</span></span> 
  
## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="9ad1e-115">Tareas que puede realizar</span><span class="sxs-lookup"><span data-stu-id="9ad1e-115">Tasks that you can perform</span></span>

<span data-ttu-id="9ad1e-116">En la página **Directiva de chat persistente** puede realizar las siguientes tareas: habilitar y administrar la directiva de servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="9ad1e-116">You can perform the following tasks on the **Persistent Chat Policy** page: enable and manage Persistent Chat Server policy.</span></span>
  
## <a name="to-configure-the-global-policy-for-persistent-chat"></a><span data-ttu-id="9ad1e-117">Para configurar la directiva Global para Chat persistente</span><span class="sxs-lookup"><span data-stu-id="9ad1e-117">To configure the Global Policy for Persistent Chat</span></span>

1. <span data-ttu-id="9ad1e-118">Inicie sesión en cualquier equipo de la implementación interna con una cuenta de usuario asignada a los roles CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="9ad1e-118">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="9ad1e-119">Desde el menú **Inicio** , seleccione el Skype para el Panel de Control de servidor empresarial o abra una ventana del explorador y, a continuación, escriba la dirección URL de administración.</span><span class="sxs-lookup"><span data-stu-id="9ad1e-119">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="9ad1e-120">En Skype para el Panel de Control de servidor empresarial, haga clic en **Chat persistente**y, a continuación, haga clic en **Directiva de Chat persistente**.</span><span class="sxs-lookup"><span data-stu-id="9ad1e-120">In Skype for Business Server Control Panel, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="9ad1e-121">Haga clic en **Global** en la lista de directivas, en **Editar** y, luego, en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="9ad1e-121">Click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="9ad1e-122">En **Editar directiva de chat persistente - Global**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9ad1e-122">In **Edit Persistent Chat Policy - Global**, do the following:</span></span>
    
   - <span data-ttu-id="9ad1e-123">En **Nombre**, especifique un nuevo nombre para la directiva global si no desea usar el valor predeterminado de Global.</span><span class="sxs-lookup"><span data-stu-id="9ad1e-123">In **Name**, specify a new name for the global policy, if you do not want to use the default of Global.</span></span>
    
   - <span data-ttu-id="9ad1e-124">En **Descripción**, proporcione información detallada acerca de la directiva de usuario (por ejemplo, directiva Global de _centralSiteName_).</span><span class="sxs-lookup"><span data-stu-id="9ad1e-124">In **Description**, provide details about what the user policy is (for example, Global policy for  _centralSiteName_).</span></span>
    
   - <span data-ttu-id="9ad1e-125">Para controlar el Chat persistente para todos los sitios y los usuarios no controlados específicamente mediante una directiva de sitio o usuario, active o desactive la casilla de verificación **Habilitar Chat persistente** .</span><span class="sxs-lookup"><span data-stu-id="9ad1e-125">To control Persistent Chat for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="9ad1e-126">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="9ad1e-126">Click **Commit**.</span></span>
    
## <a name="to-create-a-persistent-chat-policy-for-a-site"></a><span data-ttu-id="9ad1e-127">Para crear una directiva de Chat persistente para un sitio</span><span class="sxs-lookup"><span data-stu-id="9ad1e-127">To create a Persistent Chat policy for a site</span></span>

<span data-ttu-id="9ad1e-128">Para cada sitio que haya implementado, puede crear una directiva de Chat persistente específica del sitio.</span><span class="sxs-lookup"><span data-stu-id="9ad1e-128">For each site you have deployed, you can create a site-specific Persistent Chat policy.</span></span>
  
<span data-ttu-id="9ad1e-129">La configuración de la directiva de sitio reemplaza la directiva global, pero solo para el sitio específico que abarca la directiva de sitio.</span><span class="sxs-lookup"><span data-stu-id="9ad1e-129">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span>
  
1. <span data-ttu-id="9ad1e-130">Inicie sesión en cualquier equipo de la implementación interna con una cuenta de usuario asignada a los roles CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="9ad1e-130">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="9ad1e-131">Desde el menú **Inicio** , seleccione el Skype para el Panel de Control de servidor empresarial o abra una ventana del explorador y, a continuación, escriba la dirección URL de administración.</span><span class="sxs-lookup"><span data-stu-id="9ad1e-131">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="9ad1e-132">En la barra de navegación izquierda, haga clic en **Chat persistente** y, luego, en **Directiva de chat persistente**.</span><span class="sxs-lookup"><span data-stu-id="9ad1e-132">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="9ad1e-133">Haga clic en **Nuevo** y en **Directiva de sitio**.</span><span class="sxs-lookup"><span data-stu-id="9ad1e-133">Click **New**, and then click **Site policy**.</span></span>
    
5. <span data-ttu-id="9ad1e-134">En **Seleccionar un sitio**, haga clic en el sitio al que se va a aplicar la directiva.</span><span class="sxs-lookup"><span data-stu-id="9ad1e-134">In **Select a Site**, click the site to which the policy is to be applied.</span></span>
    
6. <span data-ttu-id="9ad1e-135">En **Nueva directiva de chat persistente**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9ad1e-135">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="9ad1e-136">En **Nombre**, especifique un nombre para la nueva directiva de sitio (por ejemplo, Redmond).</span><span class="sxs-lookup"><span data-stu-id="9ad1e-136">In **Name**, specify a name for the new site policy (for example, Redmond).</span></span>
    
   - <span data-ttu-id="9ad1e-137">En **Descripción**, dé detalles sobre lo que es la directiva del sitio (por ejemplo, directiva de salón de chat de Redmond).</span><span class="sxs-lookup"><span data-stu-id="9ad1e-137">In **Description**, provide details about what the site policy is (for example, chat room policy for Redmond).</span></span>
    
   - <span data-ttu-id="9ad1e-138">Para controlar el chat persistente para todos los sitios no controlados específicamente con una directiva de sitio, active o desactive la casilla **Habilitar chat persistente**.</span><span class="sxs-lookup"><span data-stu-id="9ad1e-138">To control Persistent Chat for all sites not specifically controlled through a site policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
7. <span data-ttu-id="9ad1e-139">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="9ad1e-139">Click **Commit**.</span></span>
    
## <a name="to-create-a-user-policy-for-persistent-chat"></a><span data-ttu-id="9ad1e-140">Para crear una directiva de usuario para Chat persistente</span><span class="sxs-lookup"><span data-stu-id="9ad1e-140">To create a user policy for Persistent Chat</span></span>

<span data-ttu-id="9ad1e-141">En Skype para el Panel de Control de servidor empresarial, es posible definir directivas de usuario que se pueden asignar a los usuarios de **los usuarios**.</span><span class="sxs-lookup"><span data-stu-id="9ad1e-141">In the Skype for Business Server Control Panel, you define user policies that can be assigned to users in **Users**.</span></span>
  
<span data-ttu-id="9ad1e-142">La directiva de usuario reemplaza la directiva global y las directivas de sitio, pero solo para los usuarios específicos que tienen asignada dicha directiva.</span><span class="sxs-lookup"><span data-stu-id="9ad1e-142">The user policy overrides the global policy and site policies, but only for the specific users who are assigned the user policy.</span></span>
  
1. <span data-ttu-id="9ad1e-143">Inicie sesión en cualquier equipo de la implementación interna con una cuenta de usuario asignada a los roles CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="9ad1e-143">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="9ad1e-144">Desde el menú **Inicio** , seleccione el Skype para el Panel de Control de servidor empresarial o abra una ventana del explorador y, a continuación, escriba la dirección URL de administración.</span><span class="sxs-lookup"><span data-stu-id="9ad1e-144">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="9ad1e-145">En la barra de navegación izquierda, haga clic en **Chat persistente** y, luego, en **Directiva de chat persistente**.</span><span class="sxs-lookup"><span data-stu-id="9ad1e-145">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="9ad1e-146">Haga clic en **Nuevo** y, luego, en **Directiva de usuario**.</span><span class="sxs-lookup"><span data-stu-id="9ad1e-146">Click **New**, and then click **User policy**.</span></span>
    
5. <span data-ttu-id="9ad1e-147">En **Nueva directiva de chat persistente**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9ad1e-147">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="9ad1e-148">En **Nombre**, especifique un nombre para la nueva directiva de usuario.</span><span class="sxs-lookup"><span data-stu-id="9ad1e-148">In **Name**, specify a name for the new user policy.</span></span>
    
   - <span data-ttu-id="9ad1e-149">En **Descripción**, proporcione información detallada acerca de la directiva de usuario (por ejemplo, directiva de Chat persistente para usuario específico).</span><span class="sxs-lookup"><span data-stu-id="9ad1e-149">In **Description**, provide details about what the user policy is (for example, Persistent Chat policy for specific user).</span></span>
    
   - <span data-ttu-id="9ad1e-150">Para controlar el Chat persistente para todos los usuarios que no se controlan específicamente a través de una directiva de usuario, active o desactive la casilla de verificación **Habilitar Chat persistente** .</span><span class="sxs-lookup"><span data-stu-id="9ad1e-150">To control Persistent Chat for all users who are not specifically controlled through a user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="9ad1e-151">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="9ad1e-151">Click **Commit**.</span></span>
    
## <a name="to-apply-a-persistent-chat-user-policy-to-a-user-account"></a><span data-ttu-id="9ad1e-152">Para aplicar una directiva de usuario de Chat persistente a una cuenta de usuario</span><span class="sxs-lookup"><span data-stu-id="9ad1e-152">To apply a Persistent Chat user policy to a user account</span></span>

<span data-ttu-id="9ad1e-153">Si un usuario se ha habilitado para Skype para la empresa, puede aplicar las directivas adecuadas a determinados usuarios para habilitar o deshabilitarlas para servidor de Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="9ad1e-153">If a user has been enabled for Skype for Business, you can apply appropriate policies to specific users to enable or disable them for Persistent Chat Server.</span></span>
  
<span data-ttu-id="9ad1e-154">Use el procedimiento de este tema para aplicar una directiva de usuario de Chat persistente creada previamente a una o más cuentas de usuario o grupos de usuarios.</span><span class="sxs-lookup"><span data-stu-id="9ad1e-154">Use the procedure in this topic to apply a previously created Persistent Chat user policy to one or more user accounts or user groups.</span></span>
  
1. <span data-ttu-id="9ad1e-155">Inicie sesión en cualquier equipo de la implementación interna con una cuenta de usuario asignada a los roles CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="9ad1e-155">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="9ad1e-156">Desde el menú **Inicio** , seleccione el Skype para el Panel de Control de servidor empresarial o abra una ventana del explorador y, a continuación, escriba la dirección URL de administración.</span><span class="sxs-lookup"><span data-stu-id="9ad1e-156">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="9ad1e-157">En la barra de navegación izquierda, haga clic en **Usuarios** y, luego, busque la cuenta de usuario que desea configurar.</span><span class="sxs-lookup"><span data-stu-id="9ad1e-157">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>
    
4. <span data-ttu-id="9ad1e-158">En la tabla donde se enumeran los resultados de la búsqueda, haga clic en la cuenta de usuario, en **Editar** y, luego, en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="9ad1e-158">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="9ad1e-159">En **Editar usuario de Lync Server** en **Directiva de Chat persistente**, seleccione la directiva de usuario de Chat persistente que se desea aplicar.</span><span class="sxs-lookup"><span data-stu-id="9ad1e-159">In **Edit Lync Server User** under **Persistent Chat policy**, select the Persistent Chat user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9ad1e-160">La \*\* \<automática\> \*\* configuración aplica la directiva en vigor de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="9ad1e-160">The **\<Automatic\>** settings apply the default effective policy.</span></span> <span data-ttu-id="9ad1e-161">El servidor aplica automáticamente esta configuración.</span><span class="sxs-lookup"><span data-stu-id="9ad1e-161">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="9ad1e-162">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="9ad1e-162">Click **Commit**.</span></span>
    

