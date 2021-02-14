---
title: Página principal de directiva de chat persistente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.PersistentChatPolicyMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0dc18d5c-82d6-4d39-afb1-efdb3ae6d2c7
description: Puede usar la página Directiva de chat persistente del grupo de chat persistente para administrar directivas a nivel global, de grupo, de sitio o de usuario, incluida la configuración de la directiva global predeterminada y la creación de una o más directivas de usuario y sitio adicionales para la implementación. Si un usuario está habilitado para el servidor de chat persistente por directiva, el entorno del servidor de chat persistente aparece en su cliente.
ms.openlocfilehash: 9664cbf182fe388fbffd2b270e306a4c17b36e95
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49819310"
---
# <a name="persistent-chat-policy-main-page"></a><span data-ttu-id="ba3e0-104">Página principal de directiva de chat persistente</span><span class="sxs-lookup"><span data-stu-id="ba3e0-104">Persistent Chat Policy Main Page</span></span>
 
<span data-ttu-id="ba3e0-105">Puede usar la página Directiva de **chat** persistente del grupo de **chat** persistente para administrar directivas a nivel global, de grupo, de sitio o de usuario, incluida la configuración de la directiva global predeterminada y la creación de una o más directivas de usuario y sitio adicionales para su implementación.</span><span class="sxs-lookup"><span data-stu-id="ba3e0-105">You can use the **Persistent Chat Policy** page of the **Persistent Chat** group to manage policies at a global, pool, site, or user level, including configuring the default global policy and creating one or more additional user and site policies for your deployment.</span></span> <span data-ttu-id="ba3e0-106">Si un usuario está habilitado para el servidor de chat persistente por directiva, el entorno del servidor de chat persistente aparece en su cliente.</span><span class="sxs-lookup"><span data-stu-id="ba3e0-106">If a user is enabled for Persistent Chat Server by policy, then the Persistent Chat Server environment appears in their client.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ba3e0-107">En la topología, las directivas de sitio del servidor de chat persistente se aplican globalmente, por grupo de usuarios, por sitio de usuario o por usuario.</span><span class="sxs-lookup"><span data-stu-id="ba3e0-107">In the topology, Persistent Chat Server site policies apply globally, per user's pool, or per user's site, or per user.</span></span> 
  
<span data-ttu-id="ba3e0-108">La directiva global se crea automáticamente al implementar el servidor de chat persistente y se puede configurar, pero no eliminar.</span><span class="sxs-lookup"><span data-stu-id="ba3e0-108">The global policy is created automatically when you deploy Persistent Chat Server, and it can be configured, but not deleted.</span></span> <span data-ttu-id="ba3e0-109">Dado que la directiva global se aplica a todos los usuarios, no tiene que establecerse por usuario.</span><span class="sxs-lookup"><span data-stu-id="ba3e0-109">Because the global policy applies to all users, it doesn't have to be set per user.</span></span>
  
<span data-ttu-id="ba3e0-110">Puede crear y configurar varias directivas de sitio y usuario que, junto con la directiva global, habilitan a los usuarios para el servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="ba3e0-110">You can create and configure multiple site and user policies which, together with the global policy, enable users for Persistent Chat Server.</span></span> <span data-ttu-id="ba3e0-111">Las directivas de servidor de chat persistente de grupo y sitio invalidan la directiva global del servidor de chat persistente, pero solo para los usuarios de ese sitio.</span><span class="sxs-lookup"><span data-stu-id="ba3e0-111">Pool and site Persistent Chat Server policies override the global Persistent Chat Server policy, but only for users of that site.</span></span> <span data-ttu-id="ba3e0-112">Las directivas de usuario anulan las directivas globales, de grupo y de sitio para los usuarios a los que se asigna la directiva de usuario.</span><span class="sxs-lookup"><span data-stu-id="ba3e0-112">User policies override both global, pool, and site policies for the users to whom the user policy is assigned.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ba3e0-113">Para configurar y usar el servidor de chat persistente, primero debe usar el Generador de topologías para agregar compatibilidad con el servidor de chat persistente a la topología y, a continuación, publicar la topología.</span><span class="sxs-lookup"><span data-stu-id="ba3e0-113">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="ba3e0-114">Para obtener más información, consulte Agregar un servidor de chat persistente a la topología de [Skype Empresarial Server 2015.](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)</span><span class="sxs-lookup"><span data-stu-id="ba3e0-114">For details, see [Add Persistent Chat Server to your Skype for Business Server 2015 topology](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md).</span></span> 
  
## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="ba3e0-115">Tareas que puede realizar</span><span class="sxs-lookup"><span data-stu-id="ba3e0-115">Tasks that you can perform</span></span>

<span data-ttu-id="ba3e0-116">Puede realizar las siguientes tareas en la página Directiva de **chat** persistente: habilitar y administrar la directiva de servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="ba3e0-116">You can perform the following tasks on the **Persistent Chat Policy** page: enable and manage Persistent Chat Server policy.</span></span>
  
## <a name="to-configure-the-global-policy-for-persistent-chat"></a><span data-ttu-id="ba3e0-117">Para configurar la directiva global para chat persistente</span><span class="sxs-lookup"><span data-stu-id="ba3e0-117">To configure the Global Policy for Persistent Chat</span></span>

1. <span data-ttu-id="ba3e0-118">Desde una cuenta de usuario que se asigne al rol CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="ba3e0-118">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="ba3e0-119">En el **menú Inicio,** seleccione el Panel de control de Skype Empresarial Server o abra una ventana del explorador y, a continuación, escriba la dirección URL de administración.</span><span class="sxs-lookup"><span data-stu-id="ba3e0-119">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="ba3e0-120">En el Panel de control de Skype Empresarial Server, haga clic en **Chat** persistente y, a continuación, haga clic en **Directiva de chat persistente.**</span><span class="sxs-lookup"><span data-stu-id="ba3e0-120">In Skype for Business Server Control Panel, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="ba3e0-121">Haga clic en **Global** en la lista de directivas, haga clic en **Editar** y, a continuación, en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="ba3e0-121">Click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="ba3e0-122">In **Editar directiva de chat persistente - Global**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ba3e0-122">In **Edit Persistent Chat Policy - Global**, do the following:</span></span>
    
   - <span data-ttu-id="ba3e0-123">En **Nombre**, especifique un nombre nuevo para la directiva global, si no desea usar el nombre predeterminado (Global).</span><span class="sxs-lookup"><span data-stu-id="ba3e0-123">In **Name**, specify a new name for the global policy, if you do not want to use the default of Global.</span></span>
    
   - <span data-ttu-id="ba3e0-124">En **Descripción,** proporcione detalles sobre cuál es la directiva de usuario (por ejemplo, Directiva global para  _centralSiteName_).</span><span class="sxs-lookup"><span data-stu-id="ba3e0-124">In **Description**, provide details about what the user policy is (for example, Global policy for  _centralSiteName_).</span></span>
    
   - <span data-ttu-id="ba3e0-125">Para controlar el chat persistente para todos los sitios y usuarios que no se controlan específicamente a través de una directiva de sitio o de usuario, active o desactive la casilla Habilitar **chat** persistente.</span><span class="sxs-lookup"><span data-stu-id="ba3e0-125">To control Persistent Chat for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="ba3e0-126">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="ba3e0-126">Click **Commit**.</span></span>
    
## <a name="to-create-a-persistent-chat-policy-for-a-site"></a><span data-ttu-id="ba3e0-127">Para crear una directiva de chat persistente para un sitio</span><span class="sxs-lookup"><span data-stu-id="ba3e0-127">To create a Persistent Chat policy for a site</span></span>

<span data-ttu-id="ba3e0-128">Para cada sitio que haya implementado, puede crear una directiva de chat persistente específica del sitio.</span><span class="sxs-lookup"><span data-stu-id="ba3e0-128">For each site you have deployed, you can create a site-specific Persistent Chat policy.</span></span>
  
<span data-ttu-id="ba3e0-129">La configuración de la directiva de sitio invalida la directiva global, pero solo en el caso del sitio específico que determina la directiva.</span><span class="sxs-lookup"><span data-stu-id="ba3e0-129">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span>
  
1. <span data-ttu-id="ba3e0-130">Desde una cuenta de usuario que se asigne al rol CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="ba3e0-130">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="ba3e0-131">En el **menú Inicio,** seleccione el Panel de control de Skype Empresarial Server o abra una ventana del explorador y, a continuación, escriba la dirección URL de administración.</span><span class="sxs-lookup"><span data-stu-id="ba3e0-131">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="ba3e0-132">En la barra de navegación izquierda, haga clic en **Chat persistente** y, a continuación, en **Directiva de chat persistente**.</span><span class="sxs-lookup"><span data-stu-id="ba3e0-132">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="ba3e0-133">Haga clic en **Nuevo** y en **Directiva de sitio**.</span><span class="sxs-lookup"><span data-stu-id="ba3e0-133">Click **New**, and then click **Site policy**.</span></span>
    
5. <span data-ttu-id="ba3e0-134">En **Seleccionar un sitio**, haga clic en el sitio al que se va a aplicar la directiva.</span><span class="sxs-lookup"><span data-stu-id="ba3e0-134">In **Select a Site**, click the site to which the policy is to be applied.</span></span>
    
6. <span data-ttu-id="ba3e0-135">En **Nueva directiva de chat persistente**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ba3e0-135">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="ba3e0-136">En **Nombre**, especifique un nombre para la nueva directiva de sitio (por ejemplo, Redmond).</span><span class="sxs-lookup"><span data-stu-id="ba3e0-136">In **Name**, specify a name for the new site policy (for example, Redmond).</span></span>
    
   - <span data-ttu-id="ba3e0-137">En **Descripción**, proporcione información detallada sobre la directiva de sitio (por ejemplo, directiva de salón de chat para Redmond).</span><span class="sxs-lookup"><span data-stu-id="ba3e0-137">In **Description**, provide details about what the site policy is (for example, chat room policy for Redmond).</span></span>
    
   - <span data-ttu-id="ba3e0-138">Para controlar el chat persistente para todos los sitios no controlados específicamente mediante una directiva de sitio, active o desactive la casilla **Habilitar chat persistente**.</span><span class="sxs-lookup"><span data-stu-id="ba3e0-138">To control Persistent Chat for all sites not specifically controlled through a site policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
7. <span data-ttu-id="ba3e0-139">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="ba3e0-139">Click **Commit**.</span></span>
    
## <a name="to-create-a-user-policy-for-persistent-chat"></a><span data-ttu-id="ba3e0-140">Para crear una directiva de usuario para chat persistente</span><span class="sxs-lookup"><span data-stu-id="ba3e0-140">To create a user policy for Persistent Chat</span></span>

<span data-ttu-id="ba3e0-141">En el Panel de control de Skype Empresarial Server, defina las directivas de usuario que se pueden asignar a los usuarios en **Usuarios.**</span><span class="sxs-lookup"><span data-stu-id="ba3e0-141">In the Skype for Business Server Control Panel, you define user policies that can be assigned to users in **Users**.</span></span>
  
<span data-ttu-id="ba3e0-142">Las directivas de usuario invalidan las directivas globales y las directivas de sitio, aunque solo se pueden asignar a usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="ba3e0-142">The user policy overrides the global policy and site policies, but only for the specific users who are assigned the user policy.</span></span>
  
1. <span data-ttu-id="ba3e0-143">Desde una cuenta de usuario que se asigne al rol CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="ba3e0-143">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="ba3e0-144">En el **menú Inicio,** seleccione el Panel de control de Skype Empresarial Server o abra una ventana del explorador y, a continuación, escriba la dirección URL de administración.</span><span class="sxs-lookup"><span data-stu-id="ba3e0-144">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="ba3e0-145">En la barra de navegación izquierda, haga clic en **Chat persistente** y, a continuación, en **Directiva de chat persistente**.</span><span class="sxs-lookup"><span data-stu-id="ba3e0-145">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="ba3e0-146">Haga clic en **Nuevo** y en **Directiva de usuario**.</span><span class="sxs-lookup"><span data-stu-id="ba3e0-146">Click **New**, and then click **User policy**.</span></span>
    
5. <span data-ttu-id="ba3e0-147">En **Nueva directiva de chat persistente**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ba3e0-147">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="ba3e0-148">En **Nombre**, especifique un nombre para la nueva directiva de usuario.</span><span class="sxs-lookup"><span data-stu-id="ba3e0-148">In **Name**, specify a name for the new user policy.</span></span>
    
   - <span data-ttu-id="ba3e0-149">En **Descripción,** proporcione detalles sobre la directiva de usuario (por ejemplo, directiva de chat persistente para un usuario específico).</span><span class="sxs-lookup"><span data-stu-id="ba3e0-149">In **Description**, provide details about what the user policy is (for example, Persistent Chat policy for specific user).</span></span>
    
   - <span data-ttu-id="ba3e0-150">Para controlar el chat persistente para todos los usuarios que no están controlados específicamente a través de una directiva de usuario, active o desactive la casilla Habilitar **chat** persistente.</span><span class="sxs-lookup"><span data-stu-id="ba3e0-150">To control Persistent Chat for all users who are not specifically controlled through a user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="ba3e0-151">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="ba3e0-151">Click **Commit**.</span></span>
    
## <a name="to-apply-a-persistent-chat-user-policy-to-a-user-account"></a><span data-ttu-id="ba3e0-152">Para aplicar una directiva de usuario de chat persistente a una cuenta de usuario</span><span class="sxs-lookup"><span data-stu-id="ba3e0-152">To apply a Persistent Chat user policy to a user account</span></span>

<span data-ttu-id="ba3e0-153">Si un usuario se ha habilitado para Skype Empresarial, puede aplicar directivas adecuadas a usuarios específicos para habilitarlos o deshabilitarlos para el servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="ba3e0-153">If a user has been enabled for Skype for Business, you can apply appropriate policies to specific users to enable or disable them for Persistent Chat Server.</span></span>
  
<span data-ttu-id="ba3e0-154">Use el procedimiento descrito en este tema para aplicar una directiva de usuario de chat persistente creada anteriormente a una o varias cuentas de usuario o grupos de usuarios.</span><span class="sxs-lookup"><span data-stu-id="ba3e0-154">Use the procedure in this topic to apply a previously created Persistent Chat user policy to one or more user accounts or user groups.</span></span>
  
1. <span data-ttu-id="ba3e0-155">Desde una cuenta de usuario que se asigne al rol CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="ba3e0-155">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="ba3e0-156">En el **menú Inicio,** seleccione el Panel de control de Skype Empresarial Server o abra una ventana del explorador y, a continuación, escriba la dirección URL de administración.</span><span class="sxs-lookup"><span data-stu-id="ba3e0-156">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="ba3e0-157">En la barra de navegación izquierda, haga clic en  **Usuarios** y, a continuación, busque en la cuenta de usuario que desea configurar.</span><span class="sxs-lookup"><span data-stu-id="ba3e0-157">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>
    
4. <span data-ttu-id="ba3e0-158">En la tabla donde se enumeran los resultados de la búsqueda, haga clic en la cuenta de usuario, en  **Editar** y, a continuación, en  **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="ba3e0-158">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="ba3e0-159">En **Editar usuario de Lync Server en** la directiva de chat **persistente,** seleccione la directiva de usuario de chat persistente que desee aplicar.</span><span class="sxs-lookup"><span data-stu-id="ba3e0-159">In **Edit Lync Server User** under **Persistent Chat policy**, select the Persistent Chat user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ba3e0-160">La **\<Automatic\>** configuración aplica la directiva efectiva predeterminada.</span><span class="sxs-lookup"><span data-stu-id="ba3e0-160">The **\<Automatic\>** settings apply the default effective policy.</span></span> <span data-ttu-id="ba3e0-161">Esta configuración se aplica automáticamente por el servidor.</span><span class="sxs-lookup"><span data-stu-id="ba3e0-161">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="ba3e0-162">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="ba3e0-162">Click **Commit**.</span></span>
    

