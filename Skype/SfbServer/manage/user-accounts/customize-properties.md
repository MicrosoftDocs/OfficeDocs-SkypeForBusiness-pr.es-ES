---
title: Personalizar las propiedades de la cuenta de usuario para Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 505d9619-adab-4cc4-b054-89286e18a19b
description: Puede utilizar los procedimientos que se describen en esta sección para modificar las propiedades de cuenta de usuario individuales.
ms.openlocfilehash: 6f2c3a76f9047da0a5d78695518cfb8355ab82e3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826270"
---
# <a name="customize-user-account-properties-for-skype-for-business-server"></a><span data-ttu-id="94695-103">Personalizar las propiedades de la cuenta de usuario para Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="94695-103">Customize user account properties for Skype for Business Server</span></span>
 
<span data-ttu-id="94695-104">Puede utilizar los procedimientos que se describen en esta sección para modificar las propiedades de cuenta de usuario individuales.</span><span class="sxs-lookup"><span data-stu-id="94695-104">You can use the procedures in this section to modify individual user account properties.</span></span>
  
<span data-ttu-id="94695-105">Hay dos operaciones básicas que se pueden realizar en el nivel de usuario individual:</span><span class="sxs-lookup"><span data-stu-id="94695-105">There are two basic operations that can be done at the individual user level:</span></span>
  
- [<span data-ttu-id="94695-106">Configurar opciones de telefonía para una cuenta de usuario específica</span><span class="sxs-lookup"><span data-stu-id="94695-106">Configure telephony options for a specific user account</span></span>](customize-properties.md#Tel_Op)
    
- [<span data-ttu-id="94695-107">Mover usuarios a otro grupo</span><span class="sxs-lookup"><span data-stu-id="94695-107">Move users to another pool</span></span>](customize-properties.md#Move_Users)
    
## <a name="configure-telephony-options-for-a-specific-user-account"></a><span data-ttu-id="94695-108">Configurar opciones de telefonía para una cuenta de usuario específica</span><span class="sxs-lookup"><span data-stu-id="94695-108">Configure telephony options for a specific user account</span></span>
<span data-ttu-id="94695-109"><a name="Tel_Op"> </a></span><span class="sxs-lookup"><span data-stu-id="94695-109"><a name="Tel_Op"> </a></span></span>

<span data-ttu-id="94695-110">Puede personalizar la configuración de telefonía para un usuario específico (siempre que el usuario individual se haya habilitado para Skype Empresarial Server y la organización admita telefonía).</span><span class="sxs-lookup"><span data-stu-id="94695-110">You can customize the telephony settings for a specific user (so long as the individual user has been enabled for Skype for Business Server and the organization supports telephony).</span></span>
  
<span data-ttu-id="94695-111">Entre las opciones de telefonía de usuario de Skype Empresarial Server se incluyen las siguientes:</span><span class="sxs-lookup"><span data-stu-id="94695-111">Skype for Business Server user telephony options include the following:</span></span>
  
- <span data-ttu-id="94695-112">**Audio/vídeo deshabilitado** El usuario no puede realizar llamadas con audio y vídeo.</span><span class="sxs-lookup"><span data-stu-id="94695-112">**Audio/video disabled** The user cannot make calls with audio and video.</span></span>
    
- <span data-ttu-id="94695-113">**Solo de equipo a equipo** El usuario solo puede realizar llamadas de audio o vídeo de un equipo a otro.</span><span class="sxs-lookup"><span data-stu-id="94695-113">**PC-to-PC only** The user can make only PC-to-PC audio or video calls.</span></span>
    
- <span data-ttu-id="94695-114">**Telefonía IP empresarial** El usuario puede usar la infraestructura de Skype Empresarial Server para enrutar todas las llamadas entrantes y salientes.</span><span class="sxs-lookup"><span data-stu-id="94695-114">**Enterprise Voice** The user can use the Skype for Business Server infrastructure to route all incoming and outgoing calls.</span></span> <span data-ttu-id="94695-115">También puede realizar llamadas de equipo a equipo.</span><span class="sxs-lookup"><span data-stu-id="94695-115">The user can also make PC-to-PC calls.</span></span>
    
- <span data-ttu-id="94695-116">**Control remoto de llamadas** El usuario puede usar Skype Empresarial Server para controlar el teléfono de escritorio y también puede realizar llamadas de equipo a equipo.</span><span class="sxs-lookup"><span data-stu-id="94695-116">**Remote call control** The user can use Skype for Business Server to control the desktop phone, and can also make PC-to-PC calls.</span></span>
    
<span data-ttu-id="94695-117">Para obtener más información sobre cómo configurar la telefonía para una organización, consulte Habilitar usuarios para Telefonía IP empresarial en Skype Empresarial [Server](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md) e Implementar Telefonía IP empresarial en Skype Empresarial [Server](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="94695-117">For details about configuring telephony for an organization, see [Enable users for Enterprise Voice in Skype for Business Server](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md) and [Deploy Enterprise Voice in Skype for Business Server](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) in the Deployment documentation.</span></span>
  
1. <span data-ttu-id="94695-118">Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="94695-118">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="94695-119">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="94695-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="94695-120">En la barra de navegación izquierda, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="94695-120">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="94695-121">En el cuadro **Buscar usuarios**, escriba la primera parte del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de la cuenta de usuario que desee y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="94695-121">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span>
    
5. <span data-ttu-id="94695-122">En la tabla, haga clic en la cuenta de usuario que desee modificar.</span><span class="sxs-lookup"><span data-stu-id="94695-122">In the table, click the user account that you want to modify.</span></span>
    
6. <span data-ttu-id="94695-123">En el menú **Editar**, haga clic en **Modificar**.</span><span class="sxs-lookup"><span data-stu-id="94695-123">On the **Edit** menu, click **Modify**.</span></span>
    
7. <span data-ttu-id="94695-124">En **Telefonía**, siga este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="94695-124">In **Telephony**, do the following:</span></span>
    
   - <span data-ttu-id="94695-125">Para deshabilitar las llamadas de audio y vídeo del usuario, haga clic en **Audio y vídeo deshabilitados**.</span><span class="sxs-lookup"><span data-stu-id="94695-125">To disable audio and video calls for the user, click **Audio/video disabled**.</span></span>
    
   - <span data-ttu-id="94695-p102">Para habilitar las comunicaciones de audio de equipo a equipo para el usuario, pero no el control remoto de llamadas ni la Telefonía IP empresarial, haga clic en **Solo de equipo a equipo**. Especifique un valor para **URI de línea** para el teléfono que usa el usuario para comunicaciones de audio de equipo a equipo.</span><span class="sxs-lookup"><span data-stu-id="94695-p102">To enable PC-to-PC audio communications for the user, but not remote call control or Enterprise Voice, click **PC-to-PC only**. Specify a value for **Line URI** for the telephone that the user uses for PC-to-PC audio communications.</span></span>
    
   - <span data-ttu-id="94695-128">Para enrutar las llamadas telefónicas del usuario mediante la infraestructura de Skype Empresarial de acuerdo con la clase de directiva de servicio, incluida la comunicación de audio de equipo a **equipo,** haga clic en Telefonía IP empresarial .</span><span class="sxs-lookup"><span data-stu-id="94695-128">To route the user's phone calls by using the Skype for Business infrastructure in accordance with the class of service policy, including PC-to-PC audio communication, click **Enterprise Voice**.</span></span> <span data-ttu-id="94695-129">En **URI de línea**, especifique el número de teléfono para la Telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="94695-129">In **Line URI**, specify the telephone number for Enterprise Voice.</span></span> <span data-ttu-id="94695-130">En **Directiva de plan de marcado** y **Directiva de voz**, especifique las directivas adecuadas para el usuario.</span><span class="sxs-lookup"><span data-stu-id="94695-130">In **Dial plan policy** and **Voice policy**, specify the appropriate policies for the user.</span></span> <span data-ttu-id="94695-131">Para especificar las reglas de normalización para convertir los números de teléfono que marque el usuario a formato E.164, seleccione el perfil de ubicación apropiado en **Directiva de ubicación**.</span><span class="sxs-lookup"><span data-stu-id="94695-131">To specify the normalization rules for translating phone numbers dialed by the user to the E.164 format, select the appropriate location profile in **Location policy**.</span></span>
    
   - <span data-ttu-id="94695-132">Para habilitar el control remoto de llamadas, que permite a los usuarios controlar su línea de teléfono de escritorio desde Skype Empresarial Server para realizar llamadas de equipo a equipo y de equipo a teléfono, haga clic en **Control** remoto de llamadas.</span><span class="sxs-lookup"><span data-stu-id="94695-132">To enable remote call control, which enables users to control their desktop phone line from Skype for Business Server to make PC-to-PC calls and PC-to-phone calls, click **Remote call control**.</span></span> <span data-ttu-id="94695-133">En **URI de línea**, especifique el número de teléfono para el control remoto de llamadas.</span><span class="sxs-lookup"><span data-stu-id="94695-133">In **Line URI**, specify the telephone number for remote call control.</span></span> <span data-ttu-id="94695-134">El usuario debe tener un teléfono de escritorio y una conexión de central de conmutación (PBX) para el enrutamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="94695-134">The user must have a desktop phone and private branch exchange (PBX) connection for call routing.</span></span>
    
## <a name="move-users-to-another-pool"></a><span data-ttu-id="94695-135">Mover usuarios a otro grupo</span><span class="sxs-lookup"><span data-stu-id="94695-135">Move users to another pool</span></span>
<span data-ttu-id="94695-136"><a name="Move_Users"> </a></span><span class="sxs-lookup"><span data-stu-id="94695-136"><a name="Move_Users"> </a></span></span>

<span data-ttu-id="94695-137">Puede usar el Panel de control de Skype Empresarial Server para asignar usuarios a un servidor o grupo específico.</span><span class="sxs-lookup"><span data-stu-id="94695-137">You can use Skype for Business Server Control Panel to assign users to a specific server or pool.</span></span>
  
> [!TIP]
> <span data-ttu-id="94695-138">Mover todos los usuarios existentes de un grupo de servidores de origen que ejecuta Lync Server 2010 o versiones anteriores a un grupo de destino de Skype Empresarial Server en un entorno complejo de Active Directory puede producir una replicación de Active Directory más lenta.</span><span class="sxs-lookup"><span data-stu-id="94695-138">Moving all existing users from a source pool that is running Lync Server 2010 or earlier to a Skype for Business Server destination pool in a complex Active Directory environment might result in slower Active Directory replication.</span></span> <span data-ttu-id="94695-139">Para evitar esto, puede usar filtros de búsqueda para mover usuarios de grupos que ejecutan Lync Server 2010 o versiones anteriores por separado, o puede usar el Shell de administración de Skype Empresarial Server para mover usuarios con cmdlets.</span><span class="sxs-lookup"><span data-stu-id="94695-139">To avoid this, you can use search filters to move users from pools that are running Lync Server 2010 or earlier separately, or you can use Skype for Business Server Management Shell to move users with cmdlets.</span></span> <span data-ttu-id="94695-140">Además, la funcionalidad de filtro funciona con usuarios de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="94695-140">Also, the filter functionality works with Skype for Business Server users.</span></span> 
  
### <a name="to-move-selected-users-to-a-different-server-or-pool"></a><span data-ttu-id="94695-141">Para mover determinados usuarios a otro servidor o grupo de servidores</span><span class="sxs-lookup"><span data-stu-id="94695-141">To move selected users to a different server or pool</span></span>

1. <span data-ttu-id="94695-142">Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="94695-142">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="94695-143">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="94695-143">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="94695-144">En la barra de navegación izquierda, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="94695-144">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="94695-145">En el cuadro **Buscar usuarios**, escriba la primera parte del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de la cuenta de usuario que desee y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="94695-145">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span> 
    
5. <span data-ttu-id="94695-146">En la tabla, seleccione uno o varios usuarios de la lista.</span><span class="sxs-lookup"><span data-stu-id="94695-146">In the table, select a specific user or users in the list.</span></span> 
    
6. <span data-ttu-id="94695-147">En el menú **Acción**, haga clic en **Mover usuarios seleccionados a un grupo de servidores**.</span><span class="sxs-lookup"><span data-stu-id="94695-147">On the **Action** menu, click **Move selected users to pool**.</span></span>
    
7. <span data-ttu-id="94695-148">En **Mover usuarios**, seleccione el grupo de servidores al que desea trasladar los usuarios en **Grupo de registrador de destino**.</span><span class="sxs-lookup"><span data-stu-id="94695-148">In **Move Users**, select the pool that you want to move the users to in **Destination registrar pool**.</span></span>
    
8. <span data-ttu-id="94695-149">(Opcional) Si el servidor o grupo de destino no está disponible, active la casilla **Imponer**.</span><span class="sxs-lookup"><span data-stu-id="94695-149">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="94695-p106">Si selecciona **Forzar**, se mueve la cuenta de usuario pero se eliminan los datos de usuario asociados (por ejemplo, conferencias que el usuario ha programado). Si no se selecciona, se mueven la cuenta y los datos asociados.</span><span class="sxs-lookup"><span data-stu-id="94695-p106">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled). If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-all-users-from-one-server-or-pool-to-a-different-server-or-pool"></a><span data-ttu-id="94695-152">Para mover todos los usuarios de un servidor o grupo de servidores a otro servidor o grupo de servidores</span><span class="sxs-lookup"><span data-stu-id="94695-152">To move all users from one server or pool to a different server or pool</span></span>

1. <span data-ttu-id="94695-153">Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="94695-153">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="94695-154">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="94695-154">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="94695-155">En la barra de navegación izquierda, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="94695-155">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="94695-156">En el menú **Acción**, haga clic en **Mover todos los usuarios a un grupo de servidores**.</span><span class="sxs-lookup"><span data-stu-id="94695-156">On the **Action** menu, click **Move all users to pool**.</span></span>
    
5. <span data-ttu-id="94695-157">En **Mover usuarios**, seleccione el grupo de servidores que contiene las cuentas de usuario que desea trasladar en **Grupo de registrador de origen**.</span><span class="sxs-lookup"><span data-stu-id="94695-157">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>
    
6. <span data-ttu-id="94695-158">En **Grupo de registrador de destino**, seleccione el grupo de servidores al que desea trasladar los usuarios.</span><span class="sxs-lookup"><span data-stu-id="94695-158">In **Destination registrar pool**, select the pool that you want to move the users to.</span></span>
    
7. <span data-ttu-id="94695-159">(Opcional) Si el servidor o grupo de destino no está disponible, active la casilla **Imponer**.</span><span class="sxs-lookup"><span data-stu-id="94695-159">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="94695-p107">Si selecciona **Forzar**, se mueve la cuenta de usuario pero se eliminan los datos de usuario asociados (por ejemplo, conferencias que el usuario ha programado). Si no se selecciona, se mueven la cuenta y los datos asociados.</span><span class="sxs-lookup"><span data-stu-id="94695-p107">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled). If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a><span data-ttu-id="94695-162">Para mover usuarios de un grupo a otro grupo diferente mediante un filtro</span><span class="sxs-lookup"><span data-stu-id="94695-162">To move users from one pool to a different pool by using a filter</span></span>

1. <span data-ttu-id="94695-163">Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="94695-163">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="94695-164">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="94695-164">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="94695-165">En la barra de navegación izquierda, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="94695-165">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="94695-166">En **Búsqueda de usuarios,** haga **clic en** Buscar y, a continuación, haga clic en **Agregar filtro.**</span><span class="sxs-lookup"><span data-stu-id="94695-166">In **User Search**, click **Search**, and then click **Add Filter**.</span></span>
    
5. <span data-ttu-id="94695-167">En los Criterios de búsqueda, seleccione **Grupo de registradores**, **Igual que**, **FQDN del grupo actual** y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="94695-167">In the Search criteria, select **Registrar Pool**, select **Equal to**, select **Current Pool FQDN**, and then click **Find**.</span></span>
    
6. <span data-ttu-id="94695-168">En el menú **Acción**, haga clic en **Mover todos los usuarios al grupo**.</span><span class="sxs-lookup"><span data-stu-id="94695-168">On the **Action** menu, click **Move all users to pool**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="94695-169">Cuando se aplica un filtro a un conjunto de usuarios existente, la opción **Mover todos los usuarios al grupo** se refiere al subconjunto de usuarios filtrados, no a **todos** los usuarios posibles.</span><span class="sxs-lookup"><span data-stu-id="94695-169">When a filter is applied to an existing set of users, the option **Move all users to pool** is in the context of the filtered subset of users, not **all** possible users.</span></span>
  
7. <span data-ttu-id="94695-170">En **Mover usuarios**, seleccione el grupo de servidores que contiene las cuentas de usuario que desea trasladar en **Grupo de registradores de origen**.</span><span class="sxs-lookup"><span data-stu-id="94695-170">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>
    
8. <span data-ttu-id="94695-171">En **Grupo de registradores de destino**, seleccione el grupo de servidores al que desea trasladar los usuarios.</span><span class="sxs-lookup"><span data-stu-id="94695-171">In **Destination registrar pool**, select the pool where you want to move the users.</span></span>
    
9. <span data-ttu-id="94695-172">(Opcional) Si el servidor o grupo de destino no está disponible, active la casilla **Forzar**.</span><span class="sxs-lookup"><span data-stu-id="94695-172">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="94695-p108">Si selecciona **Forzar**, se mueve la cuenta de usuario pero se eliminan los datos de usuario asociados (por ejemplo, conferencias que el usuario ha programado y contactos). Si no se selecciona, se mueven la cuenta y los datos asociados.</span><span class="sxs-lookup"><span data-stu-id="94695-p108">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled and contacts). If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a><span data-ttu-id="94695-175">Para mover usuarios de un grupo a otro mediante cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="94695-175">To move users from one pool to another using Windows Powershell cmdlets</span></span>

1. <span data-ttu-id="94695-176">Dependiendo de cómo ejecute Windows PowerShell comandos (es decir, de forma local o remota), debe iniciar sesión como miembro de los roles administrativos correctos de Skype Empresarial Server de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="94695-176">Depending on how you run Windows PowerShell commands (that is, locally or remotely), you need to log on as a member of the correct Skype for Business Server administrative roles as follows:</span></span>
    
   <span data-ttu-id="94695-177">a.</span><span class="sxs-lookup"><span data-stu-id="94695-177">a.</span></span> <span data-ttu-id="94695-178">Si ejecuta los comandos en el equipo local (por ejemplo, inicia sesión directamente en un servidor front-end): inicie sesión en el equipo donde está instalado el Shell de administración de Skype Empresarial Server como miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios, como se describe en Permisos de configuración **delegados.**</span><span class="sxs-lookup"><span data-stu-id="94695-178">If you are running the commands on the local machine (for example, you log on directly to a Front End Server): Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
   <span data-ttu-id="94695-179">b.</span><span class="sxs-lookup"><span data-stu-id="94695-179">b.</span></span> <span data-ttu-id="94695-180">Si ejecuta los comandos de forma remota en otro equipo (por ejemplo, inicia sesión en el equipo y ejecuta los comandos de forma remota en un servidor front-end Standard Edition): desde una cuenta de usuario asignada al rol CsUserAdministrator o al rol CsAdministrator, inicie sesión en cualquier equipo de la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="94695-180">If you are running the commands remotely on another computer (for example, you log on to your computer and run the commands remotely on a Standard Edition Front End Server): From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="94695-181">Inicie el Shell de administración de Skype Empresarial Server: Haga clic en **Inicio,** en Todos los **programas,** en **Skype** Empresarial y, a continuación, en Shell de administración de Skype Empresarial **Server.**</span><span class="sxs-lookup"><span data-stu-id="94695-181">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="94695-182">Para mover usuarios únicos, use el cmdlet Move-CsUser de la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="94695-182">To move single users, use the Move-CsUser cmdlet as follows:</span></span>
    
    ```PowerShell
    Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    ```

    <span data-ttu-id="94695-183">Donde el usuario que se moverá es Pilar Ackerman, y el usuario se moverá de su grupo de servidores principales actualmente asignado al grupo pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="94695-183">Where the user to move is the user Pilar Ackerman, and the user will be moved from their currently assigned home pool to the pool pool01.contoso.net</span></span>
    
4. <span data-ttu-id="94695-184">Para mover una cantidad grande de usuarios, use filtros con el cmdlet **Get-CsUser** y pase el conjunto resultante de usuarios a **Move-CsUser**:</span><span class="sxs-lookup"><span data-stu-id="94695-184">To move a large number of users, use filters with the **Get-CsUser** cmdlet and pass the resulting set of users to **Move-CsUser**:</span></span>
    
    ```PowerShell
    Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    ```

    <span data-ttu-id="94695-185">Los comandos combinados de los cmdlets **Get-CsUser** y **Move-CsUser** podrían dar el resultado siguiente:</span><span class="sxs-lookup"><span data-stu-id="94695-185">The combined commands of the **Get-CsUser** and **Move-CsUser** might result in this:</span></span>
    
    ```PowerShell
    Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"
    ```


