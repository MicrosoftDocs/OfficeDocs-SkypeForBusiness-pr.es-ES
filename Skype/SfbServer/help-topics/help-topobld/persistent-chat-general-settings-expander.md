---
title: Expansor de configuración general del chat persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.PersistentChatGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 275ee1ae-ca58-4963-bc95-523319f90d96
description: 'Para editar la configuración general del servidor de chat persistente o del grupo de servidores de chat persistente, configure o defina estas propiedades:'
ms.openlocfilehash: d44818efa1909e0fd90e4c80fcd88b3d11a616ea
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41819482"
---
# <a name="persistent-chat-general-settings-expander"></a><span data-ttu-id="313a4-103">Expansor de configuración general del chat persistente</span><span class="sxs-lookup"><span data-stu-id="313a4-103">Persistent Chat General Settings Expander</span></span>
 
<span data-ttu-id="313a4-104">Para editar la configuración **General** del servidor de chat persistente o del grupo de servidores de chat persistente, configure o defina estas propiedades:</span><span class="sxs-lookup"><span data-stu-id="313a4-104">You edit the **General** settings for the Persistent Chat Server or Persistent Chat Server pool by configuring or defining these properties:</span></span>
  
 <span data-ttu-id="313a4-105">**General**</span><span class="sxs-lookup"><span data-stu-id="313a4-105">**General**</span></span>
  
- <span data-ttu-id="313a4-106">**FQDN**: Edite esta configuración para definir el nombre de dominio completo del servidor de chat persistente o del grupo de servidores de chat persistente</span><span class="sxs-lookup"><span data-stu-id="313a4-106">**FQDN**: Edit this setting to define the fully qualified domain name of your Persistent Chat Server or Persistent Chat Server pool</span></span>
    
- <span data-ttu-id="313a4-107">**Nombre para mostrar del grupo de chat persistente**: defina esta configuración para indicar una configuración comprensible y fácil de usar del servidor o el grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="313a4-107">**Display name of the Persistent Chat pool**: Define this setting to provide a user friendly and user readable setting for the server or pool.</span></span> <span data-ttu-id="313a4-108">Esta configuración hará que sea más fácil para los usuarios asociar un servidor de chat persistente determinado o un grupo de servidores de chat persistente según el nombre para mostrar en lugar de un nombre de dominio completo más difícil de comprender.</span><span class="sxs-lookup"><span data-stu-id="313a4-108">This setting will make it easier for your users to associate a given Persistent Chat Server or Persistent Chat Server pool based on the display name instead of a more difficult to understand fully qualified domain name.</span></span>
    
- <span data-ttu-id="313a4-109">**Puerto de chat persistente**: especifique el puerto que se necesita usar para el chat persistente.</span><span class="sxs-lookup"><span data-stu-id="313a4-109">**Persistent Chat port**: Specify the port to use for Persistent Chat.</span></span>
    
<span data-ttu-id="313a4-110">Para editar la configuración de las **asociaciones** del servidor de chat persistente o del grupo de servidores de chat persistente, configure o defina estas propiedades:</span><span class="sxs-lookup"><span data-stu-id="313a4-110">You edit the **Associations** settings for the Persistent Chat Server or Persistent Chat Server pool by configuring or defining these properties:</span></span>
  
 <span data-ttu-id="313a4-111">**Asociaciones**</span><span class="sxs-lookup"><span data-stu-id="313a4-111">**Associations**</span></span>
  
- <span data-ttu-id="313a4-112">**Almacén de SQL Server**: elija el almacén de SQL Server y una instancia con nombre opcional de la lista.</span><span class="sxs-lookup"><span data-stu-id="313a4-112">**SQL Server store**: Select the SQL Server store and optional named instance from the list.</span></span>
    
    <span data-ttu-id="313a4-113">Haga clic en **Nuevo** para definir un nuevo almacén y una instancia de SQL Server opcional.</span><span class="sxs-lookup"><span data-stu-id="313a4-113">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="313a4-114">Active la casilla habilitar el reflejo de la **tienda de SQL Server** si quiere habilitar la creación de reflejos para el almacén principal de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="313a4-114">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the primary SQL Server store.</span></span>
    
    <span data-ttu-id="313a4-115">Si decide habilitar la creación de reflejo de la tienda de SQL Server, seleccione la tienda y la instancia en la lista de la lista **reflejo de SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="313a4-115">If you chose to enable SQL Server store mirroring, select the store and instance from the list **Mirroring SQL Server store**.</span></span>
    
    <span data-ttu-id="313a4-116">Haga clic en **Nuevo** para definir un nuevo almacén y una instancia de SQL Server opcional.</span><span class="sxs-lookup"><span data-stu-id="313a4-116">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="313a4-117">Active la casilla **usar el testigo de reflejo de SQL Server para habilitar la conmutación por error automática** si quiere la conmutación automática por error del almacén principal de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="313a4-117">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the primary SQL Server store.</span></span>
    
    <span data-ttu-id="313a4-118">Si decide habilitar el testigo de reflejo de la tienda de SQL Server para habilitar la conmutación automática por error, seleccione la tienda y la instancia de la lista.</span><span class="sxs-lookup"><span data-stu-id="313a4-118">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="313a4-119">Haga clic en **Nuevo** para definir un nuevo almacén de SQL Server y una instancia opcional para el almacén testigo.</span><span class="sxs-lookup"><span data-stu-id="313a4-119">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="313a4-120">Si desea habilitar el uso de la recuperación de desastres de SQL Server, seleccione la casilla **usar la copia de seguridad de almacenes de SQL Server para habilitar** la recuperación de desastres</span><span class="sxs-lookup"><span data-stu-id="313a4-120">Select the **Use backup SQL Server stores to enable disaster recovery** check box if you want to enable the use of SQL Server disaster recovery</span></span>
    
    <span data-ttu-id="313a4-121">Si optó por habilitar la recuperación ante desastres, seleccione un almacén y una instancia de la lista **Realizar copia de seguridad de almacén de SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="313a4-121">If you chose to enable disaster recovery, select a store and instance from the **Backup SQL Server store** list.</span></span>
    
    <span data-ttu-id="313a4-122">Haga clic en **Nuevo** para definir un nuevo almacén y una instancia de SQL Server opcional.</span><span class="sxs-lookup"><span data-stu-id="313a4-122">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="313a4-123">Active la casilla habilitar el reflejo de la **tienda de SQL Server** si quiere habilitar la creación de reflejos para la copia de seguridad de la tienda de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="313a4-123">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the backup SQL Server mirroring store.</span></span>
    
    <span data-ttu-id="313a4-124">Si decide habilitar la creación de reflejos de la tienda SQL Server, seleccione la tienda y la instancia de la lista de copia de seguridad de la **tienda SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="313a4-124">If you chose to enable backup SQL Server store mirroring, select the store and instance from the list **Backup SQL Server store mirror**.</span></span>
    
    <span data-ttu-id="313a4-125">Haga clic en **Nuevo** para definir un nuevo almacén y una instancia de SQL Server opcional.</span><span class="sxs-lookup"><span data-stu-id="313a4-125">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="313a4-126">Active la casilla **usar el testigo de reflejo de SQL Server para habilitar la conmutación por error automática** si quiere la conmutación por error automática del almacén de SQL Server de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="313a4-126">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the backup SQL Server store.</span></span>
    
    <span data-ttu-id="313a4-127">Si decide habilitar el testigo de reflejo de la tienda de SQL Server para habilitar la conmutación automática por error, seleccione la tienda y la instancia de la lista.</span><span class="sxs-lookup"><span data-stu-id="313a4-127">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="313a4-128">Haga clic en **Nuevo** para definir un nuevo almacén de SQL Server y una instancia opcional para el almacén testigo.</span><span class="sxs-lookup"><span data-stu-id="313a4-128">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="313a4-129">Active la casilla **Habilitar cumplimiento** si desea habilitar el uso de una base de datos de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="313a4-129">Select the **Enable compliance** check box if you want to enable the use of a compliance database</span></span>
    
    <span data-ttu-id="313a4-130">Si optó por habilitar el cumplimiento, seleccione un almacén y una instancia de la lista **Almacén de SQL Server de cumplimiento**.</span><span class="sxs-lookup"><span data-stu-id="313a4-130">If you chose to enable compliance, select a store and instance from the **Compliance SQL Server store** list.</span></span>
    
    <span data-ttu-id="313a4-131">Haga clic en **Nuevo** para definir un nuevo almacén y una instancia de SQL Server opcional.</span><span class="sxs-lookup"><span data-stu-id="313a4-131">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="313a4-132">Active la casilla habilitar el reflejo de la **tienda de SQL Server** si desea habilitar el reflejo para el almacén SQL Server de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="313a4-132">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the compliance SQL Server store.</span></span>
    
    <span data-ttu-id="313a4-133">Si decide habilitar la creación de reflejo de la tienda SQL Server de cumplimiento, seleccione la tienda y la instancia en la lista de cumplimiento de la **tienda SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="313a4-133">If you chose to enable compliance SQL Server store mirroring, select the store and instance from the list **Compliance SQL Server store mirror**.</span></span>
    
    <span data-ttu-id="313a4-134">Haga clic en **Nuevo** para definir un nuevo almacén y una instancia de SQL Server opcional.</span><span class="sxs-lookup"><span data-stu-id="313a4-134">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="313a4-135">Active la casilla **usar el testigo de reflejo de SQL Server para habilitar la conmutación por error automática** si quiere la conmutación automática por error del almacén de SQL Server de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="313a4-135">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the compliance SQL Server store.</span></span>
    
    <span data-ttu-id="313a4-136">Si decide habilitar el testigo de reflejo de la tienda de SQL Server para habilitar la conmutación automática por error, seleccione la tienda y la instancia de la lista.</span><span class="sxs-lookup"><span data-stu-id="313a4-136">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="313a4-137">Haga clic en **Nuevo** para definir un nuevo almacén de SQL Server y una instancia opcional para el almacén testigo.</span><span class="sxs-lookup"><span data-stu-id="313a4-137">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="313a4-138">Si optó por habilitar el cumplimiento, seleccione un almacén y una instancia de la lista **Realizar copia de seguridad de almacén de SQL Server de cumplimiento**.</span><span class="sxs-lookup"><span data-stu-id="313a4-138">If you chose to enable compliance, select a store and instance from the **Backup compliance SQL Server store** list.</span></span>
    
    <span data-ttu-id="313a4-139">Haga clic en **Nuevo** para definir un nuevo almacén y una instancia de SQL Server opcional.</span><span class="sxs-lookup"><span data-stu-id="313a4-139">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="313a4-140">Active la casilla habilitar el reflejo de la **tienda de SQL Server** si desea habilitar el reflejo para el almacén SQL Server de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="313a4-140">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the compliance SQL Server store.</span></span>
    
    <span data-ttu-id="313a4-141">Si decide habilitar el reflejo de la tienda SQL Server de cumplimiento, seleccione la tienda y la instancia de la lista de comprobación de cumplimiento de copia de seguridad de la **tienda SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="313a4-141">If you chose to enable compliance SQL Server store mirroring, select the store and instance from the list **Backup compliance SQL Server store mirror**.</span></span>
    
    <span data-ttu-id="313a4-142">Haga clic en **Nuevo** para definir un nuevo almacén y una instancia de SQL Server opcional.</span><span class="sxs-lookup"><span data-stu-id="313a4-142">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="313a4-143">Active la casilla **usar el testigo de reflejo de SQL Server para habilitar la conmutación por error automática** si quiere la conmutación automática por error del almacén SQL Server de cumplimiento de la copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="313a4-143">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the backup compliance SQL Server store.</span></span>
    
    <span data-ttu-id="313a4-144">Si decide habilitar el testigo de reflejo de la tienda de SQL Server para habilitar la conmutación automática por error, seleccione la tienda y la instancia de la lista.</span><span class="sxs-lookup"><span data-stu-id="313a4-144">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="313a4-145">Haga clic en **Nuevo** para definir un nuevo almacén de SQL Server y una instancia opcional para el almacén testigo.</span><span class="sxs-lookup"><span data-stu-id="313a4-145">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="313a4-146">**Almacén de archivos** Seleccione una ubicación de almacén de archivos de la lista o haga clic en **nuevo** para crear un nuevo almacén de archivos.</span><span class="sxs-lookup"><span data-stu-id="313a4-146">**File store** Select a file store location from the list, or click **New** to create a new file store.</span></span>
    
  <span data-ttu-id="313a4-147">**Aceptar.** Se aceptan y confirman los cambios en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="313a4-147">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="313a4-148">**Cancelar.** Se descartan los cambios y se cierra el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="313a4-148">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="313a4-149">**Ayuda.** Abre esta pantalla de ayuda.</span><span class="sxs-lookup"><span data-stu-id="313a4-149">**Help** Displays this help screen.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="313a4-150">Vea también</span><span class="sxs-lookup"><span data-stu-id="313a4-150">See also</span></span>

[<span data-ttu-id="313a4-151">Planificar el servidor de chat persistente en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="313a4-151">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="313a4-152">Agregar un servidor de chat persistente a su topología de 2015 de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="313a4-152">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[<span data-ttu-id="313a4-153">Configurar la alta disponibilidad y la recuperación ante desastres para el servidor de chat persistente en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="313a4-153">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
