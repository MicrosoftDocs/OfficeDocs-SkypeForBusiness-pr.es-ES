---
title: Proceso de migración - Detalles
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migration process - details
ms:assetid: ca7e352c-9bde-47d9-8273-5cf2fdfdfe7e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205264(v=OCS.15)
ms:contentKeyID: 48185412
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1d3b46e2b80d9ad5a4b08108d1dc2bad03cf5f0f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757144"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-process---details"></a><span data-ttu-id="03c1f-102">Proceso de migración - Detalles</span><span class="sxs-lookup"><span data-stu-id="03c1f-102">Migration process - details</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="03c1f-103">_**Última modificación del tema:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="03c1f-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="03c1f-104">Use los siguientes requisitos previos y pasos detallados para migrar Lync Server 2010, chat grupal o chat grupal de Office Communications Server 2007 R2 a Lync Server 2013, servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="03c1f-104">Use the following prerequisites and detailed steps to migrate either Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server.</span></span>

<div>

## <a name="prerequisites-for-migration"></a><span data-ttu-id="03c1f-105">Requisitos previos para la migración</span><span class="sxs-lookup"><span data-stu-id="03c1f-105">Prerequisites for Migration</span></span>

<span data-ttu-id="03c1f-106">Asegúrese de que ha cumplido los siguientes requisitos previos antes de migrar Lync Server 2010, chat grupal o chat grupal de Office Communications Server 2007 R2 a Lync Server 2013, servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="03c1f-106">Be sure that you’ve met the following prerequisites before migrating either Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server.</span></span>

1.  <span data-ttu-id="03c1f-107">Implemente un mínimo de un grupo de 2013 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="03c1f-107">Deploy at least one Lync Server 2013 pool.</span></span> <span data-ttu-id="03c1f-108">Si tiene varios grupos de servidores de Lync Server 2013, decida qué grupo de servidores de Lync Server 2013 será el grupo principal para el nuevo grupo de servidores de chat persistente de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="03c1f-108">If you have multiple Lync Server 2013 pools, decide which Lync Server 2013 pool will be the home pool for the new Lync Server 2013 Persistent Chat Server pool.</span></span>

2.  <span data-ttu-id="03c1f-109">Instale Lync Server 2013, grupo de servidores de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="03c1f-109">Install the Lync Server 2013, Persistent Chat Server pool.</span></span> <span data-ttu-id="03c1f-110">Estará vacío (no hay categorías, salones ni complementos).</span><span class="sxs-lookup"><span data-stu-id="03c1f-110">It will be empty (no categories, rooms, or add-ins).</span></span> <span data-ttu-id="03c1f-111">Antes de migrar las categorías, salas o complementos heredados, puede crear salas, categorías o complementos en su Lync Server 2013, implementación persistente del servidor de chat.</span><span class="sxs-lookup"><span data-stu-id="03c1f-111">Before you migrate your legacy categories, rooms, or add-ins, you can create rooms, categories, or add-ins in your Lync Server 2013, Persistent Chat Server deployment.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="03c1f-112">Tenga en cuenta que estos elementos recién creados pueden entrar en conflicto con los elementos heredados que migra.</span><span class="sxs-lookup"><span data-stu-id="03c1f-112">Be aware that these newly created items may conflict with legacy items that you migrate.</span></span> <span data-ttu-id="03c1f-113">Evitar conflictos de nombres; de lo contrario, se sobrescribirán cuando se migren los datos heredados.</span><span class="sxs-lookup"><span data-stu-id="03c1f-113">Avoid any naming conflicts; otherwise, they will be overwritten when the legacy data is migrated.</span></span>

    
    </div>

</div>

<div>

## <a name="preparing-the-source-data-for-migration"></a><span data-ttu-id="03c1f-114">Preparar los datos de origen para la migración</span><span class="sxs-lookup"><span data-stu-id="03c1f-114">Preparing the Source Data for Migration</span></span>

<span data-ttu-id="03c1f-115">Realice los siguientes pasos para preparar correctamente los datos de origen para la migración.</span><span class="sxs-lookup"><span data-stu-id="03c1f-115">Perform the following steps to properly prepare your source data for migration.</span></span>

1.  <span data-ttu-id="03c1f-116">Haga una copia de seguridad de las bases de datos de origen para Lync Server 2010, chat grupal u Office Communications Server 2007 R2 chat grupal.</span><span class="sxs-lookup"><span data-stu-id="03c1f-116">Back up the source databases for either Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat.</span></span> <span data-ttu-id="03c1f-117">Para obtener detalles sobre cómo realizar copias de seguridad de SQL Server, consulte "Introducción a la <http://go.microsoft.com/fwlink/p/?linkid=254851>copia de seguridad (SQL Server)" en.</span><span class="sxs-lookup"><span data-stu-id="03c1f-117">For details about backing up SQL Server, see "Backup Overview (SQL Server)" at <http://go.microsoft.com/fwlink/p/?linkid=254851>.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="03c1f-118">Los servicios de dominio de Active Directory deben ser iguales.</span><span class="sxs-lookup"><span data-stu-id="03c1f-118">Active Directory Domain Services should be the same.</span></span> <span data-ttu-id="03c1f-119">Como condición para la migración, no se puede migrar a un grupo en una implementación diferente (en concreto, en un bosque de Active Directory diferente).</span><span class="sxs-lookup"><span data-stu-id="03c1f-119">As a condition for migration, you cannot migrate to a pool in a different deployment (specifically, in a different Active Directory forest).</span></span>

    
    </div>

2.  <span data-ttu-id="03c1f-120">Inspeccione su Lync Server 2010, chat grupal u Office Communications Server 2007 R2 chats grupales chat y configuración de categoría.</span><span class="sxs-lookup"><span data-stu-id="03c1f-120">Inspect your Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat chat rooms and category configuration.</span></span> <span data-ttu-id="03c1f-121">Los cambios en las categorías, salas o complementos de la implementación heredada existente serán realizados por la herramienta de administración de chats grupales.</span><span class="sxs-lookup"><span data-stu-id="03c1f-121">Any changes to categories, rooms, or add-ins in your existing legacy deployment will be done by the Group Chat Admin Tool.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="03c1f-122">Cualquier cambio en las categorías, salas o complementos de su Lync Server 2013, el panel de control de Lync Server o los cmdlets de Windows PowerShell realizan la implementación del servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="03c1f-122">Any changes to categories, rooms, or add-ins in your Lync Server 2013, Persistent Chat Server deployment are performed by the Lync Server Control Panel or Windows PowerShell cmdlets.</span></span>

    
    </div>
    
    <span data-ttu-id="03c1f-123">Siga estos pasos para preparar el sistema heredado para la migración.</span><span class="sxs-lookup"><span data-stu-id="03c1f-123">Follow these steps to prepare your legacy system for migration.</span></span>
    
    1.  <span data-ttu-id="03c1f-124">El servidor de chat persistente admite un único nivel de categorías, a diferencia de un conjunto jerárquico de categorías.</span><span class="sxs-lookup"><span data-stu-id="03c1f-124">Persistent Chat Server supports a single level of categories, unlike a deep hierarchical set of categories.</span></span> <span data-ttu-id="03c1f-125">Después de la migración, las subcategorías van precedidas de nombres de categorías primarias completas.</span><span class="sxs-lookup"><span data-stu-id="03c1f-125">After migration, the subcategories are prefixed with full parent category names.</span></span> <span data-ttu-id="03c1f-126">Es posible que desee simplificar y acoplar la estructura de categorías existente para que la estructura resultante cumpla sus requisitos.</span><span class="sxs-lookup"><span data-stu-id="03c1f-126">You might want to simplify and flatten your existing category structure so that the resulting structure meets your requirements.</span></span>
    
    2.  <span data-ttu-id="03c1f-127">Verifica los **administradores** en la categoría raíz.</span><span class="sxs-lookup"><span data-stu-id="03c1f-127">Verify the **Managers** at the root Category.</span></span> <span data-ttu-id="03c1f-128">Si hay algún administrador en este nivel, estos usuarios se agregarán como **administradores a todas las salas después de** la migración.</span><span class="sxs-lookup"><span data-stu-id="03c1f-128">If any Managers exist at this level, these users will be added as **Managers to all rooms** after migration.</span></span> <span data-ttu-id="03c1f-129">Si esto no es un requisito para su organización, debe quitar estos administradores de la categoría raíz.</span><span class="sxs-lookup"><span data-stu-id="03c1f-129">If this is not a requirement for your organization, you need to remove these Managers from the root Category.</span></span>
    
    3.  <span data-ttu-id="03c1f-130">Verifique la longitud de los nombres de las salas.</span><span class="sxs-lookup"><span data-stu-id="03c1f-130">Verify the length of room names.</span></span> <span data-ttu-id="03c1f-131">Después de la migración, debido a las estructuras de categoría simplificadas, si los salones existen en una categoría secundaria, están prefijados con nombres completos de categorías primarias.</span><span class="sxs-lookup"><span data-stu-id="03c1f-131">After migration, due to simplified category structures, if the rooms exist under a child category, they are prefixed with full parent category names.</span></span> <span data-ttu-id="03c1f-132">El límite de nombres es de 256 caracteres, incluidos los nombres de categorías principales.</span><span class="sxs-lookup"><span data-stu-id="03c1f-132">The naming limit is 256 characters, including parent category names.</span></span> <span data-ttu-id="03c1f-133">Debe verificar la longitud de los nombres de las salas y, posiblemente, acortar la longitud si son demasiado largas.</span><span class="sxs-lookup"><span data-stu-id="03c1f-133">You must verify the length of the room names and possibly shorten the length, if they are too long.</span></span>
    
    4.  <span data-ttu-id="03c1f-134">En Lync Server 2013, si la configuración de **invitaciones** de categoría se establece en verdadero, puede elegir verdadero o falso para las invitaciones a salas de esta categoría.</span><span class="sxs-lookup"><span data-stu-id="03c1f-134">In Lync Server 2013, if the category **invitations** settings are set to true, you can choose true or false for invitations to rooms under that category.</span></span> <span data-ttu-id="03c1f-135">Sin embargo, si la configuración de invitaciones de categorías está establecida en falso, las salas de esta categoría tienen desactivadas las invitaciones.</span><span class="sxs-lookup"><span data-stu-id="03c1f-135">However if the category invitations settings are set to false, rooms under that category have invitations turned off.</span></span> <span data-ttu-id="03c1f-136">Antes de la migración, debe restablecer la configuración de la invitación en la versión del servidor de chat del grupo de Lync Server heredado, si quiere que los salones existan en una categoría específica.</span><span class="sxs-lookup"><span data-stu-id="03c1f-136">Before migration, you must reset the invitation settings in your legacy Lync Server Group Chat Server version, if you want room(s) to exist under a specific category.</span></span> <span data-ttu-id="03c1f-137">De lo contrario, durante la migración, Lync Server 2013 muestra advertencias y establece salas en el valor predeterminado de falso.</span><span class="sxs-lookup"><span data-stu-id="03c1f-137">Otherwise, during migration, Lync Server 2013 displays warnings and sets rooms to the default value of false.</span></span>
    
    5.  <span data-ttu-id="03c1f-138">Si ha usado archivos en salones de chat, debe XCOPY manualmente en el nuevo almacén de archivos de chat persistente después de la migración.</span><span class="sxs-lookup"><span data-stu-id="03c1f-138">If you used files in chat rooms, you must XCOPY the files manually to the new Persistent Chat file store after migration.</span></span> <span data-ttu-id="03c1f-139">Las herramientas no hacen esto.</span><span class="sxs-lookup"><span data-stu-id="03c1f-139">The tools don’t do this.</span></span>
    
    6.  <span data-ttu-id="03c1f-140">Si tiene usuarios federados y salas con usuarios federados, tenga en cuenta que el servidor de chat persistente no admite Federación.</span><span class="sxs-lookup"><span data-stu-id="03c1f-140">If you had federated users and rooms with federated users, be aware that Persistent Chat Server does not support federation.</span></span> <span data-ttu-id="03c1f-141">Se migrarán las salas con usuarios federados; sin embargo, los usuarios ellos mismos no podrán acceder al contenido porque no se admite el acceso federado.</span><span class="sxs-lookup"><span data-stu-id="03c1f-141">Rooms with federated users will be migrated; however, the users themselves won’t be able to access the content, because federated access is not supported.</span></span>
    
    7.  <span data-ttu-id="03c1f-142">Identifique los salones que no desea migrar y márquelos como deshabilitados.</span><span class="sxs-lookup"><span data-stu-id="03c1f-142">Identify those rooms that you do not want to migrate, and mark them as disabled.</span></span>
    
    8.  <span data-ttu-id="03c1f-143">Identifique la fecha más allá de la cual desea migrar el contenido del salón de chat.</span><span class="sxs-lookup"><span data-stu-id="03c1f-143">Identify the date beyond which you want to migrate the chat room content.</span></span> <span data-ttu-id="03c1f-144">Por ejemplo, es posible que no desee migrar mensajes anteriores al 1 de enero de 2010, ya que estos mensajes pueden estar obsoletos o no son relevantes para la migración.</span><span class="sxs-lookup"><span data-stu-id="03c1f-144">For example, you may not want to migrate messages earlier than January 1, 2010, because these messages may be obsolete or not relevant for migration.</span></span>

</div>

<div>

## <a name="performing-the-migration"></a><span data-ttu-id="03c1f-145">Realizar la migración</span><span class="sxs-lookup"><span data-stu-id="03c1f-145">Performing the Migration</span></span>

<span data-ttu-id="03c1f-146">Realice los siguientes pasos para migrar el servidor de chat de grupo heredado.</span><span class="sxs-lookup"><span data-stu-id="03c1f-146">Perform the following steps to migrate your legacy Group Chat Server.</span></span>

1.  <span data-ttu-id="03c1f-147">Apague Lync Server 2010, chat grupal, chat grupal de Office Communications Server 2007 R2 o Lync Server 2013, servicios de servidor de chat persistentes.</span><span class="sxs-lookup"><span data-stu-id="03c1f-147">Shut down the Lync Server 2010, Group Chat, Office Communications Server 2007 R2 Group Chat or Lync Server 2013, Persistent Chat Server services.</span></span> <span data-ttu-id="03c1f-148">Todos los servicios deben detenerse, así que planifique hacerlo en un momento en el que haya suficiente tiempo de inactividad.</span><span class="sxs-lookup"><span data-stu-id="03c1f-148">All services must be stopped, so plan to do this at a time when there is enough downtime.</span></span> <span data-ttu-id="03c1f-149">Como se ha descrito anteriormente, asegúrese de realizar una copia de seguridad de la base de datos de chat de grupo actual.</span><span class="sxs-lookup"><span data-stu-id="03c1f-149">As previously described, make sure to back up your current Group Chat database.</span></span>

2.  <span data-ttu-id="03c1f-150">Ejecute el cmdlet **Export-CsPersistentChatData** de Windows PowerShell como miembro del rol de RBAC de administrador de chat persistente (CsPersistentChatAdministrator).</span><span class="sxs-lookup"><span data-stu-id="03c1f-150">Run the Windows PowerShell **Export-CsPersistentChatData** cmdlet as a member of the Persistent Chat administrator RBAC role (CsPersistentChatAdministrator).</span></span> <span data-ttu-id="03c1f-151">Para obtener más información sobre los cmdlets de exportación/importación, consulte [solución de problemas de configuración del servidor de chat persistente con cmdlets de Windows PowerShell en Lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="03c1f-151">For details about the export/import cmdlets, see [Troubleshooting Persistent Chat Server configuration using Windows PowerShell cmdlets in Lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).</span></span>
    
    <span data-ttu-id="03c1f-152">Inspeccione el contenido exportado.</span><span class="sxs-lookup"><span data-stu-id="03c1f-152">Inspect the exported contents.</span></span>

3.  <span data-ttu-id="03c1f-153">Antes de estar listo para importar, apague Lync Server 2013, servicios de servidor de chat persistentes.</span><span class="sxs-lookup"><span data-stu-id="03c1f-153">Before you’re ready to import, shut down Lync Server 2013, Persistent Chat Server services.</span></span> <span data-ttu-id="03c1f-154">Todos los servicios deben detenerse, por lo que debe planificar hacerlo en un momento en que haya suficiente tiempo de inactividad.</span><span class="sxs-lookup"><span data-stu-id="03c1f-154">All services need to be stopped, so plan to do this at a time when there is enough downtime.</span></span>

4.  <span data-ttu-id="03c1f-155">Realice una copia de seguridad de la base de datos de chat persistente si ha creado categorías, salas o complementos en la implementación de Lync Server 2013 antes de la migración.</span><span class="sxs-lookup"><span data-stu-id="03c1f-155">Perform a backup of the Persistent Chat database if you had created any categories, rooms, or add-ins in your Lync Server 2013 deployment before the migration.</span></span> <span data-ttu-id="03c1f-156">El proceso de exportación e importación podrá fusionar los datos heredados en la implementación de Lync Server 2013, pero tendrá que realizar una copia de seguridad de la base de datos en caso de que se sobrescriba el contenido por error (por ejemplo, si aún existen conflictos de nombres).</span><span class="sxs-lookup"><span data-stu-id="03c1f-156">The export/import process will be able to merge the legacy data into the Lync Server 2013 deployment, but you’ll want to back up the database in case that content is inadvertently overwritten (for example, if naming conflicts still exist).</span></span>

5.  <span data-ttu-id="03c1f-157">Ejecute el cmdlet **Import-CsPersistentChatData** de Windows PowerShell (herramienta de importación) con un comando **Whatif** para rellenar el servidor back-end del grupo de servidores de chat persistente con datos migrados.</span><span class="sxs-lookup"><span data-stu-id="03c1f-157">Run the Windows PowerShell **Import-CsPersistentChatData** cmdlet (import tool), with a **WhatIf** command to populate the Back End Server of the Persistent Chat Server pool with migrated data.</span></span> <span data-ttu-id="03c1f-158">Algunas conversiones se realizan en el proceso para acomodar el modelo de administración simplificado.</span><span class="sxs-lookup"><span data-stu-id="03c1f-158">Some conversions happen in the process to accommodate the simplified administration model.</span></span> <span data-ttu-id="03c1f-159">Corrija los errores o advertencias que aparezcan.</span><span class="sxs-lookup"><span data-stu-id="03c1f-159">Fix any errors or warnings that appear.</span></span>

6.  <span data-ttu-id="03c1f-160">Ejecute el cmdlet **Import-CsPersistentChatData** del servidor de chat persistente como miembro del rol de RBAC de administrador de chat persistente (CsPersistentChatAdministrator).</span><span class="sxs-lookup"><span data-stu-id="03c1f-160">Run the Persistent Chat Server Windows PowerShell **Import-CsPersistentChatData** cmdlet as a member of the Persistent Chat administrator RBAC role (CsPersistentChatAdministrator).</span></span> <span data-ttu-id="03c1f-161">Para obtener más información sobre los cmdlets de exportación/importación, consulte [solución de problemas de configuración del servidor de chat persistente con cmdlets de Windows PowerShell en Lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="03c1f-161">For details about the export/import cmdlets, see [Troubleshooting Persistent Chat Server configuration using Windows PowerShell cmdlets in Lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).</span></span>

7.  <span data-ttu-id="03c1f-162">Debe Autocompletar todos los archivos cargados (toda la carpeta) en el nuevo Lync Server 2013, almacén de archivos de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="03c1f-162">You must XCOPY all uploaded files (the entire folder) to the new Lync Server 2013, Persistent Chat file store.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="03c1f-163">Lync 2013 (cliente) no admite la carga ni la visualización de archivos en salones de chat.</span><span class="sxs-lookup"><span data-stu-id="03c1f-163">The Lync 2013 (client) does not support uploading or viewing files in chat rooms.</span></span> <span data-ttu-id="03c1f-164">Aún puede usar el cliente heredado para publicar y ver archivos en el salón.</span><span class="sxs-lookup"><span data-stu-id="03c1f-164">You can still use the legacy client to post and view files in the room.</span></span>

    
    </div>

8.  <span data-ttu-id="03c1f-165">Porte el URI del servidor de búsqueda de chat de Lync Server 2010, chat de grupo u Office Communications Server 2007 R2 a Lync Server 2013, objeto de contacto del servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="03c1f-165">Port the Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat Lookup Server URI to the Lync Server 2013, Persistent Chat Server contact object.</span></span> <span data-ttu-id="03c1f-166">Los pasos siguientes son necesarios si el chat grupal de Lync 2010 o los clientes de chat grupal de Office Communicator 2007 R2 necesitan conectarse a la última versión de Lync 2013, chat persistente (cliente) después de la migración sin cambios en la configuración del cliente:</span><span class="sxs-lookup"><span data-stu-id="03c1f-166">The following steps are required if either your Lync 2010 Group Chat or Office Communicator 2007 R2 Group Chat clients need to connect to the latest Lync 2013, Persistent Chat (client) after migration without any client-side configuration changes:</span></span>
    
      - <span data-ttu-id="03c1f-167">Elimine la\<cuenta\>de usuario del servidor de búsqueda ocschat@ domainname. com.</span><span class="sxs-lookup"><span data-stu-id="03c1f-167">Delete the ocschat@\<domainName\>.com Lookup Server user account.</span></span> <span data-ttu-id="03c1f-168">Esto se usaba para apuntar al servicio de búsqueda en Lync Server 2010, conversación grupal.</span><span class="sxs-lookup"><span data-stu-id="03c1f-168">This was used to point to the Lookup Service in Lync Server 2010, Group Chat.</span></span> <span data-ttu-id="03c1f-169">Puede desinstalar el grupo y quitar las entradas de confianza más adelante.</span><span class="sxs-lookup"><span data-stu-id="03c1f-169">You can uninstall the pool and remove trusted entries later.</span></span>
    
      - <span data-ttu-id="03c1f-170">Cree un extremo heredado (objeto de contacto del servidor de chat persistente) ejecutando el cmdlet de Windows PowerShell, **New-CsPersistentChatEndpoint**, con el URI de SIP idéntico para que el cliente heredado funcione de forma eficaz cuando se reinicie el servicio.</span><span class="sxs-lookup"><span data-stu-id="03c1f-170">Create a legacy endpoint (Persistent Chat Server contact object) by running the Windows PowerShell cmdlet, **New-CsPersistentChatEndpoint**, with the identical SIP URI so that the legacy client will work effectively when the service is restarted.</span></span>
    
    <span data-ttu-id="03c1f-171">El proceso de migración obligatoria ha finalizado en este momento.</span><span class="sxs-lookup"><span data-stu-id="03c1f-171">The mandatory migration process is complete at this point.</span></span> <span data-ttu-id="03c1f-172">Los chats grupales de Lync 2010 o de Office Communicator 2007 R2 (clientes) se pueden conectar al nuevo grupo de servidores de chat persistente ahora, de forma transparente.</span><span class="sxs-lookup"><span data-stu-id="03c1f-172">Lync 2010 Group Chat (clients) or Office Communicator 2007 R2 Group Chat (clients) can connect to the new Persistent Chat Server pool now, transparently.</span></span>
    
    <span data-ttu-id="03c1f-173">Siga estos pasos adicionales de retiro para Lync Server 2010, chat grupal u Office Communications Server 2007 R2 chat grupal.</span><span class="sxs-lookup"><span data-stu-id="03c1f-173">Follow these additional decommissioning steps for Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat.</span></span>

9.  <span data-ttu-id="03c1f-174">Inicie los servicios del servidor de chat persistentes activando todos los equipos del nuevo grupo de servidores de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="03c1f-174">Start the Persistent Chat Server services by turning on all computers in the new Persistent Chat Server pool.</span></span>

10. <span data-ttu-id="03c1f-175">Use el panel de control de Lync Server y los cmdlets de Windows PowerShell para comprobar que los datos se han migrado correctamente.</span><span class="sxs-lookup"><span data-stu-id="03c1f-175">Use the Lync Server Control Panel and Windows PowerShell cmdlets to verify that the data has migrated successfully.</span></span>

11. <span data-ttu-id="03c1f-176">Desinstale chat grupal de Lync 2010 u conversación grupal de Office Communicator 2007 R2 de los equipos del grupo de servidores de chats grupales.</span><span class="sxs-lookup"><span data-stu-id="03c1f-176">Uninstall Lync 2010 Group Chat or Office Communicator 2007 R2 Group Chat from the computers in the Group Chat Server pool.</span></span>

12. <span data-ttu-id="03c1f-177">Elimine la aplicación de confianza y el grupo de aplicaciones de confianza con cmdlets de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="03c1f-177">Delete the trusted application and trusted application pool using Windows PowerShell cmdlets.</span></span> <span data-ttu-id="03c1f-178">Esto elimina estos elementos del almacén de administración central y las entradas de servicios de confianza asociados (EET) de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="03c1f-178">This deletes these items from the Central Management store and the associated Trusted Service Entries (TSEs) from the Active Directory.</span></span> <span data-ttu-id="03c1f-179">Como alternativa, este paso funciona con el generador de topología (los grupos y las aplicaciones de confianza también tienen un nodo dedicado).</span><span class="sxs-lookup"><span data-stu-id="03c1f-179">Alternatively, this step works by using the Topology Builder (the trusted applications/pools have a dedicated node there, also).</span></span>

13. <span data-ttu-id="03c1f-180">Ahora puede empezar a habilitar la funcionalidad del servidor de chat persistente a través de los nuevos clientes.</span><span class="sxs-lookup"><span data-stu-id="03c1f-180">You can now begin to enable Persistent Chat Server functionality through the new clients.</span></span> <span data-ttu-id="03c1f-181">Para obtener más información sobre cómo habilitar el servidor de chat persistente, consulte [implementar un servidor de chat persistente en Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="03c1f-181">For details about enabling Persistent Chat Server, see [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="03c1f-182">Lync Server 2013 admite varios grupos de servidores de chat persistentes.</span><span class="sxs-lookup"><span data-stu-id="03c1f-182">Lync Server 2013 supports multiple Persistent Chat Server pools.</span></span> <span data-ttu-id="03c1f-183">Sin embargo, admitimos migrar un chat grupal de Lync 2010 o un grupo de&nbsp;chats grupales de Office Communications Server 2007 R2 a un solo Lync Server 2013, grupo de servidores de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="03c1f-183">However, we support migrating a Lync 2010 Group Chat or Office Communications Server 2007 R2&nbsp;Group Chat pool to a single Lync Server 2013, Persistent Chat Server pool.</span></span> <span data-ttu-id="03c1f-184">Puede agregar nuevos grupos de servidores de chat persistentes en su implementación para satisfacer las necesidades de reglamentación (por ejemplo, mantener los datos dentro de una ubicación geográfica determinada).</span><span class="sxs-lookup"><span data-stu-id="03c1f-184">You can add additional new Persistent Chat Server pools in your deployment to meet the regulatory needs (for example, keeping data within a given geography).</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

