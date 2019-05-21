---
title: Personalizar las propiedades de la cuenta de usuario para Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 505d9619-adab-4cc4-b054-89286e18a19b
description: Puede usar los procedimientos de esta sección para modificar las propiedades de una cuenta de usuario individual.
ms.openlocfilehash: d0e1a3ac02f5696e91e07c0f08cf0cf10e09f98e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275076"
---
# <a name="customize-user-account-properties-for-skype-for-business-server"></a><span data-ttu-id="f9958-103">Personalizar las propiedades de la cuenta de usuario para Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="f9958-103">Customize user account properties for Skype for Business Server</span></span>
 
<span data-ttu-id="f9958-104">Puede usar los procedimientos de esta sección para modificar las propiedades de una cuenta de usuario individual.</span><span class="sxs-lookup"><span data-stu-id="f9958-104">You can use the procedures in this section to modify individual user account properties.</span></span>
  
<span data-ttu-id="f9958-105">Existen dos operaciones básicas que se pueden realizar en el nivel de usuario individual:</span><span class="sxs-lookup"><span data-stu-id="f9958-105">There are two basic operations that can be done at the individual user level:</span></span>
  
- [<span data-ttu-id="f9958-106">Configurar opciones de telefonía para una cuenta de usuario específica</span><span class="sxs-lookup"><span data-stu-id="f9958-106">Configure telephony options for a specific user account</span></span>](customize-properties.md#Tel_Op)
    
- [<span data-ttu-id="f9958-107">Mover usuarios a otro grupo</span><span class="sxs-lookup"><span data-stu-id="f9958-107">Move users to another pool </span></span>](customize-properties.md#Move_Users)
    
## <a name="configure-telephony-options-for-a-specific-user-account"></a><span data-ttu-id="f9958-108">Configurar opciones de telefonía para una cuenta de usuario específica</span><span class="sxs-lookup"><span data-stu-id="f9958-108">Configure telephony options for a specific user account</span></span>
<span data-ttu-id="f9958-109"><a name="Tel_Op"> </a></span><span class="sxs-lookup"><span data-stu-id="f9958-109"></span></span>

<span data-ttu-id="f9958-110">Puede personalizar la configuración de telefonía de un usuario específico (siempre y cuando el usuario individual se haya habilitado en Skype empresarial Server y la organización admita telefonía).</span><span class="sxs-lookup"><span data-stu-id="f9958-110">You can customize the telephony settings for a specific user (so long as the individual user has been enabled for Skype for Business Server and the organization supports telephony).</span></span>
  
<span data-ttu-id="f9958-111">Entre las opciones de telefonía de usuario de Skype empresarial Server se incluyen las siguientes:</span><span class="sxs-lookup"><span data-stu-id="f9958-111">Skype for Business Server user telephony options include the following:</span></span>
  
- <span data-ttu-id="f9958-112">**Audio/vídeo** deshabilitado El usuario no puede hacer llamadas con audio y vídeo.</span><span class="sxs-lookup"><span data-stu-id="f9958-112">**Audio/video disabled** The user cannot make calls with audio and video.</span></span>
    
- <span data-ttu-id="f9958-113">**Solo de PC a PC** El usuario solo puede hacer videollamadas o videollamadas de PC a PC.</span><span class="sxs-lookup"><span data-stu-id="f9958-113">**PC-to-PC only** The user can make only PC-to-PC audio or video calls.</span></span>
    
- <span data-ttu-id="f9958-114">**Telefonía IP empresarial** El usuario puede usar la infraestructura de Skype empresarial Server para enrutar todas las llamadas entrantes y salientes.</span><span class="sxs-lookup"><span data-stu-id="f9958-114">**Enterprise Voice** The user can use the Skype for Business Server infrastructure to route all incoming and outgoing calls.</span></span> <span data-ttu-id="f9958-115">El usuario también puede hacer llamadas de PC a PC.</span><span class="sxs-lookup"><span data-stu-id="f9958-115">The user can also make PC-to-PC calls.</span></span>
    
- <span data-ttu-id="f9958-116">**Control remoto de llamadas** El usuario puede usar Skype empresarial Server para controlar el teléfono de escritorio y también puede hacer llamadas entre equipos.</span><span class="sxs-lookup"><span data-stu-id="f9958-116">**Remote call control** The user can use Skype for Business Server to control the desktop phone, and can also make PC-to-PC calls.</span></span>
    
<span data-ttu-id="f9958-117">Para obtener detalles sobre la configuración de telefonía para una organización, vea [Habilitar usuarios de telefonía IP empresarial en Skype empresarial Server](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md) e implementar la telefonía [IP empresarial en Skype empresarial Server](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="f9958-117">For details about configuring telephony for an organization, see [Enable users for Enterprise Voice in Skype for Business Server](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md) and [Deploy Enterprise Voice in Skype for Business Server](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) in the Deployment documentation.</span></span>
  
1. <span data-ttu-id="f9958-118">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="f9958-118">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="f9958-119">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="f9958-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="f9958-120">En la barra de navegación izquierda, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="f9958-120">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="f9958-121">En el cuadro **Buscar usuarios** , escriba todas o la primera parte del nombre para mostrar, el nombre, el apellido, el nombre de cuenta del administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de la cuenta de usuario que desee y, a continuación, haga clic en \*\*Buscar. \*\*.</span><span class="sxs-lookup"><span data-stu-id="f9958-121">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span>
    
5. <span data-ttu-id="f9958-122">En la tabla, haga clic en la cuenta de usuario que desea modificar.</span><span class="sxs-lookup"><span data-stu-id="f9958-122">In the table, click the user account that you want to modify.</span></span>
    
6. <span data-ttu-id="f9958-123">En el menú **Editar** , haga clic en **modificar**.</span><span class="sxs-lookup"><span data-stu-id="f9958-123">On the **Edit** menu, click **Modify**.</span></span>
    
7. <span data-ttu-id="f9958-124">En **telefonía**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f9958-124">In **Telephony**, do the following:</span></span>
    
   - <span data-ttu-id="f9958-125">Para deshabilitar las llamadas de audio y vídeo para el usuario, haga clic en **audio/vídeo**deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="f9958-125">To disable audio and video calls for the user, click **Audio/video disabled**.</span></span>
    
   - <span data-ttu-id="f9958-126">Para habilitar las comunicaciones de audio de PC a PC para el usuario, pero no para el control remoto de llamadas ni para la telefonía IP empresarial, haga clic en **solo de PC a PC**.</span><span class="sxs-lookup"><span data-stu-id="f9958-126">To enable PC-to-PC audio communications for the user, but not remote call control or Enterprise Voice, click **PC-to-PC only**.</span></span> <span data-ttu-id="f9958-127">Especifique un valor para el **URI de línea** del teléfono que usa el usuario para las comunicaciones de audio de PC a PC.</span><span class="sxs-lookup"><span data-stu-id="f9958-127">Specify a value for **Line URI** for the telephone that the user uses for PC-to-PC audio communications.</span></span>
    
   - <span data-ttu-id="f9958-128">Para enrutar las llamadas telefónicas del usuario mediante la infraestructura de Skype empresarial según la política de clase de servicio, incluidas las comunicaciones de audio de PC a PC, haga clic en **telefonía IP empresarial**.</span><span class="sxs-lookup"><span data-stu-id="f9958-128">To route the user's phone calls by using the Skype for Business infrastructure in accordance with the class of service policy, including PC-to-PC audio communication, click **Enterprise Voice**.</span></span> <span data-ttu-id="f9958-129">En **URI de línea**, especifique el número de teléfono de la telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="f9958-129">In **Line URI**, specify the telephone number for Enterprise Voice.</span></span> <span data-ttu-id="f9958-130">En **Directiva de plan de marcado** y **Directiva de voz**, especifique las directivas apropiadas para el usuario.</span><span class="sxs-lookup"><span data-stu-id="f9958-130">In **Dial plan policy** and **Voice policy**, specify the appropriate policies for the user.</span></span> <span data-ttu-id="f9958-131">Para especificar las reglas de normalización para traducir números de teléfono marcados por el usuario al formato E. 164, seleccione el perfil de ubicación adecuado en la **política de ubicación**.</span><span class="sxs-lookup"><span data-stu-id="f9958-131">To specify the normalization rules for translating phone numbers dialed by the user to the E.164 format, select the appropriate location profile in **Location policy**.</span></span>
    
   - <span data-ttu-id="f9958-132">Para habilitar el control remoto de llamadas, que permite a los usuarios controlar su línea telefónica de escritorio desde Skype empresarial Server para realizar llamadas de PC a PC y llamadas de PC a teléfono, haga clic en **control remoto de llamadas**.</span><span class="sxs-lookup"><span data-stu-id="f9958-132">To enable remote call control, which enables users to control their desktop phone line from Skype for Business Server to make PC-to-PC calls and PC-to-phone calls, click **Remote call control**.</span></span> <span data-ttu-id="f9958-133">En **URI de línea**, especifique el número de teléfono para el control de llamada remota.</span><span class="sxs-lookup"><span data-stu-id="f9958-133">In **Line URI**, specify the telephone number for remote call control.</span></span> <span data-ttu-id="f9958-134">El usuario debe tener una conexión de teléfono de escritorio y de central de conmutación (PBX) para el enrutamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="f9958-134">The user must have a desktop phone and private branch exchange (PBX) connection for call routing.</span></span>
    
## <a name="move-users-to-another-pool"></a><span data-ttu-id="f9958-135">Mover usuarios a otro grupo</span><span class="sxs-lookup"><span data-stu-id="f9958-135">Move users to another pool</span></span>
<span data-ttu-id="f9958-136"><a name="Move_Users"> </a></span><span class="sxs-lookup"><span data-stu-id="f9958-136"></span></span>

<span data-ttu-id="f9958-137">Puede usar el panel de control de Skype empresarial Server para asignar usuarios a un servidor o grupo de servidores específico.</span><span class="sxs-lookup"><span data-stu-id="f9958-137">You can use Skype for Business Server Control Panel to assign users to a specific server or pool.</span></span>
  
> [!TIP]
> <span data-ttu-id="f9958-138">El traslado de todos los usuarios existentes de un grupo de origen que ejecuta Lync Server 2010 o una versión anterior a un grupo de destino de Skype empresarial Server en un entorno complejo de Active Directory puede ralentizar la replicación de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f9958-138">Moving all existing users from a source pool that is running Lync Server 2010 or earlier to a Skype for Business Server destination pool in a complex Active Directory environment might result in slower Active Directory replication.</span></span> <span data-ttu-id="f9958-139">Para evitar esto, puede usar filtros de búsqueda para mover los usuarios de los grupos que ejecutan Lync Server 2010 o una versión anterior por separado, o bien puede usar el shell de administración de Skype empresarial Server para mover usuarios con cmdlets.</span><span class="sxs-lookup"><span data-stu-id="f9958-139">To avoid this, you can use search filters to move users from pools that are running Lync Server 2010 or earlier separately, or you can use Skype for Business Server Management Shell to move users with cmdlets.</span></span> <span data-ttu-id="f9958-140">Además, la funcionalidad de filtro funciona con usuarios de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="f9958-140">Also, the filter functionality works with Skype for Business Server users.</span></span> 
  
### <a name="to-move-selected-users-to-a-different-server-or-pool"></a><span data-ttu-id="f9958-141">Para mover los usuarios seleccionados a otro servidor o grupo de servidores</span><span class="sxs-lookup"><span data-stu-id="f9958-141">To move selected users to a different server or pool</span></span>

1. <span data-ttu-id="f9958-142">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="f9958-142">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="f9958-143">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="f9958-143">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="f9958-144">En la barra de navegación izquierda, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="f9958-144">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="f9958-145">En el cuadro **Buscar usuarios** , escriba todas o la primera parte del nombre para mostrar, el nombre, el apellido, el nombre de cuenta del administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de la cuenta de usuario que desee y, a continuación, haga clic en \*\*Buscar. \*\*.</span><span class="sxs-lookup"><span data-stu-id="f9958-145">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span> 
    
5. <span data-ttu-id="f9958-146">En la tabla, seleccione un usuario o usuarios específicos de la lista.</span><span class="sxs-lookup"><span data-stu-id="f9958-146">In the table, select a specific user or users in the list.</span></span> 
    
6. <span data-ttu-id="f9958-147">En el menú **acción** , haga clic en **mover los usuarios seleccionados al grupo**.</span><span class="sxs-lookup"><span data-stu-id="f9958-147">On the **Action** menu, click **Move selected users to pool**.</span></span>
    
7. <span data-ttu-id="f9958-148">En **mover usuarios**, seleccione el grupo al que desea mover los usuarios en el grupo de registrador de **destinos**.</span><span class="sxs-lookup"><span data-stu-id="f9958-148">In **Move Users**, select the pool that you want to move the users to in **Destination registrar pool**.</span></span>
    
8. <span data-ttu-id="f9958-149">Faculta Si el servidor de destino o el grupo de servidores no \*\*\*\* están disponibles, active la casilla forzar.</span><span class="sxs-lookup"><span data-stu-id="f9958-149">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="f9958-150">Si selecciona **Force**, se mueve la cuenta de usuario, pero se eliminan los datos de los usuarios asociados (por ejemplo, las conferencias que el usuario ha programado).</span><span class="sxs-lookup"><span data-stu-id="f9958-150">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled).</span></span> <span data-ttu-id="f9958-151">Si no la selecciona, tanto la cuenta como los datos asociados se mueven.</span><span class="sxs-lookup"><span data-stu-id="f9958-151">If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-all-users-from-one-server-or-pool-to-a-different-server-or-pool"></a><span data-ttu-id="f9958-152">Para mover todos los usuarios de un servidor o grupo de servidores a otro servidor o grupo de servidores</span><span class="sxs-lookup"><span data-stu-id="f9958-152">To move all users from one server or pool to a different server or pool</span></span>

1. <span data-ttu-id="f9958-153">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="f9958-153">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="f9958-154">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="f9958-154">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="f9958-155">En la barra de navegación izquierda, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="f9958-155">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="f9958-156">En el menú **acción** , haga clic en **mover todos los usuarios al grupo**.</span><span class="sxs-lookup"><span data-stu-id="f9958-156">On the **Action** menu, click **Move all users to pool**.</span></span>
    
5. <span data-ttu-id="f9958-157">En **mover usuarios**, seleccione el grupo que contiene las cuentas de usuario que desea mover en el **Grupo**de registrador de origen.</span><span class="sxs-lookup"><span data-stu-id="f9958-157">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>
    
6. <span data-ttu-id="f9958-158">En **Grupo**de registradores de destino, seleccione el grupo al que desea mover a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="f9958-158">In **Destination registrar pool**, select the pool that you want to move the users to.</span></span>
    
7. <span data-ttu-id="f9958-159">Faculta Si el servidor de destino o el grupo de servidores no \*\*\*\* están disponibles, active la casilla forzar.</span><span class="sxs-lookup"><span data-stu-id="f9958-159">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="f9958-160">Si selecciona **Force**, se mueve la cuenta de usuario, pero se eliminan los datos de los usuarios asociados (por ejemplo, las conferencias que el usuario ha programado).</span><span class="sxs-lookup"><span data-stu-id="f9958-160">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled).</span></span> <span data-ttu-id="f9958-161">Si no la selecciona, tanto la cuenta como los datos asociados se mueven.</span><span class="sxs-lookup"><span data-stu-id="f9958-161">If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a><span data-ttu-id="f9958-162">Para mover los usuarios de un grupo a otro mediante un filtro</span><span class="sxs-lookup"><span data-stu-id="f9958-162">To move users from one pool to a different pool by using a filter</span></span>

1. <span data-ttu-id="f9958-163">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="f9958-163">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="f9958-164">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="f9958-164">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="f9958-165">En la barra de navegación izquierda, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="f9958-165">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="f9958-166">En **búsqueda de usuario**, haga clic en **Buscar**y, a continuación, haga clic en **Agregar filtro**.</span><span class="sxs-lookup"><span data-stu-id="f9958-166">In **User Search**, click **Search**, and then click **Add Filter**.</span></span>
    
5. <span data-ttu-id="f9958-167">En los criterios de búsqueda, seleccione **registrar grupo**, seleccione **igual a**, seleccione **FQDN del grupo actual**y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="f9958-167">In the Search criteria, select **Registrar Pool**, select **Equal to**, select **Current Pool FQDN**, and then click **Find**.</span></span>
    
6. <span data-ttu-id="f9958-168">En el menú **acción** , haga clic en **mover todos los usuarios al grupo**.</span><span class="sxs-lookup"><span data-stu-id="f9958-168">On the **Action** menu, click **Move all users to pool**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f9958-169">Cuando se aplica un filtro a un conjunto de usuarios existente, la opción **mover todos los usuarios al grupo** se encuentra en el contexto del subconjunto filtrado de usuarios, no de **todos** los usuarios posibles.</span><span class="sxs-lookup"><span data-stu-id="f9958-169">When a filter is applied to an existing set of users, the option **Move all users to pool** is in the context of the filtered subset of users, not **all** possible users.</span></span>
  
7. <span data-ttu-id="f9958-170">En **mover usuarios**, seleccione el grupo que contiene las cuentas de usuario que desea mover en el **Grupo**de registrador de origen.</span><span class="sxs-lookup"><span data-stu-id="f9958-170">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>
    
8. <span data-ttu-id="f9958-171">En **Grupo**de registradores de destino, seleccione el grupo al que desea mover los usuarios.</span><span class="sxs-lookup"><span data-stu-id="f9958-171">In **Destination registrar pool**, select the pool where you want to move the users.</span></span>
    
9. <span data-ttu-id="f9958-172">Faculta Si el servidor de destino o el grupo de servidores no \*\*\*\* están disponibles, active la casilla forzar.</span><span class="sxs-lookup"><span data-stu-id="f9958-172">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="f9958-173">Si selecciona **fuerza**, se mueve la cuenta de usuario, pero se eliminan los datos de los usuarios asociados (por ejemplo, las conferencias que el usuario ha programado y a las que los contactos han programado).</span><span class="sxs-lookup"><span data-stu-id="f9958-173">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled and contacts).</span></span> <span data-ttu-id="f9958-174">Si no la selecciona, tanto la cuenta como los datos asociados se mueven.</span><span class="sxs-lookup"><span data-stu-id="f9958-174">If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a><span data-ttu-id="f9958-175">Para mover usuarios de un grupo a otro mediante cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f9958-175">To move users from one pool to another using Windows Powershell cmdlets</span></span>

1. <span data-ttu-id="f9958-176">En función de cómo ejecute los comandos de Windows PowerShell (es decir, de forma local o remota), debe iniciar sesión como miembro de las funciones administrativas del servidor de Skype empresarial correctas de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="f9958-176">Depending on how you run Windows PowerShell commands (that is, locally or remotely), you need to log on as a member of the correct Skype for Business Server administrative roles as follows:</span></span>
    
   <span data-ttu-id="f9958-177">a.</span><span class="sxs-lookup"><span data-stu-id="f9958-177">a.</span></span> <span data-ttu-id="f9958-178">Si está ejecutando los comandos en el equipo local (por ejemplo, inicia sesión directamente en un servidor de solicitudes de cliente): inicie sesión en el equipo en el que está instalado el shell de administración de Skype empresarial Server como miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario, tal y como se describe en **permisos de configuración**de delegados.</span><span class="sxs-lookup"><span data-stu-id="f9958-178">If you are running the commands on the local machine (for example, you log on directly to a Front End Server): Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
   <span data-ttu-id="f9958-179">b.</span><span class="sxs-lookup"><span data-stu-id="f9958-179">b.</span></span> <span data-ttu-id="f9958-180">Si ejecuta los comandos de forma remota en otro equipo (por ejemplo, inicia sesión en el equipo y ejecuta los comandos de forma remota en un servidor front-end Standard Edition): desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator rol, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="f9958-180">If you are running the commands remotely on another computer (for example, you log on to your computer and run the commands remotely on a Standard Edition Front End Server): From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="f9958-181">Inicie el shell de administración de Skype empresarial Server: haga clic en **Inicio**, haga clic en **todos los programas**, en **Skype empresarial**y, a continuación, haga clic en **consola de administración de Skype empresarial**.</span><span class="sxs-lookup"><span data-stu-id="f9958-181">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="f9958-182">Para mover usuarios individuales, use el cmdlet Move-CsUser de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="f9958-182">To move single users, use the Move-CsUser cmdlet as follows:</span></span>
    
    ```
    Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    ```

    <span data-ttu-id="f9958-183">Donde el usuario debe mover es el usuario Pilar Ackerman, y el usuario se moverá de su grupo local asignado a la agrupación pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="f9958-183">Where the user to move is the user Pilar Ackerman, and the user will be moved from their currently assigned home pool to the pool pool01.contoso.net</span></span>
    
4. <span data-ttu-id="f9958-184">Para mover un gran número de usuarios, use filtros con el cmdlet **Get-CsUser** y pase el conjunto de usuarios resultante a **Move-CsUser**:</span><span class="sxs-lookup"><span data-stu-id="f9958-184">To move a large number of users, use filters with the **Get-CsUser** cmdlet and pass the resulting set of users to **Move-CsUser**:</span></span>
    
    ```
    Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    ```

    <span data-ttu-id="f9958-185">Los comandos combinados de **Get-CsUser** y **Move-CsUser** pueden dar lugar a esto:</span><span class="sxs-lookup"><span data-stu-id="f9958-185">The combined commands of the **Get-CsUser** and **Move-CsUser** might result in this:</span></span>
    
    ```
    Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"
    ```


