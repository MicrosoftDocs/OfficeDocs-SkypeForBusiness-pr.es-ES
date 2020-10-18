---
title: Migrar la configuración de la aplicación de estacionamiento de llamadas
description: Migrar la configuración de la aplicación de estacionamiento de llamadas.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate Call Park application settings
ms:assetid: 23b192d2-93ec-42a8-b175-b6ed502a2c35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687993(v=OCS.15)
ms:contentKeyID: 49733583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da90ca4ee4dd53451c29b8c39861dc76a17ca3c7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579416"
---
# <a name="migrate-call-park-application-settings"></a><span data-ttu-id="e3d2e-103">Migrar la configuración de la aplicación de estacionamiento de llamadas</span><span class="sxs-lookup"><span data-stu-id="e3d2e-103">Migrate Call Park application settings</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e3d2e-104">_**Última modificación del tema:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="e3d2e-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="e3d2e-105">La migración de la aplicación de estacionamiento de llamadas de Lync Server 2010 a Lync Server 2013 incluye el aprovisionamiento del grupo de Lync Server 2013 con cualquier archivo de música personalizado en retención que se haya cargado en Lync Server 2010, restaurando la configuración del nivel de servicio y redestinando todas las órbitas de estacionamiento de llamadas al grupo de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e3d2e-105">The migration of the Call Park application from Lync Server 2010 to Lync Server 2013 includes provisioning the Lync Server 2013 pool with any custom music on hold files that have been uploaded in Lync Server 2010, restoring the service level settings and retargeting all Call Park orbits to the Lync Server 2013 pool.</span></span> <span data-ttu-id="e3d2e-106">Si se han configurado archivos de música en espera personalizados en el grupo de servidores de Lync Server 2010, estos archivos deben copiarse en el nuevo grupo de servidores de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e3d2e-106">If customized music-on-hold files have been configured in the Lync Server 2010 pool, these files need to be copied to the new Lync Server 2013 pool.</span></span> <span data-ttu-id="e3d2e-107">Además, se recomienda realizar una copia de seguridad de los archivos de música en espera personalizados de la música en espera de Lync Server 2010 en otro destino para mantener una copia de seguridad independiente de los archivos de música en espera personalizados que se han cargado para el estacionamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="e3d2e-107">Additionally, it is recommended that you back up any Call Park customized music-on-hold files from Lync Server 2010 to another destination to keep a separate backup copy of any customized music-on-hold files that have been uploaded for Call Park.</span></span> <span data-ttu-id="e3d2e-108">Los archivos de música en espera personalizados para la aplicación de estacionamiento de llamadas se almacenan en el almacén de archivos del grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="e3d2e-108">The customized music-on-hold files for the Call Park application are stored in the file store of the pool.</span></span> <span data-ttu-id="e3d2e-109">Para copiar los archivos de audio de un almacén de archivos de un grupo de servidores de Lync Server 2010 en un almacén de archivos de Lync Server 2013, use el comando **xcopy** con los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="e3d2e-109">To copy the audio files from a Lync Server 2010 pool file store to a Lync Server 2013 file store, use the **Xcopy** command with the following parameters:</span></span>

   ```console
    Xcopy <Source: Lync Server 2010 Pool CPS File Store Path> <Destination: Lync Server 2013 Pool CPS File Store Path>
   ```

   ```console
    Example usage:  Xcopy "<Lync Server 2010 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Lync Server 2013 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
   ```

<span data-ttu-id="e3d2e-110">Cuando todos los archivos de audio personalizados se han copiado en el almacén de archivos de Lync Server 2013, la configuración de la aplicación de estacionamiento de llamadas del grupo de Lync Server 2013 debe configurarse, y los intervalos de órbita de estacionamiento de llamadas asociados con el grupo de Lync Server 2010 deben reasignarse al grupo de servidores de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e3d2e-110">When all customized audio files have been copied to the Lync Server 2013 file store, the Call Park application settings of the Lync Server 2013 pool must be configured, and the Call Park orbit ranges that are associated with the Lync Server 2010 pool must be reassigned to the Lync Server 2013 pool.</span></span>

<span data-ttu-id="e3d2e-111">Los valores de aplicación de estacionamiento de llamadas incluyen el umbral de tiempo de espera de recogida, la habilitación o deshabilitación de la música en espera, los intentos de recogida de llamadas máximos y la solicitud de tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="e3d2e-111">The Call Park application settings include the pickup timeout threshold, enabling or disabling music on hold, the maximum call pickup attempts and the timeout request.</span></span> <span data-ttu-id="e3d2e-112">Debe administrar la configuración de la aplicación de estacionamiento de llamadas mediante el shell de administración de Lync Server para ejecutar el cmdlet **set-CsCpsConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="e3d2e-112">You must manage Call Park application settings by using the Lync Server Management Shell to run the **Set-CsCpsConfiguration** cmdlet.</span></span> <span data-ttu-id="e3d2e-113">No se puede administrar la configuración de la aplicación estacionamiento de llamadas mediante el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e3d2e-113">You cannot manage the Call Park application settings using the Lync Server Control Panel.</span></span>

<span data-ttu-id="e3d2e-114">**Volver a configurar los valores de servicio de estacionamiento de llamadas**</span><span class="sxs-lookup"><span data-stu-id="e3d2e-114">**Reconfigure the Call Park Service Settings**</span></span>

1.  <span data-ttu-id="e3d2e-115">En el servidor front-end de Lync Server 2013, abra el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e3d2e-115">From the Lync Server 2013 Front End Server, open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="e3d2e-116">Escriba lo siguiente en la línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="e3d2e-116">At the command line, type the following:</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e3d2e-117">Si la configuración de la aplicación de estacionamiento de llamadas de Lync Server 2013 es idéntica a la configuración heredada de Lync Server 2010, puede omitir este paso.</span><span class="sxs-lookup"><span data-stu-id="e3d2e-117">If your Lync Server 2013 Call Park application settings are identical to the legacy Lync Server 2010 settings, you can skip running this step.</span></span> <span data-ttu-id="e3d2e-118">Si la configuración de la aplicación estacionamiento de llamadas es diferente para los entornos Lync Server 2013 y Lync Server 2010, use el cmdlet siguiente como plantilla para actualizar dichos cambios.</span><span class="sxs-lookup"><span data-stu-id="e3d2e-118">If Call Park application settings are different for the Lync Server 2013 and Lync Server 2010 environments, use the cmdlet below as a template to update those changes.</span></span>

    
    <span data-ttu-id="e3d2e-119"></div>
    ```powershell
        Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>"-CallPickupTimeoutThreshold" <LS2010 CPS TimeSpan> "-EnableMusicOnHold" <LS2010 CPS value> "-MaxCallPickupAttempts" <LS2010 CPS pickup attempts> "-OnTimeoutURI" <LS2010 CPS timeout URI> " ```</span><span class="sxs-lookup"><span data-stu-id="e3d2e-119"></div>
    ```powershell
        Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>" ```</span></span>

<span data-ttu-id="e3d2e-120">Para reasignar todos los intervalos de órbitas de estacionamiento de llamadas del grupo de servidores de Lync Server 2010 al grupo de Lync Server 2013, puede usar el panel de control de Lync Server o el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e3d2e-120">To reassign all Call Park orbit ranges from Lync Server 2010 pool to the Lync Server 2013 pool, you can use either the Lync Server Control Panel or the Lync Server Management Shell.</span></span>

<span data-ttu-id="e3d2e-121">**Reasignar todos los intervalos de órbitas de estacionamiento de llamadas mediante el panel de control de Lync Server**</span><span class="sxs-lookup"><span data-stu-id="e3d2e-121">**Reassign all Call Park Orbit Ranges using Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="e3d2e-122">Abra Panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="e3d2e-122">Open Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="e3d2e-123">En el panel izquierdo, seleccione **Características de voz**.</span><span class="sxs-lookup"><span data-stu-id="e3d2e-123">In the left pane, select **Voice Features**.</span></span>

3.  <span data-ttu-id="e3d2e-124">Seleccione la pestaña **Estacionamiento de llamadas**.</span><span class="sxs-lookup"><span data-stu-id="e3d2e-124">Select the **Call Park** tab.</span></span>

4.  <span data-ttu-id="e3d2e-125">Para cada intervalo de órbitas de estacionamiento de llamadas asignado a un grupo de servidores de Lync Server 2010, edite el FQDN de la configuración del **servidor de destino** y seleccione el grupo de lync Server 2013 que procesará las solicitudes de estacionamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="e3d2e-125">For each Call Park orbit range assigned to a Lync Server 2010 pool, edit the **FQDN of destination server** setting and select the Lync Server 2013 pool that will process the Call Park requests.</span></span>

5.  <span data-ttu-id="e3d2e-126">Seleccione **Confirmar** para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="e3d2e-126">Select **Commit** to save the changes.</span></span>

<span data-ttu-id="e3d2e-127">**Vuelva a asignar todos los intervalos de órbita de estacionamiento de llamadas mediante el Shell de administración de Lync Server**</span><span class="sxs-lookup"><span data-stu-id="e3d2e-127">**Reassign all Call Park Orbit Ranges using Lync Server Management Shell**</span></span>

1.  <span data-ttu-id="e3d2e-128">Abra el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e3d2e-128">Open Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="e3d2e-129">En la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e3d2e-129">At the command line, type the following:</span></span>
    ```powershell
    Get-CsCallParkOrbit
    ```
    
    <span data-ttu-id="e3d2e-130">Este cmdlet muestra todos los intervalos de órbita de estacionamiento de llamadas de la implementación.</span><span class="sxs-lookup"><span data-stu-id="e3d2e-130">This cmdlet lists all of the Call Park orbit ranges in the deployment.</span></span> <span data-ttu-id="e3d2e-131">Todas las órbitas de estacionamiento de llamadas que tienen los parámetros **CallParkServiceId** y **CallParkServerFqdn** establecidos como grupo de Lync Server 2010 deben reasignarse.</span><span class="sxs-lookup"><span data-stu-id="e3d2e-131">All Call Park orbits that have the **CallParkServiceId** and **CallParkServerFqdn** parameters set as the Lync Server 2010 pool must be reassigned.</span></span>
    
    <span data-ttu-id="e3d2e-132">Para reasignar intervalos de órbita de estacionamiento de llamadas de Lync Server 2010 al grupo de servidores de Lync Server 2013, en la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e3d2e-132">To reassign the Lync Server 2010 Call Park orbit ranges to the Lync Server 2013 pool, at the command line, type the following:</span></span>
    
    ```powershell
    Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Lync Server 2013 Pool FQDN>"
    ```

<span data-ttu-id="e3d2e-133">Después de reasignar todos los intervalos de órbitas de estacionamiento de llamadas al grupo de servidores de Lync Server 2013, se completará el proceso de migración de la aplicación de estacionamiento de llamadas y el grupo de servidores de Lync Server 2013 administrará todas las solicitudes de estacionamiento de llamadas futuras.</span><span class="sxs-lookup"><span data-stu-id="e3d2e-133">After reassigning all Call Park orbit ranges to the Lync Server 2013 pool, the migration process for the Call Park application will be completed and the Lync Server 2013 pool will handle all future Call Park requests.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

