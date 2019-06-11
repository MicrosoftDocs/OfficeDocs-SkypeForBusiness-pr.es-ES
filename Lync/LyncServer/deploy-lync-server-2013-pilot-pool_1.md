---
title: Implementar el grupo de pruebas piloto de Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploy Lync Server 2013 pilot pool
ms:assetid: 19c27053-8b21-401f-ad91-75c2dd355e91
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204718(v=OCS.15)
ms:contentKeyID: 48183539
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f5e9068ca3ff5a2827991869598a2066473cc5af
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842837"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-lync-server-2013-pilot-pool"></a><span data-ttu-id="ab96c-102">Implementar el grupo de pruebas piloto de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ab96c-102">Deploy Lync Server 2013 pilot pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ab96c-103">_**Última modificación del tema:** 2013-11-22_</span><span class="sxs-lookup"><span data-stu-id="ab96c-103">_**Topic Last Modified:** 2013-11-22_</span></span>

<span data-ttu-id="ab96c-104">Uno de los primeros pasos necesarios para la migración a Lync Server 2013 es implementar un grupo piloto.</span><span class="sxs-lookup"><span data-stu-id="ab96c-104">One of the first steps required for migration to Lync Server 2013 is to deploy a pilot pool.</span></span> <span data-ttu-id="ab96c-105">El grupo piloto es donde se prueba la coexistencia de Lync Server 2013 con la implementación de Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="ab96c-105">The pilot pool is where you test coexistence of Lync Server 2013 with your Office Communications Server 2007 R2 deployment.</span></span> <span data-ttu-id="ab96c-106">La coexistencia es un estado temporal que dura hasta que haya movido todos los usuarios y los grupos a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ab96c-106">Coexistence is a temporary state that lasts until you have moved all users and pools to Lync Server 2013.</span></span>

<span data-ttu-id="ab96c-107">Al implementar un grupo piloto, se usa el Asistente para definir el nuevo grupo frontal.</span><span class="sxs-lookup"><span data-stu-id="ab96c-107">When you deploy a pilot pool, you use the Define New Front End Pool wizard.</span></span> <span data-ttu-id="ab96c-108">Debe implementar las mismas características y cargas de trabajo en el grupo de pruebas piloto de Lync Server 2013 que tiene en su grupo de Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="ab96c-108">You should deploy the same features and workloads in your Lync Server 2013 pilot pool that you have in your Office Communications Server 2007 R2 pool.</span></span> <span data-ttu-id="ab96c-109">Si ha implementado el servidor de archivado, Monitoring Server o System Center Operations Manager para archivar o supervisar el entorno de Office Communications Server 2007 R2, y desea seguir archivando o supervisando toda la migración, necesita también puede implementar estas características en su entorno piloto.</span><span class="sxs-lookup"><span data-stu-id="ab96c-109">If you deployed Archiving Server, Monitoring Server, or System Center Operations Manager for archiving or monitoring your Office Communications Server 2007 R2 environment, and you want to continue archiving or monitoring throughout the migration, you need to also deploy these features in your pilot environment.</span></span> <span data-ttu-id="ab96c-110">La versión que implementó para archivar o supervisar el entorno de Office Communications Server 2007 R2 no capturará datos en el entorno de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ab96c-110">The version you deployed to archive or monitor your Office Communications Server 2007 R2 environment will not capture data in your Lync Server 2013 environment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ab96c-111">El procedimiento siguiente describe las características y la configuración que debe tener en cuenta como parte del proceso general de implementación del grupo piloto.</span><span class="sxs-lookup"><span data-stu-id="ab96c-111">The following procedure discusses features and settings you should consider as part of your overall pilot pool deployment process.</span></span> <span data-ttu-id="ab96c-112">Esta sección solo resalta los puntos clave que debe considerar como parte de la implementación de un grupo piloto.</span><span class="sxs-lookup"><span data-stu-id="ab96c-112">This section only highlights key points you should consider as part of your pilot pool deployment.</span></span> <span data-ttu-id="ab96c-113">Para conocer los pasos detallados, consulte la guía de implementación de <A href="lync-server-2013-deploying-lync-server.md">Lync Server 2013</A> .</span><span class="sxs-lookup"><span data-stu-id="ab96c-113">For detailed steps, refer to the <A href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</A> deployment guide.</span></span>



</div>

<span data-ttu-id="ab96c-114">**Para implementar un grupo de pruebas piloto de Lync Server 2013**</span><span class="sxs-lookup"><span data-stu-id="ab96c-114">**To deploy a Lync Server 2013 pilot pool**</span></span>

1.  <span data-ttu-id="ab96c-115">Inicie sesión en el equipo donde se encuentre instalado el Generador de topologías como miembro del grupo Administradores del dominio y el grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="ab96c-115">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="ab96c-116">Abra el generador de topologías y elija crear una nueva topología.</span><span class="sxs-lookup"><span data-stu-id="ab96c-116">Open Topology Builder and choose to create a new topology.</span></span>

3.  <span data-ttu-id="ab96c-117">Escriba el dominio SIP principal.</span><span class="sxs-lookup"><span data-stu-id="ab96c-117">Enter the primary SIP domain.</span></span>
    
    <span data-ttu-id="ab96c-118">![Crear una nueva topología, definir la página de dominio principal] (images/JJ204718.68775d87-f32c-494a-8386-6d4c81e81284(OCS.15).jpg "Crear una nueva topología, definir la página de dominio principal")</span><span class="sxs-lookup"><span data-stu-id="ab96c-118">![Create New Topology, Define primary domain page](images/JJ204718.68775d87-f32c-494a-8386-6d4c81e81284(OCS.15).jpg "Create New Topology, Define primary domain page")</span></span>

4.  <span data-ttu-id="ab96c-119">Siga completando el asistente hasta que llegue al Asistente para **definir el nuevo grupo front end** .</span><span class="sxs-lookup"><span data-stu-id="ab96c-119">Continue completing the wizard until you reach the **Define the New Front End pool** wizard.</span></span> <span data-ttu-id="ab96c-120">Haga clic en Siguiente.</span><span class="sxs-lookup"><span data-stu-id="ab96c-120">Click Next.</span></span>

5.  <span data-ttu-id="ab96c-121">Escriba el FQDN del grupo.</span><span class="sxs-lookup"><span data-stu-id="ab96c-121">Enter the pool FQDN.</span></span> <span data-ttu-id="ab96c-122">Cuando define el grupo piloto, puede optar por implementar un grupo de servidores front-end Enterprise Edition o un servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="ab96c-122">When you define your pilot pool, you can choose to deploy an Enterprise Edition Front End pool or a Standard Edition server.</span></span> <span data-ttu-id="ab96c-123">Lync Server 2013 no requiere que las características de su grupo piloto coincidan con lo que se ha implementado en su grupo heredado.</span><span class="sxs-lookup"><span data-stu-id="ab96c-123">Lync Server 2013 does not require that your pilot pool features match what was deployed in your legacy pool.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="ab96c-124">El nombre de dominio completo (FQDN) de grupo o servidor que defina para la agrupación piloto debe ser único.</span><span class="sxs-lookup"><span data-stu-id="ab96c-124">The pool or server fully qualified domain name (FQDN) that you define for the pilot pool must be unique.</span></span> <span data-ttu-id="ab96c-125">No puede coincidir con el nombre del grupo de Office Communications Server 2007 R2 implementado actualmente o de cualquier otro servidor implementado actualmente.</span><span class="sxs-lookup"><span data-stu-id="ab96c-125">It cannot match the name of the currently deployed Office Communications Server 2007 R2 pool, or any other servers currently deployed.</span></span>

    
    </div>
    
    <span data-ttu-id="ab96c-126">![Definir la página FQDN del grupo de servidores front-end] (images/JJ204718.5ff4336c-13fa-47cc-899b-066f267eb3f0(OCS.15).jpg "Definir la página FQDN del grupo de servidores front-end")</span><span class="sxs-lookup"><span data-stu-id="ab96c-126">![Define the Front End pool FQDN page](images/JJ204718.5ff4336c-13fa-47cc-899b-066f267eb3f0(OCS.15).jpg "Define the Front End pool FQDN page")</span></span>

6.  <span data-ttu-id="ab96c-127">Defina el equipo que se agregará al grupo.</span><span class="sxs-lookup"><span data-stu-id="ab96c-127">Define the computer that will be added to the pool.</span></span>
    
    <span data-ttu-id="ab96c-128">![Cuadro de diálogo definir nuevo grupo front-end] (images/JJ204718.374f0ed4-988b-465f-9861-8d1db401e76f(OCS.15).jpg "Cuadro de diálogo definir nuevo grupo front-end")</span><span class="sxs-lookup"><span data-stu-id="ab96c-128">![Define New Front End Pool dialog](images/JJ204718.374f0ed4-988b-465f-9861-8d1db401e76f(OCS.15).jpg "Define New Front End Pool dialog")</span></span>

7.  <span data-ttu-id="ab96c-129">En la página **seleccionar características** , seleccione las casillas de las características que desee en este grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="ab96c-129">On the **Select features** page, select the check boxes for the features that you want on this Front End pool.</span></span> <span data-ttu-id="ab96c-130">Por ejemplo, si va a implementar solo la mensajería instantánea (mi) y las características de presencia, active la casilla conferencias para permitir la mensajería instantánea entre usuarios, pero no seleccione las casillas Conferencia de acceso telefónico local (RTC), telefonía IP empresarial o control de admisión de llamadas. porque representan características de conferencia de voz, vídeo y colaboración.</span><span class="sxs-lookup"><span data-stu-id="ab96c-130">For example, if you are deploying only instant messaging (IM) and presence features, you would select the Conferencing check box to allow multiparty IM, but would not select the Dial-in (PSTN) conferencing, Enterprise Voice, or Call Admission Control check boxes, because they represent voice, video, and collaborative conferencing features.</span></span> <span data-ttu-id="ab96c-131">Para obtener más información sobre cómo seleccionar las características, vea [definir y configurar un grupo de servidores front-end o un servidor Standard Edition en Lync server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="ab96c-131">For additional information on selecting features, see [Define and configure a Front End pool or Standard Edition server in Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) in the Deployment documentation.</span></span>
    
    <span data-ttu-id="ab96c-132">![Página seleccionar características de la agrupación de front-end] (images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "Página seleccionar características de la agrupación de front-end")</span><span class="sxs-lookup"><span data-stu-id="ab96c-132">![Front End Pool Select features page](images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "Front End Pool Select features page")</span></span>

8.  <span data-ttu-id="ab96c-133">En la página **Seleccionar roles de servidor** de la aplicación, le recomendamos que Collocate el servidor de mediación en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ab96c-133">On the **Select collocated server roles** page, we recommend you collocate the Mediation Server in Lync Server 2013.</span></span> <span data-ttu-id="ab96c-134">Al combinar una topología heredada con Lync Server 2013, es necesario que primero Collocate el servidor de mediación de Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="ab96c-134">When merging a legacy topology with Lync Server 2013, we require that you first collocate the Office Communications Server 2007 R2 Mediation Server.</span></span> <span data-ttu-id="ab96c-135">Después de combinar las topologías y configurar el servidor de mediación de Lync Server 2013, puede decidir si desea mantener el servidor de mediación o cambiarlo a un servidor independiente cuando mueva la función de servidor de mediación a Lync Server 2013 más adelante en la implementación. cuatricromía.</span><span class="sxs-lookup"><span data-stu-id="ab96c-135">After merging the topologies and configuring the Lync Server 2013 Mediation Server, you can decide whether to keep the collocated Mediation Server, or change it to a stand-alone server when you move the Mediation Server role to Lync Server 2013 later in the deployment process.</span></span>
    
    <span data-ttu-id="ab96c-136">![Página del grupo de servidores front-end seleccionar roles de servidor en la página] (images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "Página del grupo de servidores front-end seleccionar roles de servidor en la página")</span><span class="sxs-lookup"><span data-stu-id="ab96c-136">![Front End Pool Select collocated server roles page](images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "Front End Pool Select collocated server roles page")</span></span>

9.  <span data-ttu-id="ab96c-137">En la página **asociar roles de servidor con este grupo de servidores front-end** , durante la implementación de un grupo piloto, no elija la opción **habilitar un grupo perimetral para que lo use el componente multimedia de este grupo de servidores front-end** .</span><span class="sxs-lookup"><span data-stu-id="ab96c-137">On the **Associate server roles with this Front End pool** page, during pilot pool deployment, do not choose the **Enable an Edge pool to be used by the media component of this Front End pool** option.</span></span> <span data-ttu-id="ab96c-138">Esta es una característica que habilitará y se conectará en línea en una fase posterior de la migración.</span><span class="sxs-lookup"><span data-stu-id="ab96c-138">This is a feature you will enable and bring online in a later phase of migration.</span></span> <span data-ttu-id="ab96c-139">Mantener esta configuración desactivada por ahora.</span><span class="sxs-lookup"><span data-stu-id="ab96c-139">Keep this setting cleared for now.</span></span>
    
    <span data-ttu-id="ab96c-140">![Página asociar roles de servidor con grupo de servidores front-end] (images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "Página asociar roles de servidor con grupo de servidores front-end")</span><span class="sxs-lookup"><span data-stu-id="ab96c-140">![Associate server roles with Front End pool page](images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "Associate server roles with Front End pool page")</span></span>

10. <span data-ttu-id="ab96c-141">En la página **seleccionar un servidor de Office Web Apps** , haga clic en **nuevo**y especifique el FQDN del servidor de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="ab96c-141">On the **Select an Office Web Apps Server** page, click **New**, and specify the FQDN of the application server.</span></span>
    
    <span data-ttu-id="ab96c-142">![Definir nuevas propiedades de FQDN de Office Web Apps Server] (images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "Definir nuevas propiedades de FQDN de Office Web Apps Server")</span><span class="sxs-lookup"><span data-stu-id="ab96c-142">![Define New Office Web Apps Server FQDN properties](images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "Define New Office Web Apps Server FQDN properties")</span></span>

11. <span data-ttu-id="ab96c-143">En la página **definir el archivado del almacén SQL Server** , seleccione la instancia de SQL Server que se creó anteriormente para Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ab96c-143">On the **Define the Archiving SQL Server store** page, select the SQL Server instance created earlier for Lync Server 2013.</span></span>
    
    <span data-ttu-id="ab96c-144">Definir el archivado de la ![página del almacén SQL Server] Definir el archivado de la (images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "página del almacén SQL Server")</span><span class="sxs-lookup"><span data-stu-id="ab96c-144">![Define Archiving SQL Server store page](images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "Define Archiving SQL Server store page")</span></span>

12. <span data-ttu-id="ab96c-145">En la página **definir la supervisión del almacén SQL Server** , seleccione la instancia de SQL Server que se creó anteriormente para Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ab96c-145">On the **Define the Monitoring SQL Server store** page, select the SQL Server instance created earlier for Lync Server 2013.</span></span> <span data-ttu-id="ab96c-146">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="ab96c-146">Click **Finish**.</span></span>

13. <span data-ttu-id="ab96c-147">Desde el nodo superior del generador de topología, haga clic con el botón derecho en **Lync Server** y haga clic en **Editar propiedades.**</span><span class="sxs-lookup"><span data-stu-id="ab96c-147">From the top node of Topology Builder, right click **Lync Server** and click **Edit Properties.**</span></span> <span data-ttu-id="ab96c-148">Haga clic en **direcciones URL simples**.</span><span class="sxs-lookup"><span data-stu-id="ab96c-148">Click **Simple URLs**.</span></span>

14. <span data-ttu-id="ab96c-149">Actualice la **dirección URL de acceso administrativo**.</span><span class="sxs-lookup"><span data-stu-id="ab96c-149">Update the **Administrative access URL**.</span></span>
    
    <span data-ttu-id="ab96c-150">![Editar propiedades, página direcciones URL simples] (images/JJ204718.ef596dd2-1983-47e0-b342-4fc7a0e36380(OCS.15).jpg "Editar propiedades, página direcciones URL simples")</span><span class="sxs-lookup"><span data-stu-id="ab96c-150">![Edit Properties, Simple URLs page](images/JJ204718.ef596dd2-1983-47e0-b342-4fc7a0e36380(OCS.15).jpg "Edit Properties, Simple URLs page")</span></span>
    
    <span data-ttu-id="ab96c-151">Para obtener más información sobre las direcciones URL simples, vea el tema sobre cómo [modificar o configurar direcciones URL simples en Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="ab96c-151">For additional information on Simple URLs, see the topic [Edit or configure simple URLs in Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md) in the Deployment documentation.</span></span>

15. <span data-ttu-id="ab96c-152">En **Editar propiedades**, haga clic en **servidor de administración central**.</span><span class="sxs-lookup"><span data-stu-id="ab96c-152">From the **Edit Properties**, click **Central Management Server**.</span></span>

16. <span data-ttu-id="ab96c-153">En la lista desplegable, seleccione el grupo de 2013 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ab96c-153">From the drop-down list, select the Lync Server 2013 pool.</span></span>
    
    <span data-ttu-id="ab96c-154">![Editar propiedades, página servidor de administración central] (images/JJ204718.211955fc-85f2-462d-8709-e6ea67092e89(OCS.15).jpg "Editar propiedades, página servidor de administración central")</span><span class="sxs-lookup"><span data-stu-id="ab96c-154">![Edit Properties, Central Management Server page](images/JJ204718.211955fc-85f2-462d-8709-e6ea67092e89(OCS.15).jpg "Edit Properties, Central Management Server page")</span></span>

17. <span data-ttu-id="ab96c-155">Haga clic en Aceptar para cerrar **la página Editar propiedades** .</span><span class="sxs-lookup"><span data-stu-id="ab96c-155">Click OK to close **the Edit Properties** page.</span></span>

18. <span data-ttu-id="ab96c-156">En el menú **acción** , seleccione **publicar topología**.</span><span class="sxs-lookup"><span data-stu-id="ab96c-156">From the **Action** menu, select **Publish Topology**.</span></span>

19. <span data-ttu-id="ab96c-157">Cuando el proceso de publicación haya finalizado, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="ab96c-157">When the publish process has completed, click **Finish**.</span></span>

20. <span data-ttu-id="ab96c-158">Volver al Asistente para la implementación de Lync Server 2013, haga clic en **instalar o actualizar el sistema de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="ab96c-158">Returning to the Lync Server 2013 Deployment Wizard, click **Install or Update Lync Server System**.</span></span>
    
    <span data-ttu-id="ab96c-159">![Asistente para la implementación de Lync Server 2013] (images/JJ204718.fb05adef-ad29-4905-9090-d409261b0e48(OCS.15).jpg "Asistente para la implementación de Lync Server 2013")</span><span class="sxs-lookup"><span data-stu-id="ab96c-159">![Lync Server 2013 Deployment Wizard](images/JJ204718.fb05adef-ad29-4905-9090-d409261b0e48(OCS.15).jpg "Lync Server 2013 Deployment Wizard")</span></span>

<span data-ttu-id="ab96c-160">Para instalar una copia local del almacén de configuración e iniciar los servicios necesarios, consulte [configuración de servidores front-end y grupos front-end para Lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="ab96c-160">To install a local copy of the configuration store and start the required services, see [Setting up Front End Servers and Front End pools for Lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md) in the Deployment documentation.</span></span>


</div>

<span> </span>

</div>

</div>

</div>

