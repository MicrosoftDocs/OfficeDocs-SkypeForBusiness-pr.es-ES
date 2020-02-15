---
title: Migrar los grupos de respuesta
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate response groups
ms:assetid: 5c07bf4b-ad8a-4b83-b970-7d933bb7c4ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204931(v=OCS.15)
ms:contentKeyID: 48184250
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d537182c4d770d6bc7ffc98f71ea891de6552675
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030714"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-response-groups"></a><span data-ttu-id="9bafe-102">Migrar los grupos de respuesta</span><span class="sxs-lookup"><span data-stu-id="9bafe-102">Migrate response groups</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9bafe-103">_**Última modificación del tema:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="9bafe-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="9bafe-104">Una vez que los usuarios se han movido a grupos de servidores de Lync Server 2013, puede migrar los grupos de respuesta.</span><span class="sxs-lookup"><span data-stu-id="9bafe-104">After your users are moved to Lync Server 2013 pools, you can migrate your response groups.</span></span> <span data-ttu-id="9bafe-105">Migrar grupos de respuesta incluye copiar grupos de agentes, colas, flujos de trabajo y archivos de audio, y mover objetos de contacto de grupo de respuesta de la implementación heredada al grupo de servidores de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9bafe-105">Migrating response groups includes copying agent groups, queues, workflows, and audio files, and moving Response Group contact objects from the legacy deployment to the Lync Server 2013 pool.</span></span> <span data-ttu-id="9bafe-106">Después de migrar los grupos de respuesta heredados, las llamadas a los grupos de respuesta se controlan mediante la aplicación grupo de respuesta en el grupo de servidores de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9bafe-106">After you migrate your legacy response groups, calls to the response groups are handled by the Response Group application in the Lync Server 2013 pool.</span></span> <span data-ttu-id="9bafe-107">El grupo heredado ya no maneja las llamadas a los grupos de respuesta.</span><span class="sxs-lookup"><span data-stu-id="9bafe-107">Calls to response groups are no longer handled by the legacy pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9bafe-108">Aunque puede migrar grupos de respuesta antes de mover todos los usuarios al grupo de servidores de Lync Server 2013, le recomendamos que mueva todos los usuarios en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="9bafe-108">Although you can migrate response groups before you move all users to the Lync Server 2013 pool, we recommend that you move all users first.</span></span> <span data-ttu-id="9bafe-109">En concreto, los usuarios que son agentes de grupo de respuesta no tendrán la funcionalidad completa de las nuevas características hasta que se muevan al grupo de servidores de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9bafe-109">In particular, users who are response group agents will not have full functionality of new features until they are moved to the Lync Server 2013 pool.</span></span>



</div>

<span data-ttu-id="9bafe-110">Antes de migrar los grupos de respuesta, debe haber implementado un grupo de servidores de 2013 de Lync Server que incluya la aplicación de grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="9bafe-110">Before you migrate response groups, you must have deployed a Lync Server 2013 pool that includes the Response Group application.</span></span> <span data-ttu-id="9bafe-111">La aplicación de grupo de respuesta se instala y activa de forma predeterminada al implementar la telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="9bafe-111">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="9bafe-112">Para asegurarse de que la aplicación de grupo de respuesta está instalada, ejecute el cmdlet **Get-CsService – ApplicationServer** .</span><span class="sxs-lookup"><span data-stu-id="9bafe-112">You can ensure that the Response Group application is installed by running the **Get-CsService–ApplicationServer** cmdlet.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9bafe-113">Puede crear nuevos grupos de respuesta 2013 de Lync Server en el grupo de Lync Server 2013 antes de migrar los grupos de respuesta heredados.</span><span class="sxs-lookup"><span data-stu-id="9bafe-113">You can create new Lync Server 2013 response groups in the Lync Server 2013 pool before you migrate your legacy response groups.</span></span>



</div>

<span data-ttu-id="9bafe-114">Para migrar grupos de respuesta de un grupo heredado a la versión 2013 de Lync Server, ejecute el cmdlet **Move-CsRgsConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="9bafe-114">To migrate response groups from a legacy pool to the Lync Server 2013, you run the **Move-CsRgsConfiguration** cmdlet.</span></span> <span data-ttu-id="9bafe-115">Antes de ejecutar el **Move-CsRgsConfiguration**, primero debe instalar el paquete de interfaces de Compatibilidad con versiones anteriores del Instrumental de administración de Windows (WMI).</span><span class="sxs-lookup"><span data-stu-id="9bafe-115">Before you can run **Move-CsRgsConfiguration**, you must first install the Windows Management Instrumentation (WMI) Backward Compatibility interfaces package.</span></span> <span data-ttu-id="9bafe-116">Instale esta aplicación al ejecutar OCSWMIBC.msi.</span><span class="sxs-lookup"><span data-stu-id="9bafe-116">Install this application by running OCSWMIBC.msi.</span></span> <span data-ttu-id="9bafe-117">Puede encontrar el archivo OCSWMIBC.msi en los medios de instalación en la carpeta de instalación.</span><span class="sxs-lookup"><span data-stu-id="9bafe-117">You can find OCSWMIBC.msi on the installation media in the Setup folder.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="9bafe-118">El cmdlet de migración del grupo de respuesta mueve la configuración del grupo de respuesta para todo el grupo.</span><span class="sxs-lookup"><span data-stu-id="9bafe-118">The Response Group migration cmdlet moves the Response Group configuration for the entire pool.</span></span> <span data-ttu-id="9bafe-119">No es posible seleccionar grupos, colas o flujos de trabajo específicos para la migración.</span><span class="sxs-lookup"><span data-stu-id="9bafe-119">You cannot select specific groups, queues, or workflows to migrate.</span></span>



</div>

<span data-ttu-id="9bafe-120">Después de migrar los grupos de respuesta, debe actualizar la URL que los agentes formales usan para iniciar y cerrar sesión en sus grupos de respuesta, y usar el panel de control de Lync Server o los cmdlets del shell de administración de Lync Server para comprobar que todos los grupos de agentes, las colas y los flujos de trabajo se movieron siguiera.</span><span class="sxs-lookup"><span data-stu-id="9bafe-120">After you migrate the response groups, you need to update the URL that formal agents use to sign into and out of their response groups, and use Lync Server Control Panel or Lync Server Management Shell cmdlets to verify that all agent groups, queues, and workflows moved successfully.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="9bafe-121">Al migrar grupos de respuesta, los grupos de respuesta de Office Communications Server 2007 R2 no se quitan.</span><span class="sxs-lookup"><span data-stu-id="9bafe-121">When you migrate response groups, the Office Communications Server 2007 R2 response groups are not removed.</span></span> <span data-ttu-id="9bafe-122">No quite los grupos de respuesta de Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="9bafe-122">Do not remove Office Communications Server 2007 R2 response groups.</span></span> <span data-ttu-id="9bafe-123">Si quita un grupo de respuesta de Office Communications Server 2007 R2, los grupos de respuesta de Lync Server 2013 dejarán de funcionar.</span><span class="sxs-lookup"><span data-stu-id="9bafe-123">If you remove an Office Communications Server 2007 R2 response group, the response groups in Lync Server 2013 stop working.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="9bafe-124">Se aconseja no eliminar ningún dato de la implementación anterior hasta retirar el grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="9bafe-124">We recommend that you do not remove any data from your previous deployment until you decommission the pool.</span></span> <span data-ttu-id="9bafe-125">También se recomienda encarecidamente exportar los grupos de respuesta inmediatamente después de haber realizado la migración.</span><span class="sxs-lookup"><span data-stu-id="9bafe-125">In addition, we strongly recommend that you export response groups immediately after you migrate.</span></span> <span data-ttu-id="9bafe-126">Si se quita un grupo de respuesta de Office Communications Server 2007 R2, puede restaurar los grupos de respuesta a partir de la copia de seguridad para obtener los grupos de respuesta de Lync Server 2013 que se ejecuten de nuevo.</span><span class="sxs-lookup"><span data-stu-id="9bafe-126">If an Office Communications Server 2007 R2 response group gets removed, you can then restore your response groups from the backup to get Lync Server 2013 response groups running again.</span></span>



</div>

<span data-ttu-id="9bafe-127">Al ejecutar el cmdlet **Move-CsRgsConfiguration**, los grupos de agente, las colas, los flujos de trabajo y los archivos de audio permanecen en el grupo heredado para la reversión.</span><span class="sxs-lookup"><span data-stu-id="9bafe-127">When you run the **Move-CsRgsConfiguration** cmdlet, the agent groups, queues, workflows, and audio files remain in the legacy pool for rollback purposes.</span></span> <span data-ttu-id="9bafe-128">Si embargo, si no necesita revertir el grupo heredado, debe ejecutar el cmdlet **Move-CsApplicationEndpoint** para trasladar los objetos de contacto nuevamente al grupo heredado.</span><span class="sxs-lookup"><span data-stu-id="9bafe-128">If you do need to roll back to the legacy pool, however, you need to run the **Move-CsApplicationEndpoint** cmdlet to move contact objects back to the legacy pool.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="9bafe-129">Se recomienda no eliminar ningún dato los grupos de respuesta del grupo de servidores heredado hasta retirar dicho grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="9bafe-129">We recommend that you don't delete any response group data from the legacy pool until you decommission the pool.</span></span>



</div>

<span data-ttu-id="9bafe-130">El procedimiento que se describe a continuación para migrar configuraciones de grupo de respuesta supone que tiene una relación de uno a uno entre los grupos de servidores heredados y los grupos de servidores de 2013 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9bafe-130">The procedure that follows for migrating Response Group configurations assumes that you have a one-to-one relationship between your legacy pools and the Lync Server 2013 pools.</span></span> <span data-ttu-id="9bafe-131">Si tiene previsto consolidar o dividir grupos durante la migración y la implementación, debe planear el grupo de servidores heredado asignado a cada grupo de servidores de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9bafe-131">If you plan to consolidate or split up pools during your migration and deployment, you need to plan which legacy pool maps to which Lync Server 2013 pool.</span></span>

<div>

## <a name="to-migrate-response-group-configurations"></a><span data-ttu-id="9bafe-132">Para migrar configuraciones de grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="9bafe-132">To Migrate Response Group Configurations</span></span>

1.  <span data-ttu-id="9bafe-133">Busque OCSWMIBC.msi en la carpeta de instalación de los medios de instalación e instálelo.</span><span class="sxs-lookup"><span data-stu-id="9bafe-133">Locate OCSWMIBC.msi in the Setup folder of the installation media and install it.</span></span>

2.  <span data-ttu-id="9bafe-134">Inicie sesión en el equipo con una cuenta que sea miembro del grupo RTCUniversalServerAdmins o que tenga derechos y permisos de administrador equivalentes.</span><span class="sxs-lookup"><span data-stu-id="9bafe-134">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins group or has equivalent administrator rights and permissions.</span></span>

3.  <span data-ttu-id="9bafe-135">Abra el Shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9bafe-135">Open the Lync Server Management Shell.</span></span>

4.  <span data-ttu-id="9bafe-136">Escriba lo siguiente en la línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="9bafe-136">At the command line, type the following:</span></span>
    
        Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
    
    <span data-ttu-id="9bafe-137">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="9bafe-137">For example:</span></span>
    
        Move-CsRgsConfiguration -Source pool01.contoso.net -Destination pool02.contoso.net

5.  <span data-ttu-id="9bafe-138">Si ha implementado la pestaña grupo de respuesta para Microsoft Office Communicator 2007 R2 en su entorno de Office Communications Server 2007 R2, quite la pestaña del archivo Tabs. XML de Office Communicator 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="9bafe-138">If you deployed the Response Group tab for Microsoft Office Communicator 2007 R2 in your Office Communications Server 2007 R2 environment, remove the tab from the Office Communicator 2007 R2 tabs.xml file.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9bafe-139">Los agentes formales utilizaban la pestaña Grupo de respuesta para iniciar sesión en sus grupos de respuesta para así poder recibir llamadas.</span><span class="sxs-lookup"><span data-stu-id="9bafe-139">Formal agents used the Response Group tab to sign in to their response groups before they could receive calls.</span></span> <span data-ttu-id="9bafe-140">Si ha implementado la pestaña grupo de respuesta, eligió la ubicación del archivo Tabs. XML de Office Communicator 2007 R2 cuando lo implementó.</span><span class="sxs-lookup"><span data-stu-id="9bafe-140">If you deployed the Response Group tab, you chose the location for the Office Communicator 2007 R2 tabs.xml file when you deployed it.</span></span>

    
    </div>

6.  <span data-ttu-id="9bafe-141">Proporcione a los usuarios la dirección URL actualizada que los agentes necesitan para iniciar y cerrar sesión en sus grupos de respuesta.</span><span class="sxs-lookup"><span data-stu-id="9bafe-141">Provide users with the updated URL that agents need to sign into and out of their response groups.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9bafe-142">La dirección URL suele https://webpoolFQDN/RgsClients/Tab.aspxser, donde fqdngrupoweb es el nombre de dominio completo (FQDN) del grupo de servidores web que está asociado al grupo de servidores que acaba de migrar a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9bafe-142">The URL is typically https://webpoolFQDN/RgsClients/Tab.aspx, where webpoolFQDN is the fully qualified domain name (FQDN) of the web pool that is associated with the pool that you just migrated to Lync Server 2013.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9bafe-143">Este paso no es necesario después de que los usuarios actualicen a Lync 2013 porque la dirección URL está disponible en el menú <STRONG>herramientas</STRONG> de Lync.</span><span class="sxs-lookup"><span data-stu-id="9bafe-143">This step is not required after users upgrade to Lync 2013 because the URL is available from the <STRONG>Tools</STRONG> menu in Lync.</span></span>

    
    </div>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-control-panel"></a><span data-ttu-id="9bafe-144">Para comprobar la migración del grupo de respuesta mediante el panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="9bafe-144">To Verify Response Group Migration by Using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="9bafe-145">Abra el Panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9bafe-145">Open the Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="9bafe-146">En el panel de navegación izquierdo, haga clic en **Grupos de respuesta**.</span><span class="sxs-lookup"><span data-stu-id="9bafe-146">In the left navigation pane, click **Response Groups**.</span></span>

3.  <span data-ttu-id="9bafe-147">En la pestaña **flujo de trabajo** , compruebe que todos los flujos de trabajo del entorno de Office Communications Server 2007 R2 se incluyen en la lista.</span><span class="sxs-lookup"><span data-stu-id="9bafe-147">On the **Workflow** tab, verify that all the workflows in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

4.  <span data-ttu-id="9bafe-148">Haga clic en la pestaña **cola** y compruebe que todas las colas del entorno de Office Communications Server 2007 R2 están incluidas en la lista.</span><span class="sxs-lookup"><span data-stu-id="9bafe-148">Click the **Queue** tab, and verify that all the queues in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

5.  <span data-ttu-id="9bafe-149">Haga clic en la pestaña **Grupo** y compruebe que todos los grupos de agentes del entorno de Office Communications Server 2007 R2 se incluyen en la lista.</span><span class="sxs-lookup"><span data-stu-id="9bafe-149">Click the **Group** tab, and verify that all the agent groups in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-cmdlets"></a><span data-ttu-id="9bafe-150">Para comprobar la migración del grupo de respuesta mediante cmdlets</span><span class="sxs-lookup"><span data-stu-id="9bafe-150">To Verify Response Group Migration by Using Cmdlets</span></span>

1.  <span data-ttu-id="9bafe-151">Abra el Shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9bafe-151">Open the Lync Server Management Shell.</span></span>
    
    <span data-ttu-id="9bafe-152">Para obtener más información sobre los siguientes cmdlets, ejecute:</span><span class="sxs-lookup"><span data-stu-id="9bafe-152">For details about the following cmdlets, run:</span></span>
    
        Get-Help <cmdlet name> -Detailed

2.  <span data-ttu-id="9bafe-153">Escriba lo siguiente en la línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="9bafe-153">At the command line, type the following:</span></span>
    
        Get-CsRgsAgentGroup

3.  <span data-ttu-id="9bafe-154">Compruebe que todos los grupos de agentes del entorno de Office Communications Server 2007 R2 se incluyen en la lista.</span><span class="sxs-lookup"><span data-stu-id="9bafe-154">Verify that all the agent groups in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

4.  <span data-ttu-id="9bafe-155">Escriba lo siguiente en la línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="9bafe-155">At the command line, type the following:</span></span>
    
        Get-CsRgsQueue

5.  <span data-ttu-id="9bafe-156">Compruebe que todas las colas del entorno de Office Communications Server 2007 R2 están incluidas en la lista.</span><span class="sxs-lookup"><span data-stu-id="9bafe-156">Verify that all the queues in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

6.  <span data-ttu-id="9bafe-157">Escriba lo siguiente en la línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="9bafe-157">At the command line, type the following:</span></span>
    
        Get-CsRgsWorkflow

7.  <span data-ttu-id="9bafe-158">Compruebe que todos los flujos de trabajo del entorno de Office Communications Server 2007 R2 se incluyen en la lista.</span><span class="sxs-lookup"><span data-stu-id="9bafe-158">Verify that all the workflows in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

