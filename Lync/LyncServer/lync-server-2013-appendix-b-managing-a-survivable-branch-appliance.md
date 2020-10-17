---
title: 'Lync Server 2013: Apéndice B: administración de una aplicación de sucursal con funciones de supervivencia'
description: 'Lync Server 2013: Apéndice B: administración de una aplicación de sucursal con funciones de supervivencia.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Appendix B: Managing a Survivable Branch Appliance'
ms:assetid: 2ec9d505-6d39-491c-9524-8cf36866b855
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425797(v=OCS.15)
ms:contentKeyID: 48183773
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e66d97f538ee751d7bf12b0d0f70ff3a3f5576b2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561836"
---
# <a name="appendix-b-managing-a-survivable-branch-appliance-in-lync-server-2013"></a><span data-ttu-id="d5351-103">Apéndice B: administración de una aplicación de sucursal con funciones de supervivencia en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5351-103">Appendix B: Managing a Survivable Branch Appliance in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d5351-104">_**Última modificación del tema:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="d5351-104">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="d5351-105">En este tema se describen los procedimientos para administrar una aplicación de sucursal con funciones de supervivencia.</span><span class="sxs-lookup"><span data-stu-id="d5351-105">This topic describes the procedures for managing a Survivable Branch Appliance.</span></span> <span data-ttu-id="d5351-106">En concreto, cómo reemplazar y cambiar el nombre de una aplicación de sucursal con funciones de supervivencia y cómo cambiar el grupo de servidores front-end 2013 de Lync Server con el que está asociada la aplicación de sucursal con funciones de supervivencia.</span><span class="sxs-lookup"><span data-stu-id="d5351-106">Specifically, how to replace and rename a Survivable Branch Appliance, and how to change the Lync Server 2013 Front End pool that the Survivable Branch Appliance is associated with.</span></span>

<div>

## <a name="to-replace-a-survivable-branch-appliance"></a><span data-ttu-id="d5351-107">Reemplazar una aplicación de sucursal con funciones de supervivencia</span><span class="sxs-lookup"><span data-stu-id="d5351-107">To Replace a Survivable Branch Appliance</span></span>

1.  <span data-ttu-id="d5351-108">Detenga todos los servicios de Lync Server 2013 en la aplicación de sucursal con funciones de supervivencia.</span><span class="sxs-lookup"><span data-stu-id="d5351-108">Stop all Lync Server 2013 services on the Survivable Branch Appliance.</span></span> <span data-ttu-id="d5351-109">(Consulte la documentación del proveedor de la aplicación de sucursal con funciones de supervivencia).</span><span class="sxs-lookup"><span data-stu-id="d5351-109">(See the Survivable Branch Appliance vendor documentation.)</span></span>

2.  <span data-ttu-id="d5351-110">Recomenda Quite la aplicación de sucursal con funciones de supervivencia del dominio.</span><span class="sxs-lookup"><span data-stu-id="d5351-110">(Recommended) Remove the Survivable Branch Appliance from the domain.</span></span>

3.  <span data-ttu-id="d5351-111">Para eliminar el objeto de equipo de aplicación de sucursal con funciones de supervivencia de servicios de dominio de Active Directory, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="d5351-111">Delete the Survivable Branch Appliance computer object in Active Directory Domain Services, by following these steps:</span></span>
    
      - <span data-ttu-id="d5351-112">Inicie sesión en un servidor miembro como miembro del grupo Administradores de organización.</span><span class="sxs-lookup"><span data-stu-id="d5351-112">Log on to a member server as a member of the Enterprise Admins group.</span></span>
    
      - <span data-ttu-id="d5351-113">Haga clic en **Inicio**, en **Herramientas administrativas** y, a continuación, en **Usuarios y equipos de Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="d5351-113">Click **Start**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>
    
      - <span data-ttu-id="d5351-114">Haga clic con el botón derecho en el objeto aplicación de sucursal con funciones de supervivencia y haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="d5351-114">Right-click the Survivable Branch Appliance object, and click **Delete**.</span></span>

4.  <span data-ttu-id="d5351-115">Vuelva a agregar el objeto de equipo de aplicación de sucursal con funciones de supervivencia.</span><span class="sxs-lookup"><span data-stu-id="d5351-115">Add the Survivable Branch Appliance computer object again.</span></span> <span data-ttu-id="d5351-116">(Consulte [Agregar una aplicación de sucursal con funciones de supervivencia a Active Directory en Lync Server 2013](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md)).</span><span class="sxs-lookup"><span data-stu-id="d5351-116">(See [Add a Survivable Branch Appliance to Active Directory in Lync Server 2013](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md).)</span></span>

5.  <span data-ttu-id="d5351-117">Espere a que se produzca la replicación de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d5351-117">Wait for Active Directory replication to take place.</span></span>

6.  <span data-ttu-id="d5351-118">Abra el shell de administración de Lync Server y escriba **enable-CSTopology**.</span><span class="sxs-lookup"><span data-stu-id="d5351-118">Open the Lync Server Management Shell, and type **Enable-CSTopology**.</span></span>

7.  <span data-ttu-id="d5351-119">Conecte la nueva aplicación de sucursal con funciones de supervivencia a la red y siga los pasos de [implementación de una aplicación o servidor de sucursal con funciones de supervivencia con las tareas del sitio de Lync server 2013-central](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) e [implemente una aplicación o servidor de sucursal con funciones de supervivencia con Lync Server 2013-Branch site Task](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md).</span><span class="sxs-lookup"><span data-stu-id="d5351-119">Connect the new Survivable Branch Appliance to the network, and follow the steps in [Deploying a Survivable Branch Appliance or Server with Lync Server 2013 - central site tasks](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) and [Deploy a Survivable Branch Appliance or Server with Lync Server 2013 - branch site task](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md).</span></span>

</div>

<div>

## <a name="to-rename-a-survivable-branch-appliance"></a><span data-ttu-id="d5351-120">Cambiar el nombre de una aplicación de sucursal con funciones de supervivencia</span><span class="sxs-lookup"><span data-stu-id="d5351-120">To Rename a Survivable Branch Appliance</span></span>

1.  <span data-ttu-id="d5351-121">Mueva los usuarios a un sitio central.</span><span class="sxs-lookup"><span data-stu-id="d5351-121">Move users to the central site.</span></span> <span data-ttu-id="d5351-122">Para obtener más información, consulte [Move users to a otro pool in Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).</span><span class="sxs-lookup"><span data-stu-id="d5351-122">For details, see [Move users to another pool in Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).</span></span>

2.  <span data-ttu-id="d5351-123">Detenga todos los servicios de Lync Server 2013 en la aplicación de sucursal con funciones de supervivencia.</span><span class="sxs-lookup"><span data-stu-id="d5351-123">Stop all Lync Server 2013 services on the Survivable Branch Appliance.</span></span> <span data-ttu-id="d5351-124">(Consulte la documentación del proveedor de la aplicación de sucursal con funciones de supervivencia).</span><span class="sxs-lookup"><span data-stu-id="d5351-124">(See the Survivable Branch Appliance vendor documentation.)</span></span>

3.  <span data-ttu-id="d5351-125">Para quitar la aplicación de sucursal con funciones de supervivencia de la topología, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="d5351-125">Remove the Survivable Branch Appliance from the topology, by following these steps:</span></span>
    
      - <span data-ttu-id="d5351-126">Haga clic sucesivamente en **Inicio**, **Todos los programas**, **Microsoft Lync Server** y **Lync Server Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="d5351-126">Click **Start**, click **All Programs**, click **Microsoft Lync Server**, and then click **Lync Server Topology Builder**.</span></span>
    
      - <span data-ttu-id="d5351-127">En el árbol de la consola, expanda **sitios de sucursal**, haga clic en la aplicación de sucursal con funciones de supervivencia y, a continuación, haga clic en **eliminar** en el panel de acciones.</span><span class="sxs-lookup"><span data-stu-id="d5351-127">In the console tree, expand **Branch Sites**, click the Survivable Branch Appliance, and then click **Delete** on the Action pane.</span></span>

4.  <span data-ttu-id="d5351-128">Quite la aplicación de sucursal con funciones de supervivencia del dominio.</span><span class="sxs-lookup"><span data-stu-id="d5351-128">Remove the Survivable Branch Appliance from the domain.</span></span>

5.  <span data-ttu-id="d5351-129">Para eliminar el objeto de equipo de aplicación de sucursal con funciones de supervivencia de Active Directory, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="d5351-129">Delete the Survivable Branch Appliance computer object in Active Directory, by following these steps:</span></span>
    
      - <span data-ttu-id="d5351-130">Inicie sesión en un controlador de dominio como miembro del grupo Administradores de organización.</span><span class="sxs-lookup"><span data-stu-id="d5351-130">Log on to a domain controller as a member of the Enterprise Admins group.</span></span>
    
      - <span data-ttu-id="d5351-131">Haga clic en **Inicio**, en **Herramientas administrativas** y después en **Usuarios y equipos de Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="d5351-131">Click **Start**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>
    
      - <span data-ttu-id="d5351-132">Haga clic con el botón derecho en el objeto aplicación de sucursal con funciones de supervivencia y haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="d5351-132">Right-click the Survivable Branch Appliance object, and click **Delete**.</span></span>

6.  <span data-ttu-id="d5351-133">Restaurar la aplicación de sucursal con funciones de supervivencia a los valores predeterminados de fábrica.</span><span class="sxs-lookup"><span data-stu-id="d5351-133">Restore the Survivable Branch Appliance to factory defaults.</span></span> <span data-ttu-id="d5351-134">(Consulte la documentación del proveedor de la aplicación de sucursal con funciones de supervivencia).</span><span class="sxs-lookup"><span data-stu-id="d5351-134">(See the Survivable Branch Appliance vendor documentation.)</span></span>

7.  <span data-ttu-id="d5351-135">Siga los pasos que se indican en [implementar una aplicación o servidor de sucursal con funciones de supervivencia con las tareas del sitio de Lync server 2013-central](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) e [implemente una aplicación o un servidor de sucursal con funciones de supervivencia con Lync Server 2013: tarea de sitio de sucursal](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md).</span><span class="sxs-lookup"><span data-stu-id="d5351-135">Follow the steps in [Deploying a Survivable Branch Appliance or Server with Lync Server 2013 - central site tasks](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) and [Deploy a Survivable Branch Appliance or Server with Lync Server 2013 - branch site task](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md).</span></span>

8.  <span data-ttu-id="d5351-136">Mueva a los usuarios a la aplicación de sucursal con el nombre supervivencia.</span><span class="sxs-lookup"><span data-stu-id="d5351-136">Move users to the renamed Survivable Branch Appliance.</span></span> <span data-ttu-id="d5351-137">Para obtener más información, consulte [Move users to a otro pool in Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).</span><span class="sxs-lookup"><span data-stu-id="d5351-137">For details, see [Move users to another pool in Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).</span></span>

</div>

<div>

## <a name="to-change-the-lync-server-front-end-pool-that-the-survivable-branch-appliance-is-associated-with"></a><span data-ttu-id="d5351-138">Cambiar el grupo de servidores front-end de Lync Server al que la aplicación de sucursal con funciones de supervivencia está asociada</span><span class="sxs-lookup"><span data-stu-id="d5351-138">To Change the Lync Server Front End Pool that the Survivable Branch Appliance Is Associated With</span></span>

1.  <span data-ttu-id="d5351-139">Mueva los usuarios de la aplicación de sucursal con funciones de supervivencia al grupo de servidores front-end de Lync Server en el sitio central.</span><span class="sxs-lookup"><span data-stu-id="d5351-139">Move users from the Survivable Branch Appliance to the Lync Server Front End pool at the central site.</span></span> <span data-ttu-id="d5351-140">Para obtener más información, consulte [Move users to a otro pool in Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).</span><span class="sxs-lookup"><span data-stu-id="d5351-140">For details, see [Move users to another pool in Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).</span></span>

2.  <span data-ttu-id="d5351-141">Detenga todos los servicios de Lync Server en la aplicación de sucursal con funciones de supervivencia.</span><span class="sxs-lookup"><span data-stu-id="d5351-141">Stop all Lync Server services on the Survivable Branch Appliance.</span></span> <span data-ttu-id="d5351-142">(Consulte la documentación del proveedor de la aplicación de sucursal con funciones de supervivencia).</span><span class="sxs-lookup"><span data-stu-id="d5351-142">(See the Survivable Branch Appliance vendor documentation).</span></span>

3.  <span data-ttu-id="d5351-143">Siga estos pasos para actualizar el grupo de servidores front-end de Lync Server con el que está asociada la aplicación de sucursal con funciones de supervivencia:</span><span class="sxs-lookup"><span data-stu-id="d5351-143">Update the Lync Server Front End pool that the Survivable Branch Appliance is associated with, by following these steps:</span></span>
    
      - <span data-ttu-id="d5351-144">Haga clic sucesivamente en **Inicio**, **Todos los programas**, **Microsoft Lync Server ** y **Lync Server Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="d5351-144">Click **Start**, click **All Programs**, click **Microsoft Lync Server**, and then click **Lync Server Topology Builder**.</span></span>
    
      - <span data-ttu-id="d5351-145">Expanda **Sitios de sucursal**.</span><span class="sxs-lookup"><span data-stu-id="d5351-145">Expand **Branch Sites**.</span></span>
    
      - <span data-ttu-id="d5351-146">Haga clic con el botón secundario en el objeto aplicación de sucursal con funciones de supervivencia que desea modificar y haga clic en **Editar propiedades** .</span><span class="sxs-lookup"><span data-stu-id="d5351-146">Right-click the Survivable Branch Appliance object to modify, and click **Edit Properties**</span></span>
    
      - <span data-ttu-id="d5351-147">En resistencia, seleccione el nuevo grupo de servidores front-end al que se asociará la aplicación de sucursal con funciones de supervivencia y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d5351-147">Under Resiliency, select the new Front End pool the Survivable Branch Appliance is to be associated to, and then click **Next**.</span></span>
    
      - <span data-ttu-id="d5351-148">En el árbol de la consola, haga clic con el botón secundario en la nueva aplicación de sucursal con funciones de supervivencia, haga clic en **topología**y, a continuación, en **publicar**.</span><span class="sxs-lookup"><span data-stu-id="d5351-148">In the console tree, right-click the new Survivable Branch Appliance, click **Topology**, and then click **Publish**.</span></span>

4.  <span data-ttu-id="d5351-149">Reinicie todos los servicios de Lync Server en la aplicación de sucursal con funciones de supervivencia.</span><span class="sxs-lookup"><span data-stu-id="d5351-149">Restart all Lync Server Services on the Survivable Branch Appliance.</span></span>

5.  <span data-ttu-id="d5351-150">Pruebe la aplicación de sucursal con funciones de supervivencia.</span><span class="sxs-lookup"><span data-stu-id="d5351-150">Test the Survivable Branch Appliance.</span></span> <span data-ttu-id="d5351-151">Para obtener más información, consulte [usuarios domésticos en una aplicación o un servidor de sucursal con funciones de supervivencia en Lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md).</span><span class="sxs-lookup"><span data-stu-id="d5351-151">For details, see [Home users on a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md).</span></span>

6.  <span data-ttu-id="d5351-152">Mueva a los usuarios del grupo de servidores front-end de Lync Server en el sitio central a la aplicación de sucursal con funciones de supervivencia.</span><span class="sxs-lookup"><span data-stu-id="d5351-152">Move users from the Lync Server Front End pool at the central site to the Survivable Branch Appliance.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

