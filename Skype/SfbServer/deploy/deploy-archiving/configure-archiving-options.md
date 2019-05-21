---
title: Configurar opciones de archivado para Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2f534697-ac7f-45b7-8cdc-ba67f052223b
description: 'Resumen: Lea este tema para obtener información sobre cómo configurar las opciones iniciales de archivado de Skype empresarial Server. Inicialmente, debe configurar las configuraciones de archivado al implementar el archivado, pero puede cambiar, agregar y eliminar configuraciones después de la implementación.'
ms.openlocfilehash: 33438bb56c1ce55b0b449b9ee4124e27ae8638cc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286607"
---
# <a name="configure-archiving-options-for-skype-for-business-server"></a><span data-ttu-id="eb1f6-104">Configurar opciones de archivado para Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="eb1f6-104">Configure archiving options for Skype for Business Server</span></span>
 
<span data-ttu-id="eb1f6-105">**Resumen:** Lea este tema para obtener información sobre cómo configurar las opciones iniciales de archivado para Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="eb1f6-105">**Summary:** Read this topic to learn how to configure initial archiving options for Skype for Business Server.</span></span> <span data-ttu-id="eb1f6-106">Inicialmente, debe configurar las configuraciones de archivado al implementar el archivado, pero puede cambiar, agregar y eliminar configuraciones después de la implementación.</span><span class="sxs-lookup"><span data-stu-id="eb1f6-106">You initially set up archiving configurations when you deploy archiving, but you can change, add, and delete configurations after deployment.</span></span>
  
<span data-ttu-id="eb1f6-107">Para configurar las configuraciones iniciales de archivado, use el panel de control de Skype empresarial Server para especificar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="eb1f6-107">To configure initial archiving configurations, you use Skype for Business Server Control Panel to specify the following:</span></span>
  
- <span data-ttu-id="eb1f6-108">Configuración de nivel global que se crea de forma predeterminada al implementar Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="eb1f6-108">Global-level configuration that is created by default when you deploy Skype for Business Server</span></span>
    
- <span data-ttu-id="eb1f6-109">En la configuración de sitio opcional, que especifica cómo se implementa el archivado para un sitio específico</span><span class="sxs-lookup"><span data-stu-id="eb1f6-109">Optional site-level configurations that specify how archiving is implemented for a specific site</span></span>
    
- <span data-ttu-id="eb1f6-110">Configuraciones de nivel de grupo opcionales que especifican cómo se implementa el archivado para un grupo específico</span><span class="sxs-lookup"><span data-stu-id="eb1f6-110">Optional pool-level configurations that specify how archiving is implemented for a specific pool</span></span>
    
<span data-ttu-id="eb1f6-111">Necesitará configurar las opciones para determinar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="eb1f6-111">You will need to configure options for the following:</span></span>
  
- <span data-ttu-id="eb1f6-112">Si desea habilitar o deshabilitar el archivado</span><span class="sxs-lookup"><span data-stu-id="eb1f6-112">Whether to enable or disable archiving</span></span>
    
- <span data-ttu-id="eb1f6-113">Si desea archivar las sesiones de mensajería instantánea (MI)</span><span class="sxs-lookup"><span data-stu-id="eb1f6-113">Whether to archive IM sessions</span></span>
    
- <span data-ttu-id="eb1f6-114">Si desea archivar las sesiones de conferencias web</span><span class="sxs-lookup"><span data-stu-id="eb1f6-114">Whether to archive web conferencing sessions</span></span>
    
- <span data-ttu-id="eb1f6-115">Si desea bloquear la actividad cuando el archivado no está disponible</span><span class="sxs-lookup"><span data-stu-id="eb1f6-115">Whether to block activity when archiving is not available</span></span>
    
- <span data-ttu-id="eb1f6-116">Si desea utilizar la integración de Exchange</span><span class="sxs-lookup"><span data-stu-id="eb1f6-116">Whether to use Exchange integration</span></span>
    
- <span data-ttu-id="eb1f6-117">Cómo configurar la purga y la exportación de datos</span><span class="sxs-lookup"><span data-stu-id="eb1f6-117">How to set up purging and exporting of data</span></span>
    
> [!NOTE]
> <span data-ttu-id="eb1f6-118">Es preciso que especifique todas las opciones adecuadas antes de habilitar el archivado.</span><span class="sxs-lookup"><span data-stu-id="eb1f6-118">You should specify all appropriate options before enabling archiving.</span></span> 
  
<span data-ttu-id="eb1f6-119">Para obtener más información sobre cómo se implementan las configuraciones de archivado, incluidas las opciones que puede especificar y la jerarquía de las configuraciones de archivado, consulte [planear el archivado en Skype empresarial Server](../../plan-your-deployment/archiving/archiving.md).</span><span class="sxs-lookup"><span data-stu-id="eb1f6-119">For details about how archiving configurations are implemented, including which options you can specify and the hierarchy of archiving configurations, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span> <span data-ttu-id="eb1f6-120">Para obtener detalles sobre cómo administrar las configuraciones después de la implementación mediante el panel de control o mediante Windows PowerShell, consulte [administrar las opciones de archivado en Skype empresarial Server](../../manage/archiving/options.md).</span><span class="sxs-lookup"><span data-stu-id="eb1f6-120">For details about how to manage configurations after deployment by using the Control Panel or by using Windows PowerShell, see [Manage archiving options in Skype for Business Server](../../manage/archiving/options.md).</span></span>
  
## <a name="configure-global-level-archiving-options"></a><span data-ttu-id="eb1f6-121">Configurar las opciones de archivado en el ámbito global</span><span class="sxs-lookup"><span data-stu-id="eb1f6-121">Configure global level archiving options</span></span>

<span data-ttu-id="eb1f6-122">Cuando agrega un archivo a su topología y publica la topología, Skype empresarial Server crea una configuración global para el archivado.</span><span class="sxs-lookup"><span data-stu-id="eb1f6-122">When you add archiving to your topology and publish the topology, Skype for Business Server creates a global configuration for archiving.</span></span> <span data-ttu-id="eb1f6-123">De forma predeterminada, no se habilita ninguna opción de archivado en la configuración global.</span><span class="sxs-lookup"><span data-stu-id="eb1f6-123">By default, no archiving options are enabled in the global configuration.</span></span> <span data-ttu-id="eb1f6-124">La configuración global controla qué opciones se habilitan para toda la implementación, a menos que realice configuraciones de sitio o de grupo, que omiten la configuración global.</span><span class="sxs-lookup"><span data-stu-id="eb1f6-124">The global configuration controls which options are enabled for your entire deployment, unless you set up site or pool configurations, which override the global configuration.</span></span>
  
<span data-ttu-id="eb1f6-125">Para configurar las opciones de archivado en el ámbito global:</span><span class="sxs-lookup"><span data-stu-id="eb1f6-125">To configure archiving options at the global level:</span></span>
  
1. <span data-ttu-id="eb1f6-126">Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="eb1f6-126">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="eb1f6-127">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="eb1f6-127">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="eb1f6-128">En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, después, en **Configuración de archivado**.</span><span class="sxs-lookup"><span data-stu-id="eb1f6-128">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="eb1f6-129">En la página **Configuración de archivado**, haga clic en **Global**, en **Editar** y, luego, en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="eb1f6-129">On the **Archiving Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="eb1f6-130">En **Editar configuración de archivado: global**, en la lista desplegable **Configuración de archivado**, seleccione una de las siguientes opciones de archivado:</span><span class="sxs-lookup"><span data-stu-id="eb1f6-130">In **Edit Archiving Setting - Global**, in the **Archiving setting** drop-down list, select one of the following archiving options:</span></span>
    
   - <span data-ttu-id="eb1f6-131">**Deshabilitar archivado**</span><span class="sxs-lookup"><span data-stu-id="eb1f6-131">**Disable archiving**</span></span>
    
   - <span data-ttu-id="eb1f6-132">**Archivar sesiones de mensajería instantánea (MI)**</span><span class="sxs-lookup"><span data-stu-id="eb1f6-132">**Archive IM sessions**</span></span>
    
   - <span data-ttu-id="eb1f6-133">**Archivar sesiones de mensajería instantánea (MI) y conferencias web**</span><span class="sxs-lookup"><span data-stu-id="eb1f6-133">**Archive IM and web conferencing sessions**</span></span>
    
6. <span data-ttu-id="eb1f6-134">Además, en la página **Editar configuración de archivado global** , haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="eb1f6-134">Also on the **Edit Archiving Setting - Global** page, do the following:</span></span>
    
   - <span data-ttu-id="eb1f6-135">Para bloquear la actividad cuando el archivado no está disponible, active la casilla **Bloquear sesiones de mensajería instantánea (MI) o de conferencias web si no se pueden archivar**.</span><span class="sxs-lookup"><span data-stu-id="eb1f6-135">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
   - <span data-ttu-id="eb1f6-136">Para usar Microsoft Exchange Server para almacenar datos de archivado, haga clic en la casilla de verificación **integración con Microsoft Exchange** .</span><span class="sxs-lookup"><span data-stu-id="eb1f6-136">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="eb1f6-137">Para habilitar la purga de datos, active la casilla **Habilitar purgado de los datos de archivado** y realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="eb1f6-137">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
    
   - <span data-ttu-id="eb1f6-138">Para especificar la purga al transcurrir una cantidad de días determinada, haga clic en **Purgar los datos de archivado exportados y los datos de archivado almacenados tras la duración máxima (días)** y especifique la cantidad de días.</span><span class="sxs-lookup"><span data-stu-id="eb1f6-138">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
   - <span data-ttu-id="eb1f6-139">Para limitar la purga de los datos de archivado que se han exportado, haga clic en **Purgar solo datos de archivado exportados**.</span><span class="sxs-lookup"><span data-stu-id="eb1f6-139">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>
    
7. <span data-ttu-id="eb1f6-140">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="eb1f6-140">Click **Commit**.</span></span>
    
## <a name="configure-site-level-archiving-options"></a><span data-ttu-id="eb1f6-141">Configurar las opciones de archivado en el sitio</span><span class="sxs-lookup"><span data-stu-id="eb1f6-141">Configure site level archiving options</span></span>

<span data-ttu-id="eb1f6-142">Puede especificar opciones de archivado para un sitio específico.</span><span class="sxs-lookup"><span data-stu-id="eb1f6-142">You can specify archiving options for a specific site.</span></span> <span data-ttu-id="eb1f6-143">Una configuración de sitio reemplaza la configuración global, pero solo para el sitio especificado en la configuración del sitio.</span><span class="sxs-lookup"><span data-stu-id="eb1f6-143">A site configuration overrides the global configuration, but only for the site specified in the site configuration.</span></span> 
  
1. <span data-ttu-id="eb1f6-144">Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="eb1f6-144">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="eb1f6-145">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="eb1f6-145">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="eb1f6-146">En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, después, en **Configuración de archivado**.</span><span class="sxs-lookup"><span data-stu-id="eb1f6-146">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="eb1f6-147">En la página **Configuración de archivado**, haga clic en **Nuevo** y, luego, en **Configuración de sitio**.</span><span class="sxs-lookup"><span data-stu-id="eb1f6-147">On the **Archiving Configuration** page, click **New**, and then click **Site Configuration**.</span></span>
    
5. <span data-ttu-id="eb1f6-148">En **Seleccionar un sitio**, seleccione el sitio que necesita configurar para el archivado.</span><span class="sxs-lookup"><span data-stu-id="eb1f6-148">In **Select a Site**, select the site to be configured for archiving.</span></span>
    
6. <span data-ttu-id="eb1f6-149">En **Nueva configuración de archivado**, vaya al cuadro de lista desplegable **Configuración de archivado** y siga uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="eb1f6-149">In **New Archiving Setting**, in the **Archiving setting** drop-down list box, do one of the following:</span></span>
    
   - <span data-ttu-id="eb1f6-150">Para habilitar el archivado solo para las sesiones de mensajería instantánea (MI), haga clic en **Archivar sesiones de mensajería instantánea (MI)**.</span><span class="sxs-lookup"><span data-stu-id="eb1f6-150">To enable archiving only for instant messaging (IM) sessions, click **Archive IM sessions**.</span></span>
    
   - <span data-ttu-id="eb1f6-151">Para habilitar el archivado tanto para las sesiones de mensajería instantánea (MI) y las conferencias, haga clic en **Archivar sesiones de mensajería instantánea y conferencias web**.</span><span class="sxs-lookup"><span data-stu-id="eb1f6-151">To enable archiving for both IM sessions and conferences, click **Archive IM and web conferencing sessions**.</span></span>
    
   - <span data-ttu-id="eb1f6-152">A fin de deshabilitar el archivado de la directiva, haga clic en **Deshabilitar archivado**.</span><span class="sxs-lookup"><span data-stu-id="eb1f6-152">To disable archiving for the policy, click **Disable archiving**.</span></span>
    
7. <span data-ttu-id="eb1f6-153">Además, en **Nueva configuración de archivado**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="eb1f6-153">Also in **New Archiving Setting**, do the following:</span></span>
    
   - <span data-ttu-id="eb1f6-154">Para bloquear la actividad cuando el archivado no está disponible, active la casilla **Bloquear sesiones de mensajería instantánea (MI) o de conferencias web si no se pueden archivar**.</span><span class="sxs-lookup"><span data-stu-id="eb1f6-154">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
   - <span data-ttu-id="eb1f6-155">Para usar Microsoft Exchange Server para almacenar datos de archivado, haga clic en la casilla de verificación **integración con Microsoft Exchange** .</span><span class="sxs-lookup"><span data-stu-id="eb1f6-155">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="eb1f6-156">Para habilitar la purga de datos, active la casilla **Habilitar purgado de los datos de archivado** y realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="eb1f6-156">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
    
   - <span data-ttu-id="eb1f6-157">Para especificar la purga al transcurrir una cantidad de días determinada, haga clic en **Purgar los datos de archivado exportados y los datos de archivado almacenados tras la duración máxima (días)** y especifique la cantidad de días.</span><span class="sxs-lookup"><span data-stu-id="eb1f6-157">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
   - <span data-ttu-id="eb1f6-158">Para limitar la purga de los datos de archivado que se han exportado, haga clic en **Purgar solo datos de archivado exportados**.</span><span class="sxs-lookup"><span data-stu-id="eb1f6-158">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>
    
8. <span data-ttu-id="eb1f6-159">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="eb1f6-159">Click **Commit**.</span></span>
    
## <a name="configure-pool-level-archiving-options"></a><span data-ttu-id="eb1f6-160">Configurar las opciones de archivado en el grupo</span><span class="sxs-lookup"><span data-stu-id="eb1f6-160">Configure pool level archiving options</span></span>

<span data-ttu-id="eb1f6-p106">Puede especificar las opciones de archivado para un grupo específico. Una configuración de grupo reemplaza la configuración global y de sitio, pero solo para el grupo especificado en la configuración de grupo.</span><span class="sxs-lookup"><span data-stu-id="eb1f6-p106">You can specify archiving options for a specific pool. A pool configuration overrides the global configuration and site configuration, but only for the pool specified in the pool configuration.</span></span>
  
1. <span data-ttu-id="eb1f6-163">Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="eb1f6-163">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="eb1f6-164">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="eb1f6-164">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="eb1f6-165">En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, después, en **Configuración de archivado**.</span><span class="sxs-lookup"><span data-stu-id="eb1f6-165">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="eb1f6-166">En la página **Configuración de archivado**, haga clic en **Nuevo** y, luego, haga clic en **Configuración de grupo**.</span><span class="sxs-lookup"><span data-stu-id="eb1f6-166">On the **Archiving Configuration** page, click **New**, and then click **Pool Configuration**.</span></span>
    
5. <span data-ttu-id="eb1f6-167">En **Seleccionar un servicio**, seleccione el grupo que desea configurar para el archivado.</span><span class="sxs-lookup"><span data-stu-id="eb1f6-167">In **Select a Service**, select the pool to be configured for archiving.</span></span>
    
6. <span data-ttu-id="eb1f6-168">En **Nueva configuración de archivado**, en la lista desplegable **Configuración de archivado**, seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="eb1f6-168">In **New Archiving Setting**, in the **Archiving setting** drop-down list, select one of the following archiving options:</span></span>
    
   - <span data-ttu-id="eb1f6-169">**Deshabilitar archivado**</span><span class="sxs-lookup"><span data-stu-id="eb1f6-169">**Disable archiving**</span></span>
    
   - <span data-ttu-id="eb1f6-170">**Archivar sesiones de mensajería instantánea (MI)**</span><span class="sxs-lookup"><span data-stu-id="eb1f6-170">**Archive IM sessions**</span></span>
    
   - <span data-ttu-id="eb1f6-171">**Archivar sesiones de mensajería instantánea (MI) y conferencias web**</span><span class="sxs-lookup"><span data-stu-id="eb1f6-171">**Archive IM and web conferencing sessions**</span></span>
    
7. <span data-ttu-id="eb1f6-172">Además, en la página **Nueva configuración de archivado**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="eb1f6-172">Also in **New Archiving Setting** page, do the following:</span></span>
    
   - <span data-ttu-id="eb1f6-173">Para bloquear la actividad cuando el archivado no está disponible, active la casilla **Bloquear sesiones de mensajería instantánea (MI) o de conferencias web si no se pueden archivar**.</span><span class="sxs-lookup"><span data-stu-id="eb1f6-173">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
   - <span data-ttu-id="eb1f6-174">Para usar Microsoft Exchange Server para almacenar datos de archivado, haga clic en la casilla de verificación **integración con Microsoft Exchange** .</span><span class="sxs-lookup"><span data-stu-id="eb1f6-174">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="eb1f6-175">Para habilitar la purga de datos, active la casilla **Habilitar purgado de los datos de archivado** y realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="eb1f6-175">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
    
   - <span data-ttu-id="eb1f6-176">Para especificar la purga al transcurrir una cantidad de días determinada, haga clic en **Purgar los datos de archivado exportados y los datos de archivado almacenados tras la duración máxima (días)** y especifique la cantidad de días.</span><span class="sxs-lookup"><span data-stu-id="eb1f6-176">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
   - <span data-ttu-id="eb1f6-177">Para limitar la purga de los datos de archivado que se han exportado, haga clic en **Purgar solo datos de archivado exportados**.</span><span class="sxs-lookup"><span data-stu-id="eb1f6-177">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>
    
8. <span data-ttu-id="eb1f6-178">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="eb1f6-178">Click **Commit**.</span></span>
    

