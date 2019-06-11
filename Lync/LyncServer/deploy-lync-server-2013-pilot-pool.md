---
title: Implementar el grupo de pruebas piloto de Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploy Lync Server 2013 pilot pool
ms:assetid: a81aba1e-e636-434b-8c56-4150435bb55d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205144(v=OCS.15)
ms:contentKeyID: 48185028
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 93fb3c5062cc1f817d3de7b869f57600178ad454
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842835"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-lync-server-2013-pilot-pool"></a><span data-ttu-id="2fb94-102">Implementar el grupo de pruebas piloto de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2fb94-102">Deploy Lync Server 2013 pilot pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2fb94-103">_**Última modificación del tema:** 2013-11-22_</span><span class="sxs-lookup"><span data-stu-id="2fb94-103">_**Topic Last Modified:** 2013-11-22_</span></span>

<span data-ttu-id="2fb94-104">Uno de los primeros pasos necesarios para la migración a Lync Server 2013 es implementar un grupo piloto.</span><span class="sxs-lookup"><span data-stu-id="2fb94-104">One of the first steps required for migration to Lync Server 2013 is to deploy a pilot pool.</span></span> <span data-ttu-id="2fb94-105">El grupo piloto es donde se prueba la coexistencia de Lync Server 2013 con la implementación de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2fb94-105">The pilot pool is where you test coexistence of Lync Server 2013 with your Lync Server 2010 deployment.</span></span> <span data-ttu-id="2fb94-106">La coexistencia es un estado temporal que dura hasta que haya movido todos los usuarios y los grupos a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2fb94-106">Coexistence is a temporary state that lasts until you have moved all users and pools to Lync Server 2013.</span></span>

<span data-ttu-id="2fb94-107">Al implementar un grupo piloto, se usa el Asistente para definir el nuevo grupo frontal.</span><span class="sxs-lookup"><span data-stu-id="2fb94-107">When you deploy a pilot pool, you use the Define New Front End Pool wizard.</span></span> <span data-ttu-id="2fb94-108">Debe implementar las mismas características y cargas de trabajo en el grupo de pruebas piloto de Lync Server 2013 que tiene en su grupo de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2fb94-108">You should deploy the same features and workloads in your Lync Server 2013 pilot pool that you have in your Lync Server 2010 pool.</span></span> <span data-ttu-id="2fb94-109">Si ha implementado el servidor de archivado, Monitoring Server o System Center Operations Manager para archivar o supervisar el entorno de Lync Server 2010, y desea seguir archivando o supervisando toda la migración, también debe implementar estos características del entorno de la prueba piloto.</span><span class="sxs-lookup"><span data-stu-id="2fb94-109">If you deployed Archiving Server, Monitoring Server, or System Center Operations Manager for archiving or monitoring your Lync Server 2010 environment, and you want to continue archiving or monitoring throughout the migration, you need to also deploy these features in your pilot environment.</span></span> <span data-ttu-id="2fb94-110">La versión que implementó para archivar o supervisar el entorno de Lync Server 2010 no capturará datos en el entorno de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2fb94-110">The version you deployed to archive or monitor your Lync Server 2010 environment will not capture data in your Lync Server 2013 environment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2fb94-111">El procedimiento siguiente describe las características y la configuración que debe tener en cuenta como parte del proceso general de implementación del grupo piloto.</span><span class="sxs-lookup"><span data-stu-id="2fb94-111">The following procedure discusses features and settings you should consider as part of your overall pilot pool deployment process.</span></span> <span data-ttu-id="2fb94-112">Esta sección solo resalta los puntos clave que debe considerar como parte de la implementación de un grupo piloto.</span><span class="sxs-lookup"><span data-stu-id="2fb94-112">This section only highlights key points you should consider as part of your pilot pool deployment.</span></span> <span data-ttu-id="2fb94-113">Para conocer los pasos detallados, consulte la guía de implementación de <A href="lync-server-2013-deploying-lync-server.md">Lync Server 2013</A> .</span><span class="sxs-lookup"><span data-stu-id="2fb94-113">For detailed steps, refer to the <A href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</A> deployment guide.</span></span>



</div>

<span data-ttu-id="2fb94-114">**Para implementar un grupo de pruebas piloto de Lync Server 2013**</span><span class="sxs-lookup"><span data-stu-id="2fb94-114">**To deploy a Lync Server 2013 pilot pool**</span></span>

1.  <span data-ttu-id="2fb94-115">Inicie sesión en el equipo donde se encuentre instalado el Generador de topologías como miembro del grupo Administradores del dominio y el grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="2fb94-115">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="2fb94-116">Expanda el árbol hasta llegar a los **grupos de servidores front-end**de **Lync Server 2013** Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="2fb94-116">Expand the tree until you reach **Lync Server 2013** **Enterprise Edition Front End pools**.</span></span>

3.  <span data-ttu-id="2fb94-117">Haga clic con el botón secundario en **grupos front-end Enterprise Edition**y seleccione **nuevo grupo de servidores front-end**.</span><span class="sxs-lookup"><span data-stu-id="2fb94-117">Right click **Enterprise Edition Front End pools**, and select **New Front End Pool**.</span></span>
    
    <span data-ttu-id="2fb94-118">![Submenú selección del grupo de servidores del generador] de topologías (images/JJ205144.c2feed27-3418-42a6-a254-76e83607db9c(OCS.15).jpg "Submenú selección del grupo de servidores del generador") de topologías</span><span class="sxs-lookup"><span data-stu-id="2fb94-118">![Topology Builder Server pool selection submenu](images/JJ205144.c2feed27-3418-42a6-a254-76e83607db9c(OCS.15).jpg "Topology Builder Server pool selection submenu")</span></span>

4.  <span data-ttu-id="2fb94-119">Escriba el FQDN del grupo.</span><span class="sxs-lookup"><span data-stu-id="2fb94-119">Enter the pool FQDN.</span></span> <span data-ttu-id="2fb94-120">Cuando define el grupo piloto, puede optar por implementar un grupo de servidores front-end Enterprise Edition o un servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="2fb94-120">When you define your pilot pool, you can choose to deploy an Enterprise Edition Front End pool or a Standard Edition server.</span></span> <span data-ttu-id="2fb94-121">Lync Server 2013 no requiere que las características de su grupo piloto coincidan con lo que se ha implementado en su grupo heredado.</span><span class="sxs-lookup"><span data-stu-id="2fb94-121">Lync Server 2013 does not require that your pilot pool features match what was deployed in your legacy pool.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="2fb94-122">El nombre de dominio completo (FQDN) de grupo o servidor que defina para la agrupación piloto debe ser único.</span><span class="sxs-lookup"><span data-stu-id="2fb94-122">The pool or server fully qualified domain name (FQDN) that you define for the pilot pool must be unique.</span></span> <span data-ttu-id="2fb94-123">No puede coincidir con el nombre del grupo de servidores de Lync Server 2010 actualmente implementado o cualquier otro servidor implementado actualmente.</span><span class="sxs-lookup"><span data-stu-id="2fb94-123">It cannot match the name of the currently deployed Lync Server 2010 pool, or any other servers currently deployed.</span></span>

    
    </div>
    
    <span data-ttu-id="2fb94-124">![Página FQDN del Asistente para definir un nuevo grupo front end] (images/JJ205144.c5fd138c-e75a-413a-827f-b1461c996d40(OCS.15).jpg "Página FQDN del Asistente para definir un nuevo grupo front end")</span><span class="sxs-lookup"><span data-stu-id="2fb94-124">![Define New Front End Pool Wizard FQDN page](images/JJ205144.c5fd138c-e75a-413a-827f-b1461c996d40(OCS.15).jpg "Define New Front End Pool Wizard FQDN page")</span></span>

5.  <span data-ttu-id="2fb94-125">En la página **seleccionar características** , seleccione las casillas de las características que desee en este grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="2fb94-125">On the **Select features** page, select the check boxes for the features that you want on this Front End pool.</span></span> <span data-ttu-id="2fb94-126">Por ejemplo, si va a implementar solo la mensajería instantánea (mi) y las características de presencia, active la casilla conferencias para permitir la mensajería instantánea entre usuarios, pero no seleccione las casillas Conferencia de acceso telefónico local (RTC), telefonía IP empresarial o control de admisión de llamadas. porque representan características de conferencia de voz, vídeo y colaboración.</span><span class="sxs-lookup"><span data-stu-id="2fb94-126">For example, if you are deploying only instant messaging (IM) and presence features, you would select the Conferencing check box to allow multiparty IM, but would not select the Dial-in (PSTN) conferencing, Enterprise Voice, or Call Admission Control check boxes, because they represent voice, video, and collaborative conferencing features.</span></span> <span data-ttu-id="2fb94-127">Para obtener más información sobre cómo seleccionar las características, vea [definir y configurar un grupo de servidores front-end o un servidor Standard Edition en Lync server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="2fb94-127">For additional information on selecting features, see [Define and configure a Front End pool or Standard Edition server in Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) in the Deployment documentation.</span></span>
    
    <span data-ttu-id="2fb94-128">![Página seleccionar características de la agrupación de front-end] (images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "Página seleccionar características de la agrupación de front-end")</span><span class="sxs-lookup"><span data-stu-id="2fb94-128">![Front End Pool Select features page](images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "Front End Pool Select features page")</span></span>

6.  <span data-ttu-id="2fb94-129">En la página **Seleccionar roles de servidor** de la aplicación, le recomendamos que Collocate el servidor de mediación en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2fb94-129">On the **Select collocated server roles** page, we recommend you collocate the Mediation Server in Lync Server 2013.</span></span> <span data-ttu-id="2fb94-130">Al combinar una topología heredada con Lync Server 2013, es necesario que primero Collocate el servidor de mediación de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2fb94-130">When merging a legacy topology with Lync Server 2013, we require that you first collocate the Lync Server 2010 Mediation Server.</span></span> <span data-ttu-id="2fb94-131">Después de combinar las topologías y configurar el servidor de mediación de Lync Server 2013, puede decidir si desea mantener el servidor de mediación o cambiarlo a un servidor independiente cuando mueva la función de servidor de mediación a Lync Server 2013 más adelante en la implementación. cuatricromía.</span><span class="sxs-lookup"><span data-stu-id="2fb94-131">After merging the topologies and configuring the Lync Server 2013 Mediation Server, you can decide whether to keep the collocated Mediation Server, or change it to a stand-alone server when you move the Mediation Server role to Lync Server 2013 later in the deployment process.</span></span>
    
    <span data-ttu-id="2fb94-132">![Página del grupo de servidores front-end seleccionar roles de servidor en la página] (images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "Página del grupo de servidores front-end seleccionar roles de servidor en la página")</span><span class="sxs-lookup"><span data-stu-id="2fb94-132">![Front End Pool Select collocated server roles page](images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "Front End Pool Select collocated server roles page")</span></span>

7.  <span data-ttu-id="2fb94-133">En la página **asociar roles de servidor con este grupo de servidores front-end** , durante la implementación de un grupo piloto, no elija la opción **habilitar un grupo perimetral para que lo use el componente multimedia de este grupo de servidores front-end** .</span><span class="sxs-lookup"><span data-stu-id="2fb94-133">On the **Associate server roles with this Front End pool** page, during pilot pool deployment, do not choose the **Enable an Edge pool to be used by the media component of this Front End pool** option.</span></span> <span data-ttu-id="2fb94-134">Esta es una característica que habilitará y se conectará en línea en una fase posterior de la migración.</span><span class="sxs-lookup"><span data-stu-id="2fb94-134">This is a feature you will enable and bring online in a later phase of migration.</span></span> <span data-ttu-id="2fb94-135">Mantener esta configuración desactivada por ahora.</span><span class="sxs-lookup"><span data-stu-id="2fb94-135">Keep this setting cleared for now.</span></span>
    
    <span data-ttu-id="2fb94-136">![Página asociar roles de servidor con grupo de servidores front-end] (images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "Página asociar roles de servidor con grupo de servidores front-end")</span><span class="sxs-lookup"><span data-stu-id="2fb94-136">![Associate server roles with Front End pool page](images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "Associate server roles with Front End pool page")</span></span>

8.  <span data-ttu-id="2fb94-137">En la página **seleccionar un servidor de Office Web Apps** , haga clic en **nuevo**y especifique el FQDN del servidor de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="2fb94-137">On the **Select an Office Web Apps Server** page, click **New**, and specify the FQDN of the application server.</span></span>
    
    <span data-ttu-id="2fb94-138">![Definir nuevas propiedades de FQDN de Office Web Apps Server] (images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "Definir nuevas propiedades de FQDN de Office Web Apps Server")</span><span class="sxs-lookup"><span data-stu-id="2fb94-138">![Define New Office Web Apps Server FQDN properties](images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "Define New Office Web Apps Server FQDN properties")</span></span>

9.  <span data-ttu-id="2fb94-139">En la página **definir el archivado del almacén SQL Server** , al definir el almacén de SQL Server para el archivado y la supervisión de Lync Server, seleccione la instancia de SQL Server creada anteriormente para Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2fb94-139">On the **Define the Archiving SQL Server store** page, when defining the SQL Server store for both Lync Server Archiving and Monitoring, select the SQL Server instance created earlier for Lync Server 2013.</span></span>
    
    <span data-ttu-id="2fb94-140">Definir el archivado de la ![página del almacén SQL Server] Definir el archivado de la (images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "página del almacén SQL Server")</span><span class="sxs-lookup"><span data-stu-id="2fb94-140">![Define Archiving SQL Server store page](images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "Define Archiving SQL Server store page")</span></span>

10. <span data-ttu-id="2fb94-141">Para publicar su topología, haga clic con el botón secundario en el nodo de **Lync Server** y, a continuación, haga clic en **publicar topología**.</span><span class="sxs-lookup"><span data-stu-id="2fb94-141">To publish your topology, right-click the **Lync Server** node, and then click **Publish Topology**.</span></span>
    
    <span data-ttu-id="2fb94-142">![Generador de topología que muestra una topología] configurada (images/JJ205144.c3eafa20-159e-4355-a23d-9f72aeb26037(OCS.15).jpg "Generador de topología que muestra una topología") configurada</span><span class="sxs-lookup"><span data-stu-id="2fb94-142">![Topology Builder displaying a configured topology](images/JJ205144.c3eafa20-159e-4355-a23d-9f72aeb26037(OCS.15).jpg "Topology Builder displaying a configured topology")</span></span>

11. <span data-ttu-id="2fb94-143">Cuando el proceso de publicación haya finalizado, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="2fb94-143">When the publish process has completed, click **Finish**.</span></span>

<span data-ttu-id="2fb94-144">Para instalar una copia local del almacén de configuración e iniciar los servicios necesarios, consulte [configuración de servidores front-end y grupos front-end para Lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="2fb94-144">To install a local copy of the configuration store and start the required services, see [Setting up Front End Servers and Front End pools for Lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md) in the Deployment documentation.</span></span>


</div>

<span> </span>

</div>

</div>

</div>

