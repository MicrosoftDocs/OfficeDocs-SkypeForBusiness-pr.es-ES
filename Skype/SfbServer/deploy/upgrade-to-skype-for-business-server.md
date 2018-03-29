---
title: Actualizar a Skype Empresarial Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 7/14/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 74ce73bc-356b-4705-83b1-341ee010fd19
description: 'Resumen: Conozca cómo actualizar desde Lync Server 2013 a Skype para Business Server 2015. Descargue una prueba gratuita de Skype para Business Server 2015 desde el centro de Evaluation de Microsoft en: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: f3c451e0c1590daab2c6576964c1e1ce5ec3c4ec
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="upgrade-to-skype-for-business-server-2015"></a><span data-ttu-id="a7889-104">Actualizar a Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="a7889-104">Upgrade to Skype for Business Server 2015</span></span>
 
<span data-ttu-id="a7889-105">**Resumen:** Obtenga información sobre cómo actualizar Lync Server 2013 a Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="a7889-105">**Summary:** Learn how to upgrade from Lync Server 2013 to Skype for Business Server 2015.</span></span> <span data-ttu-id="a7889-106">Descargue una prueba gratuita de Skype para Business Server 2015 desde el [Centro de evaluación de Microsoft](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span><span class="sxs-lookup"><span data-stu-id="a7889-106">Download a free trial of Skype for Business Server 2015 from the  [Microsoft Evaluation center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="a7889-107">Utilice los procedimientos de este documento para actualizar de Lync Server 2013 a Skype para Business Server 2015 utilizando el Skype para el generador de topología de servidor empresarial y la nueva característica de actualización In-situ.</span><span class="sxs-lookup"><span data-stu-id="a7889-107">Use the procedures in this document to upgrade from Lync Server 2013 to Skype for Business Server 2015 by using the Skype for Business Server Topology Builder and the new In-Place Upgrade feature.</span></span> <span data-ttu-id="a7889-108">Si desea actualizar de Lync Server 2010 o Office Communications Server 2007 R2, vea [previsto actualizar a Skype para Business Server 2015](../plan-your-deployment/upgrade.md).</span><span class="sxs-lookup"><span data-stu-id="a7889-108">If you want to upgrade from Lync Server 2010 or Office Communications Server 2007 R2, see [Plan to upgrade to Skype for Business Server 2015](../plan-your-deployment/upgrade.md).</span></span>
  
## <a name="upgrade-from-lync-server-2013"></a><span data-ttu-id="a7889-109">Actualización de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a7889-109">Upgrade from Lync Server 2013</span></span>

<span data-ttu-id="a7889-110">Actualización de Lync Server 2013 a Skype para Business Server 2015 implica la instalación del software necesario, utilizando el Skype para el generador de topología de servidor de negocios para actualizar las bases de datos en el grupo y utilizando el Skype para actualización In-situ de Business Server en cada uno de los servidores asociados al grupo.</span><span class="sxs-lookup"><span data-stu-id="a7889-110">Upgrading Lync Server 2013 to Skype for Business Server 2015 involves installing prerequisite software, using the Skype for Business Server Topology Builder to upgrade databases in the pool, and using the Skype for Business Server In-Place Upgrade on each of the servers associated with the pool.</span></span> <span data-ttu-id="a7889-111">Para completar la actualización, siga los ocho pasos descritos en este tema.</span><span class="sxs-lookup"><span data-stu-id="a7889-111">To complete the upgrade, go through the eight steps in this topic.</span></span>
  
### <a name="before-you-begin"></a><span data-ttu-id="a7889-112">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="a7889-112">Before you begin</span></span>

- <span data-ttu-id="a7889-113">Revisar [previsto actualizar a Skype para Business Server 2015](../plan-your-deployment/upgrade.md).</span><span class="sxs-lookup"><span data-stu-id="a7889-113">Review [Plan to upgrade to Skype for Business Server 2015](../plan-your-deployment/upgrade.md).</span></span>
    
- <span data-ttu-id="a7889-114">Revise los [requisitos del servidor para Skype para Business Server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a7889-114">Review [Server requirements for Skype for Business Server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span>
    
- <span data-ttu-id="a7889-115">[Instalar los requisitos previos para Skype para Business Server 2015](install/install-prerequisites.md) .</span><span class="sxs-lookup"><span data-stu-id="a7889-115">[Install prerequisites for Skype for Business Server 2015](install/install-prerequisites.md) .</span></span>
    
- <span data-ttu-id="a7889-116">[Instalar Skype para Business Server 2015](install/install.md) .</span><span class="sxs-lookup"><span data-stu-id="a7889-116">[Install Skype for Business Server 2015](install/install.md) .</span></span>
    
### <a name="step-1-install-administrator-tools-and-download-topology"></a><span data-ttu-id="a7889-117">Paso 1: Instalar las herramientas de administrador y descargar la topología</span><span class="sxs-lookup"><span data-stu-id="a7889-117">Step 1: Install Administrator tools and download topology</span></span>

1. <span data-ttu-id="a7889-118">Conectarse al equipo en la topología que carece de Lync OCSCore u otros componentes de Lync instalados.</span><span class="sxs-lookup"><span data-stu-id="a7889-118">Connect to computer in the topology that does not have Lync OCSCore or any other Lync components installed.</span></span>
    
2. <span data-ttu-id="a7889-119">De Skype para los medios de instalación de Business Server 2015, ejecute **Setup.exe** desde **OCS_Volume\Setup\AMD64**.</span><span class="sxs-lookup"><span data-stu-id="a7889-119">From Skype for Business Server 2015 installation media, run **Setup.exe** from **OCS_Volume\Setup\AMD64**.</span></span> 
    
3. <span data-ttu-id="a7889-120">Haga clic en **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="a7889-120">Click **Install**.</span></span> 
    
4. <span data-ttu-id="a7889-121">Acepte el acuerdo de licencia.</span><span class="sxs-lookup"><span data-stu-id="a7889-121">Accept the license agreement.</span></span>
    
5. <span data-ttu-id="a7889-122">En el asistente de implementación, haga clic en **Instalar herramientas de administrador** y siga todos los pasos indicados.</span><span class="sxs-lookup"><span data-stu-id="a7889-122">On the Deployment Wizard, click **Install Administrator tools**, and follow the steps to install.</span></span>
    
     ![Captura de pantalla del Asistente para la implementación con enlace a Instalar herramientas de administrador activado.](../media/5bbac2d6-a5b3-42b4-a243-7bcf2b04477a.png)
  
6. <span data-ttu-id="a7889-124">Desde la pantalla de inicio de Windows, abra Skype para el generador de topología de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="a7889-124">From the Windows Start screen, open Skype for Business Server Topology Builder.</span></span>
    
7. <span data-ttu-id="a7889-125">Haga clic en **Descargar topología desde implementación existente** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="a7889-125">Click **Download topology from existing deployment**, and click **Next**.</span></span>
    
8. <span data-ttu-id="a7889-126">Introduzca un nombre para la topología y haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="a7889-126">Enter a name for the topology, and click **Save**.</span></span>
    
9. <span data-ttu-id="a7889-127">Vaya a la ubicación donde ha guardado la topología y cree una copia de la misma.</span><span class="sxs-lookup"><span data-stu-id="a7889-127">Go to location where you saved the topology, and make a copy of the topology.</span></span>
    
### <a name="step-2-upgrade-and-publish-topology-using-topology-builder"></a><span data-ttu-id="a7889-128">Paso 2: Actualizar y publicar la topología con el Generador de topologías</span><span class="sxs-lookup"><span data-stu-id="a7889-128">Step 2: Upgrade and publish topology using Topology Builder</span></span>

<span data-ttu-id="a7889-129">Antes de iniciar el proceso de actualización, deben ejecutar todos los servicios para los grupos que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="a7889-129">Before you start the upgrade process, all services must be running for the pools you plan to upgrade.</span></span> <span data-ttu-id="a7889-130">El objetivo es que los cambios en la topología se repliquen en las bases de datos locales de los servidores del grupo.</span><span class="sxs-lookup"><span data-stu-id="a7889-130">This is so the topology changes will be replicated to the local database of the servers in the pool.</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="a7889-131">Guarde una copia del archivo con la topología antes de actualizar.</span><span class="sxs-lookup"><span data-stu-id="a7889-131">Save a copy of your topology file before you upgrade.</span></span> <span data-ttu-id="a7889-132">Después de la actualización, no podrá degradar la topología. > Si los servicios están en los mismos servidores que las bases de datos, al igual que el servicio está en el mismo servidor que la base de datos persistente Chat persistente Chat omitir este paso y vaya al paso 4.</span><span class="sxs-lookup"><span data-stu-id="a7889-132">After you upgrade, you will not be able to downgrade the topology.>  If your services are on the same servers as your databases, like the Persistent Chat service is on the same server as the Persistent Chat database, skip this step, and go to step 4.</span></span> <span data-ttu-id="a7889-133">Después de detener los servicios, ejecute la instalación de la actualización local en cada uno de los servidores para actualizar las bases de datos locales.</span><span class="sxs-lookup"><span data-stu-id="a7889-133">After you stop the services, run the In-Place Upgrade setup on each server to upgrade the local databases.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a7889-p107">Si la topología tiene una base de datos back-end que se refleja, verá tanto la base de datos principal como la reflejada al **publicar la topología** con el Generador de topologías. Asegúrese de que todas las bases de datos se estén ejecutando en la principal y seleccione solo la principal, no el reflejo, cuando publique la topología, de lo contrario verá una advertencia después de publicarla.</span><span class="sxs-lookup"><span data-stu-id="a7889-p107">If the topology has a back-end database that is mirrored then you will see both the Principal and the Mirrored databases show up **when you publish the topology** using Topology Builder. Make sure all of the databases are running on the Principal and only select the Principal, not the mirror, when publishing the topology otherwise you will see a warning after publishing the topology.</span></span>
  
<span data-ttu-id="a7889-136">Elija una de las opciones siguientes para actualizar y publicar una nueva topología mediante el Skype para el generador de topología de Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="a7889-136">Pick one of the options below to upgrade and publish a new topology by using the Skype for Business Server 2015 Topology Builder.</span></span> <span data-ttu-id="a7889-137">Cuando complete los pasos y haya publicado la topología actualizada, vaya al paso 3 de este tema.</span><span class="sxs-lookup"><span data-stu-id="a7889-137">After you complete the steps and publish the updated topology, move to Step 3 in this topic.</span></span>
  
#### <a name="option-1-upgrade-an-isolated-front-end-pool-and-associated-archiving-and-monitoring-stores"></a><span data-ttu-id="a7889-138">Opción 1: Actualizar un grupo front-end aislado y los almacenes de archivado y supervisión asociados</span><span class="sxs-lookup"><span data-stu-id="a7889-138">Option 1: Upgrade an isolated Front End pool and associated Archiving and Monitoring stores</span></span>

<span data-ttu-id="a7889-139">Si el grupo que está actualizando tiene una dependencia respecto a un almacén de archivado y supervisión, dicho almacén también se actualizará al realizar los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="a7889-139">If the pool you're upgrading has an Archiving and Monitoring store dependency, when you use the following steps, the Archiving and Monitoring store will be upgraded as well.</span></span>
  
1. <span data-ttu-id="a7889-140">Generador de topología, haga clic en un grupo de Lync Server 2013, seleccione **actualizar a Skype para Business Server 2015**y siga los pasos.</span><span class="sxs-lookup"><span data-stu-id="a7889-140">In Topology Builder, right-click a Lync Server 2013 pool, select **Upgrade to Skype for Business Server 2015**, and follow the steps.</span></span> 
    
     ![Captura de pantalla del menú contextual con opción de actualización de Lync Server 2013.](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
2. <span data-ttu-id="a7889-142">Generador de topología, haga clic en la **acción** > **topología de publicar** o **acción** > **topología** > **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="a7889-142">In Topology Builder, click **Action** > **Publish topology** or **Action** > **Topology** > **Publish**.</span></span> 
    
     ![Captura de pantalla del menú Acción con la opción Publicar topología en Topology Builder.](../media/d6712634-9205-401f-a0b0-3ea096ca51bf.png)
  
3. <span data-ttu-id="a7889-144">Durante la publicación, elija instalar una base de datos en el almacén de archivado y supervisión.</span><span class="sxs-lookup"><span data-stu-id="a7889-144">During publishing, choose to install a database on the Archiving and Monitoring store.</span></span>
    
#### <a name="option-2-upgrade-front-end-pool-without-upgrading-archiving-and-monitoring-stores"></a><span data-ttu-id="a7889-145">Opción 2: Grupo actualización de Front-End sin actualizar Archiving y supervisión de almacenes</span><span class="sxs-lookup"><span data-stu-id="a7889-145">Option 2: Upgrade Front End pool without upgrading Archiving and Monitoring stores</span></span>

<span data-ttu-id="a7889-p109">Si sigue los siguientes pasos, el archivado y la supervisión del grupo seleccionado quedarán deshabilitados. Tras la actualización, el grupo no tendrá almacén de archivado y supervisión.</span><span class="sxs-lookup"><span data-stu-id="a7889-p109">If you use the following steps, archiving and monitoring for the selected pool are disabled. The pool will not have Archiving and Monitoring stores after the upgrade.</span></span>
  
1. <span data-ttu-id="a7889-148">Generador de topología, seleccione el grupo de 2013 de Lync Server que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="a7889-148">In Topology Builder, select the Lync Server 2013 pool that you want to upgrade.</span></span>
    
2. <span data-ttu-id="a7889-149">Quitar la dependencia a las tiendas de Lync Server 2013 Archiving y supervisión.</span><span class="sxs-lookup"><span data-stu-id="a7889-149">Remove the dependency to the Lync Server 2013 Archiving and Monitoring stores.</span></span> 
    
   - <span data-ttu-id="a7889-150">Ir a la **acción** > **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="a7889-150">Go to **Action** > **Edit properties**.</span></span>
    
   - <span data-ttu-id="a7889-151">Desmarque la casilla **Archivado**.</span><span class="sxs-lookup"><span data-stu-id="a7889-151">Clear the **Archiving** check box.</span></span>
    
     ![Captura de pantalla de la casilla de verificación Archivado del cuadro de diálogo Editar propiedades.](../media/9a88427e-80ee-49d0-a767-809fa9a5faf1.png)
  
   - <span data-ttu-id="a7889-153">Desmarque la casilla **Supervisión**.</span><span class="sxs-lookup"><span data-stu-id="a7889-153">Clear the **Monitoring** check box.</span></span>
    
     ![Captura de pantalla del cuadro de diálogo Editar propiedades que en la que aparece la casilla de verificación Supervisión.](../media/880acf33-57bb-4521-8717-cf5b67261ed4.png)
  
3. <span data-ttu-id="a7889-155">Haga clic derecho en el grupo de Lync Server 2013, seleccione **actualizar a Skype para Business Server 2015**y siga los pasos.</span><span class="sxs-lookup"><span data-stu-id="a7889-155">Right-click the Lync Server 2013 pool, select **Upgrade to Skype for Business Server 2015**, and follow the steps.</span></span> 
    
     ![Captura de pantalla del menú contextual con opción de actualización de Lync Server 2013.](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
4. <span data-ttu-id="a7889-157">Generador de topología, haga clic en la **acción** > **topología de publicar** o **acción** > **topología** > **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="a7889-157">In Topology Builder, click **Action** > **Publish topology** or **Action** > **Topology** > **Publish**.</span></span> 
    
#### <a name="option-3-upgrade-front-end-pool-and-associated-it-to-new-skype-for-business-server-2015-archiving-and-monitoring-stores"></a><span data-ttu-id="a7889-158">Opción 3: Grupo actualización de Front-End y la asocia a Skype nuevos almacenes Business Server 2015 Archiving y supervisión</span><span class="sxs-lookup"><span data-stu-id="a7889-158">Option 3: Upgrade Front End pool and associated it to new Skype for Business Server 2015 Archiving and Monitoring stores</span></span>

<span data-ttu-id="a7889-159">Si sigue los pasos siguientes, se interrumpirá el archivado y supervisión en el almacén anterior y se iniciará en un nuevo almacén que haya creado.</span><span class="sxs-lookup"><span data-stu-id="a7889-159">If you use the following steps, archiving and monitoring will stop in the previous store and start in the new store you've created.</span></span> 
  
1. <span data-ttu-id="a7889-160">Generador de topología, seleccione el grupo de 2013 de Lync Server que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="a7889-160">In Topology Builder, select the Lync Server 2013 pool that you want to upgrade.</span></span> 
    
2. <span data-ttu-id="a7889-161">Quitar la dependencia a las tiendas de Lync Server 2013 Archiving y supervisión.</span><span class="sxs-lookup"><span data-stu-id="a7889-161">Remove the dependency to the Lync Server 2013 Archiving and Monitoring stores.</span></span> 
    
   - <span data-ttu-id="a7889-162">Ir a la **acción** > **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="a7889-162">Go to **Action** > **Edit properties**.</span></span>
    
   - <span data-ttu-id="a7889-163">Desmarque la casilla **Archivado**.</span><span class="sxs-lookup"><span data-stu-id="a7889-163">Clear the **Archiving** check box.</span></span>
    
     ![Captura de pantalla de la casilla de verificación Archivado del cuadro de diálogo Editar propiedades.](../media/9a88427e-80ee-49d0-a767-809fa9a5faf1.png)
  
   - <span data-ttu-id="a7889-165">Desmarque la casilla **Supervisión**.</span><span class="sxs-lookup"><span data-stu-id="a7889-165">Clear the **Monitoring** check box.</span></span>
    
     ![Captura de pantalla del cuadro de diálogo Editar propiedades que en la que aparece la casilla de verificación Supervisión.](../media/880acf33-57bb-4521-8717-cf5b67261ed4.png)
  
3. <span data-ttu-id="a7889-167">Haga clic derecho en el grupo de Lync Server 2013, seleccione **actualizar a Skype para Business Server 2015**y siga los pasos.</span><span class="sxs-lookup"><span data-stu-id="a7889-167">Right-click the Lync Server 2013 pool, select **Upgrade to Skype for Business Server 2015**, and follow the steps.</span></span> 
    
     ![Captura de pantalla del menú contextual con opción de actualización de Lync Server 2013.](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
4. <span data-ttu-id="a7889-169">Cree un nuevo almacén SQL para archivado.</span><span class="sxs-lookup"><span data-stu-id="a7889-169">Create a new SQL store for Archiving.</span></span> 
    
   - <span data-ttu-id="a7889-170">Seleccione el grupo y la **acción** > **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="a7889-170">Select the pool and **Action** > **Edit properties**.</span></span> 
    
   -  <span data-ttu-id="a7889-171">Marque la casilla **Archivado**.</span><span class="sxs-lookup"><span data-stu-id="a7889-171">Select the **Archiving** check box.</span></span>
    
   - <span data-ttu-id="a7889-172">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="a7889-172">Click **New**.</span></span>
    
     ![Captura de pantalla del cuadro de diálogo Editar propiedades en la que aparece el botón Nuevo bajo la sección de archivado.](../media/3a4a18e7-8251-4736-837c-2b486f64f896.png)
  
5. <span data-ttu-id="a7889-174">Cree un nuevo almacén SQL para supervisión.</span><span class="sxs-lookup"><span data-stu-id="a7889-174">Create a new SQL store for Monitoring.</span></span> 
    
   - <span data-ttu-id="a7889-175">Seleccione el grupo y la **acción** > **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="a7889-175">Select the pool and **Action** > **Edit properties**.</span></span> 
    
   -  <span data-ttu-id="a7889-176">Marque la casilla **Supervisión**.</span><span class="sxs-lookup"><span data-stu-id="a7889-176">Select the **Monitoring** check box.</span></span>
    
   - <span data-ttu-id="a7889-177">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="a7889-177">Click **New**.</span></span>
    
     ![Captura de pantalla del cuadro de diálogo Editar propiedades en la que aparece el botón Nuevo bajo la sección de supervisión.](../media/729c72a7-0068-4e0d-99dc-e480a6bfbf1d.png)
  
6. <span data-ttu-id="a7889-179">Generador de topología, haga clic en la **acción** > **topología de publicar** o **acción** > **topología** > **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="a7889-179">In Topology Builder, click **Action** > **Publish topology** or **Action** > **Topology** > **Publish**.</span></span> 
    
7. <span data-ttu-id="a7889-180">Durante la publicación, elija instalar la base de datos en el nuevo almacén de archivado y supervisión.</span><span class="sxs-lookup"><span data-stu-id="a7889-180">During publishing, choose to install the database on the new Archiving and Monitoring store.</span></span>
    
### <a name="step-3-wait-for-replication"></a><span data-ttu-id="a7889-181">Paso 3: Esperar la replicación</span><span class="sxs-lookup"><span data-stu-id="a7889-181">Step 3: Wait for replication</span></span>

<span data-ttu-id="a7889-182">Espere un tiempo para que la topología actualizada se publique en todos los servidores del entorno.</span><span class="sxs-lookup"><span data-stu-id="a7889-182">Give replication some time to publish the updated topology to all the servers in the environment.</span></span>
  
### <a name="step-4-stop-all-services-in-pool-to-be-upgraded"></a><span data-ttu-id="a7889-183">Paso 4: Detener todos los servicios en el grupo a actualizar</span><span class="sxs-lookup"><span data-stu-id="a7889-183">Step 4: Stop all services in pool to be upgraded</span></span>

<span data-ttu-id="a7889-184">En cada servidor que atiende el grupo que va a actualizar, ejecute el siguiente cmdlet de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a7889-184">On each server that is servicing the pool that you're going to upgrade, run the following cmdlet in PowerShell:</span></span>
  
```
Disable-CsComputer -Scorch
```

<span data-ttu-id="a7889-185">Se recomienda utilizar deshabilitar CsComputer porque puede que necesite reiniciar el servidor durante el proceso de actualización en contexto.</span><span class="sxs-lookup"><span data-stu-id="a7889-185">We recommend using Disable-CsComputer because you may need to reboot the server during the In-Place Upgrade process.</span></span> <span data-ttu-id="a7889-186">Si utiliza Stop-CsWindowsService, algunos servicios se reinician automáticamente después de reiniciar el equipo.</span><span class="sxs-lookup"><span data-stu-id="a7889-186">If you use Stop-CsWindowsService, some services may restart automatically after a reboot.</span></span> <span data-ttu-id="a7889-187">Esto puede provocar la actualización In situ a fallar.</span><span class="sxs-lookup"><span data-stu-id="a7889-187">This may cause the In-Place Upgrade to fail.</span></span>
  
### <a name="step-5-upgrade-front-end-pools-and-non-front-end-pool-servers"></a><span data-ttu-id="a7889-188">Paso 5: Actualizar grupos front-end y servidores de grupos que no son front-end</span><span class="sxs-lookup"><span data-stu-id="a7889-188">Step 5: Upgrade Front End pools and non-Front End pool servers</span></span>

> [!NOTE]
>  <span data-ttu-id="a7889-189">Antes de actualizar instale todos los nuevos requisitos previos requeridos por Skype para Business Server 2015 que incluyen: > al menos 32GB de espacio libre antes de intentar una actualización.</span><span class="sxs-lookup"><span data-stu-id="a7889-189">Before upgrading please install all new prerequisites required for Skype for Business Server 2015 which include:>  At least 32GB of free space before attempting an upgrade.</span></span> <span data-ttu-id="a7889-190">Además, asegúrese de que la unidad es una unidad local fija, no está conectada mediante USB o Firewire, está formateada con el sistema de archivos NTFS, no se comprime y no contiene un archivo de página. > PowerShell versión 6.2.9200.0 o posterior. > la más reciente de Lync Server 2013 Actualización acumulativa instalada. > instalado el SP1 de SQL Server 2012. > los siguiente KB instalado (instala automáticamente si usa Microsoft Update): > Windows Server 2008 R2 -[KB2533623](https://support.microsoft.com/kb/2533623)> Windows Server 2012 -[KB2858668](https://support.microsoft.com/kb/2858668)> Windows 2012 Server R2 -[KB2982006](https://support.microsoft.com/kb/2982006)</span><span class="sxs-lookup"><span data-stu-id="a7889-190">In addition, make sure that the drive is a fixed local drive, is not connected by USB or Firewire, is formatted with NTFS file system, is not compressed, and does not contain a page file.>  PowerShell version 6.2.9200.0 or later.>  The latest Lync Server 2013 Cumulative Update installed.>  SQL Server 2012 SP1 installed.>  The following KB's installed (installed automatically if using Microsoft Update):>  Windows Server 2008 R2 -[KB2533623](https://support.microsoft.com/kb/2533623)>  Windows Server 2012 -[KB2858668](https://support.microsoft.com/kb/2858668)>  Windows Server 2012 R2 -[KB2982006](https://support.microsoft.com/kb/2982006)</span></span>
  
<span data-ttu-id="a7889-191">Utilice la actualización en contexto en cada servidor para actualizar el grupo de servidores Front-End, piscina de borde, servidor de mediación y el grupo de Chat persistentes.</span><span class="sxs-lookup"><span data-stu-id="a7889-191">Use the In-Place Upgrade on each server to update the Front End pool, Edge pool, Mediation server, and the Persistent Chat pool.</span></span>
  
1. <span data-ttu-id="a7889-192">En cada servidor, ejecute **Setup.exe** desde **OCS_Volume\Setup\amd64** en el Skype para los medios de instalación de Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="a7889-192">On each server, run **Setup.exe** from **OCS_Volume\Setup\amd64** on the Skype for Business Server 2015 installation media.</span></span>
    
2. <span data-ttu-id="a7889-193">Acepte el contrato de licencia y siga las instrucciones para la actualización en contexto.</span><span class="sxs-lookup"><span data-stu-id="a7889-193">Accept the license agreement and follow the prompts for the In-Place Upgrade.</span></span>
    
3. <span data-ttu-id="a7889-194">Repita estos pasos para cada servidor en el grupo de servidores Front-End y en cada servidor del grupo no Front-End.</span><span class="sxs-lookup"><span data-stu-id="a7889-194">Repeat these steps for each server in the Front End pool and on each non-Front End pool server.</span></span>
    
> [!NOTE]
> <span data-ttu-id="a7889-195">Es posible que se le solicite que reinicie el servidor durante la actualización local.</span><span class="sxs-lookup"><span data-stu-id="a7889-195">You might be prompted to reboot the server during the In-Place Upgrade.</span></span> <span data-ttu-id="a7889-196">Es normal.</span><span class="sxs-lookup"><span data-stu-id="a7889-196">That's ok.</span></span> <span data-ttu-id="a7889-197">Después de reiniciar, la actualización en contexto continuará desde donde se quedó.</span><span class="sxs-lookup"><span data-stu-id="a7889-197">After you reboot, the In-Place Upgrade will continue from where it left off.</span></span> 
  
<span data-ttu-id="a7889-198">Cuando la actualización local se complete correctamente, verá el siguiente mensaje.</span><span class="sxs-lookup"><span data-stu-id="a7889-198">When the In-Place Upgrade completes successfully, you see the following message.</span></span>
  
![Captura de pantalla que muestra la actualización in situ completada correctamente.](../media/2f52cb50-9bb4-4714-a982-9c7a0865f78a.png)
  
### <a name="step-6-restart-services-on-all-upgraded-servers"></a><span data-ttu-id="a7889-200">Paso 6: Reiniciar servicios en todos los servidores actualizados</span><span class="sxs-lookup"><span data-stu-id="a7889-200">Step 6: Restart services on all upgraded servers</span></span>

> [!NOTE]
> <span data-ttu-id="a7889-201">Antes de reiniciar los servicios, asegúrese de que %ProgramData%\WindowsFabric no existe en todos los servidores frontales.</span><span class="sxs-lookup"><span data-stu-id="a7889-201">Before restarting the services, please make sure %ProgramData%\WindowsFabric doesn't exist on all Front End Servers.</span></span> <span data-ttu-id="a7889-202">Si existe, elimínelo antes de iniciar los servicios.</span><span class="sxs-lookup"><span data-stu-id="a7889-202">If it exists, delete it before starting the services.</span></span> 
  
- <span data-ttu-id="a7889-203">Después de haber actualizado todos los servidores del grupo de Front-End, reinicie los servicios utilizando el siguiente comando de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a7889-203">After you've upgraded all servers in the Front End pool, restart the services by using the following PowerShell command:</span></span> 
    
  ```
  Start-CsPool
  ```

    > [!NOTE]
    > <span data-ttu-id="a7889-p114">Si aún se encuentra pendiente un reinicio del sistema antes de empezar la ejecución de la actualización local, esta no le solicitará el reinicio al final de la instalación. De esta manera, se provocarán excepciones de ensamblado en el primer servidor front-end cuando intente iniciar los servicios con el cmdlet Start-CSPool. Para resolver estos errores, reinicie todos los servidores del grupo y ejecute nuevamente el cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a7889-p114">If there is already a pending system reboot needed before you start running In-Place Upgrade, then In-Place Upgrade won't ask you to reboot at the end of the installation. This will cause some assembly exceptions to be thrown against the first Front End server when you try to start services using the Start-CSPool cmdlet. To resolve these errors, reboot all of the servers in the pool and run the cmdlet again.</span></span> 
  
- <span data-ttu-id="a7889-207">En los servidores de los demás grupos, reinicie los servicios con el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="a7889-207">On the non-Front End pool servers, restart the services by using the following command:</span></span>
    
  ```
  Start-CsWindowsService
  ```

<span data-ttu-id="a7889-208">Cuando haga clic en **Aceptar** en la página de actualización local, verá el siguiente recordatorio para que complete este paso.</span><span class="sxs-lookup"><span data-stu-id="a7889-208">After you click **OK** on the In-Place Upgrade page, you'll see the following reminder to complete this step.</span></span>
  
![Captura de pantalla que muestra los siguientes pasos una vez finalizada correctamente la actualización in situ.](../media/6a7236b6-9ef9-4df3-8682-b0e4021810f9.png)
  
### <a name="step-7-verify-skype-for-business-functionality-works"></a><span data-ttu-id="a7889-210">Paso 7: Comprobar Skype para obras de funcionalidad de negocios</span><span class="sxs-lookup"><span data-stu-id="a7889-210">Step 7: Verify Skype for Business functionality works</span></span>

<span data-ttu-id="a7889-211">Skype para empresas para asegurarse de que la funcionalidad de prueba para asegurarse de que la actualización tuvo éxito, para el grupo que se haya actualizado, funciona como está previsto.</span><span class="sxs-lookup"><span data-stu-id="a7889-211">To make sure the upgrade was successful, for the pool that was upgraded, test Skype for Business to make sure the functionality is working as expected.</span></span> 
  
### <a name="step-8-upgrade-secondary-pools"></a><span data-ttu-id="a7889-212">Paso 8: Actualizar grupos secundarios</span><span class="sxs-lookup"><span data-stu-id="a7889-212">Step 8: Upgrade secondary pools</span></span>

<span data-ttu-id="a7889-213">Repita los pasos de este tema para actualizar cualquier grupo adicional que tenga en su entorno.</span><span class="sxs-lookup"><span data-stu-id="a7889-213">Repeat the steps in this topic to upgrade any additional pools that you have in your environment.</span></span>
  
## <a name="troubleshoot-issues-with-the-in-place-upgrade"></a><span data-ttu-id="a7889-214">Solución de problemas con la actualización local</span><span class="sxs-lookup"><span data-stu-id="a7889-214">Troubleshoot issues with the In-Place Upgrade</span></span>

<span data-ttu-id="a7889-215">Si se produce un error en la actualización local, es posible que vea un mensaje similar al de la siguiente imagen.</span><span class="sxs-lookup"><span data-stu-id="a7889-215">If the In-Place Upgrade fails, you might see a message similar to what's in the following image.</span></span> 
  
![Captura de pantalla que muestra el fallo de una actualización in situ porque no se ha instalado una actualización acumulada requerida.](../media/f84db06b-0841-45a9-870d-7ba4b5a463d5.png)
  
<span data-ttu-id="a7889-p115">Revise el mensaje completo que aparece en la parte inferior de la pantalla para solucionar el problema. Haga clic en **Ver registros** para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="a7889-p115">Review the full message at the bottom of the page to help you troubleshoot the issue. Click **View logs** to get more detail.</span></span>
  
<span data-ttu-id="a7889-219">Si la actualización In situ se produce un error en la **comprobación de preparación de actualización** o ** instalar los requisitos previos que faltan **, asegúrese de que el servidor tiene todas las más recientes de Windows Server, Lync Server y actualizaciones de SQL Server y el software necesario y los roles son instalado.</span><span class="sxs-lookup"><span data-stu-id="a7889-219">If the In-Place Upgrade fails on **Verifying upgrade readiness** or ** Installing missing prerequisites**, make sure the server has all the latest Windows Server, Lync Server, and SQL Server updates applied, and all the required software and roles are installed.</span></span> <span data-ttu-id="a7889-220">Para obtener una lista de lo que se requiere, consulte [requisitos del servidor para Skype para Business Server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md) e [Instalar requisitos previos de Skype para Business Server 2015](install/install-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="a7889-220">For a list of what's required, see [Server requirements for Skype for Business Server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md) and [Install prerequisites for Skype for Business Server 2015](install/install-prerequisites.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a7889-221">Vea también</span><span class="sxs-lookup"><span data-stu-id="a7889-221">See also</span></span>

#### 

[<span data-ttu-id="a7889-222">Plan de actualización a Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="a7889-222">Plan to upgrade to Skype for Business Server 2015</span></span>](../plan-your-deployment/upgrade.md)
  
[<span data-ttu-id="a7889-223">Requisitos del servidor para Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="a7889-223">Server requirements for Skype for Business Server 2015</span></span>](../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="a7889-224">Instalar los requisitos previos para Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="a7889-224">Install prerequisites for Skype for Business Server 2015</span></span>](install/install-prerequisites.md)
  
[<span data-ttu-id="a7889-225">Instalar Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="a7889-225">Install Skype for Business Server 2015</span></span>](install/install.md)

