---
title: Página principal de directiva de chat persistente
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.PersistentChatPolicyMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0dc18d5c-82d6-4d39-afb1-efdb3ae6d2c7
description: Puede utilizar la página de directiva persistente Chat del grupo Chat persistentes para administrar directivas en un nivel global, de grupo, sitio o usuario, incluyendo la configuración de la directiva global predeterminada y la creación de uno o más usuarios y sitio directivas adicionales para su implementación. Si un usuario está habilitado para el servidor de charla persistente por directiva, el entorno de servidor de charla persistente aparece en su cliente.
ms.openlocfilehash: 14d600c558a7a72887aa7ff3e349857115e8a792
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="persistent-chat-policy-main-page"></a><span data-ttu-id="87572-104">Página principal de directiva de chat persistente</span><span class="sxs-lookup"><span data-stu-id="87572-104">Persistent Chat Policy Main Page</span></span>
 
<span data-ttu-id="87572-105">Puede usar la página **Directiva de chat persistente** del grupo **Chat persistente** para administrar directivas en un nivel global, de grupo, de sitio o de usuario, además de configurar la directiva global predeterminada y crear una o varias directivas de sitio y usuario adicionales para su implementación.</span><span class="sxs-lookup"><span data-stu-id="87572-105">You can use the **Persistent Chat Policy** page of the **Persistent Chat** group to manage policies at a global, pool, site, or user level, including configuring the default global policy and creating one or more additional user and site policies for your deployment.</span></span> <span data-ttu-id="87572-106">Si un usuario está habilitado para el servidor de charla persistente por directiva, el entorno de servidor de charla persistente aparece en su cliente.</span><span class="sxs-lookup"><span data-stu-id="87572-106">If a user is enabled for Persistent Chat Server by policy, then the Persistent Chat Server environment appears in their client.</span></span>
  
> [!NOTE]
> <span data-ttu-id="87572-107">En la topología, el servidor de charla persistente sitio directivas se aplica globalmente, por grupo de usuario, o por el sitio del usuario o por usuario.</span><span class="sxs-lookup"><span data-stu-id="87572-107">In the topology, Persistent Chat Server site policies apply globally, per user's pool, or per user's site, or per user.</span></span> 
  
<span data-ttu-id="87572-108">La directiva global se crea automáticamente al implementar servidor de Chat persistente, y puede ser configurado, pero no eliminar.</span><span class="sxs-lookup"><span data-stu-id="87572-108">The global policy is created automatically when you deploy Persistent Chat Server, and it can be configured, but not deleted.</span></span> <span data-ttu-id="87572-109">Porque la directiva global se aplica a todos los usuarios, no tiene que establecerse para cada usuario.</span><span class="sxs-lookup"><span data-stu-id="87572-109">Because the global policy applies to all users, it doesn't have to be set per user.</span></span>
  
<span data-ttu-id="87572-110">Puede crear y configurar varias directivas de usuario y sitio que, junto con la directiva global, permiten a los usuarios para el servidor de charla persistente.</span><span class="sxs-lookup"><span data-stu-id="87572-110">You can create and configure multiple site and user policies which, together with the global policy, enable users for Persistent Chat Server.</span></span> <span data-ttu-id="87572-111">Sitio y grupo de directivas de servidor de charla persistente anulan la directiva persistente Chat Server global, pero sólo para los usuarios de ese sitio.</span><span class="sxs-lookup"><span data-stu-id="87572-111">Pool and site Persistent Chat Server policies override the global Persistent Chat Server policy, but only for users of that site.</span></span> <span data-ttu-id="87572-112">Las directivas de usuario reemplazan a las directivas globales, de grupo y de sitio para los usuarios que tengan asignada esa directiva de usuario.</span><span class="sxs-lookup"><span data-stu-id="87572-112">User policies override both global, pool, and site policies for the users to whom the user policy is assigned.</span></span>
  
> [!NOTE]
> <span data-ttu-id="87572-113">Para configurar y utilizar el servidor de charla persistente, debe utilizar primero el generador de topología para agregar compatibilidad con el servidor de charla persistente a la topología y, a continuación, publicar la topología.</span><span class="sxs-lookup"><span data-stu-id="87572-113">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="87572-114">Para obtener información detallada, vea [Agregar servidor Chat persistente a su Skype para Business Server 2015 topología](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="87572-114">For details, see [Add Persistent Chat Server to your Skype for Business Server 2015 topology](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md).</span></span> 
  
## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="87572-115">Tareas que puede realizar</span><span class="sxs-lookup"><span data-stu-id="87572-115">Tasks that you can perform</span></span>

<span data-ttu-id="87572-116">En la página **Directiva de chat persistente** puede realizar las siguientes tareas: habilitar y administrar la directiva de servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="87572-116">You can perform the following tasks on the **Persistent Chat Policy** page: enable and manage Persistent Chat Server policy.</span></span>
  
## <a name="to-configure-the-global-policy-for-persistent-chat"></a><span data-ttu-id="87572-117">Para configurar la directiva Global para Chat persistente</span><span class="sxs-lookup"><span data-stu-id="87572-117">To configure the Global Policy for Persistent Chat</span></span>

1. <span data-ttu-id="87572-118">Inicie sesión en cualquier equipo de la implementación interna con una cuenta de usuario asignada a los roles CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="87572-118">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="87572-119">Desde el menú **Inicio** , seleccione el Skype para Panel de Control de servidor de Business o abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin.</span><span class="sxs-lookup"><span data-stu-id="87572-119">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="87572-120">En Skype para Business Server Control Panel, haga clic en **Charla persistente**y, a continuación, haga clic en **Directiva de Chat persistentes**.</span><span class="sxs-lookup"><span data-stu-id="87572-120">In Skype for Business Server Control Panel, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="87572-121">Haga clic en **Global** en la lista de directivas, en **Editar** y, luego, en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="87572-121">Click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="87572-122">En **Editar directiva de chat persistente - Global**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="87572-122">In **Edit Persistent Chat Policy - Global**, do the following:</span></span>
    
  - <span data-ttu-id="87572-123">En **Nombre**, especifique un nuevo nombre para la directiva global si no desea usar el valor predeterminado de Global.</span><span class="sxs-lookup"><span data-stu-id="87572-123">In **Name**, specify a new name for the global policy, if you do not want to use the default of Global.</span></span>
    
  - <span data-ttu-id="87572-124">En **Descripción**, proporcione detalles acerca de la directiva de usuario (por ejemplo, la directiva Global para _centralSiteName_).</span><span class="sxs-lookup"><span data-stu-id="87572-124">In **Description**, provide details about what the user policy is (for example, Global policy for  _centralSiteName_).</span></span>
    
  - <span data-ttu-id="87572-125">Para controlar la charla persistente para todos los sitios y los usuarios que no específicamente se controla a través de una directiva de sitio o usuario, active o desactive la casilla de verificación **Habilitar Chat persistente** .</span><span class="sxs-lookup"><span data-stu-id="87572-125">To control Persistent Chat for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="87572-126">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="87572-126">Click **Commit**.</span></span>
    
## <a name="to-create-a-persistent-chat-policy-for-a-site"></a><span data-ttu-id="87572-127">Para crear una directiva persistente de charla para un sitio</span><span class="sxs-lookup"><span data-stu-id="87572-127">To create a Persistent Chat policy for a site</span></span>

<span data-ttu-id="87572-128">Para cada sitio que se ha implementado, puede crear una directiva persistente Chat específico del sitio.</span><span class="sxs-lookup"><span data-stu-id="87572-128">For each site you have deployed, you can create a site-specific Persistent Chat policy.</span></span>
  
<span data-ttu-id="87572-129">La configuración de la directiva de sitio reemplaza la directiva global, pero solo para el sitio específico que abarca la directiva de sitio.</span><span class="sxs-lookup"><span data-stu-id="87572-129">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span>
  
1. <span data-ttu-id="87572-130">Inicie sesión en cualquier equipo de la implementación interna con una cuenta de usuario asignada a los roles CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="87572-130">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="87572-131">Desde el menú **Inicio** , seleccione el Skype para Panel de Control de servidor de Business o abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin.</span><span class="sxs-lookup"><span data-stu-id="87572-131">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="87572-132">En la barra de navegación izquierda, haga clic en **Chat persistente** y, luego, en **Directiva de chat persistente**.</span><span class="sxs-lookup"><span data-stu-id="87572-132">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="87572-133">Haga clic en **Nuevo** y en **Directiva de sitio**.</span><span class="sxs-lookup"><span data-stu-id="87572-133">Click **New**, and then click **Site policy**.</span></span>
    
5. <span data-ttu-id="87572-134">En **Seleccionar un sitio**, haga clic en el sitio al que se va a aplicar la directiva.</span><span class="sxs-lookup"><span data-stu-id="87572-134">In **Select a Site**, click the site to which the policy is to be applied.</span></span>
    
6. <span data-ttu-id="87572-135">En **Nueva directiva de chat persistente**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="87572-135">In **New Persistent Chat Policy**, do the following:</span></span>
    
  - <span data-ttu-id="87572-136">En **Nombre**, especifique un nombre para la nueva directiva de sitio (por ejemplo, Redmond).</span><span class="sxs-lookup"><span data-stu-id="87572-136">In **Name**, specify a name for the new site policy (for example, Redmond).</span></span>
    
  - <span data-ttu-id="87572-137">En **Descripción**, dé detalles sobre lo que es la directiva del sitio (por ejemplo, directiva de salón de chat de Redmond).</span><span class="sxs-lookup"><span data-stu-id="87572-137">In **Description**, provide details about what the site policy is (for example, chat room policy for Redmond).</span></span>
    
  - <span data-ttu-id="87572-138">Para controlar el chat persistente para todos los sitios no controlados específicamente con una directiva de sitio, active o desactive la casilla **Habilitar chat persistente**.</span><span class="sxs-lookup"><span data-stu-id="87572-138">To control Persistent Chat for all sites not specifically controlled through a site policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
7. <span data-ttu-id="87572-139">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="87572-139">Click **Commit**.</span></span>
    
## <a name="to-create-a-user-policy-for-persistent-chat"></a><span data-ttu-id="87572-140">Para crear una directiva de usuario para Chat persistente</span><span class="sxs-lookup"><span data-stu-id="87572-140">To create a user policy for Persistent Chat</span></span>

<span data-ttu-id="87572-141">Skype para el Panel de Control de servidor empresarial, para definir las directivas de usuario que se pueden asignar a los usuarios de **los usuarios**.</span><span class="sxs-lookup"><span data-stu-id="87572-141">In the Skype for Business Server Control Panel, you define user policies that can be assigned to users in **Users**.</span></span>
  
<span data-ttu-id="87572-142">La directiva de usuario reemplaza la directiva global y las directivas de sitio, pero solo para los usuarios específicos que tienen asignada dicha directiva.</span><span class="sxs-lookup"><span data-stu-id="87572-142">The user policy overrides the global policy and site policies, but only for the specific users who are assigned the user policy.</span></span>
  
1. <span data-ttu-id="87572-143">Inicie sesión en cualquier equipo de la implementación interna con una cuenta de usuario asignada a los roles CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="87572-143">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="87572-144">Desde el menú **Inicio** , seleccione el Skype para Panel de Control de servidor de Business o abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin.</span><span class="sxs-lookup"><span data-stu-id="87572-144">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="87572-145">En la barra de navegación izquierda, haga clic en **Chat persistente** y, luego, en **Directiva de chat persistente**.</span><span class="sxs-lookup"><span data-stu-id="87572-145">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="87572-146">Haga clic en **Nuevo** y, luego, en **Directiva de usuario**.</span><span class="sxs-lookup"><span data-stu-id="87572-146">Click **New**, and then click **User policy**.</span></span>
    
5. <span data-ttu-id="87572-147">En **Nueva directiva de chat persistente**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="87572-147">In **New Persistent Chat Policy**, do the following:</span></span>
    
  - <span data-ttu-id="87572-148">En **Nombre**, especifique un nombre para la nueva directiva de usuario.</span><span class="sxs-lookup"><span data-stu-id="87572-148">In **Name**, specify a name for the new user policy.</span></span>
    
  - <span data-ttu-id="87572-149">En **Descripción**, proporcione detalles acerca de la directiva de usuario (por ejemplo, la directiva persistente de charla para un usuario específico).</span><span class="sxs-lookup"><span data-stu-id="87572-149">In **Description**, provide details about what the user policy is (for example, Persistent Chat policy for specific user).</span></span>
    
  - <span data-ttu-id="87572-150">Para controlar la charla persistente para todos los usuarios que no están controlados específicamente a través de una directiva de usuario, active o desactive la casilla de verificación **Habilitar Chat persistente** .</span><span class="sxs-lookup"><span data-stu-id="87572-150">To control Persistent Chat for all users who are not specifically controlled through a user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="87572-151">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="87572-151">Click **Commit**.</span></span>
    
## <a name="to-apply-a-persistent-chat-user-policy-to-a-user-account"></a><span data-ttu-id="87572-152">Para aplicar una directiva de usuario de charla persistente a una cuenta de usuario</span><span class="sxs-lookup"><span data-stu-id="87572-152">To apply a Persistent Chat user policy to a user account</span></span>

<span data-ttu-id="87572-153">Si un usuario se ha habilitado para Skype para el negocio, puede aplicar las políticas apropiadas a usuarios específicos para habilitarlos o deshabilitarlos para servidor de Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="87572-153">If a user has been enabled for Skype for Business, you can apply appropriate policies to specific users to enable or disable them for Persistent Chat Server.</span></span>
  
<span data-ttu-id="87572-154">Utilice el procedimiento de este tema para aplicar una directiva de usuario de charla persistente creada anteriormente a una o más cuentas de usuario o grupos de usuarios.</span><span class="sxs-lookup"><span data-stu-id="87572-154">Use the procedure in this topic to apply a previously created Persistent Chat user policy to one or more user accounts or user groups.</span></span>
  
1. <span data-ttu-id="87572-155">Inicie sesión en cualquier equipo de la implementación interna con una cuenta de usuario asignada a los roles CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator.</span><span class="sxs-lookup"><span data-stu-id="87572-155">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="87572-156">Desde el menú **Inicio** , seleccione el Skype para Panel de Control de servidor de Business o abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin.</span><span class="sxs-lookup"><span data-stu-id="87572-156">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="87572-157">En la barra de navegación izquierda, haga clic en **Usuarios** y, luego, busque la cuenta de usuario que desea configurar.</span><span class="sxs-lookup"><span data-stu-id="87572-157">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>
    
4. <span data-ttu-id="87572-158">En la tabla donde se enumeran los resultados de la búsqueda, haga clic en la cuenta de usuario, en **Editar** y, finalmente, en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="87572-158">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="87572-159">En **Editar usuario de Lync Server** en **charla persistente de la política**, seleccione la directiva de usuario persistentes de charla que desea aplicar.</span><span class="sxs-lookup"><span data-stu-id="87572-159">In **Edit Lync Server User** under **Persistent Chat policy**, select the Persistent Chat user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="87572-160">La ** \<automática\> ** configuración aplica la directiva efectiva de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="87572-160">The **\<Automatic\>** settings apply the default effective policy.</span></span> <span data-ttu-id="87572-161">El servidor aplica esta configuración automáticamente.</span><span class="sxs-lookup"><span data-stu-id="87572-161">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="87572-162">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="87572-162">Click **Commit**.</span></span>
    

