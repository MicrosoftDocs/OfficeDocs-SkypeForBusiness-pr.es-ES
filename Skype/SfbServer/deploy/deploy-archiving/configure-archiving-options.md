---
title: Configurar las opciones de archivado para Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2f534697-ac7f-45b7-8cdc-ba67f052223b
description: 'Resumen: lea este tema para obtener información sobre cómo configurar las opciones de archivado iniciales para Skype Empresarial Server. Las configuraciones de archivado se establecen inicialmente al implementar el archivado, pero puede cambiar, agregar y eliminar configuraciones después de la implementación.'
ms.openlocfilehash: 0a4803b821ee082a548b9f429b9596fd8019500f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815540"
---
# <a name="configure-archiving-options-for-skype-for-business-server"></a><span data-ttu-id="c04b5-104">Configurar las opciones de archivado para Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="c04b5-104">Configure archiving options for Skype for Business Server</span></span>
 
<span data-ttu-id="c04b5-105">**Resumen:** Lea este tema para obtener información sobre cómo configurar las opciones de archivado iniciales para Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="c04b5-105">**Summary:** Read this topic to learn how to configure initial archiving options for Skype for Business Server.</span></span> <span data-ttu-id="c04b5-106">Las configuraciones de archivado se establecen inicialmente al implementar el archivado, pero puede cambiar, agregar y eliminar configuraciones después de la implementación.</span><span class="sxs-lookup"><span data-stu-id="c04b5-106">You initially set up archiving configurations when you deploy archiving, but you can change, add, and delete configurations after deployment.</span></span>
  
<span data-ttu-id="c04b5-107">Para configurar las configuraciones de archivado iniciales, use el Panel de control de Skype Empresarial Server para especificar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c04b5-107">To configure initial archiving configurations, you use Skype for Business Server Control Panel to specify the following:</span></span>
  
- <span data-ttu-id="c04b5-108">Configuración de nivel global que se crea de forma predeterminada al implementar Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="c04b5-108">Global-level configuration that is created by default when you deploy Skype for Business Server</span></span>
    
- <span data-ttu-id="c04b5-109">Configuraciones de nivel de sitio opcionales que especifican cómo se implementa el archivado para un sitio específico</span><span class="sxs-lookup"><span data-stu-id="c04b5-109">Optional site-level configurations that specify how archiving is implemented for a specific site</span></span>
    
- <span data-ttu-id="c04b5-110">Configuraciones opcionales de nivel de grupo que especifican cómo se implementa el archivado para un grupo específico</span><span class="sxs-lookup"><span data-stu-id="c04b5-110">Optional pool-level configurations that specify how archiving is implemented for a specific pool</span></span>
    
<span data-ttu-id="c04b5-111">Tendrá que configurar las opciones para lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c04b5-111">You will need to configure options for the following:</span></span>
  
- <span data-ttu-id="c04b5-112">Si se habilita o deshabilita el archivado</span><span class="sxs-lookup"><span data-stu-id="c04b5-112">Whether to enable or disable archiving</span></span>
    
- <span data-ttu-id="c04b5-113">Si se archivarán las sesiones de mensajería instantánea</span><span class="sxs-lookup"><span data-stu-id="c04b5-113">Whether to archive IM sessions</span></span>
    
- <span data-ttu-id="c04b5-114">Si se archivarán las sesiones de conferencia web</span><span class="sxs-lookup"><span data-stu-id="c04b5-114">Whether to archive web conferencing sessions</span></span>
    
- <span data-ttu-id="c04b5-115">Si se va a bloquear la actividad cuando el archivado no está disponible</span><span class="sxs-lookup"><span data-stu-id="c04b5-115">Whether to block activity when archiving is not available</span></span>
    
- <span data-ttu-id="c04b5-116">Si se va a usar la integración de Exchange</span><span class="sxs-lookup"><span data-stu-id="c04b5-116">Whether to use Exchange integration</span></span>
    
- <span data-ttu-id="c04b5-117">Cómo configurar la purga y exportación de datos</span><span class="sxs-lookup"><span data-stu-id="c04b5-117">How to set up purging and exporting of data</span></span>
    
> [!NOTE]
> <span data-ttu-id="c04b5-118">Debe especificar todas las opciones adecuadas antes de habilitar el archivado.</span><span class="sxs-lookup"><span data-stu-id="c04b5-118">You should specify all appropriate options before enabling archiving.</span></span> 
  
<span data-ttu-id="c04b5-119">Para obtener más información sobre cómo se implementan las configuraciones de archivado, incluidas las opciones que puede especificar y la jerarquía de las configuraciones de archivado, consulte [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span><span class="sxs-lookup"><span data-stu-id="c04b5-119">For details about how archiving configurations are implemented, including which options you can specify and the hierarchy of archiving configurations, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span> <span data-ttu-id="c04b5-120">Para obtener más información sobre cómo administrar las configuraciones después de la implementación mediante el Panel de control o mediante Windows PowerShell, consulte Administrar las opciones de archivado [en Skype Empresarial Server.](../../manage/archiving/options.md)</span><span class="sxs-lookup"><span data-stu-id="c04b5-120">For details about how to manage configurations after deployment by using the Control Panel or by using Windows PowerShell, see [Manage archiving options in Skype for Business Server](../../manage/archiving/options.md).</span></span>
  
## <a name="configure-global-level-archiving-options"></a><span data-ttu-id="c04b5-121">Configurar las opciones de archivado de nivel global</span><span class="sxs-lookup"><span data-stu-id="c04b5-121">Configure global level archiving options</span></span>

<span data-ttu-id="c04b5-122">Cuando agrega archivado a la topología y publica la topología, Skype Empresarial Server crea una configuración global para el archivado.</span><span class="sxs-lookup"><span data-stu-id="c04b5-122">When you add archiving to your topology and publish the topology, Skype for Business Server creates a global configuration for archiving.</span></span> <span data-ttu-id="c04b5-123">De forma predeterminada, no hay opciones de archivado habilitadas en la configuración global.</span><span class="sxs-lookup"><span data-stu-id="c04b5-123">By default, no archiving options are enabled in the global configuration.</span></span> <span data-ttu-id="c04b5-124">La configuración global controla qué opciones se habilitan para su completa implementación, a menos que realice configuraciones de sitio o grupo de servidores, que omiten la configuración global.</span><span class="sxs-lookup"><span data-stu-id="c04b5-124">The global configuration controls which options are enabled for your entire deployment, unless you set up site or pool configurations, which override the global configuration.</span></span>
  
<span data-ttu-id="c04b5-125">Para configurar las opciones de archivado en el nivel global:</span><span class="sxs-lookup"><span data-stu-id="c04b5-125">To configure archiving options at the global level:</span></span>
  
1. <span data-ttu-id="c04b5-126">Desde una cuenta de usuario asignada al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="c04b5-126">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="c04b5-127">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="c04b5-127">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="c04b5-128">En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, a continuación, haga clic en **Configuración de archivado**.</span><span class="sxs-lookup"><span data-stu-id="c04b5-128">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="c04b5-129">En la página **Configuración de archivado**, haga clic en **Global**, **Editar** y **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="c04b5-129">On the **Archiving Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="c04b5-130">En **Editar configuración de archivado: global**, en la lista desplegable **Configuración de archivado**, seleccione una de las siguientes opciones de archivado:</span><span class="sxs-lookup"><span data-stu-id="c04b5-130">In **Edit Archiving Setting - Global**, in the **Archiving setting** drop-down list, select one of the following archiving options:</span></span>
    
   - <span data-ttu-id="c04b5-131">**Deshabilitar archivado**</span><span class="sxs-lookup"><span data-stu-id="c04b5-131">**Disable archiving**</span></span>
    
   - <span data-ttu-id="c04b5-132">**Archivar sesiones de mensajería instantánea**</span><span class="sxs-lookup"><span data-stu-id="c04b5-132">**Archive IM sessions**</span></span>
    
   - <span data-ttu-id="c04b5-133">**Archivar mensajería instantánea y sesiones de conferencias web**</span><span class="sxs-lookup"><span data-stu-id="c04b5-133">**Archive IM and web conferencing sessions**</span></span>
    
6. <span data-ttu-id="c04b5-134">También en la **página Editar configuración de archivado - Global,** haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c04b5-134">Also on the **Edit Archiving Setting - Global** page, do the following:</span></span>
    
   - <span data-ttu-id="c04b5-135">Para bloquear la actividad cuando el archivado no está disponible, active la casilla **Bloquear las sesiones de mensajería instantánea (MI) o conferencias web si se produce algún error en el archivado**.</span><span class="sxs-lookup"><span data-stu-id="c04b5-135">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
   - <span data-ttu-id="c04b5-136">Para usar Microsoft Exchange Server almacenar datos de archivado, haga clic en la casilla de **integración de Microsoft Exchange.**</span><span class="sxs-lookup"><span data-stu-id="c04b5-136">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="c04b5-137">Para habilitar la purga de datos, active la casilla **Habilitar purga de los datos de archivado** y realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="c04b5-137">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
    
   - <span data-ttu-id="c04b5-138">Para especificar la purga al transcurrir un número de días determinado, haga clic en **Purgar los datos de archivado exportados y los datos de archivado almacenados tras la duración máxima (días)** y especifique los días.</span><span class="sxs-lookup"><span data-stu-id="c04b5-138">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
   - <span data-ttu-id="c04b5-139">Para limitar la purga de los datos archivados que se han exportado, haga clic en **Purgar solo datos archivados exportados**.</span><span class="sxs-lookup"><span data-stu-id="c04b5-139">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>
    
7. <span data-ttu-id="c04b5-140">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="c04b5-140">Click **Commit**.</span></span>
    
## <a name="configure-site-level-archiving-options"></a><span data-ttu-id="c04b5-141">Configurar las opciones de archivado de nivel de sitio</span><span class="sxs-lookup"><span data-stu-id="c04b5-141">Configure site level archiving options</span></span>

<span data-ttu-id="c04b5-142">Puede especificar opciones de archivado para un sitio específico.</span><span class="sxs-lookup"><span data-stu-id="c04b5-142">You can specify archiving options for a specific site.</span></span> <span data-ttu-id="c04b5-143">Una configuración de sitio invalida la configuración global, pero solo para el sitio especificado en la configuración del sitio.</span><span class="sxs-lookup"><span data-stu-id="c04b5-143">A site configuration overrides the global configuration, but only for the site specified in the site configuration.</span></span> 
  
1. <span data-ttu-id="c04b5-144">Desde una cuenta de usuario asignada al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="c04b5-144">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="c04b5-145">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="c04b5-145">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="c04b5-146">En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, a continuación, haga clic en **Configuración de archivado**.</span><span class="sxs-lookup"><span data-stu-id="c04b5-146">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="c04b5-147">En la página **Configuración de** archivado, haga clic **en Nuevo** y, a continuación, en Configuración **del sitio.**</span><span class="sxs-lookup"><span data-stu-id="c04b5-147">On the **Archiving Configuration** page, click **New**, and then click **Site Configuration**.</span></span>
    
5. <span data-ttu-id="c04b5-148">En **Seleccionar un sitio**, seleccione el sitio que debe configurarse para el archivado.</span><span class="sxs-lookup"><span data-stu-id="c04b5-148">In **Select a Site**, select the site to be configured for archiving.</span></span>
    
6. <span data-ttu-id="c04b5-149">En **Nueva configuración de archivado**, vaya al cuadro de lista desplegable **Configuración de archivado** y siga uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="c04b5-149">In **New Archiving Setting**, in the **Archiving setting** drop-down list box, do one of the following:</span></span>
    
   - <span data-ttu-id="c04b5-150">Para habilitar el archivado solo para las sesiones de mensajería instantánea, haga clic en **Archivar sesiones de mensajería instantánea**.</span><span class="sxs-lookup"><span data-stu-id="c04b5-150">To enable archiving only for instant messaging (IM) sessions, click **Archive IM sessions**.</span></span>
    
   - <span data-ttu-id="c04b5-151">Para habilitar el archivado para sesiones de mensajería instantánea y conferencias, haga clic en Archivar sesiones de mensajería instantánea **y conferencia web.**</span><span class="sxs-lookup"><span data-stu-id="c04b5-151">To enable archiving for both IM sessions and conferences, click **Archive IM and web conferencing sessions**.</span></span>
    
   - <span data-ttu-id="c04b5-152">Para deshabilitar el archivado para la directiva, haga clic en **Deshabilitar archivado**.</span><span class="sxs-lookup"><span data-stu-id="c04b5-152">To disable archiving for the policy, click **Disable archiving**.</span></span>
    
7. <span data-ttu-id="c04b5-153">Además, en **Nueva configuración de archivado**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c04b5-153">Also in **New Archiving Setting**, do the following:</span></span>
    
   - <span data-ttu-id="c04b5-154">Para bloquear la actividad cuando el archivado no está disponible, active la casilla **Bloquear las sesiones de mensajería instantánea (MI) o conferencias web si se produce algún error en el archivado**.</span><span class="sxs-lookup"><span data-stu-id="c04b5-154">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
   - <span data-ttu-id="c04b5-155">Para usar Microsoft Exchange Server almacenar datos de archivado, haga clic en la casilla de **integración de Microsoft Exchange.**</span><span class="sxs-lookup"><span data-stu-id="c04b5-155">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="c04b5-156">Para habilitar la purga de datos, active la casilla **Habilitar purga de los datos de archivado** y realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="c04b5-156">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
    
   - <span data-ttu-id="c04b5-157">Para especificar la purga al transcurrir un número de días determinado, haga clic en **Purgar los datos de archivado exportados y los datos de archivado almacenados tras la duración máxima (días)** y especifique los días.</span><span class="sxs-lookup"><span data-stu-id="c04b5-157">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
   - <span data-ttu-id="c04b5-158">Para limitar la purga de los datos archivados que se han exportado, haga clic en **Purgar solo datos archivados exportados**.</span><span class="sxs-lookup"><span data-stu-id="c04b5-158">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>
    
8. <span data-ttu-id="c04b5-159">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="c04b5-159">Click **Commit**.</span></span>
    
## <a name="configure-pool-level-archiving-options"></a><span data-ttu-id="c04b5-160">Configurar las opciones de archivado de nivel de grupo</span><span class="sxs-lookup"><span data-stu-id="c04b5-160">Configure pool level archiving options</span></span>

<span data-ttu-id="c04b5-161">Puede especificar las opciones de archivado para un grupo específico.</span><span class="sxs-lookup"><span data-stu-id="c04b5-161">You can specify archiving options for a specific pool.</span></span> <span data-ttu-id="c04b5-162">La configuración de un grupo de servidores anula la configuración global y de sitio, pero únicamente para el grupo de servidores especificad en la configuración del grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="c04b5-162">A pool configuration overrides the global configuration and site configuration, but only for the pool specified in the pool configuration.</span></span>
  
1. <span data-ttu-id="c04b5-163">Desde una cuenta de usuario asignada al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="c04b5-163">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="c04b5-164">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="c04b5-164">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="c04b5-165">En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, a continuación, haga clic en **Configuración de archivado**.</span><span class="sxs-lookup"><span data-stu-id="c04b5-165">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="c04b5-166">En la página **Configuración de archivado**, haga clic en **Nuevo** y en **Directiva de grupo**.</span><span class="sxs-lookup"><span data-stu-id="c04b5-166">On the **Archiving Configuration** page, click **New**, and then click **Pool Configuration**.</span></span>
    
5. <span data-ttu-id="c04b5-167">En **Seleccione un servicio**, seleccione el grupo de servidores que desea configurar para el archivado.</span><span class="sxs-lookup"><span data-stu-id="c04b5-167">In **Select a Service**, select the pool to be configured for archiving.</span></span>
    
6. <span data-ttu-id="c04b5-168">En **Nueva configuración de archivado**, en la lista desplegable **Configuración de archivado**, seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="c04b5-168">In **New Archiving Setting**, in the **Archiving setting** drop-down list, select one of the following archiving options:</span></span>
    
   - <span data-ttu-id="c04b5-169">**Deshabilitar archivado**</span><span class="sxs-lookup"><span data-stu-id="c04b5-169">**Disable archiving**</span></span>
    
   - <span data-ttu-id="c04b5-170">**Archivar sesiones de mensajería instantánea**</span><span class="sxs-lookup"><span data-stu-id="c04b5-170">**Archive IM sessions**</span></span>
    
   - <span data-ttu-id="c04b5-171">**Archivar sesiones de MI y conferencias**</span><span class="sxs-lookup"><span data-stu-id="c04b5-171">**Archive IM and web conferencing sessions**</span></span>
    
7. <span data-ttu-id="c04b5-172">Además, en la página **Nueva configuración de archivado**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c04b5-172">Also in **New Archiving Setting** page, do the following:</span></span>
    
   - <span data-ttu-id="c04b5-173">Para bloquear la actividad cuando el archivado no está disponible, active la casilla  **Bloquear las sesiones de mensajería instantánea (MI) o conferencias si se produce algún error en el archivado**.</span><span class="sxs-lookup"><span data-stu-id="c04b5-173">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
   - <span data-ttu-id="c04b5-174">Para usar Microsoft Exchange Server almacenar datos de archivado, haga clic en la casilla de **integración de Microsoft Exchange.**</span><span class="sxs-lookup"><span data-stu-id="c04b5-174">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="c04b5-175">Para habilitar la purga de datos, active la casilla **Habilitar purga de los datos de archivado** y realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="c04b5-175">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
    
   - <span data-ttu-id="c04b5-176">Para especificar la purga al transcurrir un número de días determinado, haga clic en **Purgar los datos de archivado exportados y los datos de archivado almacenados tras la duración máxima (días)** y especifique los días.</span><span class="sxs-lookup"><span data-stu-id="c04b5-176">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
   - <span data-ttu-id="c04b5-177">Para limitar la purga de los datos archivados que se han exportado, haga clic en **Purgar solo datos archivados exportados**.</span><span class="sxs-lookup"><span data-stu-id="c04b5-177">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>
    
8. <span data-ttu-id="c04b5-178">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="c04b5-178">Click **Commit**.</span></span>
    

