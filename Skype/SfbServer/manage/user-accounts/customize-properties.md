---
title: Personalizar propiedades de la cuenta de usuario de Skype para Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 505d9619-adab-4cc4-b054-89286e18a19b
description: Puede usar los procedimientos de esta sección para modificar las propiedades de la cuenta de usuario individual.
ms.openlocfilehash: 5162cb187538b5288f13f25beae96f3775faa594
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214838"
---
# <a name="customize-user-account-properties-for-skype-for-business-server"></a><span data-ttu-id="b9c77-103">Personalizar propiedades de la cuenta de usuario de Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="b9c77-103">Customize user account properties for Skype for Business Server</span></span>
 
<span data-ttu-id="b9c77-104">Puede usar los procedimientos de esta sección para modificar las propiedades de la cuenta de usuario individual.</span><span class="sxs-lookup"><span data-stu-id="b9c77-104">You can use the procedures in this section to modify individual user account properties.</span></span>
  
<span data-ttu-id="b9c77-105">Hay dos operaciones básicas que pueden llevarse a cabo en el nivel de usuario individual:</span><span class="sxs-lookup"><span data-stu-id="b9c77-105">There are two basic operations that can be done at the individual user level:</span></span>
  
- [<span data-ttu-id="b9c77-106">Configurar las opciones de telefonía para una cuenta de usuario específica</span><span class="sxs-lookup"><span data-stu-id="b9c77-106">Configure telephony options for a specific user account</span></span>](customize-properties.md#Tel_Op)
    
- [<span data-ttu-id="b9c77-107">Mover usuarios a otro grupo de servidores</span><span class="sxs-lookup"><span data-stu-id="b9c77-107">Move users to another pool </span></span>](customize-properties.md#Move_Users)
    
## <a name="configure-telephony-options-for-a-specific-user-account"></a><span data-ttu-id="b9c77-108">Configurar las opciones de telefonía para una cuenta de usuario específica</span><span class="sxs-lookup"><span data-stu-id="b9c77-108">Configure telephony options for a specific user account</span></span>
<span data-ttu-id="b9c77-109"><a name="Tel_Op"> </a></span><span class="sxs-lookup"><span data-stu-id="b9c77-109"></span></span>

<span data-ttu-id="b9c77-110">Puede personalizar la configuración de telefonía para un usuario específico (siempre que se ha habilitado para el usuario individual de Skype para Business Server y la organización admite la telefonía).</span><span class="sxs-lookup"><span data-stu-id="b9c77-110">You can customize the telephony settings for a specific user (so long as the individual user has been enabled for Skype for Business Server and the organization supports telephony).</span></span>
  
<span data-ttu-id="b9c77-111">Skype para las opciones de telefonía de usuario de Business Server incluyen lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b9c77-111">Skype for Business Server user telephony options include the following:</span></span>
  
- <span data-ttu-id="b9c77-112">**Deshabilita el audio y vídeo** El usuario no puede realizar llamadas con audio y vídeo.</span><span class="sxs-lookup"><span data-stu-id="b9c77-112">**Audio/video disabled** The user cannot make calls with audio and video.</span></span>
    
- <span data-ttu-id="b9c77-113">**De PC a PC sólo** El usuario puede realizar solo de PC a PC audio o vídeos las llamadas.</span><span class="sxs-lookup"><span data-stu-id="b9c77-113">**PC-to-PC only** The user can make only PC-to-PC audio or video calls.</span></span>
    
- <span data-ttu-id="b9c77-114">**Enterprise Voice** El usuario puede utilizar el Skype para infraestructura de Business Server para enrutar todas las llamadas entrantes y salientes.</span><span class="sxs-lookup"><span data-stu-id="b9c77-114">**Enterprise Voice** The user can use the Skype for Business Server infrastructure to route all incoming and outgoing calls.</span></span> <span data-ttu-id="b9c77-115">El usuario también puede realizar llamadas de PC a PC.</span><span class="sxs-lookup"><span data-stu-id="b9c77-115">The user can also make PC-to-PC calls.</span></span>
    
- <span data-ttu-id="b9c77-116">**Control remoto de llamadas** El usuario puede usar Skype para Business Server para controlar el teléfono de escritorio y también puede realizar llamadas de PC a PC.</span><span class="sxs-lookup"><span data-stu-id="b9c77-116">**Remote call control** The user can use Skype for Business Server to control the desktop phone, and can also make PC-to-PC calls.</span></span>
    
<span data-ttu-id="b9c77-117">Para obtener información detallada sobre la configuración de telefonía para una organización, vea [Implementar Enterprise Voice en Skype para Business Server](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) y [permiten a los usuarios para Enterprise Voice en Skype para Business Server](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="b9c77-117">For details about configuring telephony for an organization, see [Enable users for Enterprise Voice in Skype for Business Server](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md) and [Deploy Enterprise Voice in Skype for Business Server](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) in the Deployment documentation.</span></span>
  
1. <span data-ttu-id="b9c77-118">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="b9c77-118">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="b9c77-119">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="b9c77-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="b9c77-120">En la barra de navegación izquierda, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="b9c77-120">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="b9c77-121">En el cuadro de **búsqueda de usuarios** , escriba todo o la primera parte del nombre para mostrar, nombre, último nombre, nombre de la cuenta de administrador de cuentas de seguridad (SAM), dirección SIP o línea de identificador uniforme de recursos (URI) de la cuenta de usuario que desee y, a continuación, haga clic en Buscar \*\* \*\*.</span><span class="sxs-lookup"><span data-stu-id="b9c77-121">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span>
    
5. <span data-ttu-id="b9c77-122">En la tabla, haga clic en la cuenta de usuario que desea modificar.</span><span class="sxs-lookup"><span data-stu-id="b9c77-122">In the table, click the user account that you want to modify.</span></span>
    
6. <span data-ttu-id="b9c77-123">En el menú **Edición** , haga clic en **Modificar**.</span><span class="sxs-lookup"><span data-stu-id="b9c77-123">On the **Edit** menu, click **Modify**.</span></span>
    
7. <span data-ttu-id="b9c77-124">En **telefonía**, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b9c77-124">In **Telephony**, do the following:</span></span>
    
   - <span data-ttu-id="b9c77-125">Para deshabilitar las llamadas de audioconferencias y vídeo para el usuario, haga clic en **Audio y vídeo deshabilitados**.</span><span class="sxs-lookup"><span data-stu-id="b9c77-125">To disable audio and video calls for the user, click **Audio/video disabled**.</span></span>
    
   - <span data-ttu-id="b9c77-126">Para habilitar las comunicaciones de audio de PC a PC para el usuario, pero el control no remoto de llamadas o la telefonía IP empresarial, haga clic en **PC a PC sólo**.</span><span class="sxs-lookup"><span data-stu-id="b9c77-126">To enable PC-to-PC audio communications for the user, but not remote call control or Enterprise Voice, click **PC-to-PC only**.</span></span> <span data-ttu-id="b9c77-127">Especifique un valor para el **URI de línea** para el teléfono que el usuario se utiliza para las comunicaciones de audio de PC a PC.</span><span class="sxs-lookup"><span data-stu-id="b9c77-127">Specify a value for **Line URI** for the telephone that the user uses for PC-to-PC audio communications.</span></span>
    
   - <span data-ttu-id="b9c77-128">Para enrutar las llamadas de teléfono del usuario mediante el uso de la Skype para infraestructura empresarial con arreglo a la clase de directiva de servicios, incluida la comunicación de audio de PC a PC, haga clic en **Enterprise Voice**.</span><span class="sxs-lookup"><span data-stu-id="b9c77-128">To route the user's phone calls by using the Skype for Business infrastructure in accordance with the class of service policy, including PC-to-PC audio communication, click **Enterprise Voice**.</span></span> <span data-ttu-id="b9c77-129">En **URI de línea**, especifique el número de teléfono para Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="b9c77-129">In **Line URI**, specify the telephone number for Enterprise Voice.</span></span> <span data-ttu-id="b9c77-130">En **Directiva de plan de marcado** y la **Directiva de voz**, especifique las directivas apropiadas para el usuario.</span><span class="sxs-lookup"><span data-stu-id="b9c77-130">In **Dial plan policy** and **Voice policy**, specify the appropriate policies for the user.</span></span> <span data-ttu-id="b9c77-131">Para especificar las reglas de normalización de la traducción de los números de teléfono marcados por el usuario para el formato E.164, seleccione el perfil de ubicación apropiada en la **Directiva de ubicación**.</span><span class="sxs-lookup"><span data-stu-id="b9c77-131">To specify the normalization rules for translating phone numbers dialed by the user to the E.164 format, select the appropriate location profile in **Location policy**.</span></span>
    
   - <span data-ttu-id="b9c77-132">Para habilitar la llamada remota control, que permite a los usuarios controlar su línea de teléfono de escritorio de Skype para Business Server realizar llamadas de PC a PC y llamadas de PC a teléfono, haga clic en **el control remoto de llamadas**.</span><span class="sxs-lookup"><span data-stu-id="b9c77-132">To enable remote call control, which enables users to control their desktop phone line from Skype for Business Server to make PC-to-PC calls and PC-to-phone calls, click **Remote call control**.</span></span> <span data-ttu-id="b9c77-133">En **URI de línea**, especifique el número de teléfono para el control remoto de llamadas.</span><span class="sxs-lookup"><span data-stu-id="b9c77-133">In **Line URI**, specify the telephone number for remote call control.</span></span> <span data-ttu-id="b9c77-134">El usuario debe tener un teléfono de escritorio y conexión de central de conmutación (PBX) de exchange para el enrutamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="b9c77-134">The user must have a desktop phone and private branch exchange (PBX) connection for call routing.</span></span>
    
## <a name="move-users-to-another-pool"></a><span data-ttu-id="b9c77-135">Mover usuarios a otro grupo de servidores</span><span class="sxs-lookup"><span data-stu-id="b9c77-135">Move users to another pool</span></span>
<span data-ttu-id="b9c77-136"><a name="Move_Users"> </a></span><span class="sxs-lookup"><span data-stu-id="b9c77-136"></span></span>

<span data-ttu-id="b9c77-137">Puede usar Skype para el Panel de Control de servidor empresarial para asignar a usuarios a un servidor específico o grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="b9c77-137">You can use Skype for Business Server Control Panel to assign users to a specific server or pool.</span></span>
  
> [!TIP]
> <span data-ttu-id="b9c77-138">Mover todos los usuarios existentes de un grupo de servidores de origen que ejecuta Lync Server 2010 o anterior a un Skype para el grupo de servidores de destino de Business Server en un entorno complejo de Active Directory puede dar lugar a que la replicación de Active Directory más lenta.</span><span class="sxs-lookup"><span data-stu-id="b9c77-138">Moving all existing users from a source pool that is running Lync Server 2010 or earlier to a Skype for Business Server destination pool in a complex Active Directory environment might result in slower Active Directory replication.</span></span> <span data-ttu-id="b9c77-139">Para evitar este problema, puede usar filtros de búsqueda para mover usuarios de los grupos de servidores que ejecutan Lync Server 2010 o anteriormente por separado, o puede usar Skype para Shell de administración de servidor empresarial para mover usuarios con los cmdlets.</span><span class="sxs-lookup"><span data-stu-id="b9c77-139">To avoid this, you can use search filters to move users from pools that are running Lync Server 2010 or earlier separately, or you can use Skype for Business Server Management Shell to move users with cmdlets.</span></span> <span data-ttu-id="b9c77-140">Además, la funcionalidad de filtro funciona con Skype para los usuarios de Business Server.</span><span class="sxs-lookup"><span data-stu-id="b9c77-140">Also, the filter functionality works with Skype for Business Server users.</span></span> 
  
### <a name="to-move-selected-users-to-a-different-server-or-pool"></a><span data-ttu-id="b9c77-141">Para mover los usuarios seleccionados a otro servidor o grupo de servidores</span><span class="sxs-lookup"><span data-stu-id="b9c77-141">To move selected users to a different server or pool</span></span>

1. <span data-ttu-id="b9c77-142">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="b9c77-142">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="b9c77-143">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="b9c77-143">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="b9c77-144">En la barra de navegación izquierda, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="b9c77-144">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="b9c77-145">En el cuadro de **búsqueda de usuarios** , escriba todo o la primera parte del nombre para mostrar, nombre, último nombre, nombre de la cuenta de administrador de cuentas de seguridad (SAM), dirección SIP o línea de identificador uniforme de recursos (URI) de la cuenta de usuario que desee y, a continuación, haga clic en Buscar \*\* \*\*.</span><span class="sxs-lookup"><span data-stu-id="b9c77-145">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span> 
    
5. <span data-ttu-id="b9c77-146">En la tabla, seleccione un usuario o usuarios específicos en la lista.</span><span class="sxs-lookup"><span data-stu-id="b9c77-146">In the table, select a specific user or users in the list.</span></span> 
    
6. <span data-ttu-id="b9c77-147">En el menú **acción** , haga clic en **mover usuarios seleccionados al grupo de servidores**.</span><span class="sxs-lookup"><span data-stu-id="b9c77-147">On the **Action** menu, click **Move selected users to pool**.</span></span>
    
7. <span data-ttu-id="b9c77-148">En **Mover usuarios**, seleccione el grupo que desea trasladar los usuarios en el **grupo de registrador de destino**.</span><span class="sxs-lookup"><span data-stu-id="b9c77-148">In **Move Users**, select the pool that you want to move the users to in **Destination registrar pool**.</span></span>
    
8. <span data-ttu-id="b9c77-149">(Opcional) Si el servidor de destino o grupo de servidores no está disponible, active la casilla de verificación **Force** .</span><span class="sxs-lookup"><span data-stu-id="b9c77-149">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="b9c77-150">Si selecciona **Force**, se mueve la cuenta de usuario, pero se eliminarán los datos de usuario asociado (por ejemplo, las conferencias que ha programado el usuario).</span><span class="sxs-lookup"><span data-stu-id="b9c77-150">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled).</span></span> <span data-ttu-id="b9c77-151">Si no se selecciona, la cuenta y los datos asociados se mueven.</span><span class="sxs-lookup"><span data-stu-id="b9c77-151">If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-all-users-from-one-server-or-pool-to-a-different-server-or-pool"></a><span data-ttu-id="b9c77-152">Para mover todos los usuarios de un servidor o grupo de servidores a otro servidor o grupo de servidores</span><span class="sxs-lookup"><span data-stu-id="b9c77-152">To move all users from one server or pool to a different server or pool</span></span>

1. <span data-ttu-id="b9c77-153">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="b9c77-153">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="b9c77-154">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="b9c77-154">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="b9c77-155">En la barra de navegación izquierda, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="b9c77-155">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="b9c77-156">En el menú **acción** , haga clic en **mover todos los usuarios al grupo de servidores**.</span><span class="sxs-lookup"><span data-stu-id="b9c77-156">On the **Action** menu, click **Move all users to pool**.</span></span>
    
5. <span data-ttu-id="b9c77-157">En **Mover usuarios**, seleccione el grupo que contiene las cuentas de usuario que desea mover en **grupo de registradores de origen**.</span><span class="sxs-lookup"><span data-stu-id="b9c77-157">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>
    
6. <span data-ttu-id="b9c77-158">En el **grupo de registrador de destino**, seleccione el grupo que desea trasladar los usuarios.</span><span class="sxs-lookup"><span data-stu-id="b9c77-158">In **Destination registrar pool**, select the pool that you want to move the users to.</span></span>
    
7. <span data-ttu-id="b9c77-159">(Opcional) Si el servidor de destino o grupo de servidores no está disponible, active la casilla de verificación **Force** .</span><span class="sxs-lookup"><span data-stu-id="b9c77-159">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="b9c77-160">Si selecciona **Force**, se mueve la cuenta de usuario, pero se eliminarán los datos de usuario asociado (por ejemplo, las conferencias que ha programado el usuario).</span><span class="sxs-lookup"><span data-stu-id="b9c77-160">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled).</span></span> <span data-ttu-id="b9c77-161">Si no se selecciona, la cuenta y los datos asociados se mueven.</span><span class="sxs-lookup"><span data-stu-id="b9c77-161">If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a><span data-ttu-id="b9c77-162">Para mover usuarios de un grupo de servidores a otro grupo diferente mediante un filtro</span><span class="sxs-lookup"><span data-stu-id="b9c77-162">To move users from one pool to a different pool by using a filter</span></span>

1. <span data-ttu-id="b9c77-163">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="b9c77-163">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="b9c77-164">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="b9c77-164">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="b9c77-165">En la barra de navegación izquierda, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="b9c77-165">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="b9c77-166">En la **Búsqueda de usuarios**, haga clic en **Buscar**y, a continuación, haga clic en **Agregar filtro**.</span><span class="sxs-lookup"><span data-stu-id="b9c77-166">In **User Search**, click **Search**, and then click **Add Filter**.</span></span>
    
5. <span data-ttu-id="b9c77-167">En los criterios de búsqueda, seleccione **Grupo de registrador**, seleccione es **igual a**, seleccione el **FQDN del grupo actual**y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="b9c77-167">In the Search criteria, select **Registrar Pool**, select **Equal to**, select **Current Pool FQDN**, and then click **Find**.</span></span>
    
6. <span data-ttu-id="b9c77-168">En el menú **acción** , haga clic en **mover todos los usuarios al grupo de servidores**.</span><span class="sxs-lookup"><span data-stu-id="b9c77-168">On the **Action** menu, click **Move all users to pool**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b9c77-169">Cuando se aplica un filtro a un conjunto existente de usuarios, la opción **mover todos los usuarios al grupo de servidores** está en el contexto del filtrado subconjunto de usuarios, no **todos los** usuarios posibles.</span><span class="sxs-lookup"><span data-stu-id="b9c77-169">When a filter is applied to an existing set of users, the option **Move all users to pool** is in the context of the filtered subset of users, not **all** possible users.</span></span>
  
7. <span data-ttu-id="b9c77-170">En **Mover usuarios**, seleccione el grupo que contiene las cuentas de usuario que desea mover en **grupo de registradores de origen**.</span><span class="sxs-lookup"><span data-stu-id="b9c77-170">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>
    
8. <span data-ttu-id="b9c77-171">En **grupo de registrador de destino**, seleccione el grupo de servidores donde desea mover los usuarios.</span><span class="sxs-lookup"><span data-stu-id="b9c77-171">In **Destination registrar pool**, select the pool where you want to move the users.</span></span>
    
9. <span data-ttu-id="b9c77-172">(Opcional) Si el servidor de destino o grupo de servidores no está disponible, active la casilla de verificación **Force** .</span><span class="sxs-lookup"><span data-stu-id="b9c77-172">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="b9c77-173">Si selecciona **Force**, se mueve la cuenta de usuario, pero se eliminarán los datos de usuario asociado (por ejemplo, las conferencias que ha programado el usuario y contactos).</span><span class="sxs-lookup"><span data-stu-id="b9c77-173">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled and contacts).</span></span> <span data-ttu-id="b9c77-174">Si no se selecciona, la cuenta y los datos asociados se mueven.</span><span class="sxs-lookup"><span data-stu-id="b9c77-174">If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a><span data-ttu-id="b9c77-175">Para mover usuarios de un grupo de servidores a otro mediante cmdlets de Windows Powershell</span><span class="sxs-lookup"><span data-stu-id="b9c77-175">To move users from one pool to another using Windows Powershell cmdlets</span></span>

1. <span data-ttu-id="b9c77-176">En función de cómo ejecutar comandos de Windows PowerShell (es decir, local o remotamente), deberá iniciar sesión como un miembro de la correcta Skype para funciones administrativas Business Server como sigue:</span><span class="sxs-lookup"><span data-stu-id="b9c77-176">Depending on how you run Windows PowerShell commands (that is, locally or remotely), you need to log on as a member of the correct Skype for Business Server administrative roles as follows:</span></span>
    
   <span data-ttu-id="b9c77-177">a.</span><span class="sxs-lookup"><span data-stu-id="b9c77-177">a.</span></span> <span data-ttu-id="b9c77-178">Si está ejecutando los comandos en la máquina local (por ejemplo, inicia sesión directamente en un servidor Front-End): inicie sesión en el equipo donde está instalado Skype para Shell de administración de servidor empresarial como un miembro del grupo RTCUniversalServerAdmins o con la necesaria derechos de usuario como se describe en **Delegar permisos de instalación**.</span><span class="sxs-lookup"><span data-stu-id="b9c77-178">If you are running the commands on the local machine (for example, you log on directly to a Front End Server): Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
   <span data-ttu-id="b9c77-179">b.</span><span class="sxs-lookup"><span data-stu-id="b9c77-179">b.</span></span> <span data-ttu-id="b9c77-180">Si está ejecutando los comandos de forma remota en otro equipo (por ejemplo, inicie sesión en su equipo y ejecuta los comandos de forma remota en una edición estándar servidor Front-End): desde una cuenta de usuario que se asigna al rol CsUserAdministrator o la CsAdministrator función, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="b9c77-180">If you are running the commands remotely on another computer (for example, you log on to your computer and run the commands remotely on a Standard Edition Front End Server): From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="b9c77-181">Iniciar el Skype para Shell de administración de negocio Server: haga clic en **Inicio**, haga clic en **Todos los programas**, haga clic en **Skype para la empresa**y, a continuación, haga clic en **Skype para Shell de administración de servidor empresarial**.</span><span class="sxs-lookup"><span data-stu-id="b9c77-181">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="b9c77-182">Para mover usuarios individuales, use el cmdlet Move-CsUser de la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="b9c77-182">To move single users, use the Move-CsUser cmdlet as follows:</span></span>
    
    ```
    Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    ```

    <span data-ttu-id="b9c77-183">Donde el usuario que se moverá es el usuario Pilar Ackerman y el usuario se moverá de su grupo de servidores principal actualmente asignado al grupo pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="b9c77-183">Where the user to move is the user Pilar Ackerman, and the user will be moved from their currently assigned home pool to the pool pool01.contoso.net</span></span>
    
4. <span data-ttu-id="b9c77-184">Para mover un gran número de usuarios, utilice filtros con el cmdlet **Get-CsUser** y pase el conjunto resultante de los usuarios a **Move-CsUser**:</span><span class="sxs-lookup"><span data-stu-id="b9c77-184">To move a large number of users, use filters with the **Get-CsUser** cmdlet and pass the resulting set of users to **Move-CsUser**:</span></span>
    
    ```
    Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    ```

    <span data-ttu-id="b9c77-185">Los comandos combinados de **Get-CsUser** y **Move-CsUser** es posible que el resultado siguiente:</span><span class="sxs-lookup"><span data-stu-id="b9c77-185">The combined commands of the **Get-CsUser** and **Move-CsUser** might result in this:</span></span>
    
    ```
    Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"
    ```


