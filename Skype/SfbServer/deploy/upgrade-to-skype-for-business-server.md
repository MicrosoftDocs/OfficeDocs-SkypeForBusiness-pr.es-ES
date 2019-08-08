---
title: Actualizar a Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/14/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 74ce73bc-356b-4705-83b1-341ee010fd19
description: 'Resumen: Obtenga información sobre cómo actualizar Lync Server 2013 a Skype empresarial Server 2015. Descargue una prueba gratuita de Skype empresarial Server 2015 en el centro de evaluación de Microsoft en https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server:.'
ms.openlocfilehash: c34cbc7ce1d755f093ac14bc85d78106216c450b
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36237451"
---
# <a name="upgrade-to-skype-for-business-server-2015"></a><span data-ttu-id="4943c-104">Upgrade to Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="4943c-104">Upgrade to Skype for Business Server 2015</span></span>
 
<span data-ttu-id="4943c-105">**Resumen:** Obtenga información sobre cómo actualizar Lync Server 2013 a Skype empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="4943c-105">**Summary:** Learn how to upgrade from Lync Server 2013 to Skype for Business Server 2015.</span></span> <span data-ttu-id="4943c-106">Descargue una prueba gratuita de Skype empresarial Server 2015 en el [centro de evaluación de Microsoft](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span><span class="sxs-lookup"><span data-stu-id="4943c-106">Download a free trial of Skype for Business Server 2015 from the  [Microsoft Evaluation center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="4943c-107">Use los procedimientos de este documento para actualizar Lync Server 2013 a Skype empresarial Server 2015 con el generador de topologías de Skype empresarial Server y la nueva característica de actualización local.</span><span class="sxs-lookup"><span data-stu-id="4943c-107">Use the procedures in this document to upgrade from Lync Server 2013 to Skype for Business Server 2015 by using the Skype for Business Server Topology Builder and the new In-Place Upgrade feature.</span></span> <span data-ttu-id="4943c-108">Si quiere actualizar a partir de Lync Server 2010 o de Office Communications Server 2007 R2, consulte [planear la actualización a Skype empresarial server 2015](../plan-your-deployment/upgrade.md).</span><span class="sxs-lookup"><span data-stu-id="4943c-108">If you want to upgrade from Lync Server 2010 or Office Communications Server 2007 R2, see [Plan to upgrade to Skype for Business Server 2015](../plan-your-deployment/upgrade.md).</span></span>

> [!NOTE]
> <span data-ttu-id="4943c-109">Las actualizaciones locales estaban disponibles en Skype empresarial Server 2015, pero ya no son compatibles con Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="4943c-109">In-place upgrades were available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="4943c-110">Se admite la coexistencia en paralelo, consulte [migración a Skype empresarial Server 2019](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="4943c-110">Side by side coexistance is supported, see [Migration to Skype for Business Server 2019](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md) for more information.</span></span>
  
## <a name="upgrade-from-lync-server-2013"></a><span data-ttu-id="4943c-111">Actualizar desde Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4943c-111">Upgrade from Lync Server 2013</span></span>

<span data-ttu-id="4943c-112">La actualización de Lync Server 2013 a Skype empresarial Server 2015 implica la instalación del software necesario, el uso del generador de topologías de Skype empresarial Server para actualizar las bases de datos del grupo, y el uso de la actualización local de Skype empresarial Server en cada uno de los servidores asociados con el grupo.</span><span class="sxs-lookup"><span data-stu-id="4943c-112">Upgrading Lync Server 2013 to Skype for Business Server 2015 involves installing prerequisite software, using the Skype for Business Server Topology Builder to upgrade databases in the pool, and using the Skype for Business Server In-Place Upgrade on each of the servers associated with the pool.</span></span> <span data-ttu-id="4943c-113">Para completar la actualización, siga los ocho pasos descritos en este tema.</span><span class="sxs-lookup"><span data-stu-id="4943c-113">To complete the upgrade, go through the eight steps in this topic.</span></span>
  
### <a name="before-you-begin"></a><span data-ttu-id="4943c-114">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="4943c-114">Before you begin</span></span>

- <span data-ttu-id="4943c-115">Revise [Plan to upgrade to Skype for Business Server 2015](../plan-your-deployment/upgrade.md).</span><span class="sxs-lookup"><span data-stu-id="4943c-115">Review [Plan to upgrade to Skype for Business Server 2015](../plan-your-deployment/upgrade.md).</span></span>
    
- <span data-ttu-id="4943c-116">Revise [los requisitos del servidor para Skype empresarial server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4943c-116">Review [Server requirements for Skype for Business Server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span>
    
- <span data-ttu-id="4943c-117">[Instale los requisitos previos para Skype empresarial Server 2015](install/install-prerequisites.md) .</span><span class="sxs-lookup"><span data-stu-id="4943c-117">[Install prerequisites for Skype for Business Server 2015](install/install-prerequisites.md) .</span></span>
    
- <span data-ttu-id="4943c-118">[Instale Skype empresarial Server 2015](install/install.md) .</span><span class="sxs-lookup"><span data-stu-id="4943c-118">[Install Skype for Business Server 2015](install/install.md) .</span></span>
    
### <a name="step-1-install-administrator-tools-and-download-topology"></a><span data-ttu-id="4943c-119">Paso 1: Instalar las herramientas de administrador y descargar la topología</span><span class="sxs-lookup"><span data-stu-id="4943c-119">Step 1: Install Administrator tools and download topology</span></span>

1. <span data-ttu-id="4943c-120">Conéctese al equipo de la topología que no tiene instalado Lync OCSCore o cualquier otro componente de Lync instalado.</span><span class="sxs-lookup"><span data-stu-id="4943c-120">Connect to computer in the topology that does not have Lync OCSCore or any other Lync components installed.</span></span>
    
2. <span data-ttu-id="4943c-121">Desde el disco de instalación de Skype empresarial Server 2015, ejecute **setup. exe** desde **OCS_Volume\Setup\AMD64**.</span><span class="sxs-lookup"><span data-stu-id="4943c-121">From Skype for Business Server 2015 installation media, run **Setup.exe** from **OCS_Volume\Setup\AMD64**.</span></span> 
    
3. <span data-ttu-id="4943c-122">Haga clic en **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="4943c-122">Click **Install**.</span></span> 
    
4. <span data-ttu-id="4943c-123">Acepte el acuerdo de licencia.</span><span class="sxs-lookup"><span data-stu-id="4943c-123">Accept the license agreement.</span></span>
    
5. <span data-ttu-id="4943c-124">En el asistente de implementación, haga clic en **Instalar herramientas de administrador** y siga todos los pasos indicados.</span><span class="sxs-lookup"><span data-stu-id="4943c-124">On the Deployment Wizard, click **Install Administrator tools**, and follow the steps to install.</span></span>
    
     ![Captura de pantalla del Asistente para la implementación con enlace a Instalar herramientas de administrador activado.](../media/5bbac2d6-a5b3-42b4-a243-7bcf2b04477a.png)
  
6. <span data-ttu-id="4943c-126">En la pantalla Inicio de Windows, abra el generador de topologías de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="4943c-126">From the Windows Start screen, open Skype for Business Server Topology Builder.</span></span>
    
7. <span data-ttu-id="4943c-127">Haga clic en **Descargar topología desde implementación existente** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="4943c-127">Click **Download topology from existing deployment**, and click **Next**.</span></span>
    
8. <span data-ttu-id="4943c-128">Introduzca un nombre para la topología y haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="4943c-128">Enter a name for the topology, and click **Save**.</span></span>
    
9. <span data-ttu-id="4943c-129">Vaya a la ubicación donde ha guardado la topología y cree una copia de la misma.</span><span class="sxs-lookup"><span data-stu-id="4943c-129">Go to location where you saved the topology, and make a copy of the topology.</span></span>
    
### <a name="step-2-upgrade-and-publish-topology-using-topology-builder"></a><span data-ttu-id="4943c-130">Paso 2: Actualizar y publicar la topología con el Generador de topologías</span><span class="sxs-lookup"><span data-stu-id="4943c-130">Step 2: Upgrade and publish topology using Topology Builder</span></span>

<span data-ttu-id="4943c-131">Antes de iniciar el proceso de actualización, todos los servicios deben estar ejecutándose para los grupos que tiene previsto actualizar.</span><span class="sxs-lookup"><span data-stu-id="4943c-131">Before you start the upgrade process, all services must be running for the pools you plan to upgrade.</span></span> <span data-ttu-id="4943c-132">El objetivo es que los cambios en la topología se repliquen en las bases de datos locales de los servidores del grupo.</span><span class="sxs-lookup"><span data-stu-id="4943c-132">This is so the topology changes will be replicated to the local database of the servers in the pool.</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="4943c-133">Guarde una copia del archivo con la topología antes de actualizar.</span><span class="sxs-lookup"><span data-stu-id="4943c-133">Save a copy of your topology file before you upgrade.</span></span> <span data-ttu-id="4943c-134">Después de la actualización, no podrá degradar la topología. > si los servicios están en los mismos servidores que las bases de datos, como el servicio de chat persistente está en el mismo servidor que la base de datos de chat persistente, omita este paso y vaya al paso 4.</span><span class="sxs-lookup"><span data-stu-id="4943c-134">After you upgrade, you will not be able to downgrade the topology.>  If your services are on the same servers as your databases, like the Persistent Chat service is on the same server as the Persistent Chat database, skip this step, and go to step 4.</span></span> <span data-ttu-id="4943c-135">Después de detener los servicios, ejecute la instalación de la actualización local en cada uno de los servidores para actualizar las bases de datos locales.</span><span class="sxs-lookup"><span data-stu-id="4943c-135">After you stop the services, run the In-Place Upgrade setup on each server to upgrade the local databases.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4943c-p108">Si la topología tiene una base de datos back-end que se refleja, verá tanto la base de datos principal como la reflejada al **publicar la topología** con el Generador de topologías. Asegúrese de que todas las bases de datos se estén ejecutando en la principal y seleccione solo la principal, no el reflejo, cuando publique la topología, de lo contrario verá una advertencia después de publicarla.</span><span class="sxs-lookup"><span data-stu-id="4943c-p108">If the topology has a back-end database that is mirrored then you will see both the Principal and the Mirrored databases show up **when you publish the topology** using Topology Builder. Make sure all of the databases are running on the Principal and only select the Principal, not the mirror, when publishing the topology otherwise you will see a warning after publishing the topology.</span></span>
  
<span data-ttu-id="4943c-138">Elija una de las siguientes opciones para actualizar y publicar una nueva topología con el generador de topología de Skype empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="4943c-138">Pick one of the options below to upgrade and publish a new topology by using the Skype for Business Server 2015 Topology Builder.</span></span> <span data-ttu-id="4943c-139">Cuando complete los pasos y haya publicado la topología actualizada, vaya al paso 3 de este tema.</span><span class="sxs-lookup"><span data-stu-id="4943c-139">After you complete the steps and publish the updated topology, move to Step 3 in this topic.</span></span>
  
#### <a name="option-1-upgrade-an-isolated-front-end-pool-and-associated-archiving-and-monitoring-stores"></a><span data-ttu-id="4943c-140">Opción 1: Actualizar un grupo front-end aislado y los almacenes de archivado y supervisión asociados</span><span class="sxs-lookup"><span data-stu-id="4943c-140">Option 1: Upgrade an isolated Front End pool and associated Archiving and Monitoring stores</span></span>

<span data-ttu-id="4943c-141">Si el grupo que está actualizando tiene una dependencia respecto a un almacén de archivado y supervisión, dicho almacén también se actualizará al realizar los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="4943c-141">If the pool you're upgrading has an Archiving and Monitoring store dependency, when you use the following steps, the Archiving and Monitoring store will be upgraded as well.</span></span>
  
1. <span data-ttu-id="4943c-142">En el generador de topología, haga clic con el botón secundario en un grupo de servidores de Lync Server 2013, seleccione **actualizar a Skype empresarial server 2015**y siga los pasos.</span><span class="sxs-lookup"><span data-stu-id="4943c-142">In Topology Builder, right-click a Lync Server 2013 pool, select **Upgrade to Skype for Business Server 2015**, and follow the steps.</span></span> 
    
     ![Captura de pantalla del menú contextual con opción de actualización de Lync Server 2013.](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
2. <span data-ttu-id="4943c-144">En el generador de topologías, haga clic en**topología de publicación** de **acciones** > o en**publicación**de**topología** > de **acción** > .</span><span class="sxs-lookup"><span data-stu-id="4943c-144">In Topology Builder, click **Action** > **Publish topology** or **Action** > **Topology** > **Publish**.</span></span> 
    
     ![Captura de pantalla del menú Acción con la opción Publicar topología en Topology Builder.](../media/d6712634-9205-401f-a0b0-3ea096ca51bf.png)
  
3. <span data-ttu-id="4943c-146">Durante la publicación, elija instalar una base de datos en el almacén de archivado y supervisión.</span><span class="sxs-lookup"><span data-stu-id="4943c-146">During publishing, choose to install a database on the Archiving and Monitoring store.</span></span>
    
#### <a name="option-2-upgrade-front-end-pool-without-upgrading-archiving-and-monitoring-stores"></a><span data-ttu-id="4943c-147">Opción 2: actualizar el grupo de servidores front-end sin actualizar los almacenes de archivado y supervisión</span><span class="sxs-lookup"><span data-stu-id="4943c-147">Option 2: Upgrade Front End pool without upgrading Archiving and Monitoring stores</span></span>

<span data-ttu-id="4943c-p110">Si sigue los siguientes pasos, el archivado y la supervisión del grupo seleccionado quedarán deshabilitados. Tras la actualización, el grupo no tendrá almacén de archivado y supervisión.</span><span class="sxs-lookup"><span data-stu-id="4943c-p110">If you use the following steps, archiving and monitoring for the selected pool are disabled. The pool will not have Archiving and Monitoring stores after the upgrade.</span></span>
  
1. <span data-ttu-id="4943c-150">En el generador de topologías, seleccione el grupo de servidores de Lync Server 2013 que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="4943c-150">In Topology Builder, select the Lync Server 2013 pool that you want to upgrade.</span></span>
    
2. <span data-ttu-id="4943c-151">Quite la dependencia de los almacenes de supervisión y archivado de 2013 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4943c-151">Remove the dependency to the Lync Server 2013 Archiving and Monitoring stores.</span></span> 
    
   - <span data-ttu-id="4943c-152">Ir a la **acción** > **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="4943c-152">Go to **Action** > **Edit properties**.</span></span>
    
   - <span data-ttu-id="4943c-153">Desmarque la casilla **Archivado**.</span><span class="sxs-lookup"><span data-stu-id="4943c-153">Clear the **Archiving** check box.</span></span>
    
     ![Captura de pantalla de la casilla de verificación Archivado del cuadro de diálogo Editar propiedades.](../media/9a88427e-80ee-49d0-a767-809fa9a5faf1.png)
  
   - <span data-ttu-id="4943c-155">Desmarque la casilla **Supervisión**.</span><span class="sxs-lookup"><span data-stu-id="4943c-155">Clear the **Monitoring** check box.</span></span>
    
     ![Captura de pantalla del cuadro de diálogo Editar propiedades que en la que aparece la casilla de verificación Supervisión.](../media/880acf33-57bb-4521-8717-cf5b67261ed4.png)
  
3. <span data-ttu-id="4943c-157">Haga clic con el botón derecho en el grupo de servidores de Lync Server 2013, seleccione **actualizar a Skype empresarial server 2015**y siga los pasos.</span><span class="sxs-lookup"><span data-stu-id="4943c-157">Right-click the Lync Server 2013 pool, select **Upgrade to Skype for Business Server 2015**, and follow the steps.</span></span> 
    
     ![Captura de pantalla del menú contextual con opción de actualización de Lync Server 2013.](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
4. <span data-ttu-id="4943c-159">En el generador de topologías, haga clic en**topología de publicación** de **acciones** > o en**publicación**de**topología** > de **acción** > .</span><span class="sxs-lookup"><span data-stu-id="4943c-159">In Topology Builder, click **Action** > **Publish topology** or **Action** > **Topology** > **Publish**.</span></span> 
    
#### <a name="option-3-upgrade-front-end-pool-and-associated-it-to-new-skype-for-business-server-2015-archiving-and-monitoring-stores"></a><span data-ttu-id="4943c-160">Opción 3: actualizar el grupo de servidores front-end y asociarlo a los nuevos almacenes de almacenamiento y supervisión de Skype empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="4943c-160">Option 3: Upgrade Front End pool and associated it to new Skype for Business Server 2015 Archiving and Monitoring stores</span></span>

<span data-ttu-id="4943c-161">Si sigue los pasos siguientes, se interrumpirá el archivado y supervisión en el almacén anterior y se iniciará en un nuevo almacén que haya creado.</span><span class="sxs-lookup"><span data-stu-id="4943c-161">If you use the following steps, archiving and monitoring will stop in the previous store and start in the new store you've created.</span></span> 
  
1. <span data-ttu-id="4943c-162">En el generador de topologías, seleccione el grupo de servidores de Lync Server 2013 que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="4943c-162">In Topology Builder, select the Lync Server 2013 pool that you want to upgrade.</span></span> 
    
2. <span data-ttu-id="4943c-163">Quite la dependencia de los almacenes de supervisión y archivado de 2013 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4943c-163">Remove the dependency to the Lync Server 2013 Archiving and Monitoring stores.</span></span> 
    
   - <span data-ttu-id="4943c-164">Ir a la **acción** > **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="4943c-164">Go to **Action** > **Edit properties**.</span></span>
    
   - <span data-ttu-id="4943c-165">Desmarque la casilla **Archivado**.</span><span class="sxs-lookup"><span data-stu-id="4943c-165">Clear the **Archiving** check box.</span></span>
    
     ![Captura de pantalla de la casilla de verificación Archivado del cuadro de diálogo Editar propiedades.](../media/9a88427e-80ee-49d0-a767-809fa9a5faf1.png)
  
   - <span data-ttu-id="4943c-167">Desmarque la casilla **Supervisión**.</span><span class="sxs-lookup"><span data-stu-id="4943c-167">Clear the **Monitoring** check box.</span></span>
    
     ![Captura de pantalla del cuadro de diálogo Editar propiedades que en la que aparece la casilla de verificación Supervisión.](../media/880acf33-57bb-4521-8717-cf5b67261ed4.png)
  
3. <span data-ttu-id="4943c-169">Haga clic con el botón derecho en el grupo de servidores de Lync Server 2013, seleccione **actualizar a Skype empresarial server 2015**y siga los pasos.</span><span class="sxs-lookup"><span data-stu-id="4943c-169">Right-click the Lync Server 2013 pool, select **Upgrade to Skype for Business Server 2015**, and follow the steps.</span></span> 
    
     ![Captura de pantalla del menú contextual con opción de actualización de Lync Server 2013.](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
4. <span data-ttu-id="4943c-171">Cree un nuevo almacén SQL para archivado.</span><span class="sxs-lookup"><span data-stu-id="4943c-171">Create a new SQL store for Archiving.</span></span> 
    
   - <span data-ttu-id="4943c-172">Seleccione las propiedades de la sección y de**Editar**la **acción** > .</span><span class="sxs-lookup"><span data-stu-id="4943c-172">Select the pool and **Action** > **Edit properties**.</span></span> 
    
   -  <span data-ttu-id="4943c-173">Marque la casilla **Archivado**.</span><span class="sxs-lookup"><span data-stu-id="4943c-173">Select the **Archiving** check box.</span></span>
    
   - <span data-ttu-id="4943c-174">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="4943c-174">Click **New**.</span></span>
    
     ![Captura de pantalla del cuadro de diálogo Editar propiedades en la que aparece el botón Nuevo bajo la sección de archivado.](../media/3a4a18e7-8251-4736-837c-2b486f64f896.png)
  
5. <span data-ttu-id="4943c-176">Cree un nuevo almacén SQL para supervisión.</span><span class="sxs-lookup"><span data-stu-id="4943c-176">Create a new SQL store for Monitoring.</span></span> 
    
   - <span data-ttu-id="4943c-177">Seleccione las propiedades de la sección y de**Editar**la **acción** > .</span><span class="sxs-lookup"><span data-stu-id="4943c-177">Select the pool and **Action** > **Edit properties**.</span></span> 
    
   -  <span data-ttu-id="4943c-178">Marque la casilla **Supervisión**.</span><span class="sxs-lookup"><span data-stu-id="4943c-178">Select the **Monitoring** check box.</span></span>
    
   - <span data-ttu-id="4943c-179">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="4943c-179">Click **New**.</span></span>
    
     ![Captura de pantalla del cuadro de diálogo Editar propiedades en la que aparece el botón Nuevo bajo la sección de supervisión.](../media/729c72a7-0068-4e0d-99dc-e480a6bfbf1d.png)
  
6. <span data-ttu-id="4943c-181">En el generador de topologías, haga clic en**topología de publicación** de **acciones** > o en**publicación**de**topología** > de **acción** > .</span><span class="sxs-lookup"><span data-stu-id="4943c-181">In Topology Builder, click **Action** > **Publish topology** or **Action** > **Topology** > **Publish**.</span></span> 
    
7. <span data-ttu-id="4943c-182">Durante la publicación, elija instalar la base de datos en el nuevo almacén de archivado y supervisión.</span><span class="sxs-lookup"><span data-stu-id="4943c-182">During publishing, choose to install the database on the new Archiving and Monitoring store.</span></span>
    
### <a name="step-3-wait-for-replication"></a><span data-ttu-id="4943c-183">Paso 3: Esperar la replicación</span><span class="sxs-lookup"><span data-stu-id="4943c-183">Step 3: Wait for replication</span></span>

<span data-ttu-id="4943c-184">Espere un tiempo para que la topología actualizada se publique en todos los servidores del entorno.</span><span class="sxs-lookup"><span data-stu-id="4943c-184">Give replication some time to publish the updated topology to all the servers in the environment.</span></span>
  
### <a name="step-4-stop-all-services-in-pool-to-be-upgraded"></a><span data-ttu-id="4943c-185">Paso 4: Detener todos los servicios en el grupo a actualizar</span><span class="sxs-lookup"><span data-stu-id="4943c-185">Step 4: Stop all services in pool to be upgraded</span></span>

<span data-ttu-id="4943c-186">En cada servidor que atiende el grupo que va a actualizar, ejecute el siguiente cmdlet en PowerShell:</span><span class="sxs-lookup"><span data-stu-id="4943c-186">On each server that is servicing the pool that you're going to upgrade, run the following cmdlet in PowerShell:</span></span>
  
```
Disable-CsComputer -Scorch
```

<span data-ttu-id="4943c-187">Le recomendamos que use Disable-CsComputer, ya que es posible que tenga que reiniciar el servidor durante el proceso de actualización local.</span><span class="sxs-lookup"><span data-stu-id="4943c-187">We recommend using Disable-CsComputer because you may need to reboot the server during the In-Place Upgrade process.</span></span> <span data-ttu-id="4943c-188">Si usas STOP-CsWindowsService, es posible que algunos servicios se reinicien automáticamente después de un reinicio.</span><span class="sxs-lookup"><span data-stu-id="4943c-188">If you use Stop-CsWindowsService, some services may restart automatically after a reboot.</span></span> <span data-ttu-id="4943c-189">Esto puede provocar errores en la actualización local.</span><span class="sxs-lookup"><span data-stu-id="4943c-189">This may cause the In-Place Upgrade to fail.</span></span>
  
### <a name="step-5-upgrade-front-end-pools-and-non-front-end-pool-servers"></a><span data-ttu-id="4943c-190">Paso 5: Actualizar grupos front-end y servidores de grupos que no son front-end</span><span class="sxs-lookup"><span data-stu-id="4943c-190">Step 5: Upgrade Front End pools and non-Front End pool servers</span></span>

> [!NOTE]
>  <span data-ttu-id="4943c-191">Antes de la actualización, instale todos los requisitos previos necesarios para Skype empresarial Server 2015, que incluyen: > al menos 32 GB de espacio libre antes de intentar una actualización.</span><span class="sxs-lookup"><span data-stu-id="4943c-191">Before upgrading please install all new prerequisites required for Skype for Business Server 2015 which include:>  At least 32GB of free space before attempting an upgrade.</span></span> <span data-ttu-id="4943c-192">Además, asegúrese de que la unidad es una unidad local fija, no está conectada por USB o FireWire, está formateada con el sistema de archivos NTFS, no está comprimida y no contiene un archivo de paginación. > PowerShell versión 6.2.9200.0 o posterior. > el último Lync Server 2013 Actualización acumulativa instalada. > SQL Server 2012 SP1 instalado. > se instalan los siguientes KB (se instalan automáticamente si usas Microsoft Update): > Windows Server 2008 R2-[KB2533623](https://support.microsoft.com/kb/2533623)> windows Server 2012-[KB2858668](https://support.microsoft.com/kb/2858668)> Windows Server 2012 R2-[KB2982006](https://support.microsoft.com/kb/2982006)</span><span class="sxs-lookup"><span data-stu-id="4943c-192">In addition, make sure that the drive is a fixed local drive, is not connected by USB or Firewire, is formatted with NTFS file system, is not compressed, and does not contain a page file.>  PowerShell version 6.2.9200.0 or later.>  The latest Lync Server 2013 Cumulative Update installed.>  SQL Server 2012 SP1 installed.>  The following KB's installed (installed automatically if using Microsoft Update):>  Windows Server 2008 R2 -[KB2533623](https://support.microsoft.com/kb/2533623)>  Windows Server 2012 -[KB2858668](https://support.microsoft.com/kb/2858668)>  Windows Server 2012 R2 -[KB2982006](https://support.microsoft.com/kb/2982006)</span></span>
  
<span data-ttu-id="4943c-193">Use la actualización local en cada servidor para actualizar el grupo de servidores front-end, el grupo perimetral, el servidor de mediación y el grupo de chats persistentes.</span><span class="sxs-lookup"><span data-stu-id="4943c-193">Use the In-Place Upgrade on each server to update the Front End pool, Edge pool, Mediation server, and the Persistent Chat pool.</span></span>
  
1. <span data-ttu-id="4943c-194">En cada servidor, ejecute **setup. exe** desde **OCS_Volume\Setup\amd64** en los medios de instalación de Skype empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="4943c-194">On each server, run **Setup.exe** from **OCS_Volume\Setup\amd64** on the Skype for Business Server 2015 installation media.</span></span>
    
2. <span data-ttu-id="4943c-195">Acepte el contrato de licencia y siga las indicaciones para la actualización local.</span><span class="sxs-lookup"><span data-stu-id="4943c-195">Accept the license agreement and follow the prompts for the In-Place Upgrade.</span></span>
    
3. <span data-ttu-id="4943c-196">Repita estos pasos para cada servidor del grupo de servidores front-end y en cada servidor de grupo que no sea front-end.</span><span class="sxs-lookup"><span data-stu-id="4943c-196">Repeat these steps for each server in the Front End pool and on each non-Front End pool server.</span></span>
    
> [!NOTE]
> <span data-ttu-id="4943c-197">Es posible que se le solicite que reinicie el servidor durante la actualización local.</span><span class="sxs-lookup"><span data-stu-id="4943c-197">You might be prompted to reboot the server during the In-Place Upgrade.</span></span> <span data-ttu-id="4943c-198">Es normal.</span><span class="sxs-lookup"><span data-stu-id="4943c-198">That's ok.</span></span> <span data-ttu-id="4943c-199">Después de reiniciar, la actualización local continuará desde el punto en que se quedó.</span><span class="sxs-lookup"><span data-stu-id="4943c-199">After you reboot, the In-Place Upgrade will continue from where it left off.</span></span> 
  
<span data-ttu-id="4943c-200">Cuando la actualización local se complete correctamente, verá el siguiente mensaje.</span><span class="sxs-lookup"><span data-stu-id="4943c-200">When the In-Place Upgrade completes successfully, you see the following message.</span></span>
  
![Captura de pantalla que muestra la actualización in situ completada correctamente.](../media/2f52cb50-9bb4-4714-a982-9c7a0865f78a.png)
  
### <a name="step-6-restart-services-on-all-upgraded-servers"></a><span data-ttu-id="4943c-202">Paso 6: Reiniciar servicios en todos los servidores actualizados</span><span class="sxs-lookup"><span data-stu-id="4943c-202">Step 6: Restart services on all upgraded servers</span></span>

> [!NOTE]
> <span data-ttu-id="4943c-203">Antes de reiniciar los servicios, asegúrese de que%ProgramData%\WindowsFabric no existe en todos los servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="4943c-203">Before restarting the services, please make sure %ProgramData%\WindowsFabric doesn't exist on all Front End Servers.</span></span> <span data-ttu-id="4943c-204">Si existe, elimínelo antes de iniciar los servicios.</span><span class="sxs-lookup"><span data-stu-id="4943c-204">If it exists, delete it before starting the services.</span></span> 
  
- <span data-ttu-id="4943c-205">Después de actualizar todos los servidores en el grupo de servidores front-end, reinicie los servicios con el siguiente comando de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="4943c-205">After you've upgraded all servers in the Front End pool, restart the services by using the following PowerShell command:</span></span> 
    
  ```
  Start-CsPool
  ```

    > [!NOTE]
    > <span data-ttu-id="4943c-p115">Si aún se encuentra pendiente un reinicio del sistema antes de empezar la ejecución de la actualización local, esta no le solicitará el reinicio al final de la instalación. De esta manera, se provocarán excepciones de ensamblado en el primer servidor front-end cuando intente iniciar los servicios con el cmdlet Start-CSPool. Para resolver estos errores, reinicie todos los servidores del grupo y ejecute nuevamente el cmdlet.</span><span class="sxs-lookup"><span data-stu-id="4943c-p115">If there is already a pending system reboot needed before you start running In-Place Upgrade, then In-Place Upgrade won't ask you to reboot at the end of the installation. This will cause some assembly exceptions to be thrown against the first Front End server when you try to start services using the Start-CSPool cmdlet. To resolve these errors, reboot all of the servers in the pool and run the cmdlet again.</span></span> 
  
- <span data-ttu-id="4943c-209">En los servidores de los demás grupos, reinicie los servicios con el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="4943c-209">On the non-Front End pool servers, restart the services by using the following command:</span></span>
    
  ```
  Start-CsWindowsService
  ```

<span data-ttu-id="4943c-210">Cuando haga clic en **Aceptar** en la página de actualización local, verá el siguiente recordatorio para que complete este paso.</span><span class="sxs-lookup"><span data-stu-id="4943c-210">After you click **OK** on the In-Place Upgrade page, you'll see the following reminder to complete this step.</span></span>
  
![Captura de pantalla que muestra los siguientes pasos una vez finalizada correctamente la actualización in situ.](../media/6a7236b6-9ef9-4df3-8682-b0e4021810f9.png)
  
### <a name="step-7-verify-skype-for-business-functionality-works"></a><span data-ttu-id="4943c-212">Paso 7: comprobar la funcionalidad de Skype empresarial</span><span class="sxs-lookup"><span data-stu-id="4943c-212">Step 7: Verify Skype for Business functionality works</span></span>

<span data-ttu-id="4943c-213">Para asegurarse de que la actualización se realizó correctamente, para el grupo que se actualizó, pruebe Skype empresarial para asegurarse de que la funcionalidad funciona según lo esperado.</span><span class="sxs-lookup"><span data-stu-id="4943c-213">To make sure the upgrade was successful, for the pool that was upgraded, test Skype for Business to make sure the functionality is working as expected.</span></span> 
  
### <a name="step-8-upgrade-secondary-pools"></a><span data-ttu-id="4943c-214">Paso 8: Actualizar grupos secundarios</span><span class="sxs-lookup"><span data-stu-id="4943c-214">Step 8: Upgrade secondary pools</span></span>

<span data-ttu-id="4943c-215">Repita los pasos de este tema para actualizar cualquier grupo adicional que tenga en su entorno.</span><span class="sxs-lookup"><span data-stu-id="4943c-215">Repeat the steps in this topic to upgrade any additional pools that you have in your environment.</span></span>
  
## <a name="troubleshoot-issues-with-the-in-place-upgrade"></a><span data-ttu-id="4943c-216">Solución de problemas con la actualización local</span><span class="sxs-lookup"><span data-stu-id="4943c-216">Troubleshoot issues with the In-Place Upgrade</span></span>

<span data-ttu-id="4943c-217">Si se produce un error en la actualización local, es posible que vea un mensaje similar al de la siguiente imagen.</span><span class="sxs-lookup"><span data-stu-id="4943c-217">If the In-Place Upgrade fails, you might see a message similar to what's in the following image.</span></span> 
  
![Captura de pantalla que muestra el fallo de una actualización in situ porque no se ha instalado una actualización acumulada requerida.](../media/f84db06b-0841-45a9-870d-7ba4b5a463d5.png)
  
<span data-ttu-id="4943c-219">Revise el mensaje completo que aparece en la parte inferior de la pantalla para solucionar el problema.</span><span class="sxs-lookup"><span data-stu-id="4943c-219">Review the full message at the bottom of the page to help you troubleshoot the issue.</span></span> <span data-ttu-id="4943c-220">Haga clic en **Ver registros** para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="4943c-220">Click **View logs** to get more detail.</span></span>
  
<span data-ttu-id="4943c-221">Si se produce un error en la actualización local al **comprobar la preparación** de la actualización o la instalación de los **requisitos previos que faltan**, asegúrese de que el servidor tiene todas las actualizaciones más recientes de Windows Server, Lync Server y SQL Server aplicadas y que todo el software y los roles necesarios son instalar.</span><span class="sxs-lookup"><span data-stu-id="4943c-221">If the In-Place Upgrade fails on **Verifying upgrade readiness** or **Installing missing prerequisites**, make sure the server has all the latest Windows Server, Lync Server, and SQL Server updates applied, and all the required software and roles are installed.</span></span> <span data-ttu-id="4943c-222">Para obtener una lista de lo que se requiere, consulte [requisitos del servidor para Skype empresarial server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md) e [Instale los requisitos previos para skype empresarial Server 2015](install/install-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="4943c-222">For a list of what's required, see [Server requirements for Skype for Business Server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md) and [Install prerequisites for Skype for Business Server 2015](install/install-prerequisites.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4943c-223">Vea también</span><span class="sxs-lookup"><span data-stu-id="4943c-223">See also</span></span>

[<span data-ttu-id="4943c-224">Plan to upgrade to Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="4943c-224">Plan to upgrade to Skype for Business Server 2015</span></span>](../plan-your-deployment/upgrade.md)
  
[<span data-ttu-id="4943c-225">Server requirements for Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="4943c-225">Server requirements for Skype for Business Server 2015</span></span>](../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="4943c-226">Instalar requisitos previos para Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="4943c-226">Install prerequisites for Skype for Business Server 2015</span></span>](install/install-prerequisites.md)
  
[<span data-ttu-id="4943c-227">Instalar Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="4943c-227">Install Skype for Business Server 2015</span></span>](install/install.md)
