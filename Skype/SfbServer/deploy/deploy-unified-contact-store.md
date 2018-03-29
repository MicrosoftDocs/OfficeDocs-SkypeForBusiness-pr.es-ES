---
title: Implementar el almacenamiento de contactos unificado en Skype Empresarial Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d1c9ebd8-af42-42a0-87d9-fc899fbd7c42
description: 'Resumen: Habilitar el almacén de contactos unificado en Skype para Business Server 2015.'
ms.openlocfilehash: fbe94023a6693f7d016d2963d49d88646c9b969e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-unified-contact-store-in-skype-for-business-server-2015"></a><span data-ttu-id="e1cc0-103">Implementar el almacenamiento de contactos unificado en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="e1cc0-103">Deploy unified contact store in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="e1cc0-104">**Resumen:** Habilitar el almacén de contactos unificado en Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="e1cc0-104">**Summary:** Enable the unified contact store in Skype for Business Server 2015 .</span></span>
  
<span data-ttu-id="e1cc0-105">Habilitar el almacén de contactos unificado en Skype para Business Server 2015 no requiere ninguna configuración de topología.</span><span class="sxs-lookup"><span data-stu-id="e1cc0-105">Enabling unified contact store in Skype for Business Server 2015 does not require any topology settings.</span></span> <span data-ttu-id="e1cc0-106">Para habilitar el almacén de contactos unificado para los usuarios:</span><span class="sxs-lookup"><span data-stu-id="e1cc0-106">To enable unified contact store for users:</span></span>
  
- <span data-ttu-id="e1cc0-107">La directiva del almacén de contactos unificado está habilitada (que es el comportamiento predeterminado).</span><span class="sxs-lookup"><span data-stu-id="e1cc0-107">Unified contact store policy is enabled (default is enabled).</span></span>
    
- <span data-ttu-id="e1cc0-108">Los usuarios inicie sesión con Skype para el negocio al menos una vez.</span><span class="sxs-lookup"><span data-stu-id="e1cc0-108">Users log in with Skype for Business at least once.</span></span>
    
<span data-ttu-id="e1cc0-109">Después de los contactos de los usuarios se han migrado, lo que sucede automáticamente cuando un usuario inicia sesión con Skype para el negocio, el usuario puede tener acceso y administrar su Skype para contactos profesionales de Skype para negocios, 2013 de Outlook o Outlook Web Access.</span><span class="sxs-lookup"><span data-stu-id="e1cc0-109">After a user's contacts have been migrated, which happens automatically when a user logs in with Skype for Business, the user can access and manage their Skype for Business contacts from Skype for Business, Outlook 2013, or Outlook Web Access.</span></span> <span data-ttu-id="e1cc0-110">El usuario no tiene que iniciar sesión en Skype para empresas administrar sus contactos de Outlook o Outlook Web Access.</span><span class="sxs-lookup"><span data-stu-id="e1cc0-110">The user does not have to be logged in to Skype for Business to manage their contacts from Outlook or Outlook Web Access.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e1cc0-111">Si un usuario inicia una sesión de Skype para empresas después de la migración, contactos y grupos que están disponibles y actualizados, pero el usuario no puede administrar (que es, agregar, eliminar, mover, etiqueta, quitar la etiqueta o modificar) los contactos.</span><span class="sxs-lookup"><span data-stu-id="e1cc0-111">If a user logs in from Skype for Business after migration, contacts and groups are available and up-to-date, but the user cannot manage (that is, add, delete, move, tag, untag, or modify) those contacts.</span></span> 
  
## <a name="enable-users-for-unified-contact-store"></a><span data-ttu-id="e1cc0-112">Habilitar usuarios para el almacenamiento de contactos unificado</span><span class="sxs-lookup"><span data-stu-id="e1cc0-112">Enable users for unified contact store</span></span>

<span data-ttu-id="e1cc0-113">Al implementar Skype para Business Server 2015 y publicar la topología, almacén de contactos unificada está habilitada de forma predeterminada para todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="e1cc0-113">When you deploy Skype for Business Server 2015 and publish the topology, unified contact store is enabled for all users by default.</span></span> <span data-ttu-id="e1cc0-114">No es necesario realizar ninguna acción adicional para habilitar el almacén de contactos unificado después de implementar Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="e1cc0-114">You do not need to take any additional action to enable unified contact store after you deploy Skype for Business Server 2015.</span></span> <span data-ttu-id="e1cc0-115">Sin embargo, puede utilizar el cmdlet **Set-CsUserServicesPolicy** para personalizar qué usuarios han unificado almacén de contactos disponibles.</span><span class="sxs-lookup"><span data-stu-id="e1cc0-115">However, you can use the **Set-CsUserServicesPolicy** cmdlet to customize which users have unified contact store available.</span></span> <span data-ttu-id="e1cc0-116">Puede habilitar esta característica globalmente, por sitio, por inquilino, por individuo o por grupos de individuos.</span><span class="sxs-lookup"><span data-stu-id="e1cc0-116">You can enable this feature globally, by site, by tenant, or by individuals or groups of individuals.</span></span>
  
### <a name="to-enable-users-for-unified-contact-store"></a><span data-ttu-id="e1cc0-117">Para habilitar usuarios para el almacén de contactos unificado</span><span class="sxs-lookup"><span data-stu-id="e1cc0-117">To enable users for unified contact store</span></span>

1. <span data-ttu-id="e1cc0-118">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="e1cc0-118">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="e1cc0-119">Siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="e1cc0-119">Do any of the following:</span></span>
    
   - <span data-ttu-id="e1cc0-120">Para habilitar el almacén de contactos unificado globalmente para todos los Skype para los usuarios de Business Server, entre el siguiente cmdlet en la interfaz de línea de comandos de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="e1cc0-120">To enable unified contact store globally for all Skype for Business Server users, inter the following cmdlet at the Windows PowerShell command-line interface:</span></span>
    
   ```
   Set-CsUserServicesPolicy -Identity global -UcsAllowed $True
   ```

   - <span data-ttu-id="e1cc0-121">Para habilitar el almacén de contactos unificado para los usuarios de un sitio específico, en el símbolo del sistema, escriba:</span><span class="sxs-lookup"><span data-stu-id="e1cc0-121">To enable unified contact store for the users at a specific site, at the prompt, type:</span></span>
    
   ```
   New-CsUserServicesPolicy -Identity site:<site name> -UcsAllowed $True
   ```

   <span data-ttu-id="e1cc0-122">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e1cc0-122">For example:</span></span>
    
   ```
   New-CsUserServicesPolicy -Identity site:Redmond -UcsAllowed $True
   ```

   - <span data-ttu-id="e1cc0-123">Para habilitar el almacén de contactos unificado por inquilino, en el símbolo del sistema, escriba:</span><span class="sxs-lookup"><span data-stu-id="e1cc0-123">To enable unified contact store by tenant, at the prompt, type:</span></span>
    
   ```
   Set-CsUserServicesPolicy -Tenant <tenantId> -UcsAllowed $True
   ```

   <span data-ttu-id="e1cc0-124">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e1cc0-124">For example:</span></span>
    
   ```
   Set-CsUserServicesPolicy -Tenant "38aad667-af54-4397-aaa7-e94c79ec2308" -UcsAllowed $True
   ```

   - <span data-ttu-id="e1cc0-125">Para habilitar el almacén de contactos unificado para usuarios especificados, en el símbolo del sistema, escriba:</span><span class="sxs-lookup"><span data-stu-id="e1cc0-125">To enable unified contact store for specific users, at the prompt, type:</span></span>
    
   ```
   New-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $True
   Grant-CsUserServicesPolicy -Identity "<user display name>" -PolicyName <"policy name">

   ```

    > [!NOTE]
    > <span data-ttu-id="e1cc0-126">También puede usar alias de usuario o URI de SIP en lugar del nombre para mostrar del usuario.</span><span class="sxs-lookup"><span data-stu-id="e1cc0-126">You can also use user alias or SIP URI instead of the user display name.</span></span> 
  
    <span data-ttu-id="e1cc0-127">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e1cc0-127">For example:</span></span>
    
   ```
   New-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $True
   Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "UCS Enabled Users"

   ```

    > [!NOTE]
    > <span data-ttu-id="e1cc0-128">En el ejemplo anterior, el primer comando crea una nueva directiva por usuario denominada usuarios de UCS habilitados con el indicador UcsAllowed establecido en True.</span><span class="sxs-lookup"><span data-stu-id="e1cc0-128">In the preceding example, the first command creates a new per-user policy named UCS Enabled Users with the UcsAllowed flag set to True.</span></span> <span data-ttu-id="e1cc0-129">El segundo comando asigna la directiva al usuario con el nombre para mostrar Ken Myer, lo que significa que Ken Myer ahora está habilitado para el almacén de contactos unificado.</span><span class="sxs-lookup"><span data-stu-id="e1cc0-129">The second command assigns the policy to the user with the display name Ken Myer, which means that Ken Myer is now enabled for unified contact store.</span></span>
  
## <a name="migrate-users-to-unified-contact-store"></a><span data-ttu-id="e1cc0-130">Migrar usuarios al almacén de contactos unificado</span><span class="sxs-lookup"><span data-stu-id="e1cc0-130">Migrate users to unified contact store</span></span>

<span data-ttu-id="e1cc0-131">Contactos de un usuario se migran automáticamente al servidor de Exchange de 2013 cuando el usuario:</span><span class="sxs-lookup"><span data-stu-id="e1cc0-131">A user's contacts are automatically migrated to the Exchange 2013 server when the user:</span></span>
  
- <span data-ttu-id="e1cc0-132">Tiene asignado una directiva de servicios de usuario que tiene UcsAllowed configurado en True.</span><span class="sxs-lookup"><span data-stu-id="e1cc0-132">Has been assigned a user services policy that has UcsAllowed set to True.</span></span>
    
- <span data-ttu-id="e1cc0-133">Se haya aprovisionado con un buzón de Exchange de 2013 y ha iniciado sesión en el buzón al menos una vez.</span><span class="sxs-lookup"><span data-stu-id="e1cc0-133">Has been provisioned with an Exchange 2013 mailbox and has signed into the mailbox at least once.</span></span>
    
- <span data-ttu-id="e1cc0-134">En los registros utilizando un Skype para cliente enriquecido de negocio.</span><span class="sxs-lookup"><span data-stu-id="e1cc0-134">Logs in by using a Skype for Business rich client.</span></span>
    
<span data-ttu-id="e1cc0-135">Si el usuario inicia sesión con un cliente anterior o de Lync, o si el usuario no está conectado a un servidor de Exchange de 2013, se omite la directiva de servicios de usuario y los contactos del usuario permanecen en Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="e1cc0-135">If the user logs in with a Lync or earlier client, or if the user is not connected to an Exchange 2013 server, the user services policy is ignored and the user's contacts remain in Skype for Business Server.</span></span>
  
<span data-ttu-id="e1cc0-136">Puede determinar si se han migrado los contactos de un usuario usando uno de los métodos siguientes:</span><span class="sxs-lookup"><span data-stu-id="e1cc0-136">You can determine whether a user's contacts have been migrated by using either of the following methods:</span></span> 
  
- <span data-ttu-id="e1cc0-137">Compruebe la siguiente clave del registro en el equipo cliente:</span><span class="sxs-lookup"><span data-stu-id="e1cc0-137">Check the following registry key on the client computer:</span></span>
    
    <span data-ttu-id="e1cc0-138">HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\\< dirección URL de SIP\>\UCS</span><span class="sxs-lookup"><span data-stu-id="e1cc0-138">HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\\<SIP URL\>\UCS</span></span>
    
    <span data-ttu-id="e1cc0-139">Si los contactos del usuario se almacenan en Exchange 2013, esta clave contiene un valor de InUCSMode con un valor de 2165.</span><span class="sxs-lookup"><span data-stu-id="e1cc0-139">If the user's contacts are stored in Exchange 2013, this key contains a value of InUCSMode with a value of 2165.</span></span>
    
- <span data-ttu-id="e1cc0-140">Ejecute el cmdlet **Test-CsUnifiedContactStore** .</span><span class="sxs-lookup"><span data-stu-id="e1cc0-140">Run the **Test-CsUnifiedContactStore** cmdlet.</span></span> <span data-ttu-id="e1cc0-141">En Skype para la línea de comandos de Shell de administración de servidor empresarial, escriba:</span><span class="sxs-lookup"><span data-stu-id="e1cc0-141">At the Skype for Business Server Management Shell command line, type:</span></span>
    
  ```
  Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
  ```

    <span data-ttu-id="e1cc0-142">Si **CsUnifiedContactStore de prueba** se realiza correctamente, se han migrado los contactos del usuario al almacén de contactos unificado.</span><span class="sxs-lookup"><span data-stu-id="e1cc0-142">If **Test-CsUnifiedContactStore** succeeds, the user's contacts were migrated to unified contact store.</span></span>
    
## <a name="roll-back-migrated-users"></a><span data-ttu-id="e1cc0-143">Revertir usuarios migrados</span><span class="sxs-lookup"><span data-stu-id="e1cc0-143">Roll Back Migrated Users</span></span>

<span data-ttu-id="e1cc0-144">Si necesita revertir el contacto unificado característica de almacén, revertir los contactos sólo si el usuario se mueve de nuevo a Exchange 2010 o Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e1cc0-144">If you need to roll back the unified contact store feature, roll back the contacts only if you move the user back to Exchange 2010 or Lync Server 2010.</span></span> <span data-ttu-id="e1cc0-145">Para deshacer, deshabilite la directiva para el usuario y, a continuación, ejecute el cmdlet **Invoke-CsUcsRollback** .</span><span class="sxs-lookup"><span data-stu-id="e1cc0-145">To roll back, disable the policy for the user, and then run the **Invoke-CsUcsRollback** cmdlet.</span></span> <span data-ttu-id="e1cc0-146">Ejecución **Invoke-CsUcsRollback** por sí solo no es suficiente para garantizar la restauración permanente, porque el almacén de contactos unificado migración se inicia otra vez si la directiva está deshabilitada no.</span><span class="sxs-lookup"><span data-stu-id="e1cc0-146">Just running **Invoke-CsUcsRollback** alone is not enough to ensure permanent rollback, because unified contact store migration will be initiated again if the policy is not disabled.</span></span> <span data-ttu-id="e1cc0-147">Por ejemplo, si un usuario es deshacer porque Exchange 2013 vuelve a Exchange 2010 y, a continuación, se mueve el buzón del usuario a Exchange de 2013, la migración del almacén de contactos unificada se inicia otra vez siete días después de la restauración, como almacenar contacto unificado todavía está habilitada para el usuario en la directiva de servicios de usuario.</span><span class="sxs-lookup"><span data-stu-id="e1cc0-147">For example, if a user is rolled back because Exchange 2013 is rolled back to Exchange 2010, and then the user's mailbox is moved to Exchange 2013, the unified contact store migration will be initiated again seven days after the rollback, as long as unified contact store is still enabled for the user in the user services policy.</span></span>
  
<span data-ttu-id="e1cc0-148">El cmdlet **Move-CsUser** deshace automáticamente almacén de contactos del usuario de Exchange de 2013 a Skype para Business Server 2015 en las siguientes situaciones:</span><span class="sxs-lookup"><span data-stu-id="e1cc0-148">The **Move-CsUser** cmdlet automatically rolls back the user's contact store from Exchange 2013 to Skype for Business Server 2015 in the following situations:</span></span>
  
- <span data-ttu-id="e1cc0-149">Cuando los usuarios se mueven desde Skype para Business Server 2015 para Microsoft Lync Server 2013 o Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e1cc0-149">When users are moved from Skype for Business Server 2015 to Microsoft Lync Server 2013 or Lync Server 2010.</span></span> 
    
- <span data-ttu-id="e1cc0-150">Cuando los usuarios se migran entre locales, como cuando un usuario se traslada de Skype para los negocios en línea a Skype para Business Server 2015 locales, o viceversa.</span><span class="sxs-lookup"><span data-stu-id="e1cc0-150">When users are migrated cross premises, such as when a user is moved from Skype for Business Online to Skype for Business Server 2015 on-premises, or vice versa.</span></span>
    
<span data-ttu-id="e1cc0-p107">La importación de datos del almacén de contactos unificado desde una base de datos de copia de seguridad puede dañar los datos del almacén de contactos unificado y del usuario si el modo de almacén de contactos unificado cambia entre la exportación y la importación. Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e1cc0-p107">Importing unified contact store data from a backup database can cause unified contact store data and user data to become corrupted if the unified contact store mode changed between the export and the import. For example:</span></span>
  
- <span data-ttu-id="e1cc0-153">Si exporta listas de contactos antes de que los contactos de los usuarios se migran a Exchange 2013 y a continuación, después de la migración, importación los mismos datos, se dañarán los datos de almacén de contactos unificado y listas de contactos.</span><span class="sxs-lookup"><span data-stu-id="e1cc0-153">If you export contact lists before the users' contacts are migrated to Exchange 2013 and then, after the migration, import the same data, the unified contact store data and contact lists will be corrupted.</span></span>
    
- <span data-ttu-id="e1cc0-154">Si exporta datos de usuario después de migrar los usuarios a Exchange 2013, deshacer la migración y luego por algún motivo que importa los datos desde después de la migración, el contacto unificado almacenar datos y listas de contactos se dañará.</span><span class="sxs-lookup"><span data-stu-id="e1cc0-154">If you export user data after you migrate users to Exchange 2013, roll back the migration, and then for some reason you import the data from after the migration, the unified contact store data and contact lists will be corrupted.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="e1cc0-155">Antes de mover un buzón de Exchange de 2013 de Exchange a Exchange 2010, el Administrador de Exchange debe asegurarse de que el Skype para el administrador del servidor de negocios primero revirtió el Skype para los contactos del usuario de Business Server de Exchange 2013 a Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="e1cc0-155">Before you move an Exchange mailbox from Exchange 2013 to Exchange 2010, the Exchange administrator must make sure that the Skype for Business Server administrator has first rolled back the Skype for Business Server user contacts from Exchange 2013 to Skype for Business Server.</span></span> <span data-ttu-id="e1cc0-156">Para restaurar almacén de contactos unificado contactos en Skype para Business Server, consulte procedimiento "para revertir unificado almacén contacto contactos de Exchange de 2013 a Skype for Business Server" más adelante en esta sección.</span><span class="sxs-lookup"><span data-stu-id="e1cc0-156">To roll back unified contact store contacts to Skype for Business Server, see procedure "To roll back unified contact store contacts from Exchange 2013 to Skype for Business Server," later in this section.</span></span> 
  
 <span data-ttu-id="e1cc0-157">**Cómo revertir los contactos del usuario:** Si utiliza el cmdlet **Move-CsUser** para mover usuarios entre Skype para Business Server 2015 y Lync Server 2010, puede omitir estos pasos porque el cmdlet **Move-CsUser** deshace automáticamente almacén de contactos unificada cuando mueve usuarios de Skype para Servidor de negocios 2015 a Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e1cc0-157">**How to roll back user contacts:** If you use the **Move-CsUser** cmdlet to move users between Skype for Business Server 2015 and Lync Server 2010, you can skip these steps because the **Move-CsUser** cmdlet automatically rolls back unified contact store when it moves users from Skype for Business Server 2015 to Lync Server 2010.</span></span> <span data-ttu-id="e1cc0-158">**Mover CsUser** deshabilitar directiva de almacén de contactos unificado, por lo que se repetirá la migración al almacén unificado de contacto si el usuario se mueve al Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="e1cc0-158">**Move-CsUser** does not disable unified contact store policy, so the migration to unified contact store will recur if the user is moved back to Skype for Business Server 2015.</span></span>
  

