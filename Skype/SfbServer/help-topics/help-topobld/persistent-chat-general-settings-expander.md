---
title: Expansor de configuración general del chat persistente
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.PersistentChatGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 275ee1ae-ca58-4963-bc95-523319f90d96
description: 'Para modificar la configuración General para el servidor de Chat persistente o grupo de servidores de Chat persistente, configure o defina estas propiedades:'
ms.openlocfilehash: 912cacaa050962b85d8e3f70bec78f01306909d6
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25374962"
---
# <a name="persistent-chat-general-settings-expander"></a><span data-ttu-id="84e2d-103">Expansor de configuración general del chat persistente</span><span class="sxs-lookup"><span data-stu-id="84e2d-103">Persistent Chat General Settings Expander</span></span>
 
<span data-ttu-id="84e2d-104">Para modificar la configuración **General** para el servidor de Chat persistente o grupo de servidores de Chat persistente, configure o defina estas propiedades:</span><span class="sxs-lookup"><span data-stu-id="84e2d-104">You edit the **General** settings for the Persistent Chat Server or Persistent Chat Server pool by configuring or defining these properties:</span></span>
  
 <span data-ttu-id="84e2d-105">**General**</span><span class="sxs-lookup"><span data-stu-id="84e2d-105">**General**</span></span>
  
- <span data-ttu-id="84e2d-106">**FQDN**: modifique esta configuración para definir el nombre de dominio completo del servidor de Chat persistente o grupo de servidores de Chat persistente</span><span class="sxs-lookup"><span data-stu-id="84e2d-106">**FQDN**: Edit this setting to define the fully qualified domain name of your Persistent Chat Server or Persistent Chat Server pool</span></span>
    
- <span data-ttu-id="84e2d-107">**Nombre para mostrar del grupo de chat persistente**: defina esta configuración para indicar una configuración comprensible y fácil de usar del servidor o el grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="84e2d-107">**Display name of the Persistent Chat pool**: Define this setting to provide a user friendly and user readable setting for the server or pool.</span></span> <span data-ttu-id="84e2d-108">Esta configuración hará sea más fácil para los usuarios asociar un determinado servidor de Chat persistente o grupo de servidores de Chat persistente según el nombre para mostrar en lugar de un más difícil de entender el nombre de dominio completo.</span><span class="sxs-lookup"><span data-stu-id="84e2d-108">This setting will make it easier for your users to associate a given Persistent Chat Server or Persistent Chat Server pool based on the display name instead of a more difficult to understand fully qualified domain name.</span></span>
    
- <span data-ttu-id="84e2d-109">**Puerto de chat persistente**: especifique el puerto que se necesita usar para el chat persistente.</span><span class="sxs-lookup"><span data-stu-id="84e2d-109">**Persistent Chat port**: Specify the port to use for Persistent Chat.</span></span>
    
<span data-ttu-id="84e2d-110">Modificar la configuración de **asociaciones** para el servidor de Chat persistente o grupo de servidores de Chat persistente, configure o defina estas propiedades:</span><span class="sxs-lookup"><span data-stu-id="84e2d-110">You edit the **Associations** settings for the Persistent Chat Server or Persistent Chat Server pool by configuring or defining these properties:</span></span>
  
 <span data-ttu-id="84e2d-111">**Asociaciones**</span><span class="sxs-lookup"><span data-stu-id="84e2d-111">**Associations**</span></span>
  
- <span data-ttu-id="84e2d-112">**Almacén de SQL Server**: elija el almacén de SQL Server y una instancia con nombre opcional de la lista.</span><span class="sxs-lookup"><span data-stu-id="84e2d-112">**SQL Server store**: Select the SQL Server store and optional named instance from the list.</span></span>
    
    <span data-ttu-id="84e2d-113">Haga clic en **Nuevo** para definir un nuevo almacén y una instancia de SQL Server opcional.</span><span class="sxs-lookup"><span data-stu-id="84e2d-113">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="84e2d-114">Active la casilla de verificación **la creación de reflejo de almacén de habilitar SQL Server** si desea habilitar la creación de reflejo para el almacén principal de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="84e2d-114">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the primary SQL Server store.</span></span>
    
    <span data-ttu-id="84e2d-115">Si opta por habilitar la creación de reflejo del almacén de SQL Server, seleccione el almacén y la instancia en la lista **almacén de la creación de reflejos de SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="84e2d-115">If you chose to enable SQL Server store mirroring, select the store and instance from the list **Mirroring SQL Server store**.</span></span>
    
    <span data-ttu-id="84e2d-116">Haga clic en **Nuevo** para definir un nuevo almacén y una instancia de SQL Server opcional.</span><span class="sxs-lookup"><span data-stu-id="84e2d-116">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="84e2d-117">Seleccione la casilla de verificación **usar SQL Server la creación de reflejos testigo para habilitar la conmutación por error automática** si desea que la conmutación por error automática del almacén de SQL Server principal.</span><span class="sxs-lookup"><span data-stu-id="84e2d-117">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the primary SQL Server store.</span></span>
    
    <span data-ttu-id="84e2d-118">Si opta por habilitar el testigo para habilitar la conmutación por error automática de reflejo de almacén de SQL Server, seleccione el almacén y la instancia de la lista.</span><span class="sxs-lookup"><span data-stu-id="84e2d-118">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="84e2d-119">Haga clic en **Nuevo** para definir un nuevo almacén de SQL Server y una instancia opcional para el almacén testigo.</span><span class="sxs-lookup"><span data-stu-id="84e2d-119">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="84e2d-120">Seleccione la casilla de verificación **Usar copia de seguridad de almacenes de SQL Server para habilitar la recuperación ante desastres** si desea habilitar el uso de recuperación ante desastres de SQL Server</span><span class="sxs-lookup"><span data-stu-id="84e2d-120">Select the **Use backup SQL Server stores to enable disaster recovery** check box if you want to enable the use of SQL Server disaster recovery</span></span>
    
    <span data-ttu-id="84e2d-121">Si optó por habilitar la recuperación ante desastres, seleccione un almacén y una instancia de la lista **Realizar copia de seguridad de almacén de SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="84e2d-121">If you chose to enable disaster recovery, select a store and instance from the **Backup SQL Server store** list.</span></span>
    
    <span data-ttu-id="84e2d-122">Haga clic en **Nuevo** para definir un nuevo almacén y una instancia de SQL Server opcional.</span><span class="sxs-lookup"><span data-stu-id="84e2d-122">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="84e2d-123">Active la casilla de verificación **la creación de reflejo de almacén de habilitar SQL Server** si desea habilitar la creación de reflejo para el almacén de la creación de reflejos de SQL Server de reserva.</span><span class="sxs-lookup"><span data-stu-id="84e2d-123">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the backup SQL Server mirroring store.</span></span>
    
    <span data-ttu-id="84e2d-124">Si opta por habilitar el reflejo del almacén de SQL Server copia de seguridad, seleccione el almacén y la instancia de la lista **reflejo del almacén de copia de seguridad de SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="84e2d-124">If you chose to enable backup SQL Server store mirroring, select the store and instance from the list **Backup SQL Server store mirror**.</span></span>
    
    <span data-ttu-id="84e2d-125">Haga clic en **Nuevo** para definir un nuevo almacén y una instancia de SQL Server opcional.</span><span class="sxs-lookup"><span data-stu-id="84e2d-125">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="84e2d-126">Si desea que la conmutación por error automática del almacén de SQL Server de copia de seguridad, seleccione la casilla de verificación **usar SQL Server testigo para habilitar la conmutación por error automática la creación de reflejo** .</span><span class="sxs-lookup"><span data-stu-id="84e2d-126">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the backup SQL Server store.</span></span>
    
    <span data-ttu-id="84e2d-127">Si opta por habilitar el testigo para habilitar la conmutación por error automática de reflejo de almacén de SQL Server, seleccione el almacén y la instancia de la lista.</span><span class="sxs-lookup"><span data-stu-id="84e2d-127">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="84e2d-128">Haga clic en **Nuevo** para definir un nuevo almacén de SQL Server y una instancia opcional para el almacén testigo.</span><span class="sxs-lookup"><span data-stu-id="84e2d-128">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="84e2d-129">Active la casilla **Habilitar cumplimiento** si desea habilitar el uso de una base de datos de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="84e2d-129">Select the **Enable compliance** check box if you want to enable the use of a compliance database</span></span>
    
    <span data-ttu-id="84e2d-130">Si optó por habilitar el cumplimiento, seleccione un almacén y una instancia de la lista **Almacén de SQL Server de cumplimiento**.</span><span class="sxs-lookup"><span data-stu-id="84e2d-130">If you chose to enable compliance, select a store and instance from the **Compliance SQL Server store** list.</span></span>
    
    <span data-ttu-id="84e2d-131">Haga clic en **Nuevo** para definir un nuevo almacén y una instancia de SQL Server opcional.</span><span class="sxs-lookup"><span data-stu-id="84e2d-131">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="84e2d-132">Active la casilla de verificación **la creación de reflejo de almacén de habilitar SQL Server** si desea habilitar la creación de reflejo para el almacén de SQL Server de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="84e2d-132">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the compliance SQL Server store.</span></span>
    
    <span data-ttu-id="84e2d-133">Si opta por habilitar el reflejo de almacén de SQL Server de cumplimiento, seleccione el almacén y la instancia de la lista **reflejo del almacén de SQL Server de cumplimiento**.</span><span class="sxs-lookup"><span data-stu-id="84e2d-133">If you chose to enable compliance SQL Server store mirroring, select the store and instance from the list **Compliance SQL Server store mirror**.</span></span>
    
    <span data-ttu-id="84e2d-134">Haga clic en **Nuevo** para definir un nuevo almacén y una instancia de SQL Server opcional.</span><span class="sxs-lookup"><span data-stu-id="84e2d-134">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="84e2d-135">Seleccione la casilla de verificación **usar SQL Server la creación de reflejos testigo para habilitar la conmutación por error automática** si desea que la conmutación por error automática del almacén de SQL Server de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="84e2d-135">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the compliance SQL Server store.</span></span>
    
    <span data-ttu-id="84e2d-136">Si opta por habilitar el testigo para habilitar la conmutación por error automática de reflejo de almacén de SQL Server, seleccione el almacén y la instancia de la lista.</span><span class="sxs-lookup"><span data-stu-id="84e2d-136">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="84e2d-137">Haga clic en **Nuevo** para definir un nuevo almacén de SQL Server y una instancia opcional para el almacén testigo.</span><span class="sxs-lookup"><span data-stu-id="84e2d-137">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="84e2d-138">Si optó por habilitar el cumplimiento, seleccione un almacén y una instancia de la lista **Realizar copia de seguridad de almacén de SQL Server de cumplimiento**.</span><span class="sxs-lookup"><span data-stu-id="84e2d-138">If you chose to enable compliance, select a store and instance from the **Backup compliance SQL Server store** list.</span></span>
    
    <span data-ttu-id="84e2d-139">Haga clic en **Nuevo** para definir un nuevo almacén y una instancia de SQL Server opcional.</span><span class="sxs-lookup"><span data-stu-id="84e2d-139">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="84e2d-140">Active la casilla de verificación **la creación de reflejo de almacén de habilitar SQL Server** si desea habilitar la creación de reflejo para el almacén de SQL Server de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="84e2d-140">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the compliance SQL Server store.</span></span>
    
    <span data-ttu-id="84e2d-141">Si opta por habilitar el reflejo de almacén de SQL Server de cumplimiento, seleccione el almacén y la instancia de la lista **reflejo del almacén de SQL Server de cumplimiento de copia de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="84e2d-141">If you chose to enable compliance SQL Server store mirroring, select the store and instance from the list **Backup compliance SQL Server store mirror**.</span></span>
    
    <span data-ttu-id="84e2d-142">Haga clic en **Nuevo** para definir un nuevo almacén y una instancia de SQL Server opcional.</span><span class="sxs-lookup"><span data-stu-id="84e2d-142">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="84e2d-143">Si desea que la conmutación por error automática del almacén de SQL Server de cumplimiento de copia de seguridad, seleccione la casilla de verificación **usar SQL Server testigo para habilitar la conmutación por error automática la creación de reflejo** .</span><span class="sxs-lookup"><span data-stu-id="84e2d-143">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the backup compliance SQL Server store.</span></span>
    
    <span data-ttu-id="84e2d-144">Si opta por habilitar el testigo para habilitar la conmutación por error automática de reflejo de almacén de SQL Server, seleccione el almacén y la instancia de la lista.</span><span class="sxs-lookup"><span data-stu-id="84e2d-144">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="84e2d-145">Haga clic en **Nuevo** para definir un nuevo almacén de SQL Server y una instancia opcional para el almacén testigo.</span><span class="sxs-lookup"><span data-stu-id="84e2d-145">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="84e2d-146">**Almacén de archivo** Seleccione una ubicación de almacén de archivos de la lista, o haga clic en **nuevo** para crear un nuevo almacén de archivos.</span><span class="sxs-lookup"><span data-stu-id="84e2d-146">**File store** Select a file store location from the list, or click **New** to create a new file store.</span></span>
    
  <span data-ttu-id="84e2d-147">**Aceptar** Se aceptan y confirman los cambios en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="84e2d-147">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="84e2d-148">**Cancelar** Se descartan los cambios y se cierra el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="84e2d-148">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="84e2d-149">**Ayuda** Abre esta pantalla de ayuda.</span><span class="sxs-lookup"><span data-stu-id="84e2d-149">**Help** Displays this help screen.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="84e2d-150">Vea también</span><span class="sxs-lookup"><span data-stu-id="84e2d-150">See also</span></span>

[<span data-ttu-id="84e2d-151">Planificar el servidor de chat persistente en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="84e2d-151">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="84e2d-152">Agregar servidor de Chat persistente a su Skype para topología empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="84e2d-152">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[<span data-ttu-id="84e2d-153">Configurar la alta disponibilidad y la recuperación ante desastres para el servidor de chat persistente en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="84e2d-153">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)