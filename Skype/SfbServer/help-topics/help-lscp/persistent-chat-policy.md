---
title: Directiva de chat persistente
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
- ms.lync.lscp.PersistentChatPolicy
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eb9e95b9-f69d-4545-970f-9dfdd93b0eff
description: Puede usar la página Directiva de chat persistente del grupo de chat persistente para administrar directivas a nivel global, de grupo, de sitio o de usuario, incluida la configuración de la directiva global predeterminada y la creación de una o más directivas de usuario y sitio adicionales para la implementación. Si el servidor de chat persistente está habilitado para un usuario por directiva, el entorno del servidor de chat persistente aparece en su cliente.
ms.openlocfilehash: e7148530f571a46937ee8d8a3bf44315ac692eb6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49819300"
---
# <a name="persistent-chat-policy"></a><span data-ttu-id="11ff8-104">Directiva de chat persistente</span><span class="sxs-lookup"><span data-stu-id="11ff8-104">Persistent Chat Policy</span></span>
 
<span data-ttu-id="11ff8-105">Puede usar la página Directiva de **chat** persistente del grupo de **chat** persistente para administrar directivas a nivel global, de grupo, de sitio o de usuario, incluida la configuración de la directiva global predeterminada y la creación de una o más directivas de usuario y sitio adicionales para su implementación.</span><span class="sxs-lookup"><span data-stu-id="11ff8-105">You can use the **Persistent Chat Policy** page of the **Persistent Chat** group to manage policies at a global, pool, site, or user level, including configuring the default global policy and creating one or more additional user and site policies for your deployment.</span></span> <span data-ttu-id="11ff8-106">Si el servidor de chat persistente está habilitado para un usuario por directiva, el entorno del servidor de chat persistente aparece en su cliente.</span><span class="sxs-lookup"><span data-stu-id="11ff8-106">If Persistent Chat Server is enabled for a user by policy, then the Persistent Chat Server environment appears in their client.</span></span>
  
<span data-ttu-id="11ff8-107">La directiva global se crea automáticamente al implementar el servidor de chat persistente y se puede configurar, pero no eliminar.</span><span class="sxs-lookup"><span data-stu-id="11ff8-107">The global policy is created automatically when you deploy Persistent Chat Server, and it can be configured, but not deleted.</span></span> <span data-ttu-id="11ff8-108">Dado que la directiva global se aplica a todos los usuarios, no tiene que establecerse por usuario.</span><span class="sxs-lookup"><span data-stu-id="11ff8-108">Because the global policy applies to all users, it doesn't have to be set per user.</span></span>
  
<span data-ttu-id="11ff8-109">Puede crear y configurar varias directivas de sitio y usuario que, junto con la directiva global, habilitan a los usuarios para el servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="11ff8-109">You can create and configure multiple site and user policies which, together with the global policy, enable users for Persistent Chat Server.</span></span> <span data-ttu-id="11ff8-110">Las directivas de servidor de chat persistente de grupo y sitio invalidan la directiva global del servidor de chat persistente, pero solo para los usuarios de ese sitio.</span><span class="sxs-lookup"><span data-stu-id="11ff8-110">Pool and site Persistent Chat Server policies override the global Persistent Chat Server policy, but only for users of that site.</span></span> <span data-ttu-id="11ff8-111">Las directivas de usuario anulan las directivas globales, de grupo y de sitio para los usuarios a los que se asigna la directiva de usuario.</span><span class="sxs-lookup"><span data-stu-id="11ff8-111">User policies override both global, pool, and site policies for the users to whom the user policy is assigned.</span></span>
  
> [!NOTE]
> <span data-ttu-id="11ff8-112">Para configurar y usar el servidor de chat persistente, primero debe usar el Generador de topologías para agregar compatibilidad con el servidor de chat persistente a la topología y, a continuación, publicar la topología.</span><span class="sxs-lookup"><span data-stu-id="11ff8-112">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="11ff8-113">Para obtener más información, consulte Agregar un servidor de chat persistente a la topología de [Skype Empresarial Server 2015.](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)</span><span class="sxs-lookup"><span data-stu-id="11ff8-113">For details, see [Add Persistent Chat Server to your Skype for Business Server 2015 topology](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md).</span></span> 
  
## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="11ff8-114">Tareas que puede realizar</span><span class="sxs-lookup"><span data-stu-id="11ff8-114">Tasks that you can perform</span></span>

<span data-ttu-id="11ff8-115">Puede realizar las siguientes tareas en la página **Directiva de chat** persistente: habilitar la directiva de servidor de chat persistente; administrar la directiva de servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="11ff8-115">You can perform the following tasks on the **Persistent Chat Policy** page: enable Persistent Chat Server policy; manage Persistent Chat Server policy.</span></span>
  
## <a name="to-configure-the-global-policy-for-persistent-chat"></a><span data-ttu-id="11ff8-116">Para configurar la directiva global para el chat persistente</span><span class="sxs-lookup"><span data-stu-id="11ff8-116">To configure the Global Policy for Persistent Chat</span></span>

1. <span data-ttu-id="11ff8-117">Desde una cuenta de usuario que se asigne al rol CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="11ff8-117">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="11ff8-118">En el **menú Inicio,** seleccione el Panel de control de Skype Empresarial Server o abra una ventana del explorador y, a continuación, escriba la dirección URL de administración.</span><span class="sxs-lookup"><span data-stu-id="11ff8-118">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="11ff8-119">En el Panel de control de Skype Empresarial Server, haga clic en **Chat** persistente y, a continuación, haga clic en **Directiva de chat persistente.**</span><span class="sxs-lookup"><span data-stu-id="11ff8-119">In Skype for Business Server Control Panel, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="11ff8-120">Haga clic en **Global** en la lista de directivas, haga clic en **Editar** y, a continuación, en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="11ff8-120">Click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="11ff8-121">In **Editar directiva de chat persistente - Global**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="11ff8-121">In **Edit Persistent Chat Policy - Global**, do the following:</span></span>
    
   - <span data-ttu-id="11ff8-122">En **Nombre**, especifique un nombre nuevo para la directiva global, si no desea usar el nombre predeterminado (Global).</span><span class="sxs-lookup"><span data-stu-id="11ff8-122">In **Name**, specify a new name for the global policy, if you do not want to use the default of Global.</span></span>
    
   - <span data-ttu-id="11ff8-123">En **Descripción,** proporcione detalles sobre la directiva de usuario (por ejemplo, directiva global para  _centralSiteName_).</span><span class="sxs-lookup"><span data-stu-id="11ff8-123">In **Description**, provide details about what the user policy is (for example, Global policy for  _centralSiteName_).</span></span>
    
   - <span data-ttu-id="11ff8-124">Para controlar el chat persistente para todos los sitios y usuarios que no se controlan específicamente a través de una directiva de sitio o de usuario, active o desactive la casilla Habilitar **chat** persistente.</span><span class="sxs-lookup"><span data-stu-id="11ff8-124">To control Persistent Chat for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="11ff8-125">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="11ff8-125">Click **Commit**.</span></span>
    
## <a name="to-create-a-persistent-chat-policy-for-a-site"></a><span data-ttu-id="11ff8-126">Para crear una directiva de chat persistente para un sitio</span><span class="sxs-lookup"><span data-stu-id="11ff8-126">To create a Persistent Chat policy for a site</span></span>

<span data-ttu-id="11ff8-127">Para cada sitio que haya implementado, puede crear una directiva de chat persistente específica del sitio.</span><span class="sxs-lookup"><span data-stu-id="11ff8-127">For each site you have deployed, you can create a site-specific Persistent Chat policy.</span></span>
  
<span data-ttu-id="11ff8-128">La configuración de la directiva de sitio invalida la directiva global, pero solo en el caso del sitio específico que determina la directiva.</span><span class="sxs-lookup"><span data-stu-id="11ff8-128">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span>
  
1. <span data-ttu-id="11ff8-129">Desde una cuenta de usuario que se asigne al rol CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="11ff8-129">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="11ff8-130">En el **menú Inicio,** seleccione el Panel de control de Skype Empresarial Server o abra una ventana del explorador y, a continuación, escriba la dirección URL de administración.</span><span class="sxs-lookup"><span data-stu-id="11ff8-130">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="11ff8-131">En la barra de navegación izquierda, haga clic en **Chat persistente** y, a continuación, en **Directiva de chat persistente**.</span><span class="sxs-lookup"><span data-stu-id="11ff8-131">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="11ff8-132">Haga clic en **Nuevo** y en **Directiva de sitio**.</span><span class="sxs-lookup"><span data-stu-id="11ff8-132">Click **New**, and then click **Site policy**.</span></span>
    
5. <span data-ttu-id="11ff8-133">En **Seleccionar un sitio**, haga clic en el sitio al que se va a aplicar la directiva.</span><span class="sxs-lookup"><span data-stu-id="11ff8-133">In **Select a Site**, click the site to which the policy is to be applied.</span></span>
    
6. <span data-ttu-id="11ff8-134">En **Nueva directiva de chat persistente**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="11ff8-134">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="11ff8-135">En **Nombre**, especifique un nombre para la nueva directiva de sitio (por ejemplo, Redmond).</span><span class="sxs-lookup"><span data-stu-id="11ff8-135">In **Name**, specify a name for the new site policy (for example, Redmond).</span></span>
    
   - <span data-ttu-id="11ff8-136">En **Descripción**, proporcione información detallada sobre la directiva de sitio (por ejemplo, directiva de salón de chat para Redmond).</span><span class="sxs-lookup"><span data-stu-id="11ff8-136">In **Description**, provide details about what the site policy is (for example, chat room policy for Redmond).</span></span>
    
   - <span data-ttu-id="11ff8-137">Para controlar el chat persistente para todos los sitios no controlados específicamente mediante una directiva de sitio, active o desactive la casilla **Habilitar chat persistente**.</span><span class="sxs-lookup"><span data-stu-id="11ff8-137">To control Persistent Chat for all sites not specifically controlled through a site policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
7. <span data-ttu-id="11ff8-138">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="11ff8-138">Click **Commit**.</span></span>
    
## <a name="to-create-a-user-policy-for-persistent-chat"></a><span data-ttu-id="11ff8-139">Para crear una directiva de usuario para chat persistente</span><span class="sxs-lookup"><span data-stu-id="11ff8-139">To create a user policy for Persistent Chat</span></span>

<span data-ttu-id="11ff8-140">En el Panel de control de Skype Empresarial Server, defina las directivas de usuario que se pueden asignar a los usuarios en **Usuarios.**</span><span class="sxs-lookup"><span data-stu-id="11ff8-140">In the Skype for Business Server Control Panel, you define user policies that can be assigned to users in **Users**.</span></span>
  
<span data-ttu-id="11ff8-141">Las directivas de usuario invalidan las directivas globales y las directivas de sitio, aunque solo se pueden asignar a usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="11ff8-141">The user policy overrides the global policy and site policies, but only for the specific users who are assigned the user policy.</span></span>
  
1. <span data-ttu-id="11ff8-142">Desde una cuenta de usuario que se asigne al rol CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="11ff8-142">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="11ff8-143">En el **menú Inicio,** seleccione el Panel de control de Skype Empresarial Server o abra una ventana del explorador y, a continuación, escriba la dirección URL de administración.</span><span class="sxs-lookup"><span data-stu-id="11ff8-143">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="11ff8-144">En la barra de navegación izquierda, haga clic en **Chat persistente** y, a continuación, en **Directiva de chat persistente**.</span><span class="sxs-lookup"><span data-stu-id="11ff8-144">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="11ff8-145">Haga clic en **Nuevo** y en **Directiva de usuario**.</span><span class="sxs-lookup"><span data-stu-id="11ff8-145">Click **New**, and then click **User policy**.</span></span>
    
5. <span data-ttu-id="11ff8-146">En **Nueva directiva de chat persistente**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="11ff8-146">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="11ff8-147">En **Nombre**, especifique un nombre para la nueva directiva de usuario.</span><span class="sxs-lookup"><span data-stu-id="11ff8-147">In **Name**, specify a name for the new user policy.</span></span>
    
   - <span data-ttu-id="11ff8-148">En **Descripción,** proporcione detalles sobre la directiva de usuario (por ejemplo, directiva de chat persistente para un usuario específico).</span><span class="sxs-lookup"><span data-stu-id="11ff8-148">In **Description**, provide details about what the user policy is (for example, Persistent Chat policy for specific user).</span></span>
    
   - <span data-ttu-id="11ff8-149">Para controlar el chat persistente para todos los usuarios que no están controlados específicamente a través de una directiva de usuario, active o desactive la casilla Habilitar **chat** persistente.</span><span class="sxs-lookup"><span data-stu-id="11ff8-149">To control Persistent Chat for all users who are not specifically controlled through a user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="11ff8-150">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="11ff8-150">Click **Commit**.</span></span>
    
## <a name="to-apply-a-persistent-chat-user-policy-to-a-user-account"></a><span data-ttu-id="11ff8-151">Para aplicar una directiva de usuario de chat persistente a una cuenta de usuario</span><span class="sxs-lookup"><span data-stu-id="11ff8-151">To apply a Persistent Chat user policy to a user account</span></span>

<span data-ttu-id="11ff8-152">Si un usuario se ha habilitado para Skype Empresarial Server, puede aplicar directivas adecuadas a usuarios específicos para habilitarlos o deshabilitarlos para el servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="11ff8-152">If a user has been enabled for Skype for Business Server, you can apply appropriate policies to specific users to enable or disable them for Persistent Chat Server.</span></span>
  
<span data-ttu-id="11ff8-153">Use el procedimiento descrito en este tema para aplicar una directiva de usuario de chat persistente creada anteriormente a una o más cuentas de usuario o grupos de usuarios.</span><span class="sxs-lookup"><span data-stu-id="11ff8-153">Use the procedure in this topic to apply a previously created Persistent Chat user policy to one or more user accounts or user groups.</span></span>
  
1. <span data-ttu-id="11ff8-154">Desde una cuenta de usuario que se asigne al rol CsPersistentChatAdministrator, CsAdministrator o CsUserAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="11ff8-154">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="11ff8-155">En el **menú Inicio,** seleccione el Panel de control de Skype Empresarial Server o abra una ventana del explorador y, a continuación, escriba la dirección URL de administración.</span><span class="sxs-lookup"><span data-stu-id="11ff8-155">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="11ff8-156">En la barra de navegación izquierda, haga clic en  **Usuarios** y, a continuación, busque en la cuenta de usuario que desea configurar.</span><span class="sxs-lookup"><span data-stu-id="11ff8-156">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>
    
4. <span data-ttu-id="11ff8-157">En la tabla donde se enumeran los resultados de la búsqueda, haga clic en la cuenta de usuario, en  **Editar** y, a continuación, en  **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="11ff8-157">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="11ff8-158">En **Editar usuario de Lync Server en** la directiva de chat **persistente,** seleccione la directiva de usuario de chat persistente que desee aplicar.</span><span class="sxs-lookup"><span data-stu-id="11ff8-158">In **Edit Lync Server User** under **Persistent Chat policy**, select the Persistent Chat user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="11ff8-159">La **\<Automatic\>** configuración aplica la directiva efectiva predeterminada.</span><span class="sxs-lookup"><span data-stu-id="11ff8-159">The **\<Automatic\>** settings apply the default effective policy.</span></span> <span data-ttu-id="11ff8-160">Esta configuración se aplica automáticamente por el servidor.</span><span class="sxs-lookup"><span data-stu-id="11ff8-160">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="11ff8-161">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="11ff8-161">Click **Commit**.</span></span>
    

