---
title: 'Implementar el almacén de contactos unificado en Skype Empresarial Server '
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d1c9ebd8-af42-42a0-87d9-fc899fbd7c42
description: 'Resumen: habilite el almacén de contactos unificado en Skype Empresarial Server.'
ms.openlocfilehash: 7bf4dcb884dc9fecee15209f5acb563fce9efd43
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812560"
---
# <a name="deploy-unified-contact-store-in-skype-for-business-server"></a><span data-ttu-id="6fbd2-103">Implementar el almacén de contactos unificado en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="6fbd2-103">Deploy unified contact store in Skype for Business Server</span></span>
 
<span data-ttu-id="6fbd2-104">**Resumen:** Habilite el almacén de contactos unificado en Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="6fbd2-104">**Summary:** Enable the unified contact store in Skype for Business Server.</span></span>
  
<span data-ttu-id="6fbd2-105">La habilitación del almacén de contactos unificado en Skype Empresarial Server no requiere ninguna configuración de topología.</span><span class="sxs-lookup"><span data-stu-id="6fbd2-105">Enabling unified contact store in Skype for Business Server does not require any topology settings.</span></span> <span data-ttu-id="6fbd2-106">Para habilitar el almacén de contactos unificado para los usuarios:</span><span class="sxs-lookup"><span data-stu-id="6fbd2-106">To enable unified contact store for users:</span></span>
  
- <span data-ttu-id="6fbd2-107">La directiva de almacén de contactos unificados está habilitada (que es el comportamiento predeterminado).</span><span class="sxs-lookup"><span data-stu-id="6fbd2-107">Unified contact store policy is enabled (default is enabled).</span></span>
    
- <span data-ttu-id="6fbd2-108">Los usuarios inician sesión con Skype Empresarial al menos una vez.</span><span class="sxs-lookup"><span data-stu-id="6fbd2-108">Users log in with Skype for Business at least once.</span></span>
    
<span data-ttu-id="6fbd2-109">Después de migrar los contactos de un usuario, lo que ocurre automáticamente cuando un usuario inicia sesión con Skype Empresarial, el usuario puede acceder a sus contactos de Skype Empresarial y administrarlos desde Skype Empresarial, Outlook 2013 o Outlook Web Access.</span><span class="sxs-lookup"><span data-stu-id="6fbd2-109">After a user's contacts have been migrated, which happens automatically when a user logs in with Skype for Business, the user can access and manage their Skype for Business contacts from Skype for Business, Outlook 2013, or Outlook Web Access.</span></span> <span data-ttu-id="6fbd2-110">No es necesario que el usuario haya iniciado sesión en Skype Empresarial para administrar sus contactos desde Outlook o Outlook Web Access.</span><span class="sxs-lookup"><span data-stu-id="6fbd2-110">The user does not have to be logged in to Skype for Business to manage their contacts from Outlook or Outlook Web Access.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="6fbd2-111">Si un usuario inicia sesión desde Skype Empresarial después de la migración, los contactos y grupos están disponibles y actualizados, pero el usuario no puede administrar (es decir, agregar, eliminar, mover, etiquetar, eliminar o modificar) esos contactos.</span><span class="sxs-lookup"><span data-stu-id="6fbd2-111">If a user logs in from Skype for Business after migration, contacts and groups are available and up-to-date, but the user cannot manage (that is, add, delete, move, tag, untag, or modify) those contacts.</span></span> 
  
## <a name="enable-users-for-unified-contact-store"></a><span data-ttu-id="6fbd2-112">Habilitar usuarios para el almacén de contactos unificado</span><span class="sxs-lookup"><span data-stu-id="6fbd2-112">Enable users for unified contact store</span></span>

<span data-ttu-id="6fbd2-113">Al implementar Skype Empresarial Server y publicar la topología, el almacén de contactos unificado está habilitado para todos los usuarios de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="6fbd2-113">When you deploy Skype for Business Server and publish the topology, unified contact store is enabled for all users by default.</span></span> <span data-ttu-id="6fbd2-114">No es necesario realizar ninguna acción adicional para habilitar el almacén de contactos unificado después de implementar Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="6fbd2-114">You do not need to take any additional action to enable unified contact store after you deploy Skype for Business Server.</span></span> <span data-ttu-id="6fbd2-115">Sin embargo, puede usar el cmdlet **Set-CsUserServicesPolicy** para personalizar qué usuarios tienen disponible el almacén de contactos unificados.</span><span class="sxs-lookup"><span data-stu-id="6fbd2-115">However, you can use the **Set-CsUserServicesPolicy** cmdlet to customize which users have unified contact store available.</span></span> <span data-ttu-id="6fbd2-116">Puede habilitar esta característica globalmente, por sitio, por inquilino o por individuos o grupos de individuos.</span><span class="sxs-lookup"><span data-stu-id="6fbd2-116">You can enable this feature globally, by site, by tenant, or by individuals or groups of individuals.</span></span>
  
### <a name="to-enable-users-for-unified-contact-store"></a><span data-ttu-id="6fbd2-117">Procedimiento para habilitar usuarios para el almacén de contactos unificados</span><span class="sxs-lookup"><span data-stu-id="6fbd2-117">To enable users for unified contact store</span></span>

1. <span data-ttu-id="6fbd2-118">Inicie el Shell de administración de Skype Empresarial Server: Haga clic en **Inicio,** en Todos los **programas,** en **Skype** Empresarial y, a continuación, en Shell de administración de Skype Empresarial **Server.**</span><span class="sxs-lookup"><span data-stu-id="6fbd2-118">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="6fbd2-119">Siga uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="6fbd2-119">Do any of the following:</span></span>
    
   - <span data-ttu-id="6fbd2-120">Para habilitar el almacén de contactos unificado globalmente para todos los usuarios de Skype Empresarial Server, entre el siguiente cmdlet en la Windows PowerShell de línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="6fbd2-120">To enable unified contact store globally for all Skype for Business Server users, inter the following cmdlet at the Windows PowerShell command-line interface:</span></span>
    
   ```powershell
   Set-CsUserServicesPolicy -Identity global -UcsAllowed $True
   ```

   - <span data-ttu-id="6fbd2-121">Para habilitar el almacén de contactos unificado para los usuarios de un sitio específico, en el símbolo del sistema, escriba:</span><span class="sxs-lookup"><span data-stu-id="6fbd2-121">To enable unified contact store for the users at a specific site, at the prompt, type:</span></span>
    
   ```powershell
   New-CsUserServicesPolicy -Identity site:<site name> -UcsAllowed $True
   ```

   <span data-ttu-id="6fbd2-122">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="6fbd2-122">For example:</span></span>
    
   ```powershell
   New-CsUserServicesPolicy -Identity site:Redmond -UcsAllowed $True
   ```

   - <span data-ttu-id="6fbd2-123">Para habilitar el almacén de contactos unificado por inquilino, en el símbolo del sistema, escriba:</span><span class="sxs-lookup"><span data-stu-id="6fbd2-123">To enable unified contact store by tenant, at the prompt, type:</span></span>
    
   ```powershell
   Set-CsUserServicesPolicy -Tenant <tenantId> -UcsAllowed $True
   ```

   <span data-ttu-id="6fbd2-124">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="6fbd2-124">For example:</span></span>
    
   ```powershell
   Set-CsUserServicesPolicy -Tenant "38aad667-af54-4397-aaa7-e94c79ec2308" -UcsAllowed $True
   ```

   - <span data-ttu-id="6fbd2-125">Para habilitar el almacén de contactos unificado para usuarios específicos, en el símbolo del sistema, escriba:</span><span class="sxs-lookup"><span data-stu-id="6fbd2-125">To enable unified contact store for specific users, at the prompt, type:</span></span>
    
   ```powershell
   New-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $True
   Grant-CsUserServicesPolicy -Identity "<user display name>" -PolicyName <"policy name">
   ```

    > [!NOTE]
    > <span data-ttu-id="6fbd2-126">También puede usar alias de usuario o URI de SIP en lugar del nombre para mostrar del usuario.</span><span class="sxs-lookup"><span data-stu-id="6fbd2-126">You can also use user alias or SIP URI instead of the user display name.</span></span> 
  
    <span data-ttu-id="6fbd2-127">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="6fbd2-127">For example:</span></span>
    
   ```powershell
   New-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $True
   Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "UCS Enabled Users"
   ```

    > [!NOTE]
    > <span data-ttu-id="6fbd2-128">En el ejemplo anterior, el primer comando crea una nueva directiva por usuario denominada Usuarios habilitados para UC con el indicador UcsAllowed establecido en Verdadero.</span><span class="sxs-lookup"><span data-stu-id="6fbd2-128">In the preceding example, the first command creates a new per-user policy named UCS Enabled Users with the UcsAllowed flag set to True.</span></span> <span data-ttu-id="6fbd2-129">El segundo comando asigna la directiva al usuario con el nombre para mostrar Ken Myer, lo cual significa que Ken Myer ahora está habilitado para el almacén de contactos unificados.</span><span class="sxs-lookup"><span data-stu-id="6fbd2-129">The second command assigns the policy to the user with the display name Ken Myer, which means that Ken Myer is now enabled for unified contact store.</span></span>
  
## <a name="migrate-users-to-unified-contact-store"></a><span data-ttu-id="6fbd2-130">Migrar usuarios al almacén de contactos unificado</span><span class="sxs-lookup"><span data-stu-id="6fbd2-130">Migrate users to unified contact store</span></span>

<span data-ttu-id="6fbd2-131">Los contactos de un usuario se migran automáticamente al servidor Exchange 2013 cuando el usuario:</span><span class="sxs-lookup"><span data-stu-id="6fbd2-131">A user's contacts are automatically migrated to the Exchange 2013 server when the user:</span></span>
  
- <span data-ttu-id="6fbd2-132">Tiene asignado una directiva de servicios del usuario que tiene UcsAllowed configurado en True.</span><span class="sxs-lookup"><span data-stu-id="6fbd2-132">Has been assigned a user services policy that has UcsAllowed set to True.</span></span>
    
- <span data-ttu-id="6fbd2-133">Se ha aprovisionado con un buzón de Exchange 2013 y ha iniciado sesión en el buzón al menos una vez.</span><span class="sxs-lookup"><span data-stu-id="6fbd2-133">Has been provisioned with an Exchange 2013 mailbox and has signed into the mailbox at least once.</span></span>
    
- <span data-ttu-id="6fbd2-134">Inicia sesión con un cliente enriquecido de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="6fbd2-134">Logs in by using a Skype for Business rich client.</span></span>
    
<span data-ttu-id="6fbd2-135">Si el usuario inicia sesión con un cliente de Lync o anterior, o si el usuario no está conectado a un servidor de Exchange 2013, se omite la directiva de servicios de usuario y los contactos del usuario permanecen en Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="6fbd2-135">If the user logs in with a Lync or earlier client, or if the user is not connected to an Exchange 2013 server, the user services policy is ignored and the user's contacts remain in Skype for Business Server.</span></span>
  
<span data-ttu-id="6fbd2-136">Puede determinar si se han migrado los contactos de un usuario usando uno de los métodos siguientes:</span><span class="sxs-lookup"><span data-stu-id="6fbd2-136">You can determine whether a user's contacts have been migrated by using either of the following methods:</span></span> 
  
- <span data-ttu-id="6fbd2-137">Compruebe la siguiente clave del registro en el equipo cliente:</span><span class="sxs-lookup"><span data-stu-id="6fbd2-137">Check the following registry key on the client computer:</span></span>
    
    <span data-ttu-id="6fbd2-138">HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync<\\ URL SIP \> \UCS</span><span class="sxs-lookup"><span data-stu-id="6fbd2-138">HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\\<SIP URL\>\UCS</span></span>
    
    <span data-ttu-id="6fbd2-139">Si los contactos del usuario se almacenan en Exchange 2013, esta clave contiene un valor de InUCSMode con un valor de 2165.</span><span class="sxs-lookup"><span data-stu-id="6fbd2-139">If the user's contacts are stored in Exchange 2013, this key contains a value of InUCSMode with a value of 2165.</span></span>
    
- <span data-ttu-id="6fbd2-140">Ejecute el cmdlet **Test-CsUnifiedContactStore**.</span><span class="sxs-lookup"><span data-stu-id="6fbd2-140">Run the **Test-CsUnifiedContactStore** cmdlet.</span></span> <span data-ttu-id="6fbd2-141">En la línea de comandos del Shell de administración de Skype Empresarial Server, escriba:</span><span class="sxs-lookup"><span data-stu-id="6fbd2-141">At the Skype for Business Server Management Shell command line, type:</span></span>
    
  ```powershell
  Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
  ```

    <span data-ttu-id="6fbd2-142">Si el cmdlet **Test-CsUnifiedContactStore** se lleva a cabo con éxito, quiere decir que los contactos del usuario se han migrado al almacén de contactos unificado.</span><span class="sxs-lookup"><span data-stu-id="6fbd2-142">If **Test-CsUnifiedContactStore** succeeds, the user's contacts were migrated to unified contact store.</span></span>
    
## <a name="roll-back-migrated-users"></a><span data-ttu-id="6fbd2-143">Revertir usuarios migrados</span><span class="sxs-lookup"><span data-stu-id="6fbd2-143">Roll Back Migrated Users</span></span>

<span data-ttu-id="6fbd2-144">Si necesita revertir la característica de almacén de contactos unificados, revierte los contactos solo si mueve al usuario a Exchange 2010 o Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="6fbd2-144">If you need to roll back the unified contact store feature, roll back the contacts only if you move the user back to Exchange 2010 or Lync Server 2010.</span></span> <span data-ttu-id="6fbd2-145">Para hacer la reversión, deshabilite la directiva del usuario y ejecute el cmdlet **Invoke-CsUcsRollback**.</span><span class="sxs-lookup"><span data-stu-id="6fbd2-145">To roll back, disable the policy for the user, and then run the **Invoke-CsUcsRollback** cmdlet.</span></span> <span data-ttu-id="6fbd2-146">Ejecutar solo **Invoke-CsUcsRollback** no es suficiente para que la reversión sea permanente, porque la migración del almacén de contactos unificado se iniciará de nuevo si la directiva no se deshabilita.</span><span class="sxs-lookup"><span data-stu-id="6fbd2-146">Just running **Invoke-CsUcsRollback** alone is not enough to ensure permanent rollback, because unified contact store migration will be initiated again if the policy is not disabled.</span></span> <span data-ttu-id="6fbd2-147">Por ejemplo, si se revierte un usuario porque Exchange 2013 se revierte a Exchange 2010 y, a continuación, el buzón del usuario se mueve a Exchange 2013, la migración del almacén de contactos unificado se iniciará de nuevo siete días después de la reversión, siempre y cuando el almacén de contactos unificado aún esté habilitado para el usuario en la directiva de servicios de usuario.</span><span class="sxs-lookup"><span data-stu-id="6fbd2-147">For example, if a user is rolled back because Exchange 2013 is rolled back to Exchange 2010, and then the user's mailbox is moved to Exchange 2013, the unified contact store migration will be initiated again seven days after the rollback, as long as unified contact store is still enabled for the user in the user services policy.</span></span>
  
<span data-ttu-id="6fbd2-148">El cmdlet **Move-CsUser** revierte automáticamente el almacén de contactos del usuario de Exchange 2013 a Skype Empresarial Server en las situaciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="6fbd2-148">The **Move-CsUser** cmdlet automatically rolls back the user's contact store from Exchange 2013 to Skype for Business Server in the following situations:</span></span>
  
- <span data-ttu-id="6fbd2-149">Cuando los usuarios se mueven de Skype Empresarial Server a Microsoft Lync Server 2013 o Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="6fbd2-149">When users are moved from Skype for Business Server to Microsoft Lync Server 2013 or Lync Server 2010.</span></span> 
    
- <span data-ttu-id="6fbd2-150">Cuando los usuarios se migran entre locales, como cuando se mueve un usuario de Skype Empresarial Online a Skype Empresarial Server local, o viceversa.</span><span class="sxs-lookup"><span data-stu-id="6fbd2-150">When users are migrated cross premises, such as when a user is moved from Skype for Business Online to Skype for Business Server on-premises, or vice versa.</span></span>
    
<span data-ttu-id="6fbd2-p107">La importación de datos del almacén de contactos unificado desde una base de datos de copia de seguridad puede dañar los datos del almacén de contactos unificado y del usuario si el modo de almacén de contactos unificado cambia entre la exportación y la importación. Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="6fbd2-p107">Importing unified contact store data from a backup database can cause unified contact store data and user data to become corrupted if the unified contact store mode changed between the export and the import. For example:</span></span>
  
- <span data-ttu-id="6fbd2-153">Si exporta listas de contactos antes de que los contactos de los usuarios se migren a Exchange 2013 y, después de la migración, importe los mismos datos, los datos del almacén de contactos unificado y las listas de contactos se dañarán.</span><span class="sxs-lookup"><span data-stu-id="6fbd2-153">If you export contact lists before the users' contacts are migrated to Exchange 2013 and then, after the migration, import the same data, the unified contact store data and contact lists will be corrupted.</span></span>
    
- <span data-ttu-id="6fbd2-154">Si exporta datos de usuario después de migrar usuarios a Exchange 2013, revierte la migración y, por algún motivo, importa los datos después de la migración, los datos del almacén de contactos unificado y las listas de contactos se dañarán.</span><span class="sxs-lookup"><span data-stu-id="6fbd2-154">If you export user data after you migrate users to Exchange 2013, roll back the migration, and then for some reason you import the data from after the migration, the unified contact store data and contact lists will be corrupted.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="6fbd2-155">Antes de mover un buzón de Exchange de Exchange 2013 a Exchange 2010, el administrador de Exchange debe asegurarse de que el administrador de Skype Empresarial Server revierte primero los contactos de usuario de Skype Empresarial Server de Exchange 2013 a Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="6fbd2-155">Before you move an Exchange mailbox from Exchange 2013 to Exchange 2010, the Exchange administrator must make sure that the Skype for Business Server administrator has first rolled back the Skype for Business Server user contacts from Exchange 2013 to Skype for Business Server.</span></span> <span data-ttu-id="6fbd2-156">Para revertir los contactos del almacén de contactos unificados a Skype Empresarial Server, consulte el procedimiento "Revertir contactos del almacén de contactos unificados de Exchange 2013 a Skype Empresarial Server", más adelante en esta sección.</span><span class="sxs-lookup"><span data-stu-id="6fbd2-156">To roll back unified contact store contacts to Skype for Business Server, see procedure "To roll back unified contact store contacts from Exchange 2013 to Skype for Business Server," later in this section.</span></span> 
  
 <span data-ttu-id="6fbd2-157">**Cómo revertir contactos de usuario:** Si usa el cmdlet **Move-CsUser** para mover usuarios entre Skype Empresarial Server 2015 y Lync Server 2010, puede omitir estos pasos porque el cmdlet **Move-CsUser** revierte automáticamente el almacén de contactos unificado cuando mueve usuarios de Skype Empresarial Server 2015 a Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="6fbd2-157">**How to roll back user contacts:** If you use the **Move-CsUser** cmdlet to move users between Skype for Business Server 2015 and Lync Server 2010, you can skip these steps because the **Move-CsUser** cmdlet automatically rolls back unified contact store when it moves users from Skype for Business Server 2015 to Lync Server 2010.</span></span> <span data-ttu-id="6fbd2-158">**Move-CsUser** no deshabilita la directiva de almacén de contactos unificado, por lo que la migración al almacén de contactos unificados se repetirá si el usuario vuelve a Skype Empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="6fbd2-158">**Move-CsUser** does not disable unified contact store policy, so the migration to unified contact store will recur if the user is moved back to Skype for Business Server 2015.</span></span>
  

