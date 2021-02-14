---
title: Migrar la configuración de la aplicación de estacionamiento de llamadas
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'La migración de la aplicación Estacionamiento de llamadas incluye el aprovisionamiento del grupo de Skype Empresarial Server 2019 con cualquier música personalizada en espera que se haya cargado en la instalación heredada, la restauración de la configuración del nivel de servicio y el nuevo destino de todas las órbitas de estacionamiento de llamadas al grupo de skype empresarial Server 2019. Si se han configurado archivos personalizados de música en espera en el grupo de servidores, estos archivos deben copiarse en el nuevo grupo de Skype Empresarial Server 2019. Además, se recomienda realizar una copia de seguridad de los archivos de música en espera personalizados de estacionamiento de llamadas desde otro destino para mantener una copia de seguridad independiente de cualquier archivo de música en espera personalizado que se haya cargado para el estacionamiento de llamadas. Los archivos de música en espera personalizados para la aplicación de estacionamiento de llamadas se almacenan en el almacén de archivos del grupo de servidores. Para copiar los archivos de audio de un almacén de archivos de grupo en un almacén de archivos de Skype Empresarial Server 2019, use el comando Xcopy con los siguientes parámetros:'
ms.openlocfilehash: ded38ab600da4b277b1cdc83218833c26df081aa
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752822"
---
# <a name="migrate-call-park-application-settings"></a><span data-ttu-id="f95f2-107">Migrar la configuración de la aplicación de estacionamiento de llamadas</span><span class="sxs-lookup"><span data-stu-id="f95f2-107">Migrate Call Park application settings</span></span>

<span data-ttu-id="f95f2-108">La migración de la aplicación estacionamiento de llamadas incluye aprovisionar el grupo de Skype Empresarial Server 2019 con cualquier archivo de música en espera personalizado que se haya cargado en la instalación heredada, restaurar la configuración de nivel de servicio y volver a dirigir todas las órbitas de estacionamiento de llamadas al grupo de Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="f95f2-108">The migration of the Call Park application includes provisioning the Skype for Business Server 2019 pool with any custom music-on-hold files that have been uploaded in the legacy install, restoring the service-level settings and re-targeting all Call Park orbits to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="f95f2-109">Si se han configurado archivos personalizados de música en espera en el grupo de servidores, estos archivos deben copiarse en el nuevo grupo de Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="f95f2-109">If customized music-on-hold files have been configured in the pool, these files need to be copied to the new Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="f95f2-110">Además, se recomienda realizar una copia de seguridad de los archivos de música en espera personalizados de estacionamiento de llamadas en otro destino para mantener una copia de seguridad independiente de cualquier archivo de música en espera personalizado que se haya cargado para el estacionamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="f95f2-110">Additionally, it is recommended that you back up any Call Park customized music-on-hold files to another destination to keep a separate backup copy of any customized music-on-hold files that have been uploaded for Call Park.</span></span> <span data-ttu-id="f95f2-111">Los archivos de música en espera personalizados para la aplicación de estacionamiento de llamadas se almacenan en el almacén de archivos del grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="f95f2-111">The customized music-on-hold files for the Call Park application are stored in the file store of the pool.</span></span> <span data-ttu-id="f95f2-112">Para copiar los archivos de audio de un almacén de archivos de grupo en un almacén de archivos de Skype Empresarial Server 2019, use el comando **Xcopy** con los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="f95f2-112">To copy the audio files from a pool file store to a Skype for Business Server 2019 file store, use the **Xcopy** command with the following parameters:</span></span> 

```console
Xcopy <Source: legacy Pool CPS File Store Path> <Destination: Skype for Business Server 2019 Pool CPS File Store Path>
```

```console
Example usage:  Xcopy "<legacy File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Skype for Business Server 2019 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
```

<span data-ttu-id="f95f2-113">Cuando se han copiado todos los archivos de audio personalizados en el almacén de archivos de Skype Empresarial Server 2019, se debe configurar la configuración de la aplicación Estacionamiento de llamadas del grupo de Skype Empresarial Server 2019 y los intervalos de órbitas de estacionamiento de llamadas asociados con el grupo heredado deben reasignarse al grupo de Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="f95f2-113">When all customized audio files have been copied to the Skype for Business Server 2019 file store, the Call Park application settings of the Skype for Business Server 2019 pool must be configured, and the Call Park orbit ranges that are associated with the legacy pool must be reassigned to the Skype for Business Server 2019 pool.</span></span>

<span data-ttu-id="f95f2-114">La configuración de la aplicación Estacionamiento de llamadas incluye el umbral de tiempo de espera de recogida, la habilitación o deshabilitación de la música en espera, el número máximo de intentos de atención de llamadas y la solicitud de tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="f95f2-114">The Call Park application settings include the pickup timeout threshold, enabling or disabling music on hold, the maximum call pickup attempts, and the timeout request.</span></span> <span data-ttu-id="f95f2-115">Debe administrar la configuración de la aplicación estacionamiento de llamadas mediante el Shell de administración de Skype Empresarial Server para ejecutar el cmdlet **Set-CsCpsConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="f95f2-115">You must manage Call Park application settings by using the Skype for Business Server Management Shell to run the **Set-CsCpsConfiguration** cmdlet.</span></span> <span data-ttu-id="f95f2-116">No puede administrar la configuración de la aplicación estacionamiento de llamadas mediante el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="f95f2-116">You cannot manage the Call Park application settings using the Skype for Business Server Control Panel.</span></span> 

## <a name="reconfigure-the-call-park-service-settings"></a><span data-ttu-id="f95f2-117">Volver a configurar los valores de servicio de estacionamiento de llamadas</span><span class="sxs-lookup"><span data-stu-id="f95f2-117">Reconfigure the Call Park Service Settings</span></span>

1. <span data-ttu-id="f95f2-118">Desde el servidor front-end de Skype Empresarial Server 2019, abra el Shell de administración de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="f95f2-118">From the Skype for Business Server 2019 Front End Server, open the Skype for Business Server Management Shell.</span></span>

2. <span data-ttu-id="f95f2-119">Escriba lo siguiente en la línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="f95f2-119">At the command line, type the following:</span></span>

    > [!NOTE]
    > <span data-ttu-id="f95f2-120">Si la configuración de la aplicación estacionamiento de llamadas de Skype Empresarial Server 2019 es idéntica a la configuración heredada, puede omitir este paso.</span><span class="sxs-lookup"><span data-stu-id="f95f2-120">If your Skype for Business Server 2019 Call Park application settings are identical to the legacy settings, you can skip this step.</span></span> <span data-ttu-id="f95f2-121">Si la configuración de la aplicación estacionamiento de llamadas es diferente para los entornos heredados y de Skype Empresarial Server 2019, use el siguiente cmdlet como plantilla para actualizar esos cambios.</span><span class="sxs-lookup"><span data-stu-id="f95f2-121">If Call Park application settings are different for the Skype for Business Server 2019 and legacy environments, use the cmdlet below as a template to update those changes.</span></span> 

   ```PowerShell
   Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>"
   ```

<span data-ttu-id="f95f2-122">Para reasignar todos los intervalos de órbitas de estacionamiento de llamadas del grupo heredado al grupo de Skype Empresarial Server 2019, puede usar el Panel de control de Skype Empresarial Server o el Shell de administración de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="f95f2-122">To reassign all Call Park orbit ranges from the legacy pool to the Skype for Business Server 2019 pool, you can use either the Skype for Business Server Control Panel or the Skype for Business Server Management Shell.</span></span> 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-control-panel"></a><span data-ttu-id="f95f2-123">Reasignar todos los intervalos de órbitas de estacionamiento de llamadas mediante el Panel de control de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="f95f2-123">Reassign all Call Park Orbit Ranges using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="f95f2-124">Abra el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="f95f2-124">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="f95f2-125">En el panel izquierdo, seleccione **Características de voz**.</span><span class="sxs-lookup"><span data-stu-id="f95f2-125">In the left pane, select **Voice Features**.</span></span>

3. <span data-ttu-id="f95f2-126">Seleccione la pestaña **Estacionamiento de llamadas**.</span><span class="sxs-lookup"><span data-stu-id="f95f2-126">Select the **Call Park** tab.</span></span> 

4. <span data-ttu-id="f95f2-127">Para cada intervalo de órbitas de estacionamiento de llamadas asignado a un grupo heredado, edite el **FQDN** de la configuración del servidor de destino y seleccione el grupo de Skype Empresarial Server 2019 que procesará las solicitudes de estacionamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="f95f2-127">For each Call Park orbit range assigned to a legacy pool, edit the **FQDN of destination server** setting and select the Skype for Business Server 2019 pool that will process the Call Park requests.</span></span> 

5. <span data-ttu-id="f95f2-128">Seleccione **Confirmar** para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="f95f2-128">Select **Commit** to save the changes.</span></span> 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-management-shell"></a><span data-ttu-id="f95f2-129">Reasignar todos los intervalos de órbitas de estacionamiento de llamadas con el Shell de administración de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="f95f2-129">Reassign all Call Park Orbit Ranges using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="f95f2-130">Abra el Shell de administración de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="f95f2-130">Open Skype for Business Server Management Shell.</span></span>

2. <span data-ttu-id="f95f2-131">En la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f95f2-131">At the command line, type the following:</span></span>

   ```PowerShell
   Get-CsCallParkOrbit
   ```

    <span data-ttu-id="f95f2-132">Este cmdlet muestra todos los intervalos de órbita de estacionamiento de llamadas de la implementación.</span><span class="sxs-lookup"><span data-stu-id="f95f2-132">This cmdlet lists all of the Call Park orbit ranges in the deployment.</span></span> <span data-ttu-id="f95f2-133">Todas las órbitas de estacionamiento de llamadas que tienen los parámetros **CallParkServiceId** y **CallParkServerFqdn** establecidos como el grupo heredado deben reasignarse.</span><span class="sxs-lookup"><span data-stu-id="f95f2-133">All Call Park orbits that have the **CallParkServiceId** and **CallParkServerFqdn** parameters set as the legacy pool must be reassigned.</span></span> 

    <span data-ttu-id="f95f2-134">Para reasignar los intervalos de órbitas de estacionamiento de llamadas heredados al grupo de Skype Empresarial Server 2019, en la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f95f2-134">To reassign the legacy Call Park orbit ranges to the Skype for Business Server 2019 pool, at the command line, type the following:</span></span>

   ```PowerShell
   Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Skype for Business Server 2019 Pool FQDN>"
   ```

<span data-ttu-id="f95f2-135">Después de reasignar todos los intervalos de órbitas de estacionamiento de llamadas al grupo de Skype Empresarial Server 2019, se completará el proceso de migración de la aplicación Estacionamiento de llamadas y el grupo de Skype Empresarial Server 2019 controlará todas las solicitudes futuras de estacionamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="f95f2-135">After reassigning all Call Park orbit ranges to the Skype for Business Server 2019 pool, the migration process for the Call Park application will be completed and the Skype for Business Server 2019 pool will handle all future Call Park requests.</span></span>


