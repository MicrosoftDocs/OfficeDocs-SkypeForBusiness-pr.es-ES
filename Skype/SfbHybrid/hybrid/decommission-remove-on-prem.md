---
title: Retirar Skype Empresarial Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Instrucciones para retirar Skype Empresarial Server.
ms.openlocfilehash: 668e3d5ebf5dfa03fcfb883adcc3e08fc5924bae
ms.sourcegitcommit: f223b5f3735f165d46bb611a52fcdfb0f4b88f66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/06/2021
ms.locfileid: "51593904"
---
# <a name="remove-your-on-premises-skype-for-business-deployment"></a><span data-ttu-id="8f532-103">Quitar la implementación local de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="8f532-103">Remove your on-premises Skype for Business deployment</span></span>

<span data-ttu-id="8f532-104">En este artículo se describe cómo quitar la implementación local de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="8f532-104">This article describes how to remove your on-premises Skype for Business deployment.</span></span> <span data-ttu-id="8f532-105">Este es el paso 3 de los siguientes pasos para retirar el entorno local:</span><span class="sxs-lookup"><span data-stu-id="8f532-105">This is step 3 of the following steps to decommission your on-premises environment:</span></span>

- <span data-ttu-id="8f532-106">Paso 1.</span><span class="sxs-lookup"><span data-stu-id="8f532-106">Step 1.</span></span> <span data-ttu-id="8f532-107">[Mueva todos los usuarios y extremos de aplicación necesarios de local a en línea.](decommission-move-on-prem-users.md)</span><span class="sxs-lookup"><span data-stu-id="8f532-107">[Move all required users and application endpoints from on-premises to online](decommission-move-on-prem-users.md).</span></span> 

- <span data-ttu-id="8f532-108">Paso 2.</span><span class="sxs-lookup"><span data-stu-id="8f532-108">Step 2.</span></span> <span data-ttu-id="8f532-109">[Deshabilite la configuración híbrida](cloud-consolidation-disabling-hybrid.md).</span><span class="sxs-lookup"><span data-stu-id="8f532-109">[Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

- <span data-ttu-id="8f532-110">**Paso 3. Quite la implementación local de Skype Empresarial.**</span><span class="sxs-lookup"><span data-stu-id="8f532-110">**Step 3. Remove your on-premises Skype for Business deployment.**</span></span> <span data-ttu-id="8f532-111">(Este artículo)</span><span class="sxs-lookup"><span data-stu-id="8f532-111">(This article)</span></span>


> [!IMPORTANT] 
> <span data-ttu-id="8f532-112">Los pasos de este artículo solo se aplican si usa el método 2 para administrar atributos de usuario, como se describe [aquí](cloud-consolidation-disabling-hybrid.md#method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory).</span><span class="sxs-lookup"><span data-stu-id="8f532-112">The steps in this article apply only if you are using Method 2 for managing user attributes, as described [here](cloud-consolidation-disabling-hybrid.md#method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory).</span></span> <span data-ttu-id="8f532-113">Si usa el método 1, no use los pasos descritos en este artículo para quitar los servidores de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="8f532-113">If you are using Method 1, do not use the steps described in this article to remove your Skype for Business servers.</span></span> <span data-ttu-id="8f532-114">En su lugar, puede volver a crear una imagen de los servidores.</span><span class="sxs-lookup"><span data-stu-id="8f532-114">Instead, you can re-image the servers.</span></span>

<span data-ttu-id="8f532-115">Para completar los pasos de este artículo, necesita privilegios tanto para el grupo Administradores de esquema como para el grupo Administración de empresa.</span><span class="sxs-lookup"><span data-stu-id="8f532-115">To complete the steps in this article, you need privileges for both the Schema Admins group and the Enterprise Admin group.</span></span> <span data-ttu-id="8f532-116">Necesitará estos privilegios para deshacer el esquema de Skype Empresarial Server y los cambios de nivel de bosque en los Servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="8f532-116">You will need these privileges to undo the Skype for Business Server schema and forest-level changes to Active Directory Domain Services.</span></span> <span data-ttu-id="8f532-117">También tendrá que ser miembro del grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="8f532-117">You will also need to be a member of the RTCUniversalServerAdmins group.</span></span>


## <a name="prepare-to-remove-the-skype-for-business-deployment"></a><span data-ttu-id="8f532-118">Prepararse para quitar la implementación de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="8f532-118">Prepare to remove the Skype for Business deployment</span></span>

<span data-ttu-id="8f532-119">Después de mover todas las cuentas de usuario necesarias a la nube, es posible que aún haya algunos objetos locales restantes, como contactos y aplicaciones, que necesitará limpiar.</span><span class="sxs-lookup"><span data-stu-id="8f532-119">After you move all required user accounts to the cloud, there may still be some remaining on-premises objects such as contacts and applications that you will need clean up.</span></span>

<span data-ttu-id="8f532-120">Siga los pasos siguientes para limpiar estos objetos y asegúrese de que es miembro del grupo Administrador local y del grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="8f532-120">Use the steps below to clean these objects, and make sure you are a member of both the Local Administrator group and the RTCUniversalServerAdmins group.</span></span> <span data-ttu-id="8f532-121">Tenga en cuenta que ExUmContacts y PersistantChatEndPoints no están disponibles en Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="8f532-121">Note that ExUmContacts and PersistantChatEndPoints are not available in Skype for Business Server 2019.</span></span> <span data-ttu-id="8f532-122">Si tiene Skype Empresarial Server 2019, se deben omitir los cmdlets correspondientes en los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="8f532-122">If you have Skype for Business Server 2019, the corresponding cmdlets in the steps below should be omitted.</span></span>

1. <span data-ttu-id="8f532-123">Para comprobar si hay contactos o aplicaciones asociados con la implementación local de Skype Empresarial Server, ejecute los siguientes cmdlets de PowerShell de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="8f532-123">To check if there are any contacts or applications associated with the Skype for Business Server on-premises deployment, run the following Skype for Business Server PowerShell cmdlets.</span></span>

   ```PowerShell
   Get-CsMeetingRoom
   Get-CsCommonAreaPhone
   Get-CsAnalogDevice
   Get-CsExUmContact
   Get-CsDialInConferencingAccessNumber
   Get-CsRgsWorkflow
   Get-CsTrustedApplicationEndpoint
   Get-CsTrustedApplication
   Get-CsPersistentChatEndpoint
   Get-CsAudioTestServiceApplication
   Get-CsCallParkOrbit
   ```
2. <span data-ttu-id="8f532-124">Revise las listas de resultados de los cmdlets del paso 1.</span><span class="sxs-lookup"><span data-stu-id="8f532-124">Review the output lists from the cmdlets in Step 1.</span></span> <span data-ttu-id="8f532-125">A continuación, si se pueden quitar objetos, ejecute los siguientes cmdlets de PowerShell de Skype Empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="8f532-125">Then if objects can be removed, run the following Skype for Business Server PowerShell cmdlets:</span></span>

   ```PowerShell
   Get-CsMeetingRoom | Disable-CsMeetingRoom
   Get-CsCommonAreaPhone | Remove-CsCommonAreaPhone 
   Get-CsAnalogDevice | Remove-CsAnalogDevice
   Get-CsExUmContact | Remove-CsExUmContact
   Get-CsDialInConferencingAccessNumber | Remove-CsDialInConferencingAccessNumber
   Get-CsRgsWorkflow | Remove-CsRgsWorkflow
   Get-CsTrustedApplicationEndpoint | Remove-CsTrustedApplicationEndpoint
   Get-CsTrustedApplication | Remove-CsTrustedApplication -Force
   Get-CsPersistentChatEndpoint |  Remove-CsPersistentChatEndpoint
   Get-CsCallParkOrbit | Remove-CsCallParkOrbit -Force
   Get-CsVoiceRoute | Remove-CsVoiceRoute -Force
   ```
## <a name="remove-your-on-premises-skype-for-business-deployment"></a><span data-ttu-id="8f532-126">Quitar la implementación local de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="8f532-126">Remove your on-premises Skype for Business deployment</span></span>

<span data-ttu-id="8f532-127">Después de completar todos los pasos preliminares, puede quitar la implementación de Skype Empresarial siguiendo estos pasos:</span><span class="sxs-lookup"><span data-stu-id="8f532-127">After completing all the preliminary steps, you can remove the Skype for Business deployment by following these steps:</span></span>

1. <span data-ttu-id="8f532-128">Quite lógicamente la implementación de Skype Empresarial Server, excepto para un único front-end, como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="8f532-128">Logically remove the Skype for Business Server deployment, except for a single front end, as follows:</span></span>

   <span data-ttu-id="8f532-129">a.</span><span class="sxs-lookup"><span data-stu-id="8f532-129">a.</span></span> <span data-ttu-id="8f532-130">Actualice la topología de Skype Empresarial Server para que tenga un único grupo de servidores front-end:</span><span class="sxs-lookup"><span data-stu-id="8f532-130">Update your Skype for Business Server topology to have a single front-end pool:</span></span>

     - <span data-ttu-id="8f532-131">En el Generador de topologías, descargue una nueva copia y vaya al grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="8f532-131">In Topology Builder, download a new copy and navigate to the Frontend pool.</span></span>
     - <span data-ttu-id="8f532-132">Haga clic con el botón secundario en el grupo y, a continuación, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="8f532-132">Right-click the pool, and then click **Edit Properties**.</span></span>
     - <span data-ttu-id="8f532-133">En **Asociaciones**, desactive **Asociar grupo perimetral** (para componentes multimedia) y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8f532-133">In **Associations**, uncheck **Associate Edge Pool** (for media components) and click **OK**.</span></span>
     - <span data-ttu-id="8f532-134">Si hay más de un grupo de servidores front-end, quite las asociaciones de todos los grupos restantes.</span><span class="sxs-lookup"><span data-stu-id="8f532-134">If there is more than one Frontend Pool, remove Associations for all remaining pools.</span></span>
     - <span data-ttu-id="8f532-135">Seleccione **Acción > Quitar implementación**.</span><span class="sxs-lookup"><span data-stu-id="8f532-135">Select **Action > Remove Deployment**.</span></span>
     - <span data-ttu-id="8f532-136">Seleccione **Acción > Publicar topología**.</span><span class="sxs-lookup"><span data-stu-id="8f532-136">Select **Action > Publish Topology**.</span></span>

    <span data-ttu-id="8f532-137">b.</span><span class="sxs-lookup"><span data-stu-id="8f532-137">b.</span></span> <span data-ttu-id="8f532-138">Después de publicar la topología, complete los pasos adicionales descritos en el asistente.</span><span class="sxs-lookup"><span data-stu-id="8f532-138">After publishing the topology, complete the additional steps described in the wizard.</span></span>

2. <span data-ttu-id="8f532-139">Quite los directorios de conferencia de Skype Empresarial Server ejecutando el siguiente cmdlet de PowerShell de Skype Empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="8f532-139">Remove Skype for Business Server conference directories by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Get-CsConferenceDirectory | Remove-CsConferenceDirectory -Force
   ```

3. <span data-ttu-id="8f532-140">Para finalizar la desinstalación de la implementación de Skype Empresarial Server, ejecute el siguiente cmdlet de PowerShell de Skype Empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="8f532-140">Finalize the uninstall of your Skype for Business Server deployment by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Publish-CsTopology -FinalizeUninstall
   ```
   > [!NOTE]
   > <span data-ttu-id="8f532-141">Si este paso devuelve un error, abra un vale de soporte técnico de Microsoft para obtener ayuda para quitar los objetos obsoletos restantes.</span><span class="sxs-lookup"><span data-stu-id="8f532-141">If this step returns an error, please open a Microsoft support ticket to get help removing the remaining stale objects.</span></span>

4. <span data-ttu-id="8f532-142">Para quitar el punto de control de servicio del Almacén de administración central, ejecute el siguiente cmdlet de PowerShell de Skype Empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="8f532-142">Remove Central Management Store Service Control Point by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Remove-CsConfigurationStoreLocation
   ``` 

5. <span data-ttu-id="8f532-143">Deshacer los cambios en el nivel de bosque de dominio de Skype Empresarial Server Active Directory ejecutando el siguiente cmdlet de PowerShell de Skype Empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="8f532-143">Undo Skype for Business Server Active Directory Domain forest-level changes by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Disable-CsAdDomain
   ```
6. <span data-ttu-id="8f532-144">Deshacer los cambios de esquema de dominio de Skype Empresarial Server Active Directory ejecutando el siguiente cmdlet de PowerShell de Skype Empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="8f532-144">Undo Skype for Business Server Active Directory Domain schema changes by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Disable-CsAdForest
   ```

## <a name="see-also"></a><span data-ttu-id="8f532-145">Ver también</span><span class="sxs-lookup"><span data-stu-id="8f532-145">See also</span></span>

- [<span data-ttu-id="8f532-146">Retirar el entorno local de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="8f532-146">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)

- [<span data-ttu-id="8f532-147">Mover usuarios y puntos de conexión a la nube</span><span class="sxs-lookup"><span data-stu-id="8f532-147">Move user and endpoints to the cloud</span></span>](decommission-move-on-prem-users.md)

- [<span data-ttu-id="8f532-148">Deshabilitar la configuración híbrida</span><span class="sxs-lookup"><span data-stu-id="8f532-148">Disable your hybrid configuration</span></span>](cloud-consolidation-disabling-hybrid.md)














