---
title: 'Proceso de migración: detalles'
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migration process - details
ms:assetid: ca7e352c-9bde-47d9-8273-5cf2fdfdfe7e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205264(v=OCS.15)
ms:contentKeyID: 48185412
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 76624475b86427d8e3b1aa4f9efa75c127afcb85
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756715"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migration-process---details"></a><span data-ttu-id="298e7-102">Proceso de migración: detalles</span><span class="sxs-lookup"><span data-stu-id="298e7-102">Migration process - details</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="298e7-103">_**Última modificación del tema:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="298e7-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="298e7-104">Use los siguientes requisitos previos y pasos detallados para migrar el chat en grupo de Lync Server 2010, de grupo o de Office Communications Server 2007 R2 a Lync Server 2013, servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="298e7-104">Use the following prerequisites and detailed steps to migrate either Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server.</span></span>

<div>

## <a name="prerequisites-for-migration"></a><span data-ttu-id="298e7-105">Requisitos previos de migración</span><span class="sxs-lookup"><span data-stu-id="298e7-105">Prerequisites for Migration</span></span>

<span data-ttu-id="298e7-106">Asegúrese de que ha cumplido los siguientes requisitos previos antes de migrar el chat en grupo de Lync Server 2010, Group chat o Office Communications Server 2007 R2 a Lync Server 2013, servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="298e7-106">Be sure that you’ve met the following prerequisites before migrating either Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server.</span></span>

1.  <span data-ttu-id="298e7-107">Implemente al menos un grupo de servidores de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="298e7-107">Deploy at least one Lync Server 2013 pool.</span></span> <span data-ttu-id="298e7-108">Si tiene varios grupos de servidores de Lync Server 2013, decida qué grupo de servidores de Lync Server 2013 será el grupo principal del nuevo grupo de servidores de chat persistente de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="298e7-108">If you have multiple Lync Server 2013 pools, decide which Lync Server 2013 pool will be the home pool for the new Lync Server 2013 Persistent Chat Server pool.</span></span>

2.  <span data-ttu-id="298e7-109">Instale el servidor Lync Server 2013, el grupo de servidores de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="298e7-109">Install the Lync Server 2013, Persistent Chat Server pool.</span></span> <span data-ttu-id="298e7-110">Estará vacío (sin categorías, salones ni complementos).</span><span class="sxs-lookup"><span data-stu-id="298e7-110">It will be empty (no categories, rooms, or add-ins).</span></span> <span data-ttu-id="298e7-111">Antes de migrar las categorías, los salones o los complementos heredados, puede crear salas, categorías o complementos en su implementación de Lync Server 2013, el servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="298e7-111">Before you migrate your legacy categories, rooms, or add-ins, you can create rooms, categories, or add-ins in your Lync Server 2013, Persistent Chat Server deployment.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="298e7-p103">Tenga presente que estos nuevos elementos pueden entrar en conflicto con los elementos heredados que migre. Evite los conflictos de nombres, de lo contrario se sobrescribirán cuando se migren los datos heredados.</span><span class="sxs-lookup"><span data-stu-id="298e7-p103">Be aware that these newly created items may conflict with legacy items that you migrate. Avoid any naming conflicts; otherwise, they will be overwritten when the legacy data is migrated.</span></span>

    
    </div>

</div>

<div>

## <a name="preparing-the-source-data-for-migration"></a><span data-ttu-id="298e7-114">Preparar los datos de origen para la migración</span><span class="sxs-lookup"><span data-stu-id="298e7-114">Preparing the Source Data for Migration</span></span>

<span data-ttu-id="298e7-115">Haga lo siguiente para preparar correctamente los datos de origen para la migración.</span><span class="sxs-lookup"><span data-stu-id="298e7-115">Perform the following steps to properly prepare your source data for migration.</span></span>

1.  <span data-ttu-id="298e7-116">Realice una copia de seguridad de las bases de datos de origen para Lync Server 2010, grupo de chat o para el chat en grupo de Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="298e7-116">Back up the source databases for either Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat.</span></span> <span data-ttu-id="298e7-117">Para obtener más información sobre cómo realizar copias de seguridad de SQL Server, vea "Introducción a la copia de seguridad (SQL Server)" en <https://go.microsoft.com/fwlink/p/?linkid=254851> .</span><span class="sxs-lookup"><span data-stu-id="298e7-117">For details about backing up SQL Server, see "Backup Overview (SQL Server)" at <https://go.microsoft.com/fwlink/p/?linkid=254851>.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="298e7-118">Los servicios de dominio de Active Directory deben ser los mismos.</span><span class="sxs-lookup"><span data-stu-id="298e7-118">Active Directory Domain Services should be the same.</span></span> <span data-ttu-id="298e7-119">Como condición para la migración, no puede migrar a un grupo de servidores en una implementación diferente (en concreto, en otro bosque de Active Directory).</span><span class="sxs-lookup"><span data-stu-id="298e7-119">As a condition for migration, you cannot migrate to a pool in a different deployment (specifically, in a different Active Directory forest).</span></span>

    
    </div>

2.  <span data-ttu-id="298e7-120">Inspeccione la configuración de categoría y los salones de chat de chat en grupo de Lync Server 2010, chat de grupo o de Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="298e7-120">Inspect your Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat chat rooms and category configuration.</span></span> <span data-ttu-id="298e7-121">Los cambios en las categorías, los salones o los complementos en la implementación heredada existente se realizarán mediante la herramienta de administración de chat en grupo.</span><span class="sxs-lookup"><span data-stu-id="298e7-121">Any changes to categories, rooms, or add-ins in your existing legacy deployment will be done by the Group Chat Admin Tool.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="298e7-122">Los cambios en las categorías, los salones o los complementos de su Lync Server 2013, la implementación del servidor de chat persistente se realizan con los cmdlets del panel de control de Lync Server o de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="298e7-122">Any changes to categories, rooms, or add-ins in your Lync Server 2013, Persistent Chat Server deployment are performed by the Lync Server Control Panel or Windows PowerShell cmdlets.</span></span>

    
    </div>
    
    <span data-ttu-id="298e7-123">Siga estos pasos para preparar el sistema heredado para la migración.</span><span class="sxs-lookup"><span data-stu-id="298e7-123">Follow these steps to prepare your legacy system for migration.</span></span>
    
    1.  <span data-ttu-id="298e7-124">El servidor de chat persistente admite un solo nivel de categorías, a diferencia de un conjunto de categorías jerárquico en profundidad.</span><span class="sxs-lookup"><span data-stu-id="298e7-124">Persistent Chat Server supports a single level of categories, unlike a deep hierarchical set of categories.</span></span> <span data-ttu-id="298e7-125">Tras la migración, se agrega a las subcategorías el prefijo con los nombres completos de categoría principal.</span><span class="sxs-lookup"><span data-stu-id="298e7-125">After migration, the subcategories are prefixed with full parent category names.</span></span> <span data-ttu-id="298e7-126">Puede simplificar la estructura de categorías actual conforme a sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="298e7-126">You might want to simplify and flatten your existing category structure so that the resulting structure meets your requirements.</span></span>
    
    2.  <span data-ttu-id="298e7-p108">Compruebe los **administradores** de la categoría raíz. Si existe algún administrador en este nivel, estos usuarios se agregarán como **administradores para todos los salones** tras la migración. Si su organización no requiere esto, tiene que eliminar estos administradores de la categoría raíz.</span><span class="sxs-lookup"><span data-stu-id="298e7-p108">Verify the **Managers** at the root Category. If any Managers exist at this level, these users will be added as **Managers to all rooms** after migration. If this is not a requirement for your organization, you need to remove these Managers from the root Category.</span></span>
    
    3.  <span data-ttu-id="298e7-p109">Compruebe la longitud de los nombres de los salones. Tras la migración, debido a que se han simplificado las estructuras de las categorías, si hay salones por debajo de una categoría secundaria, se les agregarán como prefijos los nombres completos de las categorías principales. El límite de los nombres es de 256 caracteres, incluidos los nombres de las categorías principales. Debe comprobar la longitud de los nombres de los salones y posiblemente abreviarlos, si son demasiado largos.</span><span class="sxs-lookup"><span data-stu-id="298e7-p109">Verify the length of room names. After migration, due to simplified category structures, if the rooms exist under a child category, they are prefixed with full parent category names. The naming limit is 256 characters, including parent category names. You must verify the length of the room names and possibly shorten the length, if they are too long.</span></span>
    
    4.  <span data-ttu-id="298e7-134">En Lync Server 2013, si la configuración de **invitaciones** de categoría se establece en true, puede elegir true o false para invitaciones a salas de esa categoría.</span><span class="sxs-lookup"><span data-stu-id="298e7-134">In Lync Server 2013, if the category **invitations** settings are set to true, you can choose true or false for invitations to rooms under that category.</span></span> <span data-ttu-id="298e7-135">No obstante, si se configuran las invitaciones con el valor false, los salones de esta categoría tienen las invitaciones desactivadas.</span><span class="sxs-lookup"><span data-stu-id="298e7-135">However if the category invitations settings are set to false, rooms under that category have invitations turned off.</span></span> <span data-ttu-id="298e7-136">Antes de la migración, debe restablecer la configuración de la invitación en la versión heredada del servidor de chat en grupo de Lync Server, si desea que existan salas o salas en una categoría específica.</span><span class="sxs-lookup"><span data-stu-id="298e7-136">Before migration, you must reset the invitation settings in your legacy Lync Server Group Chat Server version, if you want room(s) to exist under a specific category.</span></span> <span data-ttu-id="298e7-137">De lo contrario, durante la migración, Lync Server 2013 muestra advertencias y establece salas en el valor predeterminado de false.</span><span class="sxs-lookup"><span data-stu-id="298e7-137">Otherwise, during migration, Lync Server 2013 displays warnings and sets rooms to the default value of false.</span></span>
    
    5.  <span data-ttu-id="298e7-138">Si usó archivos en salones de chat, debe usar los archivos de forma manual en el nuevo almacén de archivos de chat persistente después de la migración.</span><span class="sxs-lookup"><span data-stu-id="298e7-138">If you used files in chat rooms, you must XCOPY the files manually to the new Persistent Chat file store after migration.</span></span> <span data-ttu-id="298e7-139">Las herramientas no lo hacen.</span><span class="sxs-lookup"><span data-stu-id="298e7-139">The tools don’t do this.</span></span>
    
    6.  <span data-ttu-id="298e7-140">Si tenía usuarios federados y salones con usuarios federados, tenga en cuenta que el servidor de chat persistente no admite la Federación.</span><span class="sxs-lookup"><span data-stu-id="298e7-140">If you had federated users and rooms with federated users, be aware that Persistent Chat Server does not support federation.</span></span> <span data-ttu-id="298e7-141">Los salones con usuarios federados se migrarán, pero los propios usuarios no tendrán acceso al contenido porque no se admite el acceso federado.</span><span class="sxs-lookup"><span data-stu-id="298e7-141">Rooms with federated users will be migrated; however, the users themselves won’t be able to access the content, because federated access is not supported.</span></span>
    
    7.  <span data-ttu-id="298e7-142">Identifique los salones que no desea migrar y márquelos como deshabilitados.</span><span class="sxs-lookup"><span data-stu-id="298e7-142">Identify those rooms that you do not want to migrate, and mark them as disabled.</span></span>
    
    8.  <span data-ttu-id="298e7-p113">Identifique la fecha a partir de la cual desea migrar el contenido de los salones de chat. Por ejemplo, quizás no desee migrar los mensajes anteriores al 1 de enero de 2010, porque ya son obsoletos o no son importantes para migrarlos.</span><span class="sxs-lookup"><span data-stu-id="298e7-p113">Identify the date beyond which you want to migrate the chat room content. For example, you may not want to migrate messages earlier than January 1, 2010, because these messages may be obsolete or not relevant for migration.</span></span>

</div>

<div>

## <a name="performing-the-migration"></a><span data-ttu-id="298e7-145">Realizar la migración</span><span class="sxs-lookup"><span data-stu-id="298e7-145">Performing the Migration</span></span>

<span data-ttu-id="298e7-146">Realice los siguientes pasos para migrar el servidor de chat de grupo heredado.</span><span class="sxs-lookup"><span data-stu-id="298e7-146">Perform the following steps to migrate your legacy Group Chat Server.</span></span>

1.  <span data-ttu-id="298e7-147">Cierre el chat en grupo de Lync Server 2010, chat en grupo, Office Communications Server 2007 R2 o Lync Server 2013, servicios del servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="298e7-147">Shut down the Lync Server 2010, Group Chat, Office Communications Server 2007 R2 Group Chat or Lync Server 2013, Persistent Chat Server services.</span></span> <span data-ttu-id="298e7-148">Se deben detener todos los servicios, así que planee hacerlo cada vez cuando haya suficiente tiempo de inactividad.</span><span class="sxs-lookup"><span data-stu-id="298e7-148">All services must be stopped, so plan to do this at a time when there is enough downtime.</span></span> <span data-ttu-id="298e7-149">Como se ha descrito anteriormente, asegúrese de realizar una copia de seguridad de la base de datos de chat de grupo actual.</span><span class="sxs-lookup"><span data-stu-id="298e7-149">As previously described, make sure to back up your current Group Chat database.</span></span>

2.  <span data-ttu-id="298e7-150">Ejecute el cmdlet **Export-CsPersistentChatData** de Windows PowerShell como miembro del rol de RBAC administrador de chat persistente (CsPersistentChatAdministrator).</span><span class="sxs-lookup"><span data-stu-id="298e7-150">Run the Windows PowerShell **Export-CsPersistentChatData** cmdlet as a member of the Persistent Chat administrator RBAC role (CsPersistentChatAdministrator).</span></span> <span data-ttu-id="298e7-151">Para obtener más información sobre los cmdlets de importación y exportación, consulte [Troubleshooting persistent chat Server Configuration Using Windows PowerShell cmdlets in Lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="298e7-151">For details about the export/import cmdlets, see [Troubleshooting Persistent Chat Server configuration using Windows PowerShell cmdlets in Lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).</span></span>
    
    <span data-ttu-id="298e7-152">Examine el contenido exportado.</span><span class="sxs-lookup"><span data-stu-id="298e7-152">Inspect the exported contents.</span></span>

3.  <span data-ttu-id="298e7-153">Antes de que esté listo para importar, cierre Lync Server 2013, servicios del servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="298e7-153">Before you’re ready to import, shut down Lync Server 2013, Persistent Chat Server services.</span></span> <span data-ttu-id="298e7-154">Es necesario detener todos los servicios, así que planee hacerlo a la vez cuando haya suficiente tiempo de inactividad.</span><span class="sxs-lookup"><span data-stu-id="298e7-154">All services need to be stopped, so plan to do this at a time when there is enough downtime.</span></span>

4.  <span data-ttu-id="298e7-155">Realice una copia de seguridad de la base de datos de chat persistente si ha creado categorías, salones o complementos en la implementación de Lync Server 2013 antes de la migración.</span><span class="sxs-lookup"><span data-stu-id="298e7-155">Perform a backup of the Persistent Chat database if you had created any categories, rooms, or add-ins in your Lync Server 2013 deployment before the migration.</span></span> <span data-ttu-id="298e7-156">El proceso de exportación e importación podrá combinar los datos heredados en la implementación de Lync Server 2013, pero querrá hacer una copia de seguridad de la base de datos en caso de que el contenido se sobrescriba involuntariamente (por ejemplo, si todavía existen conflictos de nombres).</span><span class="sxs-lookup"><span data-stu-id="298e7-156">The export/import process will be able to merge the legacy data into the Lync Server 2013 deployment, but you’ll want to back up the database in case that content is inadvertently overwritten (for example, if naming conflicts still exist).</span></span>

5.  <span data-ttu-id="298e7-157">Ejecute el cmdlet **Import-CsPersistentChatData** de Windows PowerShell (herramienta de importación) con un comando **Whatif** para rellenar el servidor back-end del grupo de servidores de chat persistente con datos migrados.</span><span class="sxs-lookup"><span data-stu-id="298e7-157">Run the Windows PowerShell **Import-CsPersistentChatData** cmdlet (import tool), with a **WhatIf** command to populate the Back End Server of the Persistent Chat Server pool with migrated data.</span></span> <span data-ttu-id="298e7-158">En el proceso se producen algunas conversiones para acomodar el modelo de administración simplificado.</span><span class="sxs-lookup"><span data-stu-id="298e7-158">Some conversions happen in the process to accommodate the simplified administration model.</span></span> <span data-ttu-id="298e7-159">Corrija los errores o las advertencias que aparezcan.</span><span class="sxs-lookup"><span data-stu-id="298e7-159">Fix any errors or warnings that appear.</span></span>

6.  <span data-ttu-id="298e7-160">Ejecute el cmdlet **Import-CsPersistentChatData** de Windows PowerShell del servidor de chat persistente como miembro del rol de RBAC administrador de chat persistente (CsPersistentChatAdministrator).</span><span class="sxs-lookup"><span data-stu-id="298e7-160">Run the Persistent Chat Server Windows PowerShell **Import-CsPersistentChatData** cmdlet as a member of the Persistent Chat administrator RBAC role (CsPersistentChatAdministrator).</span></span> <span data-ttu-id="298e7-161">Para obtener más información sobre los cmdlets de importación y exportación, consulte [Troubleshooting persistent chat Server Configuration Using Windows PowerShell cmdlets in Lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="298e7-161">For details about the export/import cmdlets, see [Troubleshooting Persistent Chat Server configuration using Windows PowerShell cmdlets in Lync Server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).</span></span>

7.  <span data-ttu-id="298e7-162">Debe tener XCOPY de todos los archivos cargados (toda la carpeta) al nuevo Lync Server 2013, el almacén de archivos de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="298e7-162">You must XCOPY all uploaded files (the entire folder) to the new Lync Server 2013, Persistent Chat file store.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="298e7-163">Lync 2013 (cliente) no admite la carga ni la visualización de archivos en salones de chat.</span><span class="sxs-lookup"><span data-stu-id="298e7-163">The Lync 2013 (client) does not support uploading or viewing files in chat rooms.</span></span> <span data-ttu-id="298e7-164">Puede seguir usando el cliente heredado para publicar y ver los archivos en el salón.</span><span class="sxs-lookup"><span data-stu-id="298e7-164">You can still use the legacy client to post and view files in the room.</span></span>

    
    </div>

8.  <span data-ttu-id="298e7-165">Porte el URI de servidor de búsqueda de chat de grupo de Lync Server 2010, chat de grupo u Office Communications Server 2007 R2 al objeto de contacto del servidor de chat persistente de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="298e7-165">Port the Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat Lookup Server URI to the Lync Server 2013, Persistent Chat Server contact object.</span></span> <span data-ttu-id="298e7-166">Los siguientes pasos son necesarios si el cliente de chat en grupo de Lync 2010 o de Office Communicator 2007 R2 tiene que conectarse a la versión más reciente de Lync 2013, chat persistente (cliente) después de la migración sin cambios en la configuración del cliente:</span><span class="sxs-lookup"><span data-stu-id="298e7-166">The following steps are required if either your Lync 2010 Group Chat or Office Communicator 2007 R2 Group Chat clients need to connect to the latest Lync 2013, Persistent Chat (client) after migration without any client-side configuration changes:</span></span>
    
      - <span data-ttu-id="298e7-167">Elimine la \<domainName\> cuenta de usuario del servidor de búsqueda ocschat@. com.</span><span class="sxs-lookup"><span data-stu-id="298e7-167">Delete the ocschat@\<domainName\>.com Lookup Server user account.</span></span> <span data-ttu-id="298e7-168">Esto se usaba para apuntar al servicio de búsqueda en Lync Server 2010, Group chat.</span><span class="sxs-lookup"><span data-stu-id="298e7-168">This was used to point to the Lookup Service in Lync Server 2010, Group Chat.</span></span> <span data-ttu-id="298e7-169">Puede desinstalar el grupo y eliminar las entradas de confianza posteriormente.</span><span class="sxs-lookup"><span data-stu-id="298e7-169">You can uninstall the pool and remove trusted entries later.</span></span>
    
      - <span data-ttu-id="298e7-170">Cree un extremo heredado (objeto de contacto del servidor de chat persistente) mediante la ejecución del cmdlet de Windows PowerShell, **New-CsPersistentChatEndpoint**, con el mismo URI del SIP para que el cliente heredado funcione correctamente cuando se reinicie el servicio.</span><span class="sxs-lookup"><span data-stu-id="298e7-170">Create a legacy endpoint (Persistent Chat Server contact object) by running the Windows PowerShell cmdlet, **New-CsPersistentChatEndpoint**, with the identical SIP URI so that the legacy client will work effectively when the service is restarted.</span></span>
    
    <span data-ttu-id="298e7-171">El proceso de migración obligatorio se completa en este punto.</span><span class="sxs-lookup"><span data-stu-id="298e7-171">The mandatory migration process is complete at this point.</span></span> <span data-ttu-id="298e7-172">Lync 2010 Group chat (clientes) o Office Communicator 2007 R2 Group chat (clientes) se pueden conectar ahora al nuevo grupo de servidores de chat persistente, en forma transparente.</span><span class="sxs-lookup"><span data-stu-id="298e7-172">Lync 2010 Group Chat (clients) or Office Communicator 2007 R2 Group Chat (clients) can connect to the new Persistent Chat Server pool now, transparently.</span></span>
    
    <span data-ttu-id="298e7-173">Siga estos pasos adicionales de retiro para Lync Server 2010, Group chat u Office Communications Server 2007 R2 Group chat.</span><span class="sxs-lookup"><span data-stu-id="298e7-173">Follow these additional decommissioning steps for Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat.</span></span>

9.  <span data-ttu-id="298e7-174">Inicie los servicios del servidor de chat persistentes activando todos los equipos del nuevo grupo de servidores de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="298e7-174">Start the Persistent Chat Server services by turning on all computers in the new Persistent Chat Server pool.</span></span>

10. <span data-ttu-id="298e7-175">Use el panel de control de Lync Server y los cmdlets de Windows PowerShell para comprobar que los datos se han migrado correctamente.</span><span class="sxs-lookup"><span data-stu-id="298e7-175">Use the Lync Server Control Panel and Windows PowerShell cmdlets to verify that the data has migrated successfully.</span></span>

11. <span data-ttu-id="298e7-176">Desinstale Lync 2010 Group chat u Office Communicator 2007 R2 Group chat en los equipos del grupo de servidores de chat en grupo.</span><span class="sxs-lookup"><span data-stu-id="298e7-176">Uninstall Lync 2010 Group Chat or Office Communicator 2007 R2 Group Chat from the computers in the Group Chat Server pool.</span></span>

12. <span data-ttu-id="298e7-177">Elimine la aplicación de confianza y el grupo de aplicaciones de confianza con los cmdlets de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="298e7-177">Delete the trusted application and trusted application pool using Windows PowerShell cmdlets.</span></span> <span data-ttu-id="298e7-178">Esto elimina estos elementos del almacén de administración central y de las entradas de servicio de confianza asociadas (TSE) de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="298e7-178">This deletes these items from the Central Management store and the associated Trusted Service Entries (TSEs) from the Active Directory.</span></span> <span data-ttu-id="298e7-179">Como alternativa, este paso funciona con el generador de topologías (los grupos y las aplicaciones de confianza también tienen un nodo dedicado).</span><span class="sxs-lookup"><span data-stu-id="298e7-179">Alternatively, this step works by using the Topology Builder (the trusted applications/pools have a dedicated node there, also).</span></span>

13. <span data-ttu-id="298e7-180">Ahora puede empezar a habilitar la funcionalidad del servidor de chat persistente a través de los nuevos clientes.</span><span class="sxs-lookup"><span data-stu-id="298e7-180">You can now begin to enable Persistent Chat Server functionality through the new clients.</span></span> <span data-ttu-id="298e7-181">Para más detalles sobre cómo habilitar el servidor de chat persistente, consulte [Deploying persistent chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="298e7-181">For details about enabling Persistent Chat Server, see [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="298e7-182">Lync Server 2013 admite varios grupos de servidores de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="298e7-182">Lync Server 2013 supports multiple Persistent Chat Server pools.</span></span> <span data-ttu-id="298e7-183">Sin embargo, se admite la migración de un grupo de chat de grupo de Lync 2010 o de Office Communications Server 2007 R2 &nbsp; a un solo grupo de servidores de chat persistente de Lync server 2013.</span><span class="sxs-lookup"><span data-stu-id="298e7-183">However, we support migrating a Lync 2010 Group Chat or Office Communications Server 2007 R2&nbsp;Group Chat pool to a single Lync Server 2013, Persistent Chat Server pool.</span></span> <span data-ttu-id="298e7-184">Puede agregar nuevos grupos de servidores de chat persistente en su implementación para cumplir con las necesidades regulatorias (por ejemplo, mantener datos dentro de una ubicación geográfica determinada).</span><span class="sxs-lookup"><span data-stu-id="298e7-184">You can add additional new Persistent Chat Server pools in your deployment to meet the regulatory needs (for example, keeping data within a given geography).</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

