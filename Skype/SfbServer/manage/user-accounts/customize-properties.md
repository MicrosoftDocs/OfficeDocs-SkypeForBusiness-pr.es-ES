---
title: Personalizar propiedades de la cuenta de usuario de Skype para Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/8/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 505d9619-adab-4cc4-b054-89286e18a19b
description: Puede utilizar los procedimientos de esta sección para modificar las propiedades de la cuenta de usuario individual.
ms.openlocfilehash: fc15dac499fe5d812d5d084a919db10096e6dc56
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="customize-user-account-properties-for-skype-for-business-server-2015"></a><span data-ttu-id="3b260-103">Personalizar propiedades de la cuenta de usuario de Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="3b260-103">Customize user account properties for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="3b260-104">Puede utilizar los procedimientos de esta sección para modificar las propiedades de la cuenta de usuario individual.</span><span class="sxs-lookup"><span data-stu-id="3b260-104">You can use the procedures in this section to modify individual user account properties.</span></span>
  
<span data-ttu-id="3b260-105">Hay dos operaciones básicas que pueden realizarse en el nivel de usuario individual:</span><span class="sxs-lookup"><span data-stu-id="3b260-105">There are two basic operations that can be done at the individual user level:</span></span>
  
- [<span data-ttu-id="3b260-106">Configurar las opciones de telefonía de una cuenta de usuario específica</span><span class="sxs-lookup"><span data-stu-id="3b260-106">Configure telephony options for a specific user account</span></span>](customize-properties.md#Tel_Op)
    
- [<span data-ttu-id="3b260-107">Mover usuarios a otro grupo</span><span class="sxs-lookup"><span data-stu-id="3b260-107">Move users to another pool </span></span>](customize-properties.md#Move_Users)
    
## <a name="configure-telephony-options-for-a-specific-user-account"></a><span data-ttu-id="3b260-108">Configurar las opciones de telefonía de una cuenta de usuario específica</span><span class="sxs-lookup"><span data-stu-id="3b260-108">Configure telephony options for a specific user account</span></span>
<span data-ttu-id="3b260-109"><a name="Tel_Op"> </a></span><span class="sxs-lookup"><span data-stu-id="3b260-109"></span></span>

<span data-ttu-id="3b260-110">Puede personalizar la configuración de telefonía para un usuario específico (siempre que el usuario se ha habilitado para Skype para Business Server 2015 y admite la telefonía de la organización).</span><span class="sxs-lookup"><span data-stu-id="3b260-110">You can customize the telephony settings for a specific user (so long as the individual user has been enabled for Skype for Business Server 2015 and the organization supports telephony).</span></span>
  
<span data-ttu-id="3b260-111">Skype para las opciones de telefonía de usuario Business Server incluyen lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3b260-111">Skype for Business Server user telephony options include the following:</span></span>
  
- <span data-ttu-id="3b260-112">**Deshabilita el audio y vídeo** El usuario no puede realizar llamadas con vídeo y audio.</span><span class="sxs-lookup"><span data-stu-id="3b260-112">**Audio/video disabled** The user cannot make calls with audio and video.</span></span>
    
- <span data-ttu-id="3b260-113">**PC-PC sólo** El usuario puede realizar sólo PC a PC audio o vídeo llamadas.</span><span class="sxs-lookup"><span data-stu-id="3b260-113">**PC-to-PC only** The user can make only PC-to-PC audio or video calls.</span></span>
    
- <span data-ttu-id="3b260-114">**Telefonía IP empresarial** El usuario puede utilizar el Skype para la infraestructura de servidor de negocios 2015 para enrutar todas las llamadas entrantes y salientes.</span><span class="sxs-lookup"><span data-stu-id="3b260-114">**Enterprise Voice** The user can use the Skype for Business Server 2015 infrastructure to route all incoming and outgoing calls.</span></span> <span data-ttu-id="3b260-115">El usuario también puede realizar llamadas de PC a PC.</span><span class="sxs-lookup"><span data-stu-id="3b260-115">The user can also make PC-to-PC calls.</span></span>
    
- <span data-ttu-id="3b260-116">**Control remoto de llamada** El usuario puede utilizar Skype para Business Server 2015 para controlar el teléfono de escritorio y también puede realizar llamadas de PC a PC.</span><span class="sxs-lookup"><span data-stu-id="3b260-116">**Remote call control** The user can use Skype for Business Server 2015 to control the desktop phone, and can also make PC-to-PC calls.</span></span>
    
<span data-ttu-id="3b260-117">Para obtener más información acerca de la configuración de telefonía de una organización, vea [Implementación de Telefonía IP empresarial en Skype para Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) y [Permitir que los usuarios de Telefonía IP empresarial en Skype para Business Server 2015](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="3b260-117">For details about configuring telephony for an organization, see [Enable users for Enterprise Voice in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md) and [Deploy Enterprise Voice in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) in the Deployment documentation.</span></span>
  
1. <span data-ttu-id="3b260-118">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="3b260-118">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="3b260-119">Abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin para abrir el Skype para Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="3b260-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="3b260-120">En la barra de navegación izquierda, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="3b260-120">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="3b260-121">En el cuadro de **búsqueda de usuarios** , escriba todo o la primera parte del nombre para mostrar, nombre, último nombre, nombre de la cuenta de administrador de cuentas de seguridad (SAM), dirección SIP o línea de Uniform Resource Identifier (URI) de la cuenta de usuario que desee y, a continuación, haga clic en **Buscar **.</span><span class="sxs-lookup"><span data-stu-id="3b260-121">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span>
    
5. <span data-ttu-id="3b260-122">En la tabla, haga clic en la cuenta de usuario que desea modificar.</span><span class="sxs-lookup"><span data-stu-id="3b260-122">In the table, click the user account that you want to modify.</span></span>
    
6. <span data-ttu-id="3b260-123">En el menú **Edición** , haga clic en **Modificar**.</span><span class="sxs-lookup"><span data-stu-id="3b260-123">On the **Edit** menu, click **Modify**.</span></span>
    
7. <span data-ttu-id="3b260-124">En **telefonía**, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3b260-124">In **Telephony**, do the following:</span></span>
    
   - <span data-ttu-id="3b260-125">Para deshabilitar las llamadas de audio y vídeo para el usuario, haga clic en **deshabilitado de Audio y vídeo**.</span><span class="sxs-lookup"><span data-stu-id="3b260-125">To disable audio and video calls for the user, click **Audio/video disabled**.</span></span>
    
   - <span data-ttu-id="3b260-126">Para habilitar las comunicaciones de audio de PC a PC del usuario, pero el control de llamadas remotas no o la Telefonía IP empresarial, haga clic en **PC a PC sólo**.</span><span class="sxs-lookup"><span data-stu-id="3b260-126">To enable PC-to-PC audio communications for the user, but not remote call control or Enterprise Voice, click **PC-to-PC only**.</span></span> <span data-ttu-id="3b260-127">Especifique un valor para el **URI de la línea** de teléfono que el usuario que se utiliza para las comunicaciones de audio de PC a PC.</span><span class="sxs-lookup"><span data-stu-id="3b260-127">Specify a value for **Line URI** for the telephone that the user uses for PC-to-PC audio communications.</span></span>
    
   - <span data-ttu-id="3b260-128">Para enrutar las llamadas de teléfono del usuario utilizando el Skype para infraestructura empresarial con arreglo a la clase de directiva de servicios, incluida la comunicación de audio de PC a PC, haga clic en **Telefonía IP empresarial**.</span><span class="sxs-lookup"><span data-stu-id="3b260-128">To route the user's phone calls by using the Skype for Business infrastructure in accordance with the class of service policy, including PC-to-PC audio communication, click **Enterprise Voice**.</span></span> <span data-ttu-id="3b260-129">En **URI de línea**, especifique el número de teléfono para Telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="3b260-129">In **Line URI**, specify the telephone number for Enterprise Voice.</span></span> <span data-ttu-id="3b260-130">En **política de voz**y **políticas del plan de marcado** , especifique las políticas adecuadas para el usuario.</span><span class="sxs-lookup"><span data-stu-id="3b260-130">In **Dial plan policy** and **Voice policy**, specify the appropriate policies for the user.</span></span> <span data-ttu-id="3b260-131">Para especificar las reglas de normalización para convertir números de teléfono marcados por el usuario en el formato E.164, seleccione el perfil de ubicación adecuada en la **política de ubicación**.</span><span class="sxs-lookup"><span data-stu-id="3b260-131">To specify the normalization rules for translating phone numbers dialed by the user to the E.164 format, select the appropriate location profile in **Location policy**.</span></span>
    
   - <span data-ttu-id="3b260-132">Para habilitar la llamada remota de control, que permite a los usuarios controlar su línea de teléfono de escritorio de Skype para Business Server 2015 realizar llamadas de PC a PC y llamadas de PC a teléfono, haga clic en **control de llamada remota**.</span><span class="sxs-lookup"><span data-stu-id="3b260-132">To enable remote call control, which enables users to control their desktop phone line from Skype for Business Server 2015 to make PC-to-PC calls and PC-to-phone calls, click **Remote call control**.</span></span> <span data-ttu-id="3b260-133">En **URI de línea**, especifique el número de teléfono para el control de llamadas remotas.</span><span class="sxs-lookup"><span data-stu-id="3b260-133">In **Line URI**, specify the telephone number for remote call control.</span></span> <span data-ttu-id="3b260-134">El usuario debe tener un teléfono de escritorio y conexión de private branch exchange (PBX) para el enrutamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="3b260-134">The user must have a desktop phone and private branch exchange (PBX) connection for call routing.</span></span>
    
## <a name="move-users-to-another-pool"></a><span data-ttu-id="3b260-135">Mover usuarios a otro grupo</span><span class="sxs-lookup"><span data-stu-id="3b260-135">Move users to another pool</span></span>
<span data-ttu-id="3b260-136"><a name="Move_Users"> </a></span><span class="sxs-lookup"><span data-stu-id="3b260-136"></span></span>

<span data-ttu-id="3b260-137">Puede utilizar Skype para Panel de Control de servidor empresarial para asignar a usuarios a un servidor específico o grupo.</span><span class="sxs-lookup"><span data-stu-id="3b260-137">You can use Skype for Business Server Control Panel to assign users to a specific server or pool.</span></span>
  
> [!TIP]
> <span data-ttu-id="3b260-138">Mover todos los usuarios de un grupo de origen que se está ejecutando Lync Server 2010 o anterior a un Skype para Business Server 2015 grupo de destino en un entorno de Active Directory complejo puede provocar una replicación de Active Directory más lenta.</span><span class="sxs-lookup"><span data-stu-id="3b260-138">Moving all existing users from a source pool that is running Lync Server 2010 or earlier to a Skype for Business Server 2015 destination pool in a complex Active Directory environment might result in slower Active Directory replication.</span></span> <span data-ttu-id="3b260-139">Para evitar esto, puede utilizar filtros de búsqueda para mover usuarios desde grupos que ejecutan Lync Server 2010 o anteriormente por separado, o puede utilizar Skype para negocios de Shell de administración de servidor para mover usuarios con cmdlets.</span><span class="sxs-lookup"><span data-stu-id="3b260-139">To avoid this, you can use search filters to move users from pools that are running Lync Server 2010 or earlier separately, or you can use Skype for Business Server Management Shell to move users with cmdlets.</span></span> <span data-ttu-id="3b260-140">Además, la funcionalidad de filtro funciona con Skype para los usuarios de Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="3b260-140">Also, the filter functionality works with Skype for Business Server 2015 users.</span></span> 
  
### <a name="to-move-selected-users-to-a-different-server-or-pool"></a><span data-ttu-id="3b260-141">Para mover los usuarios seleccionados a otro servidor o grupo de</span><span class="sxs-lookup"><span data-stu-id="3b260-141">To move selected users to a different server or pool</span></span>

1. <span data-ttu-id="3b260-142">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="3b260-142">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="3b260-143">Abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin para abrir el Skype para Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="3b260-143">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="3b260-144">En la barra de navegación izquierda, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="3b260-144">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="3b260-145">En el cuadro de **búsqueda de usuarios** , escriba todo o la primera parte del nombre para mostrar, nombre, último nombre, nombre de la cuenta de administrador de cuentas de seguridad (SAM), dirección SIP o línea de Uniform Resource Identifier (URI) de la cuenta de usuario que desee y, a continuación, haga clic en **Buscar **.</span><span class="sxs-lookup"><span data-stu-id="3b260-145">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span> 
    
5. <span data-ttu-id="3b260-146">En la tabla, seleccione un usuario específico o los usuarios de la lista.</span><span class="sxs-lookup"><span data-stu-id="3b260-146">In the table, select a specific user or users in the list.</span></span> 
    
6. <span data-ttu-id="3b260-147">En el menú **acción** , haga clic en **mover los usuarios seleccionados al grupo**.</span><span class="sxs-lookup"><span data-stu-id="3b260-147">On the **Action** menu, click **Move selected users to pool**.</span></span>
    
7. <span data-ttu-id="3b260-148">**Mover usuarios**, seleccione el grupo que desea mover los usuarios en el **grupo de registro de destino**.</span><span class="sxs-lookup"><span data-stu-id="3b260-148">In **Move Users**, select the pool that you want to move the users to in **Destination registrar pool**.</span></span>
    
8. <span data-ttu-id="3b260-149">(Opcional) Si el servidor de destino o grupo de servidores no está disponible, seleccione la casilla de verificación **Forzar** .</span><span class="sxs-lookup"><span data-stu-id="3b260-149">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="3b260-150">Si selecciona **Forzar**, se mueve la cuenta de usuario, pero se eliminará cualquier dato de usuario asociado (por ejemplo, conferencias a las que el usuario haya programado).</span><span class="sxs-lookup"><span data-stu-id="3b260-150">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled).</span></span> <span data-ttu-id="3b260-151">Si no se selecciona, se mueven la cuenta y los datos asociados.</span><span class="sxs-lookup"><span data-stu-id="3b260-151">If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-all-users-from-one-server-or-pool-to-a-different-server-or-pool"></a><span data-ttu-id="3b260-152">Para mover todos los usuarios de un servidor o grupo de servidores a otro servidor o grupo de</span><span class="sxs-lookup"><span data-stu-id="3b260-152">To move all users from one server or pool to a different server or pool</span></span>

1. <span data-ttu-id="3b260-153">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="3b260-153">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="3b260-154">Abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin para abrir el Skype para Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="3b260-154">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="3b260-155">En la barra de navegación izquierda, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="3b260-155">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="3b260-156">En el menú **acción** , haga clic en **mover todos los usuarios al grupo**.</span><span class="sxs-lookup"><span data-stu-id="3b260-156">On the **Action** menu, click **Move all users to pool**.</span></span>
    
5. <span data-ttu-id="3b260-157">**Mover usuarios**, seleccione el grupo que contiene las cuentas de usuario que desea mover en el **grupo de registro de origen**.</span><span class="sxs-lookup"><span data-stu-id="3b260-157">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>
    
6. <span data-ttu-id="3b260-158">En el **grupo de registro de destino**, seleccione el grupo que desea mover los usuarios.</span><span class="sxs-lookup"><span data-stu-id="3b260-158">In **Destination registrar pool**, select the pool that you want to move the users to.</span></span>
    
7. <span data-ttu-id="3b260-159">(Opcional) Si el servidor de destino o grupo de servidores no está disponible, seleccione la casilla de verificación **Forzar** .</span><span class="sxs-lookup"><span data-stu-id="3b260-159">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="3b260-160">Si selecciona **Forzar**, se mueve la cuenta de usuario, pero se eliminará cualquier dato de usuario asociado (por ejemplo, conferencias a las que el usuario haya programado).</span><span class="sxs-lookup"><span data-stu-id="3b260-160">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled).</span></span> <span data-ttu-id="3b260-161">Si no se selecciona, se mueven la cuenta y los datos asociados.</span><span class="sxs-lookup"><span data-stu-id="3b260-161">If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a><span data-ttu-id="3b260-162">Para mover usuarios de un grupo a una agrupación diferente utilizando un filtro</span><span class="sxs-lookup"><span data-stu-id="3b260-162">To move users from one pool to a different pool by using a filter</span></span>

1. <span data-ttu-id="3b260-163">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="3b260-163">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="3b260-164">Abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin para abrir el Skype para Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="3b260-164">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="3b260-165">En la barra de navegación izquierda, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="3b260-165">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="3b260-166">En **La búsqueda de usuario**, haga clic en **Buscar**y, a continuación, haga clic en **Agregar filtro**.</span><span class="sxs-lookup"><span data-stu-id="3b260-166">In **User Search**, click **Search**, and then click **Add Filter**.</span></span>
    
5. <span data-ttu-id="3b260-167">En los criterios de búsqueda, seleccione **Registrar el fondo**, seleccione **igual a**, seleccione **Actual FQDN del grupo de servidores**y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="3b260-167">In the Search criteria, select **Registrar Pool**, select **Equal to**, select **Current Pool FQDN**, and then click **Find**.</span></span>
    
6. <span data-ttu-id="3b260-168">En el menú **acción** , haga clic en **mover todos los usuarios al grupo**.</span><span class="sxs-lookup"><span data-stu-id="3b260-168">On the **Action** menu, click **Move all users to pool**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="3b260-169">Cuando se aplica un filtro a un conjunto existente de los usuarios, la opción **mover todos los usuarios al grupo** es en el contexto del subconjunto filtrado de usuarios, no **todos los** posibles usuarios.</span><span class="sxs-lookup"><span data-stu-id="3b260-169">When a filter is applied to an existing set of users, the option **Move all users to pool** is in the context of the filtered subset of users, not **all** possible users.</span></span>
  
7. <span data-ttu-id="3b260-170">**Mover usuarios**, seleccione el grupo que contiene las cuentas de usuario que desea mover en el **grupo de registro de origen**.</span><span class="sxs-lookup"><span data-stu-id="3b260-170">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>
    
8. <span data-ttu-id="3b260-171">En el **grupo de registro de destino**, seleccione el grupo donde desea mover los usuarios.</span><span class="sxs-lookup"><span data-stu-id="3b260-171">In **Destination registrar pool**, select the pool where you want to move the users.</span></span>
    
9. <span data-ttu-id="3b260-172">(Opcional) Si el servidor de destino o grupo de servidores no está disponible, seleccione la casilla de verificación **Forzar** .</span><span class="sxs-lookup"><span data-stu-id="3b260-172">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="3b260-173">Si selecciona **Forzar**, se mueve la cuenta de usuario, pero se eliminará cualquier dato de usuario asociado (por ejemplo, conferencias a las que el usuario haya programado y contactos).</span><span class="sxs-lookup"><span data-stu-id="3b260-173">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled and contacts).</span></span> <span data-ttu-id="3b260-174">Si no se selecciona, se mueven la cuenta y los datos asociados.</span><span class="sxs-lookup"><span data-stu-id="3b260-174">If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a><span data-ttu-id="3b260-175">Para mover los usuarios de un grupo a otro mediante cmdlets de Windows Powershell</span><span class="sxs-lookup"><span data-stu-id="3b260-175">To move users from one pool to another using Windows Powershell cmdlets</span></span>

1. <span data-ttu-id="3b260-176">Dependiendo de cómo ejecute comandos de Windows PowerShell (es decir, local o remota), debe iniciar sesión como un miembro de la correcta Skype para funciones administrativas Business Server 2015 como sigue:</span><span class="sxs-lookup"><span data-stu-id="3b260-176">Depending on how you run Windows PowerShell commands (that is, locally or remotely), you need to log on as a member of the correct Skype for Business Server 2015 administrative roles as follows:</span></span>
    
   <span data-ttu-id="3b260-177">a.</span><span class="sxs-lookup"><span data-stu-id="3b260-177">a.</span></span> <span data-ttu-id="3b260-178">Si está ejecutando los comandos en el equipo local (por ejemplo, iniciar la sesión directamente a un servidor Front-End): inicie sesión en el equipo donde está instalado Skype para el Shell de administración de servidor empresarial como miembro del grupo RTCUniversalServerAdmins o con la necesaria derechos de usuario como se describe en **Configuración de permisos de delegado**.</span><span class="sxs-lookup"><span data-stu-id="3b260-178">If you are running the commands on the local machine (for example, you log on directly to a Front End Server): Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
   <span data-ttu-id="3b260-179">b.</span><span class="sxs-lookup"><span data-stu-id="3b260-179">b.</span></span> <span data-ttu-id="3b260-180">Si está ejecutando los comandos de forma remota en otro equipo (por ejemplo, inicie sesión en el equipo y ejecutar los comandos de forma remota en un servidor estándar de edición Front-End): desde una cuenta de usuario que se asigna a la función CsUserAdministrator o la CsAdministrator función, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="3b260-180">If you are running the commands remotely on another computer (for example, you log on to your computer and run the commands remotely on a Standard Edition Front End Server): From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="3b260-181">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="3b260-181">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="3b260-182">Para mover los usuarios individuales, utilice el cmdlet Move-CsUser como sigue:</span><span class="sxs-lookup"><span data-stu-id="3b260-182">To move single users, use the Move-CsUser cmdlet as follows:</span></span>
    
    ```
    Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    ```

    <span data-ttu-id="3b260-183">Donde el usuario mover es el Pilar Ackerman del usuario y el usuario se moverá de su grupo doméstico asignada actualmente a la pool01.contoso.net de grupo</span><span class="sxs-lookup"><span data-stu-id="3b260-183">Where the user to move is the user Pilar Ackerman, and the user will be moved from their currently assigned home pool to the pool pool01.contoso.net</span></span>
    
4. <span data-ttu-id="3b260-184">Para mover un gran número de usuarios, utilice filtros con el cmdlet **Get-CsUser** y pasar el conjunto resultante de los usuarios a **Mover CsUser**:</span><span class="sxs-lookup"><span data-stu-id="3b260-184">To move a large number of users, use filters with the **Get-CsUser** cmdlet and pass the resulting set of users to **Move-CsUser**:</span></span>
    
    ```
    Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    ```

    <span data-ttu-id="3b260-185">Los comandos del **Movimiento Csusuario** y **Get-Csusuario** combinados pueden dar lugar a esto:</span><span class="sxs-lookup"><span data-stu-id="3b260-185">The combined commands of the **Get-CsUser** and **Move-CsUser** might result in this:</span></span>
    
    ```
    Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"
    ```


