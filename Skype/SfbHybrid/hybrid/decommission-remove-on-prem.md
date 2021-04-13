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
ms.openlocfilehash: 9c6051a07fc05297985b3692351c36791d8842bb
ms.sourcegitcommit: 71d90f0a0056f7604109f64e9722c80cf0eda47d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2021
ms.locfileid: "51656696"
---
# <a name="remove-your-on-premises-skype-for-business-deployment"></a><span data-ttu-id="a66ac-103">Eliminar la implementación local de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="a66ac-103">Remove your on-premises Skype for Business deployment</span></span>

<span data-ttu-id="a66ac-104">En este artículo se describe cómo quitar la implementación local de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="a66ac-104">This article describes how to remove your on-premises Skype for Business deployment.</span></span> <span data-ttu-id="a66ac-105">Este es el paso 4 de los siguientes pasos para retirar el entorno local:</span><span class="sxs-lookup"><span data-stu-id="a66ac-105">This is step 4 of the following steps to decommission your on-premises environment:</span></span>

- <span data-ttu-id="a66ac-106">Paso 1.</span><span class="sxs-lookup"><span data-stu-id="a66ac-106">Step 1.</span></span> <span data-ttu-id="a66ac-107">[Mueva todos los usuarios necesarios de local a en línea.](decommission-move-on-prem-users.md)</span><span class="sxs-lookup"><span data-stu-id="a66ac-107">[Move all required users from on-premises to online](decommission-move-on-prem-users.md).</span></span> 

- <span data-ttu-id="a66ac-108">Paso 2.</span><span class="sxs-lookup"><span data-stu-id="a66ac-108">Step 2.</span></span> <span data-ttu-id="a66ac-109">[Deshabilite la configuración híbrida](cloud-consolidation-disabling-hybrid.md).</span><span class="sxs-lookup"><span data-stu-id="a66ac-109">[Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

- <span data-ttu-id="a66ac-110">Paso 3.</span><span class="sxs-lookup"><span data-stu-id="a66ac-110">Step 3.</span></span> [<span data-ttu-id="a66ac-111">Mover puntos de conexión de aplicaciones híbridas de local a online</span><span class="sxs-lookup"><span data-stu-id="a66ac-111">Move hybrid application endpoints from on-premises to online</span></span>](decommission-move-on-prem-endpoints.md)

- <span data-ttu-id="a66ac-112">**Paso 4. Quite la implementación local de Skype Empresarial.**</span><span class="sxs-lookup"><span data-stu-id="a66ac-112">**Step 4. Remove your on-premises Skype for Business deployment.**</span></span> <span data-ttu-id="a66ac-113">(Este artículo)</span><span class="sxs-lookup"><span data-stu-id="a66ac-113">(This article)</span></span>


> [!IMPORTANT] 
> <span data-ttu-id="a66ac-114">Los pasos de este artículo solo se aplican si usa el método 2 para administrar atributos de usuario, como se describe [aquí](cloud-consolidation-disabling-hybrid.md#method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory).</span><span class="sxs-lookup"><span data-stu-id="a66ac-114">The steps in this article apply only if you are using Method 2 for managing user attributes, as described [here](cloud-consolidation-disabling-hybrid.md#method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory).</span></span> <span data-ttu-id="a66ac-115">Si usa el método 1, no use los pasos descritos en este artículo para quitar los servidores de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="a66ac-115">If you are using Method 1, do not use the steps described in this article to remove your Skype for Business servers.</span></span> <span data-ttu-id="a66ac-116">En su lugar, puede volver a crear una imagen de los servidores.</span><span class="sxs-lookup"><span data-stu-id="a66ac-116">Instead, you can re-image the servers.</span></span>

<span data-ttu-id="a66ac-117">Para completar los pasos de este artículo, necesita privilegios tanto para el grupo Administradores de esquema como para el grupo Administración de empresa.</span><span class="sxs-lookup"><span data-stu-id="a66ac-117">To complete the steps in this article, you need privileges for both the Schema Admins group and the Enterprise Admin group.</span></span> <span data-ttu-id="a66ac-118">Necesitará estos privilegios para deshacer el esquema de Skype Empresarial Server y los cambios de nivel de bosque en los Servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a66ac-118">You will need these privileges to undo the Skype for Business Server schema and forest-level changes to Active Directory Domain Services.</span></span> <span data-ttu-id="a66ac-119">También tendrá que ser miembro del grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="a66ac-119">You will also need to be a member of the RTCUniversalServerAdmins group.</span></span>


## <a name="prepare-to-remove-the-skype-for-business-deployment"></a><span data-ttu-id="a66ac-120">Prepararse para quitar la implementación de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="a66ac-120">Prepare to remove the Skype for Business deployment</span></span>

<span data-ttu-id="a66ac-121">Después de mover todas las cuentas de usuario necesarias a la nube, es posible que aún haya algunos objetos locales restantes, como contactos y aplicaciones, que necesitará limpiar.</span><span class="sxs-lookup"><span data-stu-id="a66ac-121">After you move all required user accounts to the cloud, there may still be some remaining on-premises objects such as contacts and applications that you will need clean up.</span></span>

<span data-ttu-id="a66ac-122">Siga los pasos siguientes para limpiar estos objetos y asegúrese de que es miembro del grupo Administrador local y del grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="a66ac-122">Use the steps below to clean these objects, and make sure you are a member of both the Local Administrator group and the RTCUniversalServerAdmins group.</span></span> <span data-ttu-id="a66ac-123">Tenga en cuenta que ExUmContacts y PersistantChatEndPoints no están disponibles en Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="a66ac-123">Note that ExUmContacts and PersistantChatEndPoints are not available in Skype for Business Server 2019.</span></span> <span data-ttu-id="a66ac-124">Si tiene Skype Empresarial Server 2019, se deben omitir los cmdlets correspondientes en los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="a66ac-124">If you have Skype for Business Server 2019, the corresponding cmdlets in the steps below should be omitted.</span></span>

1. <span data-ttu-id="a66ac-125">Para comprobar si hay contactos o aplicaciones asociados con la implementación local de Skype Empresarial Server, ejecute los siguientes cmdlets de PowerShell de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="a66ac-125">To check if there are any contacts or applications associated with the Skype for Business Server on-premises deployment, run the following Skype for Business Server PowerShell cmdlets.</span></span>

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
2. <span data-ttu-id="a66ac-126">Revise las listas de resultados de los cmdlets del paso 1.</span><span class="sxs-lookup"><span data-stu-id="a66ac-126">Review the output lists from the cmdlets in Step 1.</span></span> <span data-ttu-id="a66ac-127">A continuación, si se pueden quitar objetos, ejecute los siguientes cmdlets de PowerShell de Skype Empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="a66ac-127">Then if objects can be removed, run the following Skype for Business Server PowerShell cmdlets:</span></span>

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
## <a name="remove-your-on-premises-skype-for-business-deployment"></a><span data-ttu-id="a66ac-128">Eliminar la implementación local de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="a66ac-128">Remove your on-premises Skype for Business deployment</span></span>

<span data-ttu-id="a66ac-129">Después de completar todos los pasos preliminares, puede quitar la implementación de Skype Empresarial siguiendo estos pasos:</span><span class="sxs-lookup"><span data-stu-id="a66ac-129">After completing all the preliminary steps, you can remove the Skype for Business deployment by following these steps:</span></span>

1. <span data-ttu-id="a66ac-130">Quite lógicamente la implementación de Skype Empresarial Server, excepto para un único front-end, como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="a66ac-130">Logically remove the Skype for Business Server deployment, except for a single front end, as follows:</span></span>

   <span data-ttu-id="a66ac-131">a.</span><span class="sxs-lookup"><span data-stu-id="a66ac-131">a.</span></span> <span data-ttu-id="a66ac-132">Actualice la topología de Skype Empresarial Server para que tenga un único grupo de servidores front-end:</span><span class="sxs-lookup"><span data-stu-id="a66ac-132">Update your Skype for Business Server topology to have a single front-end pool:</span></span>

     - <span data-ttu-id="a66ac-133">En el Generador de topologías, descargue una nueva copia y vaya al grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="a66ac-133">In Topology Builder, download a new copy and navigate to the Frontend pool.</span></span>
     - <span data-ttu-id="a66ac-134">Haga clic con el botón secundario en el grupo y, a continuación, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="a66ac-134">Right-click the pool, and then click **Edit Properties**.</span></span>
     - <span data-ttu-id="a66ac-135">En **Asociaciones**, desactive **Asociar grupo perimetral** (para componentes multimedia) y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a66ac-135">In **Associations**, uncheck **Associate Edge Pool** (for media components) and click **OK**.</span></span>
     - <span data-ttu-id="a66ac-136">Si hay más de un grupo de servidores front-end, quite las asociaciones de todos los grupos restantes.</span><span class="sxs-lookup"><span data-stu-id="a66ac-136">If there is more than one Frontend Pool, remove Associations for all remaining pools.</span></span>
     - <span data-ttu-id="a66ac-137">Seleccione **Acción > Quitar implementación**.</span><span class="sxs-lookup"><span data-stu-id="a66ac-137">Select **Action > Remove Deployment**.</span></span>
     - <span data-ttu-id="a66ac-138">Seleccione **Acción > Publicar topología**.</span><span class="sxs-lookup"><span data-stu-id="a66ac-138">Select **Action > Publish Topology**.</span></span>

    <span data-ttu-id="a66ac-139">b.</span><span class="sxs-lookup"><span data-stu-id="a66ac-139">b.</span></span> <span data-ttu-id="a66ac-140">Después de publicar la topología, complete los pasos adicionales descritos en el asistente.</span><span class="sxs-lookup"><span data-stu-id="a66ac-140">After publishing the topology, complete the additional steps described in the wizard.</span></span>

2. <span data-ttu-id="a66ac-141">Quite los directorios de conferencia de Skype Empresarial Server ejecutando el siguiente cmdlet de PowerShell de Skype Empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="a66ac-141">Remove Skype for Business Server conference directories by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Get-CsConferenceDirectory | Remove-CsConferenceDirectory -Force
   ```

3. <span data-ttu-id="a66ac-142">Para finalizar la desinstalación de la implementación de Skype Empresarial Server, ejecute el siguiente cmdlet de PowerShell de Skype Empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="a66ac-142">Finalize the uninstall of your Skype for Business Server deployment by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Publish-CsTopology -FinalizeUninstall
   ```
   > [!NOTE]
   > <span data-ttu-id="a66ac-143">Si este paso devuelve un error, abra un vale de soporte técnico de Microsoft para obtener ayuda para quitar los objetos obsoletos restantes.</span><span class="sxs-lookup"><span data-stu-id="a66ac-143">If this step returns an error, please open a Microsoft support ticket to get help removing the remaining stale objects.</span></span>

4. <span data-ttu-id="a66ac-144">Para quitar el punto de control de servicio del Almacén de administración central, ejecute el siguiente cmdlet de PowerShell de Skype Empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="a66ac-144">Remove Central Management Store Service Control Point by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Remove-CsConfigurationStoreLocation
   ``` 

5. <span data-ttu-id="a66ac-145">Deshacer los cambios en el nivel de bosque de dominio de Skype Empresarial Server Active Directory ejecutando el siguiente cmdlet de PowerShell de Skype Empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="a66ac-145">Undo Skype for Business Server Active Directory Domain forest-level changes by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Disable-CsAdDomain
   ```
6. <span data-ttu-id="a66ac-146">Deshacer los cambios de esquema de dominio de Skype Empresarial Server Active Directory ejecutando el siguiente cmdlet de PowerShell de Skype Empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="a66ac-146">Undo Skype for Business Server Active Directory Domain schema changes by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Disable-CsAdForest
   ```

## <a name="see-also"></a><span data-ttu-id="a66ac-147">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="a66ac-147">See also</span></span>

- [<span data-ttu-id="a66ac-148">Retirar el entorno local de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="a66ac-148">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)

- [<span data-ttu-id="a66ac-149">Mover todos los usuarios necesarios de local a online</span><span class="sxs-lookup"><span data-stu-id="a66ac-149">Move all required users from on-premises to online</span></span>](decommission-move-on-prem-users.md)

- [<span data-ttu-id="a66ac-150">Deshabilitar la configuración híbrida</span><span class="sxs-lookup"><span data-stu-id="a66ac-150">Disable your hybrid configuration</span></span>](cloud-consolidation-disabling-hybrid.md)

- [<span data-ttu-id="a66ac-151">Mover puntos de conexión de aplicaciones híbridas de local a online</span><span class="sxs-lookup"><span data-stu-id="a66ac-151">Move hybrid application endpoints from on-premises to online</span></span>](decommission-move-on-prem-endpoints.md)











