---
title: Expansor de configuración general del chat persistente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.PersistentChatGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 275ee1ae-ca58-4963-bc95-523319f90d96
description: 'Puede editar la configuración general para el servidor de chat persistente o el grupo de servidores de chat persistente mediante la configuración o definición de estas propiedades:'
ms.openlocfilehash: 5c0884f4877e622a82b58ea914ffa934eecc3291
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823860"
---
# <a name="persistent-chat-general-settings-expander"></a><span data-ttu-id="e8ea7-103">Expansor de configuración general del chat persistente</span><span class="sxs-lookup"><span data-stu-id="e8ea7-103">Persistent Chat General Settings Expander</span></span>
 
<span data-ttu-id="e8ea7-104">Puede editar la configuración **general** para el servidor de chat persistente o el grupo de servidores de chat persistente mediante la configuración o definición de estas propiedades:</span><span class="sxs-lookup"><span data-stu-id="e8ea7-104">You edit the **General** settings for the Persistent Chat Server or Persistent Chat Server pool by configuring or defining these properties:</span></span>
  
 <span data-ttu-id="e8ea7-105">**General**</span><span class="sxs-lookup"><span data-stu-id="e8ea7-105">**General**</span></span>
  
- <span data-ttu-id="e8ea7-106">**FQDN:** edite esta configuración para definir el nombre de dominio completo de su servidor de chat persistente o grupo de servidores de chat persistente</span><span class="sxs-lookup"><span data-stu-id="e8ea7-106">**FQDN**: Edit this setting to define the fully qualified domain name of your Persistent Chat Server or Persistent Chat Server pool</span></span>
    
- <span data-ttu-id="e8ea7-107">**Mostrar nombre del grupo de servidores de chat persistente**: defina esta configuración para proporcionar una configuración comprensible y fácil de usar para el servidor o el grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="e8ea7-107">**Display name of the Persistent Chat pool**: Define this setting to provide a user friendly and user readable setting for the server or pool.</span></span> <span data-ttu-id="e8ea7-108">Esta configuración facilitará a los usuarios la asociación de un determinado servidor de chat persistente o grupo de servidores de chat persistente en función del nombre para mostrar en lugar de un nombre de dominio completo más difícil de entender.</span><span class="sxs-lookup"><span data-stu-id="e8ea7-108">This setting will make it easier for your users to associate a given Persistent Chat Server or Persistent Chat Server pool based on the display name instead of a more difficult to understand fully qualified domain name.</span></span>
    
- <span data-ttu-id="e8ea7-109">**Puerto de chat persistente**: especifique el puerto que se debe usar para el chat persistente.</span><span class="sxs-lookup"><span data-stu-id="e8ea7-109">**Persistent Chat port**: Specify the port to use for Persistent Chat.</span></span>
    
<span data-ttu-id="e8ea7-110">Puede editar la configuración **de** asociaciones para el servidor de chat persistente o el grupo de servidores de chat persistente mediante la configuración o definición de estas propiedades:</span><span class="sxs-lookup"><span data-stu-id="e8ea7-110">You edit the **Associations** settings for the Persistent Chat Server or Persistent Chat Server pool by configuring or defining these properties:</span></span>
  
 <span data-ttu-id="e8ea7-111">**Asociaciones**</span><span class="sxs-lookup"><span data-stu-id="e8ea7-111">**Associations**</span></span>
  
- <span data-ttu-id="e8ea7-112">**SQL Server:** seleccione el almacén de SQL Server y la instancia con nombre opcional de la lista.</span><span class="sxs-lookup"><span data-stu-id="e8ea7-112">**SQL Server store**: Select the SQL Server store and optional named instance from the list.</span></span>
    
    <span data-ttu-id="e8ea7-113">Haga clic en **Nuevo** para definir un nuevo almacén y una instancia opcional de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e8ea7-113">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="e8ea7-114">Active la **casilla SQL Server creación** de reflejos del almacén si desea habilitar la creación de reflejos para el almacén de SQL Server principal.</span><span class="sxs-lookup"><span data-stu-id="e8ea7-114">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the primary SQL Server store.</span></span>
    
    <span data-ttu-id="e8ea7-115">Si decidió habilitar la creación SQL Server reflejo del almacén, seleccione el almacén y la instancia de la lista Creación de **reflejos SQL Server almacén.**</span><span class="sxs-lookup"><span data-stu-id="e8ea7-115">If you chose to enable SQL Server store mirroring, select the store and instance from the list **Mirroring SQL Server store**.</span></span>
    
    <span data-ttu-id="e8ea7-116">Haga clic en **Nuevo** para definir un nuevo almacén y una instancia opcional de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e8ea7-116">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="e8ea7-117">Active la **casilla SQL Server** testigo de creación de reflejo para habilitar la conmutación por error automática si desea la conmutación por error automática del almacén de SQL Server principal.</span><span class="sxs-lookup"><span data-stu-id="e8ea7-117">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the primary SQL Server store.</span></span>
    
    <span data-ttu-id="e8ea7-118">Si decidió habilitar un testigo de creación SQL Server reflejo del almacén para habilitar la conmutación por error automática, seleccione el almacén y la instancia de la lista.</span><span class="sxs-lookup"><span data-stu-id="e8ea7-118">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="e8ea7-119">Haga clic en **Nuevo** para definir un nuevo almacén de SQL Server y una instancia opcional para el almacén testigo.</span><span class="sxs-lookup"><span data-stu-id="e8ea7-119">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="e8ea7-120">Active la **casilla Usar almacenes de SQL Server** copia de seguridad para habilitar la recuperación ante desastres si desea habilitar el uso de SQL Server recuperación ante desastres</span><span class="sxs-lookup"><span data-stu-id="e8ea7-120">Select the **Use backup SQL Server stores to enable disaster recovery** check box if you want to enable the use of SQL Server disaster recovery</span></span>
    
    <span data-ttu-id="e8ea7-121">Si decidió habilitar la recuperación ante desastres, seleccione un almacén y una instancia de la lista **Almacén de SQL Server de reserva**.</span><span class="sxs-lookup"><span data-stu-id="e8ea7-121">If you chose to enable disaster recovery, select a store and instance from the **Backup SQL Server store** list.</span></span>
    
    <span data-ttu-id="e8ea7-122">Haga clic en **Nuevo** para definir un nuevo almacén y una instancia opcional de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e8ea7-122">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="e8ea7-123">Active la **casilla SQL Server creación** de reflejos del almacén si desea habilitar la creación de reflejos para el almacén de creación de SQL Server copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="e8ea7-123">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the backup SQL Server mirroring store.</span></span>
    
    <span data-ttu-id="e8ea7-124">Si decidió habilitar la creación de reflejos de SQL Server copia de seguridad, seleccione el almacén y la instancia de la lista Copia de seguridad **SQL Server reflejo del almacén.**</span><span class="sxs-lookup"><span data-stu-id="e8ea7-124">If you chose to enable backup SQL Server store mirroring, select the store and instance from the list **Backup SQL Server store mirror**.</span></span>
    
    <span data-ttu-id="e8ea7-125">Haga clic en **Nuevo** para definir un nuevo almacén y una instancia opcional de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e8ea7-125">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="e8ea7-126">Active la **casilla Usar SQL Server** testigo de creación de reflejo para habilitar la conmutación por error automática si desea que la conmutación por error automática de la copia de seguridad SQL Server almacén.</span><span class="sxs-lookup"><span data-stu-id="e8ea7-126">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the backup SQL Server store.</span></span>
    
    <span data-ttu-id="e8ea7-127">Si decidió habilitar un testigo de creación SQL Server reflejo del almacén para habilitar la conmutación por error automática, seleccione el almacén y la instancia de la lista.</span><span class="sxs-lookup"><span data-stu-id="e8ea7-127">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="e8ea7-128">Haga clic en **Nuevo** para definir un nuevo almacén de SQL Server y una instancia opcional para el almacén testigo.</span><span class="sxs-lookup"><span data-stu-id="e8ea7-128">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="e8ea7-129">Active la casilla **Habilitar cumplimiento** si desea habilitar el uso de una base de datos de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="e8ea7-129">Select the **Enable compliance** check box if you want to enable the use of a compliance database</span></span>
    
    <span data-ttu-id="e8ea7-130">Si decidió habilitar el cumplimiento, seleccione un almacén y una instancia de la lista **Almacén de SQL Server de cumplimiento**.</span><span class="sxs-lookup"><span data-stu-id="e8ea7-130">If you chose to enable compliance, select a store and instance from the **Compliance SQL Server store** list.</span></span>
    
    <span data-ttu-id="e8ea7-131">Haga clic en **Nuevo** para definir un nuevo almacén y una instancia opcional de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e8ea7-131">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="e8ea7-132">Active la **casilla SQL Server creación** de reflejo del almacén si desea habilitar la creación de reflejos para el almacén de SQL Server cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="e8ea7-132">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the compliance SQL Server store.</span></span>
    
    <span data-ttu-id="e8ea7-133">Si decidió habilitar la creación de reflejos SQL Server del almacén, seleccione el almacén y la instancia de la lista **Cumplimiento SQL Server reflejo del almacén.**</span><span class="sxs-lookup"><span data-stu-id="e8ea7-133">If you chose to enable compliance SQL Server store mirroring, select the store and instance from the list **Compliance SQL Server store mirror**.</span></span>
    
    <span data-ttu-id="e8ea7-134">Haga clic en **Nuevo** para definir un nuevo almacén y una instancia opcional de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e8ea7-134">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="e8ea7-135">Active la **casilla Usar SQL Server** testigo de creación de reflejo para habilitar la conmutación por error automática si desea la conmutación por error automática del almacén de SQL Server cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="e8ea7-135">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the compliance SQL Server store.</span></span>
    
    <span data-ttu-id="e8ea7-136">Si decidió habilitar un testigo de creación SQL Server reflejo del almacén para habilitar la conmutación por error automática, seleccione el almacén y la instancia de la lista.</span><span class="sxs-lookup"><span data-stu-id="e8ea7-136">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="e8ea7-137">Haga clic en **Nuevo** para definir un nuevo almacén de SQL Server y una instancia opcional para el almacén testigo.</span><span class="sxs-lookup"><span data-stu-id="e8ea7-137">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="e8ea7-138">Si decidió habilitar el cumplimiento, seleccione un almacén y una instancia de la lista **Almacén de SQL Server de cumplimiento de reserva**.</span><span class="sxs-lookup"><span data-stu-id="e8ea7-138">If you chose to enable compliance, select a store and instance from the **Backup compliance SQL Server store** list.</span></span>
    
    <span data-ttu-id="e8ea7-139">Haga clic en **Nuevo** para definir un nuevo almacén y una instancia opcional de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e8ea7-139">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="e8ea7-140">Active la **casilla SQL Server creación** de reflejo del almacén si desea habilitar la creación de reflejos para el almacén de SQL Server cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="e8ea7-140">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the compliance SQL Server store.</span></span>
    
    <span data-ttu-id="e8ea7-141">Si decidió habilitar la creación de reflejos de SQL Server cumplimiento, seleccione el almacén y la instancia de la lista Cumplimiento de copia de seguridad **SQL Server reflejo del almacén.**</span><span class="sxs-lookup"><span data-stu-id="e8ea7-141">If you chose to enable compliance SQL Server store mirroring, select the store and instance from the list **Backup compliance SQL Server store mirror**.</span></span>
    
    <span data-ttu-id="e8ea7-142">Haga clic en **Nuevo** para definir un nuevo almacén y una instancia opcional de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e8ea7-142">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="e8ea7-143">Active la **casilla Usar SQL Server** testigo de creación de reflejo para habilitar la conmutación por error automática si desea que la conmutación por error automática de la copia de seguridad SQL Server almacén.</span><span class="sxs-lookup"><span data-stu-id="e8ea7-143">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the backup compliance SQL Server store.</span></span>
    
    <span data-ttu-id="e8ea7-144">Si decidió habilitar un testigo de creación SQL Server reflejo del almacén para habilitar la conmutación por error automática, seleccione el almacén y la instancia de la lista.</span><span class="sxs-lookup"><span data-stu-id="e8ea7-144">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="e8ea7-145">Haga clic en **Nuevo** para definir un nuevo almacén de SQL Server y una instancia opcional para el almacén testigo.</span><span class="sxs-lookup"><span data-stu-id="e8ea7-145">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="e8ea7-146">**Almacén de archivos** Seleccione una ubicación de almacén de archivos de la lista o haga clic en **Nuevo** para crear un nuevo almacén de archivos.</span><span class="sxs-lookup"><span data-stu-id="e8ea7-146">**File store** Select a file store location from the list, or click **New** to create a new file store.</span></span>
    
  <span data-ttu-id="e8ea7-147">**Aceptar** Acepta y confirma los cambios realizados en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="e8ea7-147">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="e8ea7-148">**Cancelar** Descarta los cambios y cierra el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="e8ea7-148">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="e8ea7-149">**Ayuda** Muestra la ayuda de esta pantalla.</span><span class="sxs-lookup"><span data-stu-id="e8ea7-149">**Help** Displays this help screen.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e8ea7-150">Vea también</span><span class="sxs-lookup"><span data-stu-id="e8ea7-150">See also</span></span>

[<span data-ttu-id="e8ea7-151">Planear el servidor de chat persistente en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="e8ea7-151">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="e8ea7-152">Agregar un servidor de chat persistente a la topología de Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="e8ea7-152">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[<span data-ttu-id="e8ea7-153">Configurar la alta disponibilidad y la recuperación ante desastres para el servidor de chat persistente en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="e8ea7-153">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
