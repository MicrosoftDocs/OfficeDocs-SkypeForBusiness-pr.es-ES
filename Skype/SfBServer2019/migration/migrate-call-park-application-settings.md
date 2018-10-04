---
title: Migrar la configuración de la aplicación de estacionamiento de llamadas
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'La migración de la aplicación incluye la Skype para grupo de negocio Server 2019 con cualquier personalizado de música en espera los archivos que se han cargado en la instalación heredada de aprovisionamiento de estacionamiento de llamadas, al restaurar la configuración de nivel de servicio y redirección de estacionamiento todas las órbitas a la Skype para el grupo de servidores de Business Server 2019. Si se han configurado en el grupo de archivos de música en espera personalizados, estos archivos deben copiarse a la nueva Skype para el grupo de servidores de Business Server 2019. Además, se recomienda que se haga una copia de seguridad de cualquier estacionamiento personalizado los archivos de música en espera de a otro destino para mantener una copia de seguridad independiente de cualquier archivo personalizado de música en espera que se han cargado del estacionamiento de llamadas. Los archivos de música en espera personalizados para la aplicación de estacionamiento de llamadas se almacenan en el almacén de archivos del grupo de servidores. Para copiar los archivos de audio desde un almacén de archivos de grupo de servidores a un Skype Business Server 2019 almacén de archivos, utilice el comando Xcopy con los siguientes parámetros:'
ms.openlocfilehash: bcc2da8192f0c94f20d11073b1b18439ccc9df61
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25370997"
---
# <a name="migrate-call-park-application-settings"></a><span data-ttu-id="8b128-107">Migrar la configuración de la aplicación de estacionamiento de llamadas</span><span class="sxs-lookup"><span data-stu-id="8b128-107">Migrate Call Park application settings</span></span>

<span data-ttu-id="8b128-108">La migración de la aplicación de estacionamiento de llamadas incluye la Skype para el grupo de servidores de Business Server 2019 de aprovisionamiento con cualquier archivo de música en espera personalizado que se han cargado en la instalación heredada, al restaurar la configuración de nivel de servicio e identificación de volver a todas las órbitas de estacionamiento de llamadas para Skype para el grupo de servidores de Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="8b128-108">The migration of the Call Park application includes provisioning the Skype for Business Server 2019 pool with any custom music-on-hold files that have been uploaded in the legacy install, restoring the service-level settings and re-targeting all Call Park orbits to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="8b128-109">Si se han configurado en el grupo de archivos de música en espera personalizados, estos archivos deben copiarse a la nueva Skype para el grupo de servidores de Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="8b128-109">If customized music-on-hold files have been configured in the pool, these files need to be copied to the new Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="8b128-110">Además, se recomienda que se haga una copia de seguridad de cualquier estacionamiento personalizado los archivos de música en espera a otro destino para mantener una copia de seguridad independiente de cualquier archivo personalizado de música en espera que se han cargado del estacionamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="8b128-110">Additionally, it is recommended that you back up any Call Park customized music-on-hold files to another destination to keep a separate backup copy of any customized music-on-hold files that have been uploaded for Call Park.</span></span> <span data-ttu-id="8b128-111">Los archivos de música en espera personalizados para la aplicación de estacionamiento de llamadas se almacenan en el almacén de archivos del grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="8b128-111">The customized music-on-hold files for the Call Park application are stored in the file store of the pool.</span></span> <span data-ttu-id="8b128-112">Para copiar los archivos de audio desde un almacén de archivos de grupo de servidores a un Skype Business Server 2019 almacén de archivos, utilice el comando **Xcopy** con los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="8b128-112">To copy the audio files from a pool file store to a Skype for Business Server 2019 file store, use the **Xcopy** command with the following parameters:</span></span> 

```
Xcopy <Source: legacy Pool CPS File Store Path> <Destination: Skype for Business Server 2019 Pool CPS File Store Path>
```

```
Example usage:  Xcopy "<legacy File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Skype for Business Server 2019 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
```

<span data-ttu-id="8b128-113">Cuando se han copiado todos los archivos de audioconferencias personalizados a la Skype Business Server 2019 almacén de archivos, la configuración de la aplicación de estacionamiento de llamadas de la Skype para Business Server 2019 se debe configurar el grupo de servidores y el estacionamiento de llamadas órbita rangos que están asociados con el grupo de servidores heredado debe asignarse a la Skype para el grupo de servidores de Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="8b128-113">When all customized audio files have been copied to the Skype for Business Server 2019 file store, the Call Park application settings of the Skype for Business Server 2019 pool must be configured, and the Call Park orbit ranges that are associated with the legacy pool must be reassigned to the Skype for Business Server 2019 pool.</span></span>

<span data-ttu-id="8b128-114">La configuración de la aplicación de estacionamiento de llamadas incluye el umbral de tiempo de espera pickup, habilitar o deshabilitar la música en espera, los intentos de recogida máximo de llamadas y la solicitud de tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="8b128-114">The Call Park application settings include the pickup timeout threshold, enabling or disabling music on hold, the maximum call pickup attempts, and the timeout request.</span></span> <span data-ttu-id="8b128-115">Debe administrar configuración de la aplicación de estacionamiento de llamadas mediante el Skype para Business Server Management Shell para ejecutar el cmdlet **Set-CsCpsConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="8b128-115">You must manage Call Park application settings by using the Skype for Business Server Management Shell to run the **Set-CsCpsConfiguration** cmdlet.</span></span> <span data-ttu-id="8b128-116">No se puede administrar la configuración de la aplicación de estacionamiento de llamadas mediante el Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="8b128-116">You cannot manage the Call Park application settings using the Skype for Business Server Control Panel.</span></span> 

## <a name="reconfigure-the-call-park-service-settings"></a><span data-ttu-id="8b128-117">Volver a configurar la configuración del servicio de estacionamiento de llamadas</span><span class="sxs-lookup"><span data-stu-id="8b128-117">Reconfigure the Call Park Service Settings</span></span>

1. <span data-ttu-id="8b128-118">De Skype para profesionales de 2019 Front-End Server, abra el Skype para Shell de administración de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="8b128-118">From the Skype for Business Server 2019 Front End Server, open the Skype for Business Server Management Shell.</span></span>

2. <span data-ttu-id="8b128-119">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="8b128-119">At the command line, type the following:</span></span>

    > [!NOTE]
    > <span data-ttu-id="8b128-120">Si su Skype para la configuración de la aplicación de estacionamiento de llamadas de Business Server 2019 es idéntica a la configuración heredada, puede omitir este paso.</span><span class="sxs-lookup"><span data-stu-id="8b128-120">If your Skype for Business Server 2019 Call Park application settings are identical to the legacy settings, you can skip this step.</span></span> <span data-ttu-id="8b128-121">Si la configuración de la aplicación de estacionamiento de llamadas es diferentes para la Skype para Business Server 2019 y entornos heredados, use el cmdlet a continuación como una plantilla para actualizar dichos cambios.</span><span class="sxs-lookup"><span data-stu-id="8b128-121">If Call Park application settings are different for the Skype for Business Server 2019 and legacy environments, use the cmdlet below as a template to update those changes.</span></span> 

   ```
   Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>"
   ```

<span data-ttu-id="8b128-122">Para reasignar todos los intervalos de órbitas de estacionamiento de llamadas del grupo heredado para la Skype para Business Server 2019 grupo, puede usar el Skype para el Panel de Control de servidor empresarial o el Skype para Shell de administración de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="8b128-122">To reassign all Call Park orbit ranges from the legacy pool to the Skype for Business Server 2019 pool, you can use either the Skype for Business Server Control Panel or the Skype for Business Server Management Shell.</span></span> 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-control-panel"></a><span data-ttu-id="8b128-123">Reasignar todos los intervalos de órbitas de estacionamiento de llamadas mediante Skype para el Panel de Control de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="8b128-123">Reassign all Call Park Orbit Ranges using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="8b128-124">Abra Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="8b128-124">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="8b128-125">En el panel izquierdo, seleccione **Las características de voz**.</span><span class="sxs-lookup"><span data-stu-id="8b128-125">In the left pane, select **Voice Features**.</span></span>

3. <span data-ttu-id="8b128-126">Seleccione la pestaña **Estacionamiento de llamadas** .</span><span class="sxs-lookup"><span data-stu-id="8b128-126">Select the **Call Park** tab.</span></span> 

4. <span data-ttu-id="8b128-127">Para cada intervalo de órbitas de estacionamiento de llamadas asignado a un grupo de servidores heredado, edite la configuración del **FQDN del servidor de destino** y seleccione el Skype para grupo de negocio Server 2019 que procesará las solicitudes de estacionamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="8b128-127">For each Call Park orbit range assigned to a legacy pool, edit the **FQDN of destination server** setting and select the Skype for Business Server 2019 pool that will process the Call Park requests.</span></span> 

5. <span data-ttu-id="8b128-128">Seleccione **Confirmar** para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="8b128-128">Select **Commit** to save the changes.</span></span> 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-management-shell"></a><span data-ttu-id="8b128-129">Reasignar todos los intervalos de órbitas de estacionamiento de llamadas mediante Skype para Shell de administración de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="8b128-129">Reassign all Call Park Orbit Ranges using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="8b128-130">Abra Skype para Shell de administración de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="8b128-130">Open Skype for Business Server Management Shell.</span></span>

2. <span data-ttu-id="8b128-131">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="8b128-131">At the command line, type the following:</span></span>

   ```
   Get-CsCallParkOrbit
   ```

    <span data-ttu-id="8b128-132">Este cmdlet enumera todos los intervalos de órbitas de estacionamiento de llamadas en la implementación.</span><span class="sxs-lookup"><span data-stu-id="8b128-132">This cmdlet lists all of the Call Park orbit ranges in the deployment.</span></span> <span data-ttu-id="8b128-133">Se deben reasignar todas las órbitas de estacionamiento de llamadas que tienen los parámetros **CallParkServiceId** y **CallParkServerFqdn** establecido como el grupo heredado.</span><span class="sxs-lookup"><span data-stu-id="8b128-133">All Call Park orbits that have the **CallParkServiceId** and **CallParkServerFqdn** parameters set as the legacy pool must be reassigned.</span></span> 

    <span data-ttu-id="8b128-134">Para volver a asignar la órbita de estacionamiento de llamadas heredada intervalos a la Skype para Business Server 2019 grupo de servidores, en la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8b128-134">To reassign the legacy Call Park orbit ranges to the Skype for Business Server 2019 pool, at the command line, type the following:</span></span>

   ```
   Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Skype for Business Server 2019 Pool FQDN>"
   ```

<span data-ttu-id="8b128-135">Después de reasignar todos los intervalos de órbitas de estacionamiento de llamadas a la Skype para el grupo de servidores de Business Server 2019, se completará el proceso de migración de la aplicación de estacionamiento de llamadas y el Skype para el grupo de servidores de Business Server 2019 controlará todas las solicitudes futuras de estacionamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="8b128-135">After reassigning all Call Park orbit ranges to the Skype for Business Server 2019 pool, the migration process for the Call Park application will be completed and the Skype for Business Server 2019 pool will handle all future Call Park requests.</span></span>


