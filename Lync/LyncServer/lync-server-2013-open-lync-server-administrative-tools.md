---
title: 'Lync Server 2013: abrir las herramientas administrativas de Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Open Lync Server administrative tools
ms:assetid: 8c58de94-9e0a-4368-9e14-9afcaa1142d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195741(v=OCS.15)
ms:contentKeyID: 48184778
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 172d448b3967782226335a5a3b9a4066514b7a9b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216649"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="open-lync-server-2013-administrative-tools"></a><span data-ttu-id="72012-102">Abrir las herramientas administrativas de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="72012-102">Open Lync Server 2013 administrative tools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="72012-103">_**Última modificación del tema:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="72012-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="72012-104">Puede usar los procedimientos de este tema para abrir las herramientas administrativas para implementar, configurar o solucionar los problemas de la topología de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="72012-104">You can use the procedures in this topic to open administrative tools to deploy, configure, or troubleshoot your Lync Server 2013 topology.</span></span>

  - <span data-ttu-id="72012-105">Asistente para implementación</span><span class="sxs-lookup"><span data-stu-id="72012-105">Deployment Wizard</span></span>

  - <span data-ttu-id="72012-106">Topology Builder</span><span class="sxs-lookup"><span data-stu-id="72012-106">Topology Builder</span></span>

  - <span data-ttu-id="72012-107">Panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="72012-107">Lync Server Control Panel</span></span>

  - <span data-ttu-id="72012-108">Shell de administración de Lync Server</span><span class="sxs-lookup"><span data-stu-id="72012-108">Lync Server Management Shell</span></span>

<span id="BKMK_OpenDeploymentWizard"></span>

<div>

## <a name="deployment-wizard"></a><span data-ttu-id="72012-109">Asistente para implementación</span><span class="sxs-lookup"><span data-stu-id="72012-109">Deployment Wizard</span></span>

<span data-ttu-id="72012-110">Use el siguiente procedimiento para iniciar el Asistente para la implementación localmente para agregar o quitar archivos de componentes de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="72012-110">Use the following procedure to start the Deployment Wizard locally to add or remove Lync Server 2013 component files.</span></span>

<div>

## <a name="to-start-lync-server-2013-deployment-wizard"></a><span data-ttu-id="72012-111">Para iniciar el Asistente para la implementación de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="72012-111">To start Lync Server 2013 Deployment Wizard</span></span>

1.  <span data-ttu-id="72012-112">Inicie sesión en el equipo en el que el asistente para la implementación de Lync Server esté instalado como miembro del grupo Admins. del dominio y el grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="72012-112">Log on to the computer where the Lync Server Deployment Wizard is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="72012-113">Haga clic en **Inicio**, en **todos los programas**, en **Microsoft Lync Server 2013**y, a continuación, en **Asistente para la implementación de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="72012-113">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Deployment Wizard**.</span></span>

</div>

</div>

<span id="BKMK_OpenTopologyBuilder"></span>

<div>

## <a name="topology-builder"></a><span data-ttu-id="72012-114">Topology Builder</span><span class="sxs-lookup"><span data-stu-id="72012-114">Topology Builder</span></span>

<span data-ttu-id="72012-115">Use el siguiente procedimiento para abrir el generador de topologías y definir los servidores que desea implementar en su topología de 2013 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="72012-115">Use the following procedure to open the Topology Builder to define the servers that you want to deploy in your Lync Server 2013 topology.</span></span>

<div>

## <a name="to-open-lync-server-2013-topology-builder-to-design-the-topology"></a><span data-ttu-id="72012-116">Para abrir el generador de topologías de Lync Server 2013 para diseñar la topología</span><span class="sxs-lookup"><span data-stu-id="72012-116">To open Lync Server 2013 Topology Builder to design the topology</span></span>

1.  <span data-ttu-id="72012-117">Inicie sesión en el equipo en el que Topology Builder esté instalado como miembro del grupo Admins. del dominio y el grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="72012-117">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="72012-118">Puede definir una topología con una cuenta que sea miembro del grupo de usuarios locales, pero para leer, publicar o habilitar una topología, lo cual es necesario para instalar Lync Server 2013 en un servidor, debe usar una cuenta que sea miembro del grupo administradores de dominio y de la RTCUniv Grupo ersalServerAdmins y que tiene permisos de control total (es decir, lectura, escritura y modificación) en el recurso compartido de archivos que se va a usar para el almacén de archivos de archivado, de modo que el generador de topologías pueda configurar la lista de control de acceso discrecional (DACL) requerida. o una cuenta con derechos de usuario equivalentes.</span><span class="sxs-lookup"><span data-stu-id="72012-118">You can define a topology by using an account that is a member of the local Users group, but to read, publish, or enable a topology, which is required to install Lync Server 2013 on a server, you must use an account that is a member of the Domain Admins group and the RTCUniversalServerAdmins group, and that has full control permissions (that is, read, write, and modify) on the file share that you are going to use for the archiving file store so that Topology Builder can configure the required discretionary access control list (DACLs), or an account with equivalent user rights.</span></span>

    
    </div>

2.  <span data-ttu-id="72012-119">Inicie el generador de topologías: haga clic en **Inicio**, haga clic en **todos los programas**, haga clic en **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topologías de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="72012-119">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

</div>

</div>

<span id="BKMK_OpenControlPanel"></span>

<div>

## <a name="lync-server-2013-control-panel"></a><span data-ttu-id="72012-120">Panel de control de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="72012-120">Lync Server 2013 Control Panel</span></span>

<span data-ttu-id="72012-121">Use uno de los siguientes procedimientos para abrir el panel de control de Lync Server 2013 para administrar la configuración de servidores, usuarios, clientes y dispositivos en su entorno.</span><span class="sxs-lookup"><span data-stu-id="72012-121">Use one of the following procedures to open Lync Server 2013 Control Panel to manage the configuration of servers, users, clients, and devices in your environment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="72012-122">Puede usar una cuenta de usuario asignada al rol CsAdministrator para realizar cualquier tarea en el panel de control de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="72012-122">You can use a user account that is assigned to the CsAdministrator role to perform any task in Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="72012-123">Puede usar otros roles para iniciar sesión en el panel de control de Lync Server 2013 para realizar tareas de administración específicas, en función de la tarea que necesite realizar.</span><span class="sxs-lookup"><span data-stu-id="72012-123">You can use other roles to log on to Lync Server 2013 Control Panel to perform specific administration tasks, dependent on the task you need to perform.</span></span> <span data-ttu-id="72012-124">Por ejemplo, puede usar rol csarchivingadministrator para administrar el archivado en el panel de control de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="72012-124">For example, you can use CSArchivingAdministrator to administer Archiving in Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="72012-125">Para obtener más información sobre los roles, consulte <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="72012-125">For details about roles, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="72012-126">Para obtener información sobre las funciones que puede usar para realizar una tarea específica, consulte la documentación de la tarea.</span><span class="sxs-lookup"><span data-stu-id="72012-126">For details about the roles that you can use to perform a specific task, see the documentation for the task.</span></span>



</div>

<div>

## <a name="to-open-lync-server-2013-control-panel-from-any-computer-inside-your-organizations-firewall"></a><span data-ttu-id="72012-127">Para abrir el panel de control de Lync Server 2013 desde cualquier equipo dentro del firewall de la organización</span><span class="sxs-lookup"><span data-stu-id="72012-127">To open Lync Server 2013 Control Panel from any computer inside your organization’s firewall</span></span>

1.  <span data-ttu-id="72012-128">Desde una cuenta de usuario asignada al rol CsAdministrator o a otro rol que tenga los derechos y permisos de usuario adecuados para la tarea que se va a realizar, inicie sesión en cualquier equipo en la implementación interna con una resolución de pantalla mínima de 1024 x 768.</span><span class="sxs-lookup"><span data-stu-id="72012-128">From a user account that is assigned to the CsAdministrator role or other role that has appropriate user rights and permissions for the task to be performed, log on to any computer in your internal deployment with a minimum screen resolution of 1024 x 768.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="72012-129">Si ha configurado una dirección URL sencilla de administración, puede tener acceso al panel de control de Lync Server 2013 desde un explorador de Internet que se ejecute en cualquier equipo del firewall de la organización.</span><span class="sxs-lookup"><span data-stu-id="72012-129">If you have configured an administration simple uniform resource locator (URL), you can access Lync Server 2013 Control Panel from an Internet browser that is running on any computer within your organization’s firewall.</span></span> <span data-ttu-id="72012-130">Para obtener más información sobre cómo configurar la dirección URL sencilla de administración, consulte <A href="lync-server-2013-planning-for-simple-urls.md">Planning for simple URLs in Lync server 2013</A> en la documentación de planeación y <A href="lync-server-2013-edit-or-configure-simple-urls.md">Editar o configurar direcciones URL sencillas en Lync Server 2013</A> en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="72012-130">For details about configuring the administration simple URL, see <A href="lync-server-2013-planning-for-simple-urls.md">Planning for simple URLs in Lync Server 2013</A> in the Planning documentation and <A href="lync-server-2013-edit-or-configure-simple-urls.md">Edit or configure simple URLs in Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

2.  <span data-ttu-id="72012-131">Abra una ventana del explorador y escriba la dirección URL de administración configurada para la organización.</span><span class="sxs-lookup"><span data-stu-id="72012-131">Open a browser window, and then enter the Admin URL configured for your organization.</span></span>

</div>

<div>

## <a name="to-open-lync-server-2013-control-panel-on-a-computer-running-lync-server-2013"></a><span data-ttu-id="72012-132">Para abrir el panel de control de Lync Server 2013 en un equipo que ejecuta Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="72012-132">To open Lync Server 2013 Control Panel on a computer running Lync Server 2013</span></span>

1.  <span data-ttu-id="72012-133">Desde una cuenta de usuario que sea miembro de la función CsAdministrator o de otro rol que tenga los derechos y permisos de usuario adecuados para la tarea que se va a realizar, inicie sesión en un equipo en el que tenga instalado Lync Server 2013 o, como mínimo, en el servidor Lync Server 2013 Ive Tools.</span><span class="sxs-lookup"><span data-stu-id="72012-133">From a user account that is a member of the CsAdministrator role or other role that has appropriate user rights and permissions for the task to be performed, log on to a computer on which you have installed Lync Server 2013 or, at a minimum, the Lync Server 2013 administrative tools.</span></span> <span data-ttu-id="72012-134">Para configurar las opciones, el equipo debe tener una resolución de pantalla mínima de 1024 x 768.</span><span class="sxs-lookup"><span data-stu-id="72012-134">To configure settings, the computer must have a minimum screen resolution of 1024 x 768.</span></span>

2.  <span data-ttu-id="72012-135">Inicie el panel de control 2013 de Lync Server: haga clic en **Inicio**, **todos los programas**, **herramientas administrativas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Panel de control de Lync Server 2013**.</span><span class="sxs-lookup"><span data-stu-id="72012-135">Start Lync Server 2013 Control Panel: Click **Start**, click **All Programs**, point to **Administrative Tools**, point to **Microsoft Lync Server 2013**, and then click **Lync Server 2013 Control Panel**.</span></span>

</div>

</div>

<span id="BKMK_OpenManagementShell"></span>

<div>

## <a name="lync-server-2013-management-shell"></a><span data-ttu-id="72012-136">Shell de administración de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="72012-136">Lync Server 2013 Management Shell</span></span>

<span data-ttu-id="72012-137">Use el siguiente procedimiento para abrir Shell de administración de Lync Server 2013 para administrar servidores, usuarios, clientes y dispositivos en su entorno mediante la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="72012-137">Use the following procedure to open Lync Server 2013 Management Shell to administer servers, users, clients, and devices in your environment by using the command line.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="72012-138">Puede usar una cuenta de usuario asignada al rol CsAdministrator para realizar cualquier tarea en el shell de administración de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="72012-138">You can use a user account that is assigned to the CsAdministrator role to perform any task in Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="72012-139">Puede iniciar sesión con otras funciones para realizar tareas específicas de administración, en función de la tarea que necesite realizar.</span><span class="sxs-lookup"><span data-stu-id="72012-139">You can log on using other roles to perform specific administration tasks, depending on the task you need to perform.</span></span> <span data-ttu-id="72012-140">Por ejemplo, puede usar CSArchivingAdministrator para ejecutar cmdlets relacionados con las administración de archivado.</span><span class="sxs-lookup"><span data-stu-id="72012-140">For example, you can use CSArchivingAdministrator to run cmdlets related to Archiving administration.</span></span> <span data-ttu-id="72012-141">Para obtener más información sobre los roles, consulte <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="72012-141">For details about roles, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="72012-142">Para obtener información sobre las funciones que puede usar para ejecutar un cmdlet específico, consulte la documentación del cmdlet.</span><span class="sxs-lookup"><span data-stu-id="72012-142">For details about the roles that you can use to run a specific cmdlet, see the documentation for the cmdlet.</span></span><BR><span data-ttu-id="72012-143">También puede ejecutar ciertos cmdlets mediante una cuenta de usuario en los grupos RTCUniversalServerAdmins, RTCUniversalUserAdmins, o RTCUniversalReadOnlyAdmins, según el cmdlet.</span><span class="sxs-lookup"><span data-stu-id="72012-143">You can also run certain cmdlets by using a user account in the RTCUniversalServerAdmins, RTCUniversalUserAdmins, or RTCUniversalReadOnlyAdmins groups, depending on the cmdlet.</span></span>



</div>

<div>

## <a name="to-open-the-lync-server-2013-management-shell"></a><span data-ttu-id="72012-144">Para abrir el shell de administración de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="72012-144">To open the Lync Server 2013 Management Shell</span></span>

  - <span data-ttu-id="72012-145">Si abre una ventana de Windows PowerShell en lugar del shell de administración de Lync Server 2013, de forma predeterminada, no podrá ejecutar los cmdlets de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="72012-145">If you open a Windows PowerShell window rather than the Lync Server 2013 Management Shell, by default you cannot run the Lync Server 2013 cmdlets.</span></span> <span data-ttu-id="72012-146">Para ejecutar los cmdlets de Lync Server 2013 desde dentro de Windows PowerShell, escriba lo siguiente en el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="72012-146">To run the Lync Server 2013 cmdlets from within Windows PowerShell, type the following at the Windows PowerShell command prompt:</span></span>
    
    `Import-Module Lync`

  - <span data-ttu-id="72012-147">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="72012-147">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="72012-148">Consulta también</span><span class="sxs-lookup"><span data-stu-id="72012-148">See Also</span></span>


[<span data-ttu-id="72012-149">Instalación de las herramientas administrativas de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="72012-149">Install Lync Server 2013 administrative tools</span></span>](lync-server-2013-install-lync-server-administrative-tools.md)  


[<span data-ttu-id="72012-150">Herramientas administrativas de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="72012-150">Lync Server 2013 administrative tools</span></span>](lync-server-2013-lync-server-administrative-tools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

