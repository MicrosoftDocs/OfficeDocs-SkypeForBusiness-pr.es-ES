---
title: Implementar el grupo piloto de Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy Lync Server 2013 pilot pool
ms:assetid: 19c27053-8b21-401f-ad91-75c2dd355e91
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204718(v=OCS.15)
ms:contentKeyID: 48183539
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: af8c2f5ed78bb228c4e650da983a1c82456c47b4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180503"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploy-lync-server-2013-pilot-pool"></a><span data-ttu-id="d3b19-102">Implementar el grupo piloto de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d3b19-102">Deploy Lync Server 2013 pilot pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d3b19-103">_**Última modificación del tema:** 2013-11-22_</span><span class="sxs-lookup"><span data-stu-id="d3b19-103">_**Topic Last Modified:** 2013-11-22_</span></span>

<span data-ttu-id="d3b19-104">Uno de los primeros pasos necesarios para la migración a Lync Server 2013 es implementar un grupo piloto.</span><span class="sxs-lookup"><span data-stu-id="d3b19-104">One of the first steps required for migration to Lync Server 2013 is to deploy a pilot pool.</span></span> <span data-ttu-id="d3b19-105">El grupo piloto es donde se prueba la coexistencia de Lync Server 2013 con la implementación de Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="d3b19-105">The pilot pool is where you test coexistence of Lync Server 2013 with your Office Communications Server 2007 R2 deployment.</span></span> <span data-ttu-id="d3b19-106">La coexistencia es un estado temporal que dura hasta que haya movido todos los usuarios y grupos a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d3b19-106">Coexistence is a temporary state that lasts until you have moved all users and pools to Lync Server 2013.</span></span>

<span data-ttu-id="d3b19-107">Cuando se implementa un grupo piloto, se utiliza el Asistente para definir nuevo grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="d3b19-107">When you deploy a pilot pool, you use the Define New Front End Pool wizard.</span></span> <span data-ttu-id="d3b19-108">Debe implementar las mismas características y cargas de trabajo en el grupo piloto de Lync Server 2013 que tiene en su grupo de servidores de Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="d3b19-108">You should deploy the same features and workloads in your Lync Server 2013 pilot pool that you have in your Office Communications Server 2007 R2 pool.</span></span> <span data-ttu-id="d3b19-109">Si ha implementado el servidor de archivado, el servidor de supervisión o System Center Operations Manager para archivar o supervisar el entorno de Office Communications Server 2007 R2, y desea continuar el archivado o la supervisión durante la migración, debe Implemente también estas características en el entorno piloto.</span><span class="sxs-lookup"><span data-stu-id="d3b19-109">If you deployed Archiving Server, Monitoring Server, or System Center Operations Manager for archiving or monitoring your Office Communications Server 2007 R2 environment, and you want to continue archiving or monitoring throughout the migration, you need to also deploy these features in your pilot environment.</span></span> <span data-ttu-id="d3b19-110">La versión que ha implementado para archivar o supervisar el entorno de Office Communications Server 2007 R2 no capturará datos en su entorno de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d3b19-110">The version you deployed to archive or monitor your Office Communications Server 2007 R2 environment will not capture data in your Lync Server 2013 environment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d3b19-111">El siguiente procedimiento trata las funciones y configuración que se deben tener en cuenta como parte del proceso de implementación del grupo piloto.</span><span class="sxs-lookup"><span data-stu-id="d3b19-111">The following procedure discusses features and settings you should consider as part of your overall pilot pool deployment process.</span></span> <span data-ttu-id="d3b19-112">Esta sección solo subraya puntos clave que se deberían tener en cuenta como parte de la implementación de grupo piloto.</span><span class="sxs-lookup"><span data-stu-id="d3b19-112">This section only highlights key points you should consider as part of your pilot pool deployment.</span></span> <span data-ttu-id="d3b19-113">Para conocer los pasos detallados, consulte la guía de implementación de la implementación de <A href="lync-server-2013-deploying-lync-server.md">Lync Server 2013</A> .</span><span class="sxs-lookup"><span data-stu-id="d3b19-113">For detailed steps, refer to the <A href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</A> deployment guide.</span></span>



</div>

<span data-ttu-id="d3b19-114">**Para implementar un grupo piloto de Lync Server 2013**</span><span class="sxs-lookup"><span data-stu-id="d3b19-114">**To deploy a Lync Server 2013 pilot pool**</span></span>

1.  <span data-ttu-id="d3b19-115">Inicie sesión en el equipo en el que Topology Builder esté instalado como miembro del grupo Admins. del dominio y el grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="d3b19-115">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="d3b19-116">Abra el Generador de topologías y elija para crear una nueva topología.</span><span class="sxs-lookup"><span data-stu-id="d3b19-116">Open Topology Builder and choose to create a new topology.</span></span>

3.  <span data-ttu-id="d3b19-117">Especifique el dominio SIP principal.</span><span class="sxs-lookup"><span data-stu-id="d3b19-117">Enter the primary SIP domain.</span></span>
    
    <span data-ttu-id="d3b19-118">![Crear una nueva topología, definir la página del dominio principal](images/JJ204718.68775d87-f32c-494a-8386-6d4c81e81284(OCS.15).jpg "Crear una nueva topología, definir la página del dominio principal")</span><span class="sxs-lookup"><span data-stu-id="d3b19-118">![Create New Topology, Define primary domain page](images/JJ204718.68775d87-f32c-494a-8386-6d4c81e81284(OCS.15).jpg "Create New Topology, Define primary domain page")</span></span>

4.  <span data-ttu-id="d3b19-119">Continúe completando el asistente hasta llegar al asistente **Definir el nuevo grupo de servidores front-end**.</span><span class="sxs-lookup"><span data-stu-id="d3b19-119">Continue completing the wizard until you reach the **Define the New Front End pool** wizard.</span></span> <span data-ttu-id="d3b19-120">Haga clic en Siguiente.</span><span class="sxs-lookup"><span data-stu-id="d3b19-120">Click Next.</span></span>

5.  <span data-ttu-id="d3b19-121">Especifique el FQDN de grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="d3b19-121">Enter the pool FQDN.</span></span> <span data-ttu-id="d3b19-122">Al definir el grupo piloto, puede optar por implementar un grupo de servidores front-end Enterprise Edition o un servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="d3b19-122">When you define your pilot pool, you can choose to deploy an Enterprise Edition Front End pool or a Standard Edition server.</span></span> <span data-ttu-id="d3b19-123">Lync Server 2013 no requiere que las características del grupo piloto coinciden con lo que se implementó en el grupo heredado.</span><span class="sxs-lookup"><span data-stu-id="d3b19-123">Lync Server 2013 does not require that your pilot pool features match what was deployed in your legacy pool.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="d3b19-124">El nombre de dominio completo (FQDN) del grupo o del servidor que defina para el grupo de servidores piloto debe ser único.</span><span class="sxs-lookup"><span data-stu-id="d3b19-124">The pool or server fully qualified domain name (FQDN) that you define for the pilot pool must be unique.</span></span> <span data-ttu-id="d3b19-125">No puede coincidir con el nombre del grupo de Office Communications Server 2007 R2 actualmente implementado o con cualquier otro servidor implementado actualmente.</span><span class="sxs-lookup"><span data-stu-id="d3b19-125">It cannot match the name of the currently deployed Office Communications Server 2007 R2 pool, or any other servers currently deployed.</span></span>

    
    </div>
    
    <span data-ttu-id="d3b19-126">![Definir la página de FQDN del grupo de servidores front-end](images/JJ204718.5ff4336c-13fa-47cc-899b-066f267eb3f0(OCS.15).jpg "Definir la página de FQDN del grupo de servidores front-end")</span><span class="sxs-lookup"><span data-stu-id="d3b19-126">![Define the Front End pool FQDN page](images/JJ204718.5ff4336c-13fa-47cc-899b-066f267eb3f0(OCS.15).jpg "Define the Front End pool FQDN page")</span></span>

6.  <span data-ttu-id="d3b19-127">Defina el equipo que se agregará al grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="d3b19-127">Define the computer that will be added to the pool.</span></span>
    
    <span data-ttu-id="d3b19-128">![Cuadro de diálogo definir nuevo grupo de servidores front-end](images/JJ204718.374f0ed4-988b-465f-9861-8d1db401e76f(OCS.15).jpg "Cuadro de diálogo definir nuevo grupo de servidores front-end")</span><span class="sxs-lookup"><span data-stu-id="d3b19-128">![Define New Front End Pool dialog](images/JJ204718.374f0ed4-988b-465f-9861-8d1db401e76f(OCS.15).jpg "Define New Front End Pool dialog")</span></span>

7.  <span data-ttu-id="d3b19-129">En la página **Seleccionar características**, active las casillas de las características que desee en este grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="d3b19-129">On the **Select features** page, select the check boxes for the features that you want on this Front End pool.</span></span> <span data-ttu-id="d3b19-130">Por ejemplo, si está implementado solo características de mensajería instantánea y presencia, deberá activar la casilla Conferencia para permitir la mensajería instantánea para varios participantes, pero no deberá activar las casillas Conferencia de acceso telefónico local (RTC), Enterprise Voice ni Sistema de control de admisión de llamadas, ya que representan características de conferencias de voz, vídeo y colaboración.</span><span class="sxs-lookup"><span data-stu-id="d3b19-130">For example, if you are deploying only instant messaging (IM) and presence features, you would select the Conferencing check box to allow multiparty IM, but would not select the Dial-in (PSTN) conferencing, Enterprise Voice, or Call Admission Control check boxes, because they represent voice, video, and collaborative conferencing features.</span></span> <span data-ttu-id="d3b19-131">Para obtener más información sobre cómo seleccionar características, consulte [definir y configurar un grupo de servidores front-end o un servidor Standard Edition en Lync server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="d3b19-131">For additional information on selecting features, see [Define and configure a Front End pool or Standard Edition server in Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) in the Deployment documentation.</span></span>
    
    <span data-ttu-id="d3b19-132">![Página de selección de características del grupo de servidores front-end](images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "Página de selección de características del grupo de servidores front-end")</span><span class="sxs-lookup"><span data-stu-id="d3b19-132">![Front End Pool Select features page](images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "Front End Pool Select features page")</span></span>

8.  <span data-ttu-id="d3b19-133">En la página **Seleccionar roles de servidor combinados** , le recomendamos que combinar el servidor de mediación en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d3b19-133">On the **Select collocated server roles** page, we recommend you collocate the Mediation Server in Lync Server 2013.</span></span> <span data-ttu-id="d3b19-134">Al combinar una topología heredada con Lync Server 2013, es necesario que primero combinar el servidor de mediación de Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="d3b19-134">When merging a legacy topology with Lync Server 2013, we require that you first collocate the Office Communications Server 2007 R2 Mediation Server.</span></span> <span data-ttu-id="d3b19-135">Después de combinar las topologías y configurar el servidor de mediación de Lync Server 2013, puede decidir si desea mantener el servidor de mediación combinado o cambiarlo a un servidor independiente cuando mueva la función de servidor de mediación a Lync Server 2013 más adelante en la implementación. proceso.</span><span class="sxs-lookup"><span data-stu-id="d3b19-135">After merging the topologies and configuring the Lync Server 2013 Mediation Server, you can decide whether to keep the collocated Mediation Server, or change it to a stand-alone server when you move the Mediation Server role to Lync Server 2013 later in the deployment process.</span></span>
    
    <span data-ttu-id="d3b19-136">![Página de selección de roles de servidor combinados del grupo de servidores front-end](images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "Página de selección de roles de servidor combinados del grupo de servidores front-end")</span><span class="sxs-lookup"><span data-stu-id="d3b19-136">![Front End Pool Select collocated server roles page](images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "Front End Pool Select collocated server roles page")</span></span>

9.  <span data-ttu-id="d3b19-p109">En la página **Asociar roles de servidor a este grupo de servidores front-end**, durante la implementación de un grupo piloto, no seleccione la opción **Habilitar el uso de un servidor perimetral por parte del componente multimedia de este grupo front-end**. Esta característica se habilitará y se pondrá en línea en una fase posterior de la migración. No seleccione esta opción por el momento.</span><span class="sxs-lookup"><span data-stu-id="d3b19-p109">On the **Associate server roles with this Front End pool** page, during pilot pool deployment, do not choose the **Enable an Edge pool to be used by the media component of this Front End pool** option. This is a feature you will enable and bring online in a later phase of migration. Keep this setting cleared for now.</span></span>
    
    <span data-ttu-id="d3b19-140">![Página asociar roles de servidor con grupo de servidores front-end](images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "Página asociar roles de servidor con grupo de servidores front-end")</span><span class="sxs-lookup"><span data-stu-id="d3b19-140">![Associate server roles with Front End pool page](images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "Associate server roles with Front End pool page")</span></span>

10. <span data-ttu-id="d3b19-141">En la página **Seleccionar un servidor de aplicaciones web para Office**, haga clic en **Nuevo** y especifique el FQDN del servidor de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="d3b19-141">On the **Select an Office Web Apps Server** page, click **New**, and specify the FQDN of the application server.</span></span>
    
    <span data-ttu-id="d3b19-142">![Definir nuevas propiedades de FQDN de Office Web Apps Server](images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "Definir nuevas propiedades de FQDN de Office Web Apps Server")</span><span class="sxs-lookup"><span data-stu-id="d3b19-142">![Define New Office Web Apps Server FQDN properties](images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "Define New Office Web Apps Server FQDN properties")</span></span>

11. <span data-ttu-id="d3b19-143">En la página **definir el almacén de SQL Server de archivado** , seleccione la instancia de SQL Server que se creó anteriormente para Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d3b19-143">On the **Define the Archiving SQL Server store** page, select the SQL Server instance created earlier for Lync Server 2013.</span></span>
    
    <span data-ttu-id="d3b19-144">![Definir la página de archivado del almacén de SQL Server](images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "Definir la página de archivado del almacén de SQL Server")</span><span class="sxs-lookup"><span data-stu-id="d3b19-144">![Define Archiving SQL Server store page](images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "Define Archiving SQL Server store page")</span></span>

12. <span data-ttu-id="d3b19-145">En la página **definir el almacén de SQL Server de supervisión** , seleccione la instancia de SQL Server que se creó anteriormente para Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d3b19-145">On the **Define the Monitoring SQL Server store** page, select the SQL Server instance created earlier for Lync Server 2013.</span></span> <span data-ttu-id="d3b19-146">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="d3b19-146">Click **Finish**.</span></span>

13. <span data-ttu-id="d3b19-p111">Desde el nodo principal del Generador de topologías, haga clic con el botón secundario en **Lync Server** y haga clic en **Editar propiedades.** Haga clic en **Direcciones URL simples**.</span><span class="sxs-lookup"><span data-stu-id="d3b19-p111">From the top node of Topology Builder, right click **Lync Server** and click **Edit Properties.** Click **Simple URLs**.</span></span>

14. <span data-ttu-id="d3b19-149">Actualice la **Dirección URL de acceso administrativo**.</span><span class="sxs-lookup"><span data-stu-id="d3b19-149">Update the **Administrative access URL**.</span></span>
    
    <span data-ttu-id="d3b19-150">![Editar propiedades, página de direcciones URL sencillas](images/JJ204718.ef596dd2-1983-47e0-b342-4fc7a0e36380(OCS.15).jpg "Editar propiedades, página de direcciones URL sencillas")</span><span class="sxs-lookup"><span data-stu-id="d3b19-150">![Edit Properties, Simple URLs page](images/JJ204718.ef596dd2-1983-47e0-b342-4fc7a0e36380(OCS.15).jpg "Edit Properties, Simple URLs page")</span></span>
    
    <span data-ttu-id="d3b19-151">Para obtener más información acerca de las direcciones URL sencillas, consulte el tema [Editar o configurar direcciones URL sencillas en Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="d3b19-151">For additional information on Simple URLs, see the topic [Edit or configure simple URLs in Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md) in the Deployment documentation.</span></span>

15. <span data-ttu-id="d3b19-152">En **Editar propiedades**, haga clic en **Servidor de administración central**.</span><span class="sxs-lookup"><span data-stu-id="d3b19-152">From the **Edit Properties**, click **Central Management Server**.</span></span>

16. <span data-ttu-id="d3b19-153">En la lista desplegable, seleccione el grupo de servidores de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d3b19-153">From the drop-down list, select the Lync Server 2013 pool.</span></span>
    
    <span data-ttu-id="d3b19-154">![Editar propiedades, página servidor de administración central](images/JJ204718.211955fc-85f2-462d-8709-e6ea67092e89(OCS.15).jpg "Editar propiedades, página servidor de administración central")</span><span class="sxs-lookup"><span data-stu-id="d3b19-154">![Edit Properties, Central Management Server page](images/JJ204718.211955fc-85f2-462d-8709-e6ea67092e89(OCS.15).jpg "Edit Properties, Central Management Server page")</span></span>

17. <span data-ttu-id="d3b19-155">Haga clic en Aceptar para cerrar la página **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="d3b19-155">Click OK to close **the Edit Properties** page.</span></span>

18. <span data-ttu-id="d3b19-156">En el menú **Acción**, seleccione **Publicar topología**.</span><span class="sxs-lookup"><span data-stu-id="d3b19-156">From the **Action** menu, select **Publish Topology**.</span></span>

19. <span data-ttu-id="d3b19-157">Una vez completado el proceso de publicación, haga clic en  \*\*Finalizar \*\*.</span><span class="sxs-lookup"><span data-stu-id="d3b19-157">When the publish process has completed, click **Finish**.</span></span>

20. <span data-ttu-id="d3b19-158">Volver al Asistente para la implementación de Lync Server 2013, haga clic en **instalar o actualizar el sistema Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="d3b19-158">Returning to the Lync Server 2013 Deployment Wizard, click **Install or Update Lync Server System**.</span></span>
    
    <span data-ttu-id="d3b19-159">![Asistente para la implementación de Lync Server 2013](images/JJ204718.fb05adef-ad29-4905-9090-d409261b0e48(OCS.15).jpg "Asistente para la implementación de Lync Server 2013")</span><span class="sxs-lookup"><span data-stu-id="d3b19-159">![Lync Server 2013 Deployment Wizard](images/JJ204718.fb05adef-ad29-4905-9090-d409261b0e48(OCS.15).jpg "Lync Server 2013 Deployment Wizard")</span></span>

<span data-ttu-id="d3b19-160">Para instalar una copia local del almacén de configuración e iniciar los servicios necesarios, consulte [setting up front end Servers and front end pools for Lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="d3b19-160">To install a local copy of the configuration store and start the required services, see [Setting up Front End Servers and Front End pools for Lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md) in the Deployment documentation.</span></span>


</div>

<span> </span>

</div>

</div>

</div>

