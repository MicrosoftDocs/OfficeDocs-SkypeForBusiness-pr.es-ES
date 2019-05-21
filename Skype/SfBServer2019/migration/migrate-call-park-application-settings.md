---
title: Migrar la configuración de la aplicación de estacionamiento de llamadas
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'La migración de la aplicación de estacionamiento de llamadas incluye el aprovisionamiento del grupo de servidores de Skype empresarial 2019 con cualquier música personalizada en los archivos que se hayan cargado en la instalación heredada, la restauración de la configuración del nivel de servicio y la redestinación de todas las opciones de estacionamiento de la Grupo de servidores de Skype empresarial 2019. Si se han configurado archivos de música en espera personalizados en el grupo, estos archivos deben copiarse en el nuevo grupo de servidores de Skype empresarial 2019. Además, se recomienda que haga una copia de seguridad de todos los archivos de música en espera personalizados de la llamada en espera para mantener una copia de seguridad separada de los archivos de música personalizada que se hayan cargado en el parque de llamadas. Los archivos de música personalizada habilitada para la aplicación de estacionamiento de llamadas se almacenan en el almacén de archivos del grupo. Para copiar los archivos de audio de un grupo de almacenamiento de archivos en un almacén de archivos de Skype empresarial Server 2019, use el comando xcopy con los siguientes parámetros:'
ms.openlocfilehash: aa4ac3cfbe6802b8853a8ec8886f8fffe1a20a51
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280835"
---
# <a name="migrate-call-park-application-settings"></a><span data-ttu-id="934aa-107">Migrar la configuración de la aplicación de estacionamiento de llamadas</span><span class="sxs-lookup"><span data-stu-id="934aa-107">Migrate Call Park application settings</span></span>

<span data-ttu-id="934aa-108">La migración de la aplicación de estacionamiento de llamadas incluye el aprovisionamiento del grupo de servidores de Skype empresarial 2019 con cualquier archivo de música personalizada que se haya cargado en la instalación heredada, la restauración de la configuración de nivel de servicio y la redestinación de todas las órbitas de estacionamiento de llamadas al grupo de servidores de Skype empresarial 2019.</span><span class="sxs-lookup"><span data-stu-id="934aa-108">The migration of the Call Park application includes provisioning the Skype for Business Server 2019 pool with any custom music-on-hold files that have been uploaded in the legacy install, restoring the service-level settings and re-targeting all Call Park orbits to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="934aa-109">Si se han configurado archivos de música en espera personalizados en el grupo, estos archivos deben copiarse en el nuevo grupo de servidores de Skype empresarial 2019.</span><span class="sxs-lookup"><span data-stu-id="934aa-109">If customized music-on-hold files have been configured in the pool, these files need to be copied to the new Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="934aa-110">Además, le recomendamos que haga una copia de seguridad de los archivos de música en espera personalizados de un parque a otro destino para mantener una copia de seguridad separada de los archivos de música personalizada que se hayan cargado para la llamada en espera.</span><span class="sxs-lookup"><span data-stu-id="934aa-110">Additionally, it is recommended that you back up any Call Park customized music-on-hold files to another destination to keep a separate backup copy of any customized music-on-hold files that have been uploaded for Call Park.</span></span> <span data-ttu-id="934aa-111">Los archivos de música personalizada habilitada para la aplicación de estacionamiento de llamadas se almacenan en el almacén de archivos del grupo.</span><span class="sxs-lookup"><span data-stu-id="934aa-111">The customized music-on-hold files for the Call Park application are stored in the file store of the pool.</span></span> <span data-ttu-id="934aa-112">Para copiar los archivos de audio de un grupo de almacenamiento de archivos en un almacén de archivos de Skype empresarial Server 2019, use el comando **xcopy** con los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="934aa-112">To copy the audio files from a pool file store to a Skype for Business Server 2019 file store, use the **Xcopy** command with the following parameters:</span></span> 

```
Xcopy <Source: legacy Pool CPS File Store Path> <Destination: Skype for Business Server 2019 Pool CPS File Store Path>
```

```
Example usage:  Xcopy "<legacy File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Skype for Business Server 2019 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
```

<span data-ttu-id="934aa-113">Cuando todos los archivos de audio personalizados se han copiado en el almacén de archivos de Skype empresarial Server 2019, la configuración de la aplicación estacionamiento de llamadas del grupo de Skype empresarial Server 2019 debe estar configurada y los intervalos de la órbita del parque de llamadas asociados con el grupo heredado. debe reasignarse al grupo de servidores de Skype empresarial 2019.</span><span class="sxs-lookup"><span data-stu-id="934aa-113">When all customized audio files have been copied to the Skype for Business Server 2019 file store, the Call Park application settings of the Skype for Business Server 2019 pool must be configured, and the Call Park orbit ranges that are associated with the legacy pool must be reassigned to the Skype for Business Server 2019 pool.</span></span>

<span data-ttu-id="934aa-114">La configuración de la aplicación estacionamiento de llamadas incluye el umbral de tiempo de espera de la recogida, la habilitación o deshabilitación de música en espera, los intentos de recopilación de llamadas máximas y la solicitud de tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="934aa-114">The Call Park application settings include the pickup timeout threshold, enabling or disabling music on hold, the maximum call pickup attempts, and the timeout request.</span></span> <span data-ttu-id="934aa-115">Debe administrar la configuración de la aplicación de estacionamiento de llamadas con el shell de administración de Skype empresarial Server para ejecutar el cmdlet **set-CsCpsConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="934aa-115">You must manage Call Park application settings by using the Skype for Business Server Management Shell to run the **Set-CsCpsConfiguration** cmdlet.</span></span> <span data-ttu-id="934aa-116">No puede administrar la configuración de la aplicación de estacionamiento de llamadas con el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="934aa-116">You cannot manage the Call Park application settings using the Skype for Business Server Control Panel.</span></span> 

## <a name="reconfigure-the-call-park-service-settings"></a><span data-ttu-id="934aa-117">Cambiar la configuración del servicio de estacionamiento de llamadas</span><span class="sxs-lookup"><span data-stu-id="934aa-117">Reconfigure the Call Park Service Settings</span></span>

1. <span data-ttu-id="934aa-118">Desde el servidor front-end de Skype empresarial Server 2019, abra el shell de administración de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="934aa-118">From the Skype for Business Server 2019 Front End Server, open the Skype for Business Server Management Shell.</span></span>

2. <span data-ttu-id="934aa-119">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="934aa-119">At the command line, type the following:</span></span>

    > [!NOTE]
    > <span data-ttu-id="934aa-120">Si la configuración de la aplicación de Skype para empresas Server 2019 es idéntica a la configuración heredada, puede omitir este paso.</span><span class="sxs-lookup"><span data-stu-id="934aa-120">If your Skype for Business Server 2019 Call Park application settings are identical to the legacy settings, you can skip this step.</span></span> <span data-ttu-id="934aa-121">Si la configuración de la aplicación de estacionamiento de llamadas es diferente para los entornos de Skype empresarial Server 2019 y los antiguos, use el cmdlet que se muestra a continuación como una plantilla para actualizar esos cambios.</span><span class="sxs-lookup"><span data-stu-id="934aa-121">If Call Park application settings are different for the Skype for Business Server 2019 and legacy environments, use the cmdlet below as a template to update those changes.</span></span> 

   ```
   Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>"
   ```

<span data-ttu-id="934aa-122">Para reasignar todos los intervalos de llamadas de la órbita de la agrupación heredada al grupo de servidores de Skype empresarial 2019, puede usar el panel de control de Skype empresarial Server o el shell de administración de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="934aa-122">To reassign all Call Park orbit ranges from the legacy pool to the Skype for Business Server 2019 pool, you can use either the Skype for Business Server Control Panel or the Skype for Business Server Management Shell.</span></span> 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-control-panel"></a><span data-ttu-id="934aa-123">Reasignar todos los intervalos órbitas del parque de llamadas con el panel de control de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="934aa-123">Reassign all Call Park Orbit Ranges using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="934aa-124">Abra el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="934aa-124">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="934aa-125">En el panel izquierdo, seleccione **características de voz**.</span><span class="sxs-lookup"><span data-stu-id="934aa-125">In the left pane, select **Voice Features**.</span></span>

3. <span data-ttu-id="934aa-126">Seleccione la pestaña **detener llamada** .</span><span class="sxs-lookup"><span data-stu-id="934aa-126">Select the **Call Park** tab.</span></span> 

4. <span data-ttu-id="934aa-127">Para cada rango de la órbita de la llamada que se asigna a una agrupación heredada, edite el **FQDN del servidor de destino** y seleccione el grupo de servidores de Skype empresarial 2019 que procesarán las solicitudes de estacionamiento.</span><span class="sxs-lookup"><span data-stu-id="934aa-127">For each Call Park orbit range assigned to a legacy pool, edit the **FQDN of destination server** setting and select the Skype for Business Server 2019 pool that will process the Call Park requests.</span></span> 

5. <span data-ttu-id="934aa-128">Seleccione **confirmar** para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="934aa-128">Select **Commit** to save the changes.</span></span> 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-management-shell"></a><span data-ttu-id="934aa-129">Reasignar todos los intervalos órbitas del parque de llamadas con el shell de administración de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="934aa-129">Reassign all Call Park Orbit Ranges using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="934aa-130">Abra el shell de administración de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="934aa-130">Open Skype for Business Server Management Shell.</span></span>

2. <span data-ttu-id="934aa-131">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="934aa-131">At the command line, type the following:</span></span>

   ```
   Get-CsCallParkOrbit
   ```

    <span data-ttu-id="934aa-132">Este cmdlet muestra todos los intervalos de la órbita de estacionamiento de llamadas en la implementación.</span><span class="sxs-lookup"><span data-stu-id="934aa-132">This cmdlet lists all of the Call Park orbit ranges in the deployment.</span></span> <span data-ttu-id="934aa-133">Todas las órbitas de estacionamiento de llamadas que tienen los parámetros **CallParkServiceId** y **CallParkServerFqdn** establecidos como el grupo heredado se deben reasignar.</span><span class="sxs-lookup"><span data-stu-id="934aa-133">All Call Park orbits that have the **CallParkServiceId** and **CallParkServerFqdn** parameters set as the legacy pool must be reassigned.</span></span> 

    <span data-ttu-id="934aa-134">Para reasignar los intervalos de la órbita del parque de llamadas heredadas al grupo de Skype empresarial Server 2019, en la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="934aa-134">To reassign the legacy Call Park orbit ranges to the Skype for Business Server 2019 pool, at the command line, type the following:</span></span>

   ```
   Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Skype for Business Server 2019 Pool FQDN>"
   ```

<span data-ttu-id="934aa-135">Después de reasignar todos los intervalos de la gira de llamadas al grupo de servidores de Skype empresarial 2019, se completará el proceso de migración de la aplicación de estacionamiento de llamadas y el grupo de Skype empresarial Server 2019 administrará todas las solicitudes de estacionamiento de llamadas futuras.</span><span class="sxs-lookup"><span data-stu-id="934aa-135">After reassigning all Call Park orbit ranges to the Skype for Business Server 2019 pool, the migration process for the Call Park application will be completed and the Skype for Business Server 2019 pool will handle all future Call Park requests.</span></span>


