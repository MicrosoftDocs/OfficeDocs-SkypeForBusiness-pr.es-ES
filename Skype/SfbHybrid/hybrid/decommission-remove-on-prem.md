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
ms.openlocfilehash: e96c4cd37d09fc62fbfbe34a8b8d61c79ea08289
ms.sourcegitcommit: 405b22cfd94e50d651f4c3f73fb46780cd8a6d06
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454343"
---
# <a name="remove-your-on-premises-skype-for-business-deployment"></a><span data-ttu-id="48068-103">Eliminar la implementación local de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="48068-103">Remove your on-premises Skype for Business deployment</span></span>

<span data-ttu-id="48068-104">En este artículo se describe cómo quitar la implementación Skype Empresarial local.</span><span class="sxs-lookup"><span data-stu-id="48068-104">This article describes how to remove your on-premises Skype for Business deployment.</span></span> <span data-ttu-id="48068-105">Este es el paso 4 de los siguientes pasos para retirar el entorno local:</span><span class="sxs-lookup"><span data-stu-id="48068-105">This is step 4 of the following steps to decommission your on-premises environment:</span></span>

- <span data-ttu-id="48068-106">Paso 1.</span><span class="sxs-lookup"><span data-stu-id="48068-106">Step 1.</span></span> <span data-ttu-id="48068-107">[Mueva todos los usuarios necesarios de local a en línea.](decommission-move-on-prem-users.md)</span><span class="sxs-lookup"><span data-stu-id="48068-107">[Move all required users from on-premises to online](decommission-move-on-prem-users.md).</span></span> 

- <span data-ttu-id="48068-108">Paso 2.</span><span class="sxs-lookup"><span data-stu-id="48068-108">Step 2.</span></span> <span data-ttu-id="48068-109">[Deshabilite la configuración híbrida](cloud-consolidation-disabling-hybrid.md).</span><span class="sxs-lookup"><span data-stu-id="48068-109">[Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

- <span data-ttu-id="48068-110">Paso 3.</span><span class="sxs-lookup"><span data-stu-id="48068-110">Step 3.</span></span> [<span data-ttu-id="48068-111">Migrar puntos de conexión de aplicaciones híbridas de local a online</span><span class="sxs-lookup"><span data-stu-id="48068-111">Migrate hybrid application endpoints from on-premises to online</span></span>](decommission-move-on-prem-endpoints.md)

- <span data-ttu-id="48068-112">**Paso 4. Quite la implementación Skype Empresarial local.**</span><span class="sxs-lookup"><span data-stu-id="48068-112">**Step 4. Remove your on-premises Skype for Business deployment.**</span></span> <span data-ttu-id="48068-113">(Este artículo)</span><span class="sxs-lookup"><span data-stu-id="48068-113">(This article)</span></span>


> [!IMPORTANT] 
> <span data-ttu-id="48068-114">Los pasos de este artículo solo se aplican si usa el método 2 para administrar atributos de usuario, como se describe [aquí](cloud-consolidation-managing-attributes.md#method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory).</span><span class="sxs-lookup"><span data-stu-id="48068-114">The steps in this article apply only if you are using Method 2 for managing user attributes, as described [here](cloud-consolidation-managing-attributes.md#method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory).</span></span> <span data-ttu-id="48068-115">Si usa el método 1, no use los pasos descritos en este artículo para quitar los Skype Empresarial servidores.</span><span class="sxs-lookup"><span data-stu-id="48068-115">If you are using Method 1, do not use the steps described in this article to remove your Skype for Business servers.</span></span> <span data-ttu-id="48068-116">En su lugar, puede volver a crear una imagen de los servidores.</span><span class="sxs-lookup"><span data-stu-id="48068-116">Instead, you can re-image the servers.</span></span>

<span data-ttu-id="48068-117">Para completar los pasos de este artículo, necesita privilegios tanto para el grupo Administradores de esquema como para el grupo Enterprise administración.</span><span class="sxs-lookup"><span data-stu-id="48068-117">To complete the steps in this article, you need privileges for both the Schema Admins group and the Enterprise Admin group.</span></span> <span data-ttu-id="48068-118">Necesitará estos privilegios para deshacer el esquema Skype Empresarial Server y los cambios de nivel de bosque en los Servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="48068-118">You will need these privileges to undo the Skype for Business Server schema and forest-level changes to Active Directory Domain Services.</span></span> <span data-ttu-id="48068-119">También tendrá que ser miembro del grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="48068-119">You will also need to be a member of the RTCUniversalServerAdmins group.</span></span>


## <a name="prepare-to-remove-the-skype-for-business-deployment"></a><span data-ttu-id="48068-120">Prepararse para quitar la Skype Empresarial implementación</span><span class="sxs-lookup"><span data-stu-id="48068-120">Prepare to remove the Skype for Business deployment</span></span>

<span data-ttu-id="48068-121">Después de mover todas las cuentas de usuario necesarias a la nube, es posible que aún haya algunos objetos locales restantes, como contactos y aplicaciones, que necesitará limpiar.</span><span class="sxs-lookup"><span data-stu-id="48068-121">After you move all required user accounts to the cloud, there may still be some remaining on-premises objects such as contacts and applications that you will need clean up.</span></span>

<span data-ttu-id="48068-122">Siga los pasos siguientes para limpiar estos objetos y asegúrese de que es miembro del grupo Administrador local y del grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="48068-122">Use the steps below to clean these objects, and make sure you are a member of both the Local Administrator group and the RTCUniversalServerAdmins group.</span></span> <span data-ttu-id="48068-123">Tenga en cuenta que ExUmContacts y PersistantChatEndPoints no están disponibles en Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="48068-123">Note that ExUmContacts and PersistantChatEndPoints are not available in Skype for Business Server 2019.</span></span> <span data-ttu-id="48068-124">Si ha Skype Empresarial Server 2019, se deben omitir los cmdlets correspondientes en los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="48068-124">If you have Skype for Business Server 2019, the corresponding cmdlets in the steps below should be omitted.</span></span>

1. <span data-ttu-id="48068-125">Para comprobar si hay contactos o aplicaciones asociados con la implementación Skype Empresarial Server local, ejecute los siguientes cmdlets Skype Empresarial Server PowerShell.</span><span class="sxs-lookup"><span data-stu-id="48068-125">To check if there are any contacts or applications associated with the Skype for Business Server on-premises deployment, run the following Skype for Business Server PowerShell cmdlets.</span></span>

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
2. <span data-ttu-id="48068-126">Revise las listas de resultados de los cmdlets del paso 1.</span><span class="sxs-lookup"><span data-stu-id="48068-126">Review the output lists from the cmdlets in Step 1.</span></span> <span data-ttu-id="48068-127">A continuación, si se pueden quitar objetos, ejecute los siguientes cmdlets Skype Empresarial Server PowerShell:</span><span class="sxs-lookup"><span data-stu-id="48068-127">Then if objects can be removed, run the following Skype for Business Server PowerShell cmdlets:</span></span>

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
## <a name="remove-your-on-premises-skype-for-business-deployment"></a><span data-ttu-id="48068-128">Eliminar la implementación local de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="48068-128">Remove your on-premises Skype for Business deployment</span></span>

<span data-ttu-id="48068-129">Después de completar todos los pasos preliminares, puede quitar la Skype Empresarial implementación siguiendo estos pasos:</span><span class="sxs-lookup"><span data-stu-id="48068-129">After completing all the preliminary steps, you can remove the Skype for Business deployment by following these steps:</span></span>

1. <span data-ttu-id="48068-130">Quite lógicamente la implementación Skype Empresarial Server, excepto para un único front-end, como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="48068-130">Logically remove the Skype for Business Server deployment, except for a single front end, as follows:</span></span>

   1. <span data-ttu-id="48068-131">Actualice su Skype Empresarial Server topología para que tenga un único grupo de servidores front-end:</span><span class="sxs-lookup"><span data-stu-id="48068-131">Update your Skype for Business Server topology to have a single front-end pool:</span></span>

      1. <span data-ttu-id="48068-132">En el Generador de topologías, descargue una nueva copia y vaya al grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="48068-132">In Topology Builder, download a new copy and navigate to the Frontend pool.</span></span>
      1. <span data-ttu-id="48068-133">Haga clic con el botón secundario en el grupo y, a continuación, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="48068-133">Right-click the pool, and then click **Edit Properties**.</span></span>
      1. <span data-ttu-id="48068-134">En **Asociaciones**, desactive **Asociar grupo perimetral** (para componentes multimedia) y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="48068-134">In **Associations**, uncheck **Associate Edge Pool** (for media components) and click **OK**.</span></span>
      1. <span data-ttu-id="48068-135">Si hay más de un grupo de servidores front-end, quite las asociaciones de todos los grupos restantes.</span><span class="sxs-lookup"><span data-stu-id="48068-135">If there is more than one Frontend Pool, remove Associations for all remaining pools.</span></span>
      1. <span data-ttu-id="48068-136">Seleccione **Acción > Quitar implementación**.</span><span class="sxs-lookup"><span data-stu-id="48068-136">Select **Action > Remove Deployment**.</span></span>
      1. <span data-ttu-id="48068-137">Seleccione **Acción > Publicar topología**.</span><span class="sxs-lookup"><span data-stu-id="48068-137">Select **Action > Publish Topology**.</span></span>

    1. <span data-ttu-id="48068-138">Después de publicar la topología, complete los pasos adicionales descritos en el asistente.</span><span class="sxs-lookup"><span data-stu-id="48068-138">After publishing the topology, complete the additional steps described in the wizard.</span></span>

2. <span data-ttu-id="48068-139">Quite Skype Empresarial Server directorios de conferencia ejecutando el siguiente cmdlet Skype Empresarial Server PowerShell:</span><span class="sxs-lookup"><span data-stu-id="48068-139">Remove Skype for Business Server conference directories by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Get-CsConferenceDirectory | Remove-CsConferenceDirectory -Force
   ```

3. <span data-ttu-id="48068-140">Para finalizar la desinstalación de la Skype Empresarial Server implementación, ejecute el siguiente cmdlet Skype Empresarial Server PowerShell:</span><span class="sxs-lookup"><span data-stu-id="48068-140">Finalize the uninstall of your Skype for Business Server deployment by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Publish-CsTopology -FinalizeUninstall
   ```
   > [!NOTE]
   > <span data-ttu-id="48068-141">Si este paso devuelve un error, abra un vale de soporte técnico de Microsoft para obtener ayuda para quitar los objetos obsoletos restantes.</span><span class="sxs-lookup"><span data-stu-id="48068-141">If this step returns an error, please open a Microsoft support ticket to get help removing the remaining stale objects.</span></span>

4. <span data-ttu-id="48068-142">Quite el punto de control del servicio del almacén de administración central ejecutando el siguiente cmdlet Skype Empresarial Server PowerShell:</span><span class="sxs-lookup"><span data-stu-id="48068-142">Remove Central Management Store Service Control Point by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Remove-CsConfigurationStoreLocation
   ``` 

5. <span data-ttu-id="48068-143">Para deshacer Skype Empresarial Server de dominio de Active Directory, ejecute el siguiente cmdlet Skype Empresarial Server PowerShell:</span><span class="sxs-lookup"><span data-stu-id="48068-143">Undo Skype for Business Server Active Directory domain-level changes by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Disable-CsAdDomain
   ```
6. <span data-ttu-id="48068-144">Deshaz Skype Empresarial Server cambios en el nivel de bosque de Active Directory ejecutando el siguiente cmdlet Skype Empresarial Server PowerShell:</span><span class="sxs-lookup"><span data-stu-id="48068-144">Undo Skype for Business Server Active Directory forest-level changes by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Disable-CsAdForest
   ```

## <a name="see-also"></a><span data-ttu-id="48068-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="48068-145">See also</span></span>

- [<span data-ttu-id="48068-146">Retirar el entorno local de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="48068-146">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)

- [<span data-ttu-id="48068-147">Mover todos los usuarios necesarios de local a online</span><span class="sxs-lookup"><span data-stu-id="48068-147">Move all required users from on-premises to online</span></span>](decommission-move-on-prem-users.md)

- [<span data-ttu-id="48068-148">Deshabilitar la configuración híbrida</span><span class="sxs-lookup"><span data-stu-id="48068-148">Disable your hybrid configuration</span></span>](cloud-consolidation-disabling-hybrid.md)

- [<span data-ttu-id="48068-149">Mover puntos de conexión de aplicaciones híbridas de local a online</span><span class="sxs-lookup"><span data-stu-id="48068-149">Move hybrid application endpoints from on-premises to online</span></span>](decommission-move-on-prem-endpoints.md)

