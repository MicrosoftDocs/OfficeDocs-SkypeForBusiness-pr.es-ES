---
title: 'Lync Server 2013: Apéndice B: Administración de una aplicación de sucursal con funciones de supervivencia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: 'Appendix B: Managing a Survivable Branch Appliance'
ms:assetid: 2ec9d505-6d39-491c-9524-8cf36866b855
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425797(v=OCS.15)
ms:contentKeyID: 48183773
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e267f81327e9d1f49b81ab0d999c37c02da55b31
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34843033"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appendix-b-managing-a-survivable-branch-appliance-in-lync-server-2013"></a><span data-ttu-id="a02f0-102">Apéndice B: Administración de una aplicación de sucursal con funciones de supervivencia en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a02f0-102">Appendix B: Managing a Survivable Branch Appliance in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a02f0-103">_**Última modificación del tema:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="a02f0-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="a02f0-104">En este tema se describen los procedimientos para administrar una aplicación de rama que sea superviviente.</span><span class="sxs-lookup"><span data-stu-id="a02f0-104">This topic describes the procedures for managing a Survivable Branch Appliance.</span></span> <span data-ttu-id="a02f0-105">En concreto, cómo reemplazar y cambiar el nombre de un dispositivo de sucursal con la que se puede cambiar el nombre de la aplicación de Skype Server 2013 front end,</span><span class="sxs-lookup"><span data-stu-id="a02f0-105">Specifically, how to replace and rename a Survivable Branch Appliance, and how to change the Lync Server 2013 Front End pool that the Survivable Branch Appliance is associated with.</span></span>

<div>

## <a name="to-replace-a-survivable-branch-appliance"></a><span data-ttu-id="a02f0-106">Para reemplazar un dispositivo de sucursal con la supervivencia</span><span class="sxs-lookup"><span data-stu-id="a02f0-106">To Replace a Survivable Branch Appliance</span></span>

1.  <span data-ttu-id="a02f0-107">Detenga todos los servicios de Lync Server 2013 en el equipo con la sucursal que sea sobreviviente.</span><span class="sxs-lookup"><span data-stu-id="a02f0-107">Stop all Lync Server 2013 services on the Survivable Branch Appliance.</span></span> <span data-ttu-id="a02f0-108">(Consulte la documentación del proveedor de la aplicación de sucursales supervivientes).</span><span class="sxs-lookup"><span data-stu-id="a02f0-108">(See the Survivable Branch Appliance vendor documentation.)</span></span>

2.  <span data-ttu-id="a02f0-109">Práctica Quite la aplicación de la rama superviviente del dominio.</span><span class="sxs-lookup"><span data-stu-id="a02f0-109">(Recommended) Remove the Survivable Branch Appliance from the domain.</span></span>

3.  <span data-ttu-id="a02f0-110">Elimine el objeto de equipo de la aplicación de sucursal superviviente en servicios de dominio de Active Directory, siguiendo estos pasos:</span><span class="sxs-lookup"><span data-stu-id="a02f0-110">Delete the Survivable Branch Appliance computer object in Active Directory Domain Services, by following these steps:</span></span>
    
      - <span data-ttu-id="a02f0-111">Inicie sesión en un servidor miembro como miembro del grupo administradores de la empresa.</span><span class="sxs-lookup"><span data-stu-id="a02f0-111">Log on to a member server as a member of the Enterprise Admins group.</span></span>
    
      - <span data-ttu-id="a02f0-112">Haga clic en **Inicio**, seleccione **herramientas administrativas**y, a continuación, haga clic en **usuarios y equipos de Active**Directory.</span><span class="sxs-lookup"><span data-stu-id="a02f0-112">Click **Start**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>
    
      - <span data-ttu-id="a02f0-113">Haga clic con el botón derecho en el objeto de equipo de rama superviviente y haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="a02f0-113">Right-click the Survivable Branch Appliance object, and click **Delete**.</span></span>

4.  <span data-ttu-id="a02f0-114">Vuelva a agregar el objeto de equipo de la aplicación de la aplicación superviviente.</span><span class="sxs-lookup"><span data-stu-id="a02f0-114">Add the Survivable Branch Appliance computer object again.</span></span> <span data-ttu-id="a02f0-115">(Consulte [Agregar una aplicación de rama superviviente a Active Directory en Lync Server 2013](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md)).</span><span class="sxs-lookup"><span data-stu-id="a02f0-115">(See [Add a Survivable Branch Appliance to Active Directory in Lync Server 2013](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md).)</span></span>

5.  <span data-ttu-id="a02f0-116">Espere a que se lleve a cabo la replicación de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a02f0-116">Wait for Active Directory replication to take place.</span></span>

6.  <span data-ttu-id="a02f0-117">Abra el shell de administración de Lync Server y escriba **enable-CSTopology**.</span><span class="sxs-lookup"><span data-stu-id="a02f0-117">Open the Lync Server Management Shell, and type **Enable-CSTopology**.</span></span>

7.  <span data-ttu-id="a02f0-118">Conecte el nuevo dispositivo de sucursal superviviente a la red y siga los pasos que se indican en [implementación de un dispositivo o servidor de rama con la supervivencia con Lync server 2013-tareas de sitio central](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) e [implementación de un equipo o servidor de sucursal que sea Reviviente con Lync Server 2013- tarea de sitio de sucursal](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md).</span><span class="sxs-lookup"><span data-stu-id="a02f0-118">Connect the new Survivable Branch Appliance to the network, and follow the steps in [Deploying a Survivable Branch Appliance or Server with Lync Server 2013 - central site tasks](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) and [Deploy a Survivable Branch Appliance or Server with Lync Server 2013 - branch site task](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md).</span></span>

</div>

<div>

## <a name="to-rename-a-survivable-branch-appliance"></a><span data-ttu-id="a02f0-119">Para cambiar el nombre de un equipo de sucursal con la supervivencia</span><span class="sxs-lookup"><span data-stu-id="a02f0-119">To Rename a Survivable Branch Appliance</span></span>

1.  <span data-ttu-id="a02f0-120">Mover usuarios al sitio central.</span><span class="sxs-lookup"><span data-stu-id="a02f0-120">Move users to the central site.</span></span> <span data-ttu-id="a02f0-121">Para obtener más información, vea [mover usuarios a otro grupo en Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).</span><span class="sxs-lookup"><span data-stu-id="a02f0-121">For details, see [Move users to another pool in Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).</span></span>

2.  <span data-ttu-id="a02f0-122">Detenga todos los servicios de Lync Server 2013 en el equipo con la sucursal que sea sobreviviente.</span><span class="sxs-lookup"><span data-stu-id="a02f0-122">Stop all Lync Server 2013 services on the Survivable Branch Appliance.</span></span> <span data-ttu-id="a02f0-123">(Consulte la documentación del proveedor de la aplicación de sucursales supervivientes).</span><span class="sxs-lookup"><span data-stu-id="a02f0-123">(See the Survivable Branch Appliance vendor documentation.)</span></span>

3.  <span data-ttu-id="a02f0-124">Para quitar la rama superviviente de la topología, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="a02f0-124">Remove the Survivable Branch Appliance from the topology, by following these steps:</span></span>
    
      - <span data-ttu-id="a02f0-125">Haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server**y, a continuación, haga clic en **generador de topología de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="a02f0-125">Click **Start**, click **All Programs**, click **Microsoft Lync Server**, and then click **Lync Server Topology Builder**.</span></span>
    
      - <span data-ttu-id="a02f0-126">En el árbol de consola, expanda **sitios de sucursales**, haga clic en el dispositivo de rama superviviente y, a continuación, haga clic en **eliminar** en el panel de acciones.</span><span class="sxs-lookup"><span data-stu-id="a02f0-126">In the console tree, expand **Branch Sites**, click the Survivable Branch Appliance, and then click **Delete** on the Action pane.</span></span>

4.  <span data-ttu-id="a02f0-127">Quite la aplicación de la rama superviviente del dominio.</span><span class="sxs-lookup"><span data-stu-id="a02f0-127">Remove the Survivable Branch Appliance from the domain.</span></span>

5.  <span data-ttu-id="a02f0-128">Elimine el objeto de equipo de la aplicación de la aplicación superviviente en Active Directory, siguiendo estos pasos:</span><span class="sxs-lookup"><span data-stu-id="a02f0-128">Delete the Survivable Branch Appliance computer object in Active Directory, by following these steps:</span></span>
    
      - <span data-ttu-id="a02f0-129">Inicie sesión en un controlador de dominio como miembro del grupo administradores de la empresa.</span><span class="sxs-lookup"><span data-stu-id="a02f0-129">Log on to a domain controller as a member of the Enterprise Admins group.</span></span>
    
      - <span data-ttu-id="a02f0-130">Haga clic en **Inicio**, seleccione **herramientas administrativas**y, a continuación, haga clic en **usuarios y equipos de Active**Directory.</span><span class="sxs-lookup"><span data-stu-id="a02f0-130">Click **Start**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>
    
      - <span data-ttu-id="a02f0-131">Haga clic con el botón derecho en el objeto de equipo de rama superviviente y haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="a02f0-131">Right-click the Survivable Branch Appliance object, and click **Delete**.</span></span>

6.  <span data-ttu-id="a02f0-132">Restaura los valores predeterminados de fábrica de la aplicación de rama que es superviviente.</span><span class="sxs-lookup"><span data-stu-id="a02f0-132">Restore the Survivable Branch Appliance to factory defaults.</span></span> <span data-ttu-id="a02f0-133">(Consulte la documentación del proveedor de la aplicación de sucursales supervivientes).</span><span class="sxs-lookup"><span data-stu-id="a02f0-133">(See the Survivable Branch Appliance vendor documentation.)</span></span>

7.  <span data-ttu-id="a02f0-134">Siga los pasos que se indican en [implementar un dispositivo o servidor de sucursal que sea reviviente con Lync server 2013-tareas de sitio central](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) e [implementar un equipo o servidor de rama con la supervivencia con Lync Server 2013-tarea de sitio de rama](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md).</span><span class="sxs-lookup"><span data-stu-id="a02f0-134">Follow the steps in [Deploying a Survivable Branch Appliance or Server with Lync Server 2013 - central site tasks](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) and [Deploy a Survivable Branch Appliance or Server with Lync Server 2013 - branch site task](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md).</span></span>

8.  <span data-ttu-id="a02f0-135">Mueva a los usuarios al equipo de rama con el nombre cambiado.</span><span class="sxs-lookup"><span data-stu-id="a02f0-135">Move users to the renamed Survivable Branch Appliance.</span></span> <span data-ttu-id="a02f0-136">Para obtener más información, vea [mover usuarios a otro grupo en Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).</span><span class="sxs-lookup"><span data-stu-id="a02f0-136">For details, see [Move users to another pool in Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).</span></span>

</div>

<div>

## <a name="to-change-the-lync-server-front-end-pool-that-the-survivable-branch-appliance-is-associated-with"></a><span data-ttu-id="a02f0-137">Para cambiar el grupo de servidores front-end de Lync Server al que está asociado el equipo con la rama superviviente</span><span class="sxs-lookup"><span data-stu-id="a02f0-137">To Change the Lync Server Front End Pool that the Survivable Branch Appliance Is Associated With</span></span>

1.  <span data-ttu-id="a02f0-138">Mueva los usuarios de la aplicación de rama superviviente al grupo de servidores front end de Lync Server en el sitio central.</span><span class="sxs-lookup"><span data-stu-id="a02f0-138">Move users from the Survivable Branch Appliance to the Lync Server Front End pool at the central site.</span></span> <span data-ttu-id="a02f0-139">Para obtener más información, vea [mover usuarios a otro grupo en Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).</span><span class="sxs-lookup"><span data-stu-id="a02f0-139">For details, see [Move users to another pool in Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).</span></span>

2.  <span data-ttu-id="a02f0-140">Detenga todos los servicios de Lync Server en el equipo con la sucursal que sea sobreviviente.</span><span class="sxs-lookup"><span data-stu-id="a02f0-140">Stop all Lync Server services on the Survivable Branch Appliance.</span></span> <span data-ttu-id="a02f0-141">(Consulte la documentación del proveedor de la aplicación de sucursales supervivientes).</span><span class="sxs-lookup"><span data-stu-id="a02f0-141">(See the Survivable Branch Appliance vendor documentation).</span></span>

3.  <span data-ttu-id="a02f0-142">Actualice el grupo de servidores front-end de Lync Server al que está asociado el equipo con la rama superviviente, siguiendo estos pasos:</span><span class="sxs-lookup"><span data-stu-id="a02f0-142">Update the Lync Server Front End pool that the Survivable Branch Appliance is associated with, by following these steps:</span></span>
    
      - <span data-ttu-id="a02f0-143">Haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server**y, a continuación, haga clic en **generador de topología de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="a02f0-143">Click **Start**, click **All Programs**, click **Microsoft Lync Server**, and then click **Lync Server Topology Builder**.</span></span>
    
      - <span data-ttu-id="a02f0-144">Expanda **sitios de sucursales**.</span><span class="sxs-lookup"><span data-stu-id="a02f0-144">Expand **Branch Sites**.</span></span>
    
      - <span data-ttu-id="a02f0-145">Haga clic con el botón derecho en el objeto de dispositivo de rama superviviente que desee modificar y haga clic en **Editar propiedades** .</span><span class="sxs-lookup"><span data-stu-id="a02f0-145">Right-click the Survivable Branch Appliance object to modify, and click **Edit Properties**</span></span>
    
      - <span data-ttu-id="a02f0-146">En resistencia, seleccione el nuevo grupo de servidores front-end al que se va a asociar el equipo con la rama superviviente y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="a02f0-146">Under Resiliency, select the new Front End pool the Survivable Branch Appliance is to be associated to, and then click **Next**.</span></span>
    
      - <span data-ttu-id="a02f0-147">En el árbol de consola, haga clic con el botón secundario en el nuevo dispositivo de sucursal con el que se hace clic en **topología**y luego en **publicar**.</span><span class="sxs-lookup"><span data-stu-id="a02f0-147">In the console tree, right-click the new Survivable Branch Appliance, click **Topology**, and then click **Publish**.</span></span>

4.  <span data-ttu-id="a02f0-148">Reinicie todos los servicios de Lync Server en el equipo con la sucursal que sea sobreviviente.</span><span class="sxs-lookup"><span data-stu-id="a02f0-148">Restart all Lync Server Services on the Survivable Branch Appliance.</span></span>

5.  <span data-ttu-id="a02f0-149">Prueba la aplicación de la sucursal con supervivencia.</span><span class="sxs-lookup"><span data-stu-id="a02f0-149">Test the Survivable Branch Appliance.</span></span> <span data-ttu-id="a02f0-150">Para obtener más información, consulte [usuarios domésticos en un equipo o servidor de sucursal con la supervivencia en Lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md).</span><span class="sxs-lookup"><span data-stu-id="a02f0-150">For details, see [Home users on a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md).</span></span>

6.  <span data-ttu-id="a02f0-151">Mueva los usuarios del grupo de servidores front-end de Lync Server en el sitio central a la aplicación de rama superviviente.</span><span class="sxs-lookup"><span data-stu-id="a02f0-151">Move users from the Lync Server Front End pool at the central site to the Survivable Branch Appliance.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

