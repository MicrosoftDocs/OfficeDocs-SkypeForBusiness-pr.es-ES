---
title: 'Implementar el almacén de contactos unificado en Skype empresarial Server '
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d1c9ebd8-af42-42a0-87d9-fc899fbd7c42
description: 'Resumen: habilite el almacén de contactos unificado en Skype empresarial Server.'
ms.openlocfilehash: 6cadba38f40a8ff12501e0fe73f4243dc96a5831
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003070"
---
# <a name="deploy-unified-contact-store-in-skype-for-business-server"></a><span data-ttu-id="95d5b-103">Implementar el almacén de contactos unificado en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="95d5b-103">Deploy unified contact store in Skype for Business Server</span></span>
 
<span data-ttu-id="95d5b-104">**Resumen:** Habilitar el almacén de contactos unificado en Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="95d5b-104">**Summary:** Enable the unified contact store in Skype for Business Server.</span></span>
  
<span data-ttu-id="95d5b-105">Habilitar el almacén de contactos unificado en Skype empresarial Server no requiere ninguna configuración de topología.</span><span class="sxs-lookup"><span data-stu-id="95d5b-105">Enabling unified contact store in Skype for Business Server does not require any topology settings.</span></span> <span data-ttu-id="95d5b-106">Para habilitar el almacén de contactos unificado para los usuarios:</span><span class="sxs-lookup"><span data-stu-id="95d5b-106">To enable unified contact store for users:</span></span>
  
- <span data-ttu-id="95d5b-107">La directiva del almacén de contactos unificado está habilitada (que es el comportamiento predeterminado).</span><span class="sxs-lookup"><span data-stu-id="95d5b-107">Unified contact store policy is enabled (default is enabled).</span></span>
    
- <span data-ttu-id="95d5b-108">Los usuarios inician sesión en Skype empresarial al menos una vez.</span><span class="sxs-lookup"><span data-stu-id="95d5b-108">Users log in with Skype for Business at least once.</span></span>
    
<span data-ttu-id="95d5b-109">Después de migrar los contactos de un usuario, que sucede automáticamente cuando un usuario inicia sesión con Skype empresarial, el usuario puede acceder a sus contactos de Skype empresarial y administrarlos desde Skype empresarial, Outlook 2013 o Outlook Web Access.</span><span class="sxs-lookup"><span data-stu-id="95d5b-109">After a user's contacts have been migrated, which happens automatically when a user logs in with Skype for Business, the user can access and manage their Skype for Business contacts from Skype for Business, Outlook 2013, or Outlook Web Access.</span></span> <span data-ttu-id="95d5b-110">El usuario no tiene que haber iniciado sesión en Skype empresarial para administrar sus contactos desde Outlook o Outlook Web Access.</span><span class="sxs-lookup"><span data-stu-id="95d5b-110">The user does not have to be logged in to Skype for Business to manage their contacts from Outlook or Outlook Web Access.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="95d5b-111">Si un usuario inicia sesión desde Skype empresarial después de la migración, los contactos y grupos están disponibles y actualizados, pero el usuario no puede administrarlos (es decir, agregar, eliminar, mover, etiquetar, quitar o modificar) esos contactos.</span><span class="sxs-lookup"><span data-stu-id="95d5b-111">If a user logs in from Skype for Business after migration, contacts and groups are available and up-to-date, but the user cannot manage (that is, add, delete, move, tag, untag, or modify) those contacts.</span></span> 
  
## <a name="enable-users-for-unified-contact-store"></a><span data-ttu-id="95d5b-112">Habilitar usuarios para el almacenamiento de contactos unificado</span><span class="sxs-lookup"><span data-stu-id="95d5b-112">Enable users for unified contact store</span></span>

<span data-ttu-id="95d5b-113">Al implementar Skype empresarial Server y publicar la topología, el almacén de contactos unificado está habilitado para todos los usuarios de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="95d5b-113">When you deploy Skype for Business Server and publish the topology, unified contact store is enabled for all users by default.</span></span> <span data-ttu-id="95d5b-114">No es necesario realizar ninguna acción adicional para habilitar el almacén de contactos unificado después de implementar Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="95d5b-114">You do not need to take any additional action to enable unified contact store after you deploy Skype for Business Server.</span></span> <span data-ttu-id="95d5b-115">Pero, puede usar el cmdlet **Set-CsUserServicesPolicy** para personalizar qué usuarios tienen disponible el almacén de contactos unificado.</span><span class="sxs-lookup"><span data-stu-id="95d5b-115">However, you can use the **Set-CsUserServicesPolicy** cmdlet to customize which users have unified contact store available.</span></span> <span data-ttu-id="95d5b-116">Puede habilitar esta característica globalmente, por sitio, por inquilino, por individuo o por grupos de individuos.</span><span class="sxs-lookup"><span data-stu-id="95d5b-116">You can enable this feature globally, by site, by tenant, or by individuals or groups of individuals.</span></span>
  
### <a name="to-enable-users-for-unified-contact-store"></a><span data-ttu-id="95d5b-117">Para habilitar usuarios para el almacén de contactos unificado</span><span class="sxs-lookup"><span data-stu-id="95d5b-117">To enable users for unified contact store</span></span>

1. <span data-ttu-id="95d5b-118">Inicie el shell de administración de Skype empresarial Server: haga clic en **Inicio**, haga clic en **todos los programas**, en **Skype empresarial**y, a continuación, haga clic en **consola de administración de Skype empresarial**.</span><span class="sxs-lookup"><span data-stu-id="95d5b-118">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="95d5b-119">Siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="95d5b-119">Do any of the following:</span></span>
    
   - <span data-ttu-id="95d5b-120">Para habilitar el almacén de contactos Unificado de forma global para todos los usuarios de Skype empresarial Server, en la interfaz de línea de comandos de Windows PowerShell, con el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="95d5b-120">To enable unified contact store globally for all Skype for Business Server users, inter the following cmdlet at the Windows PowerShell command-line interface:</span></span>
    
   ```powershell
   Set-CsUserServicesPolicy -Identity global -UcsAllowed $True
   ```

   - <span data-ttu-id="95d5b-121">Para habilitar el almacén de contactos unificado para los usuarios de un sitio específico, en el símbolo del sistema, escriba:</span><span class="sxs-lookup"><span data-stu-id="95d5b-121">To enable unified contact store for the users at a specific site, at the prompt, type:</span></span>
    
   ```powershell
   New-CsUserServicesPolicy -Identity site:<site name> -UcsAllowed $True
   ```

   <span data-ttu-id="95d5b-122">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="95d5b-122">For example:</span></span>
    
   ```powershell
   New-CsUserServicesPolicy -Identity site:Redmond -UcsAllowed $True
   ```

   - <span data-ttu-id="95d5b-123">Para habilitar el almacén de contactos unificado por inquilino, en el símbolo del sistema, escriba:</span><span class="sxs-lookup"><span data-stu-id="95d5b-123">To enable unified contact store by tenant, at the prompt, type:</span></span>
    
   ```powershell
   Set-CsUserServicesPolicy -Tenant <tenantId> -UcsAllowed $True
   ```

   <span data-ttu-id="95d5b-124">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="95d5b-124">For example:</span></span>
    
   ```powershell
   Set-CsUserServicesPolicy -Tenant "38aad667-af54-4397-aaa7-e94c79ec2308" -UcsAllowed $True
   ```

   - <span data-ttu-id="95d5b-125">Para habilitar el almacén de contactos unificado para usuarios especificados, en el símbolo del sistema, escriba:</span><span class="sxs-lookup"><span data-stu-id="95d5b-125">To enable unified contact store for specific users, at the prompt, type:</span></span>
    
   ```powershell
   New-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $True
   Grant-CsUserServicesPolicy -Identity "<user display name>" -PolicyName <"policy name">
   ```

    > [!NOTE]
    > <span data-ttu-id="95d5b-126">También puede usar alias de usuario o URI de SIP en lugar del nombre para mostrar del usuario.</span><span class="sxs-lookup"><span data-stu-id="95d5b-126">You can also use user alias or SIP URI instead of the user display name.</span></span> 
  
    <span data-ttu-id="95d5b-127">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="95d5b-127">For example:</span></span>
    
   ```powershell
   New-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $True
   Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "UCS Enabled Users"
   ```

    > [!NOTE]
    > <span data-ttu-id="95d5b-128">En el ejemplo anterior, el primer comando crea una directiva por usuario denominada Usuarios habilitados para UCS con el indicador UcsAllowed establecido en True.</span><span class="sxs-lookup"><span data-stu-id="95d5b-128">In the preceding example, the first command creates a new per-user policy named UCS Enabled Users with the UcsAllowed flag set to True.</span></span> <span data-ttu-id="95d5b-129">El segundo comando asigna la directiva al usuario con el nombre para mostrar Ken Myer, lo que significa que Ken Myer ahora está habilitado para el almacén de contactos unificado.</span><span class="sxs-lookup"><span data-stu-id="95d5b-129">The second command assigns the policy to the user with the display name Ken Myer, which means that Ken Myer is now enabled for unified contact store.</span></span>
  
## <a name="migrate-users-to-unified-contact-store"></a><span data-ttu-id="95d5b-130">Migrar usuarios al almacén de contactos unificado</span><span class="sxs-lookup"><span data-stu-id="95d5b-130">Migrate users to unified contact store</span></span>

<span data-ttu-id="95d5b-131">Los contactos de un usuario se migran automáticamente al servidor de Exchange 2013 cuando el usuario:</span><span class="sxs-lookup"><span data-stu-id="95d5b-131">A user's contacts are automatically migrated to the Exchange 2013 server when the user:</span></span>
  
- <span data-ttu-id="95d5b-132">Tiene asignado una directiva de servicios de usuario que tiene UcsAllowed configurado en True.</span><span class="sxs-lookup"><span data-stu-id="95d5b-132">Has been assigned a user services policy that has UcsAllowed set to True.</span></span>
    
- <span data-ttu-id="95d5b-133">Se aprovisionó con un buzón de Exchange 2013 y ha iniciado sesión en el buzón al menos una vez.</span><span class="sxs-lookup"><span data-stu-id="95d5b-133">Has been provisioned with an Exchange 2013 mailbox and has signed into the mailbox at least once.</span></span>
    
- <span data-ttu-id="95d5b-134">Inicia sesión con un cliente enriquecido de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="95d5b-134">Logs in by using a Skype for Business rich client.</span></span>
    
<span data-ttu-id="95d5b-135">Si el usuario inicia sesión con un cliente de Lync o de una versión anterior, o si el usuario no está conectado a un servidor de Exchange 2013, se ignorará la Directiva de servicios de usuario y los contactos del usuario permanecerán en Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="95d5b-135">If the user logs in with a Lync or earlier client, or if the user is not connected to an Exchange 2013 server, the user services policy is ignored and the user's contacts remain in Skype for Business Server.</span></span>
  
<span data-ttu-id="95d5b-136">Puede determinar si se han migrado los contactos de un usuario usando uno de los métodos siguientes:</span><span class="sxs-lookup"><span data-stu-id="95d5b-136">You can determine whether a user's contacts have been migrated by using either of the following methods:</span></span> 
  
- <span data-ttu-id="95d5b-137">Compruebe la siguiente clave del registro en el equipo cliente:</span><span class="sxs-lookup"><span data-stu-id="95d5b-137">Check the following registry key on the client computer:</span></span>
    
    <span data-ttu-id="95d5b-138">HKEY_CURRENT_USER \Software\Microsoft\Office\15.0\Lync\\<SIP URL\>\UCS</span><span class="sxs-lookup"><span data-stu-id="95d5b-138">HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\\<SIP URL\>\UCS</span></span>
    
    <span data-ttu-id="95d5b-139">Si los contactos del usuario se almacenan en Exchange 2013, esta clave contiene un valor de InUCSMode con un valor de 2165.</span><span class="sxs-lookup"><span data-stu-id="95d5b-139">If the user's contacts are stored in Exchange 2013, this key contains a value of InUCSMode with a value of 2165.</span></span>
    
- <span data-ttu-id="95d5b-140">Ejecute el cmdlet **Test-CsUnifiedContactStore**.</span><span class="sxs-lookup"><span data-stu-id="95d5b-140">Run the **Test-CsUnifiedContactStore** cmdlet.</span></span> <span data-ttu-id="95d5b-141">En la línea de comandos del shell de administración de Skype empresarial Server, escriba:</span><span class="sxs-lookup"><span data-stu-id="95d5b-141">At the Skype for Business Server Management Shell command line, type:</span></span>
    
  ```powershell
  Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
  ```

    <span data-ttu-id="95d5b-142">Si el cmdlet **Test-CsUnifiedContactStore** se lleva a cabo con éxito, quiere decir que los contactos del usuario se han migrado al almacén de contactos unificado.</span><span class="sxs-lookup"><span data-stu-id="95d5b-142">If **Test-CsUnifiedContactStore** succeeds, the user's contacts were migrated to unified contact store.</span></span>
    
## <a name="roll-back-migrated-users"></a><span data-ttu-id="95d5b-143">Revertir usuarios migrados</span><span class="sxs-lookup"><span data-stu-id="95d5b-143">Roll Back Migrated Users</span></span>

<span data-ttu-id="95d5b-144">Si necesita revertir la característica de almacenamiento de contactos unificado, revierta los contactos solo si vuelve a colocar el usuario en Exchange 2010 o Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="95d5b-144">If you need to roll back the unified contact store feature, roll back the contacts only if you move the user back to Exchange 2010 or Lync Server 2010.</span></span> <span data-ttu-id="95d5b-145">Para hacer la reversión, deshabilite la directiva del usuario y ejecute el cmdlet **Invoke-CsUcsRollback**.</span><span class="sxs-lookup"><span data-stu-id="95d5b-145">To roll back, disable the policy for the user, and then run the **Invoke-CsUcsRollback** cmdlet.</span></span> <span data-ttu-id="95d5b-146">Ejecutar solo **Invoke-CsUcsRollback** no es suficiente para que la reversión sea permanente, porque la migración del almacén de contactos unificado se iniciará de nuevo si la directiva no se deshabilita.</span><span class="sxs-lookup"><span data-stu-id="95d5b-146">Just running **Invoke-CsUcsRollback** alone is not enough to ensure permanent rollback, because unified contact store migration will be initiated again if the policy is not disabled.</span></span> <span data-ttu-id="95d5b-147">Por ejemplo, si un usuario se deshace porque Exchange 2013 se ha revertido a Exchange 2010 y, a continuación, el buzón del usuario se mueve a Exchange 2013, la migración del almacén de contactos unificado se iniciará de nuevo siete días después de la reversión, siempre que el almacén de contactos unificado aún está habilitado para el usuario en la Directiva de servicios de usuario.</span><span class="sxs-lookup"><span data-stu-id="95d5b-147">For example, if a user is rolled back because Exchange 2013 is rolled back to Exchange 2010, and then the user's mailbox is moved to Exchange 2013, the unified contact store migration will be initiated again seven days after the rollback, as long as unified contact store is still enabled for the user in the user services policy.</span></span>
  
<span data-ttu-id="95d5b-148">El cmdlet **Move-CsUser** revierte automáticamente el almacén de contactos del usuario de Exchange 2013 a Skype empresarial Server en las situaciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="95d5b-148">The **Move-CsUser** cmdlet automatically rolls back the user's contact store from Exchange 2013 to Skype for Business Server in the following situations:</span></span>
  
- <span data-ttu-id="95d5b-149">Cuando los usuarios se mueven de Skype empresarial Server a Microsoft Lync Server 2013 o Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="95d5b-149">When users are moved from Skype for Business Server to Microsoft Lync Server 2013 or Lync Server 2010.</span></span> 
    
- <span data-ttu-id="95d5b-150">Cuando los usuarios migran interlocales, como cuando un usuario se mueve de Skype empresarial online a Skype empresarial Server local, o viceversa.</span><span class="sxs-lookup"><span data-stu-id="95d5b-150">When users are migrated cross premises, such as when a user is moved from Skype for Business Online to Skype for Business Server on-premises, or vice versa.</span></span>
    
<span data-ttu-id="95d5b-p107">La importación de datos del almacén de contactos unificado desde una base de datos de copia de seguridad puede dañar los datos del almacén de contactos unificado y del usuario si el modo de almacén de contactos unificado cambia entre la exportación y la importación. Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="95d5b-p107">Importing unified contact store data from a backup database can cause unified contact store data and user data to become corrupted if the unified contact store mode changed between the export and the import. For example:</span></span>
  
- <span data-ttu-id="95d5b-153">Si exporta listas de contactos antes de migrar los contactos de los usuarios a Exchange 2013 y, después de la migración, importar los mismos datos, se dañarán los datos del almacén de contactos unificado y las listas de contactos.</span><span class="sxs-lookup"><span data-stu-id="95d5b-153">If you export contact lists before the users' contacts are migrated to Exchange 2013 and then, after the migration, import the same data, the unified contact store data and contact lists will be corrupted.</span></span>
    
- <span data-ttu-id="95d5b-154">Si exporta los datos de usuario después de migrar los usuarios a Exchange 2013, revertir la migración y, por algún motivo, importar los datos desde después de la migración, los datos del almacén de contactos unificados y las listas de contactos estarán dañados.</span><span class="sxs-lookup"><span data-stu-id="95d5b-154">If you export user data after you migrate users to Exchange 2013, roll back the migration, and then for some reason you import the data from after the migration, the unified contact store data and contact lists will be corrupted.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="95d5b-155">Antes de mover un buzón de Exchange de Exchange 2013 a Exchange 2010, el administrador de Exchange debe asegurarse de que el administrador de Skype empresarial Server haya revertido primero los contactos de usuario de Skype empresarial Server de Exchange 2013 a Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="95d5b-155">Before you move an Exchange mailbox from Exchange 2013 to Exchange 2010, the Exchange administrator must make sure that the Skype for Business Server administrator has first rolled back the Skype for Business Server user contacts from Exchange 2013 to Skype for Business Server.</span></span> <span data-ttu-id="95d5b-156">Para deshacer los contactos de la tienda de contactos unificada en Skype empresarial Server, consulte el procedimiento "para revertir contactos de almacenamiento de contactos Unificado de Exchange 2013 a Skype empresarial Server", más adelante en esta sección.</span><span class="sxs-lookup"><span data-stu-id="95d5b-156">To roll back unified contact store contacts to Skype for Business Server, see procedure "To roll back unified contact store contacts from Exchange 2013 to Skype for Business Server," later in this section.</span></span> 
  
 <span data-ttu-id="95d5b-157">**Cómo revertir contactos de usuario:** Si usa el cmdlet **Move-CsUser** para mover usuarios entre Skype empresarial Server 2015 y Lync Server 2010, puede omitir estos pasos porque el cmdlet **Move-CsUser** revierte automáticamente el almacén de contactos unificado cuando mueve usuarios de Skype empresarial Server 2015 a Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="95d5b-157">**How to roll back user contacts:** If you use the **Move-CsUser** cmdlet to move users between Skype for Business Server 2015 and Lync Server 2010, you can skip these steps because the **Move-CsUser** cmdlet automatically rolls back unified contact store when it moves users from Skype for Business Server 2015 to Lync Server 2010.</span></span> <span data-ttu-id="95d5b-158">**Move-CsUser** no deshabilita la Directiva del almacén de contactos unificado, por lo que la migración al almacén de contactos unificado se repetirá si el usuario vuelve a usar Skype empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="95d5b-158">**Move-CsUser** does not disable unified contact store policy, so the migration to unified contact store will recur if the user is moved back to Skype for Business Server 2015.</span></span>
  

