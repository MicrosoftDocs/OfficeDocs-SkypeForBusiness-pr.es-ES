---
title: 'Lync Server 2013: herramientas administrativas de Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server administrative tools
ms:assetid: 9b006f93-4f3d-461d-89b8-e80a34fdb3c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195756(v=OCS.15)
ms:contentKeyID: 48184972
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f6de54e91129351a153c9cf4e08925d62eeb342c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030243"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-administrative-tools"></a><span data-ttu-id="c7fc4-102">Herramientas administrativas de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c7fc4-102">Lync Server 2013 administrative tools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c7fc4-103">_**Última modificación del tema:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="c7fc4-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="c7fc4-104">En este tema se describen las herramientas administrativas para Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c7fc4-104">This topic describes the administrative tools for Lync Server 2013.</span></span>

<span data-ttu-id="c7fc4-105">Las herramientas administrativas se instalan de forma predeterminada en cada servidor de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c7fc4-105">The administrative tools are installed by default on each Lync Server server.</span></span> <span data-ttu-id="c7fc4-106">Además, puede instalar las herramientas administrativas en otros equipos, como consolas administrativas dedicadas.</span><span class="sxs-lookup"><span data-stu-id="c7fc4-106">Additionally, you can install the administrative tools on other computers, such as dedicated administrative consoles.</span></span> <span data-ttu-id="c7fc4-107">Para conocer los procedimientos para instalar las herramientas administrativas, consulte [install Lync Server 2013 Administrative Tools](lync-server-2013-install-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c7fc4-107">For procedures to install the administrative tools, see [Install Lync Server 2013 administrative tools](lync-server-2013-install-lync-server-administrative-tools.md).</span></span> <span data-ttu-id="c7fc4-108">Para ver los procedimientos para abrir las herramientas para realizar tareas de administración, consulte [Open Lync Server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c7fc4-108">For procedures to open the tools to perform management tasks, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

<span data-ttu-id="c7fc4-109">Asegúrese de revisar los requisitos de la infraestructura, el sistema operativo, el software y los derechos de administrador antes de instalar o usar las herramientas administrativas de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c7fc4-109">Ensure that you review infrastructure, operating system, software, and administrator rights requirements before you install or use the Lync Server administrative tools.</span></span> <span data-ttu-id="c7fc4-110">Para obtener más información acerca de los requisitos de infraestructura, consulte [Administrative Tools Infrastructure requirements in Lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c7fc4-110">For details about infrastructure requirements, see [Administrative tools infrastructure requirements in Lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md).</span></span> <span data-ttu-id="c7fc4-111">Para obtener más información sobre los requisitos del sistema operativo y del software para instalar las herramientas administrativas de Lync Server, consulte [compatibilidad con sistemas operativos de servidor y herramientas en Lync server 2013](lync-server-2013-server-and-tools-operating-system-support.md), [requisitos de software adicionales para Lync Server 2013](lync-server-2013-additional-software-requirements.md)y [soporte y requisitos de servidor adicionales en Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c7fc4-111">For details about operating system and software requirements to install the Lync Server administrative tools, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md), [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md), and [Additional server support and requirements in Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md).</span></span> <span data-ttu-id="c7fc4-112">Los derechos de usuario y los permisos necesarios para instalar y usar las herramientas se describen en [derechos de administrador y permisos necesarios para la instalación y administración de Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md).</span><span class="sxs-lookup"><span data-stu-id="c7fc4-112">The user rights and permissions required to install and use the tools are described in [Administrator rights and permissions required for setup and administration of Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md).</span></span>

<span data-ttu-id="c7fc4-113">Las herramientas de administración son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="c7fc4-113">The administrative tools consist of the following:</span></span>

  - <span data-ttu-id="c7fc4-114">**El asistente**   para la implementación de Lync Server usa para implementar Lync Server e instalar todas las herramientas administrativas.</span><span class="sxs-lookup"><span data-stu-id="c7fc4-114">**Lync Server Deployment Wizard**   Use to deploy Lync Server and to install all administrative tools.</span></span>

  - <span data-ttu-id="c7fc4-115">**El generador**   de topologías de Lync Server se usa para definir componentes en la implementación.</span><span class="sxs-lookup"><span data-stu-id="c7fc4-115">**Lync Server Topology Builder**   Use to define components in your deployment.</span></span>

  - <span data-ttu-id="c7fc4-116">\*\*\*\*   Uso del panel de control de Lync Server para la administración continua de la implementación mediante una interfaz basada en Web.</span><span class="sxs-lookup"><span data-stu-id="c7fc4-116">**Lync Server Control Panel**   Use for ongoing management of your deployment by using a web-based interface.</span></span>

  - <span data-ttu-id="c7fc4-117">**El shell**   de administración de Lync Server se usa para la administración continua de la implementación mediante la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="c7fc4-117">**Lync Server Management Shell**   Use for ongoing management of your deployment by using the command line.</span></span>

  - <span data-ttu-id="c7fc4-118">**Herramienta de registro de Lync Server**   Úsela para solucionar problemas de la implementación.</span><span class="sxs-lookup"><span data-stu-id="c7fc4-118">**Lync Server Logging tool**   Use to troubleshoot problems in your deployment.</span></span>

  - <span data-ttu-id="c7fc4-119">**El servicio**   de registro centralizado recopila los registros y los archivos de seguimiento de un equipo, grupo de servidores, sitio o global.</span><span class="sxs-lookup"><span data-stu-id="c7fc4-119">**Centralized Logging Service**   Collect logs and trace files from one computer, pool, site or global.</span></span> <span data-ttu-id="c7fc4-120">Seleccione y defina escenarios que contengan proveedores, marcas y niveles de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="c7fc4-120">Select and define scenarios that contain providers, flags and trace levels.</span></span> <span data-ttu-id="c7fc4-121">El registro se recopila, agrega y muestra herramientas como, por ejemplo, cualquier herramienta basada en texto o Snooper. exe.</span><span class="sxs-lookup"><span data-stu-id="c7fc4-121">Logging is collected, aggregated and displayed with tools such as any text-based tool or Snooper.exe.</span></span>

<span data-ttu-id="c7fc4-122">Para administrar la implementación, puede usar principalmente el generador de topologías y el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c7fc4-122">You can manage your deployment by primarily using Topology Builder and Lync Server Control Panel.</span></span>

<div>

## <a name="deployment-wizard"></a><span data-ttu-id="c7fc4-123">Asistente para implementación</span><span class="sxs-lookup"><span data-stu-id="c7fc4-123">Deployment Wizard</span></span>

<span data-ttu-id="c7fc4-124">Debe usar el Asistente para la implementación de Lync Server que se incluye en los medios de instalación para instalar todas las herramientas administrativas en un equipo en el que todavía no ha instalado Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c7fc4-124">You must use the Lync Server Deployment Wizard included on the installation media to install all administrative tools onto a computer on which you have not already installed Lync Server.</span></span> <span data-ttu-id="c7fc4-125">Durante el proceso de instalación de herramientas administrativas, el Asistente para la implementación de Lync Server se instala localmente junto con el resto de las herramientas, de modo que puede usarla más adelante para instalar archivos para componentes adicionales o para quitar archivos de componentes que no desea en el automático.</span><span class="sxs-lookup"><span data-stu-id="c7fc4-125">During the administrative tools installation process, the Lync Server Deployment Wizard is installed locally along with the other tools so that you can later use it to install files for additional components or remove files for components that you do not want on the computer.</span></span>

<span data-ttu-id="c7fc4-126">Para obtener más información sobre cómo ejecutar el Asistente para la implementación de Lync Server por primera vez desde los medios de instalación de Lync Server, vea [install Lync server 2013 Administrative Tools](lync-server-2013-install-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c7fc4-126">For details about how to run the Lync Server Deployment Wizard for the first time from the Lync Server installation media, see [Install Lync Server 2013 administrative tools](lync-server-2013-install-lync-server-administrative-tools.md).</span></span>

</div>

<div>

## <a name="topology-builder"></a><span data-ttu-id="c7fc4-127">Topology Builder</span><span class="sxs-lookup"><span data-stu-id="c7fc4-127">Topology Builder</span></span>

<span data-ttu-id="c7fc4-128">Para obtener más información sobre las tareas de implementación que puede realizar con el generador de topologías, consulte la documentación de implementación de cada rol de servidor.</span><span class="sxs-lookup"><span data-stu-id="c7fc4-128">For details about deployment tasks that you can you perform by using Topology Builder, see the Deployment documentation for each server role.</span></span>

</div>

<div>

## <a name="lync-server-control-panel"></a><span data-ttu-id="c7fc4-129">Panel de Control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="c7fc4-129">Lync Server Control Panel</span></span>

<span data-ttu-id="c7fc4-130">Puede usar el panel de control de Lync Server 2013 para realizar la mayoría de las tareas administrativas necesarias para administrar y mantener Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c7fc4-130">You can use Lync Server 2013 Control Panel to perform most of the administrative tasks required to manage and maintain Lync Server 2013.</span></span> <span data-ttu-id="c7fc4-131">El panel de control de Lync Server le proporciona una interfaz gráfica de usuario (GUI) para administrar la configuración de los servidores que ejecutan Lync Server, además de los usuarios, clientes y dispositivos de su organización.</span><span class="sxs-lookup"><span data-stu-id="c7fc4-131">Lync Server Control Panel provides you with a graphical user interface (GUI) to manage the configuration of the servers running Lync Server, in addition to the users, clients, and devices in your organization.</span></span> <span data-ttu-id="c7fc4-132">El shell de administración de Lync Server usa el panel de control de Lync Server como mecanismo subyacente para realizar la configuración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c7fc4-132">Lync Server Management Shell uses Lync Server Control Panel as the underlying mechanism to perform Lync Server configuration.</span></span>

<span data-ttu-id="c7fc4-133">El panel de control de Lync Server se instala automáticamente en cada servidor front-end de Lync Server o servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="c7fc4-133">Lync Server Control Panel is automatically installed on every Lync Server Front End Server or Standard Edition server.</span></span> <span data-ttu-id="c7fc4-134">En esta versión, se administran de forma remota los servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="c7fc4-134">In this release, you administer Edge Servers remotely.</span></span> <span data-ttu-id="c7fc4-135">También puede instalar el panel de control de Lync Server en otro equipo, como una consola de administración desde la que desea administrar Lync Server de forma centralizada.</span><span class="sxs-lookup"><span data-stu-id="c7fc4-135">You can also install Lync Server Control Panel on another computer, such as a management console from which you want to centrally manage Lync Server.</span></span> <span data-ttu-id="c7fc4-136">Para obtener más información, consulte [install Lync Server 2013 Administrative Tools](lync-server-2013-install-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c7fc4-136">For details, see [Install Lync Server 2013 administrative tools](lync-server-2013-install-lync-server-administrative-tools.md).</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="c7fc4-137">Para establecer la configuración mediante el panel de control de Lync Server, debe haber iniciado sesión con una cuenta asignada al rol CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="c7fc4-137">To configure settings using Lync Server Control Panel, you must be logged in using an account that is assigned to the CsAdministrator role.</span></span> <span data-ttu-id="c7fc4-138">Para obtener más información sobre los roles administrativos predefinidos disponibles en Lync Server 2013, vea <A href="lync-server-2013-planning-for-role-based-access-control.md">planeación del control de acceso basado en roles en Lync server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="c7fc4-138">For details about the predefined administrative roles available in Lync Server 2013, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="c7fc4-139">Para establecer la configuración mediante el panel de control de Lync Server, también debe usar un equipo con una resolución de pantalla mínima de 1024 x 768.</span><span class="sxs-lookup"><span data-stu-id="c7fc4-139">To configure settings using Lync Server Control Panel, you must also use a computer with a minimum screen resolution of 1024 x 768.</span></span></P></LI></UL>



</div>

</div>

<div>

## <a name="lync-server-management-shell"></a><span data-ttu-id="c7fc4-140">Shell de administración de Communications Server</span><span class="sxs-lookup"><span data-stu-id="c7fc4-140">Lync Server Management Shell</span></span>

<span data-ttu-id="c7fc4-141">En Lync Server, el shell de administración de Lync Server proporciona un nuevo método para la administración y la administración.</span><span class="sxs-lookup"><span data-stu-id="c7fc4-141">In Lync Server, the Lync Server Management Shell provides a new method for administration and management.</span></span> <span data-ttu-id="c7fc4-142">El shell de administración de Lync Server es una interfaz de administración eficaz, integrada en la interfaz de línea de comandos de Windows PowerShell, que incluye un conjunto completo de cmdlets específicos de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c7fc4-142">Lync Server Management Shell is a powerful management interface, built on the Windows PowerShell command-line interface, that includes a comprehensive set of cmdlets that are specific to Lync Server.</span></span> <span data-ttu-id="c7fc4-143">Con el shell de administración de Lync Server, obtiene un amplio conjunto de controles de configuración y automatización.</span><span class="sxs-lookup"><span data-stu-id="c7fc4-143">With Lync Server Management Shell, you gain a rich set of configuration and automation controls.</span></span> <span data-ttu-id="c7fc4-144">El generador de topologías y el panel de control de Lync Server implementan subconjuntos de estos cmdlets para admitir la administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c7fc4-144">Topology Builder and Lync Server Control Panel both implement subsets of these cmdlets to support management of Lync Server.</span></span> <span data-ttu-id="c7fc4-145">El shell de administración de Lync Server incluye cmdlets para todas las tareas de administración de Lync Server y puede usar los cmdlets individualmente para administrar la implementación.</span><span class="sxs-lookup"><span data-stu-id="c7fc4-145">The Lync Server Management Shell includes cmdlets for all Lync Server administration tasks, and you can use the cmdlets individually to manage your deployment.</span></span> <span data-ttu-id="c7fc4-146">Para obtener más información, consulte la documentación del [Shell de administración de Lync Server 2013](lync-server-2013-lync-server-management-shell.md) o la ayuda de la línea de comandos para cada cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c7fc4-146">For details, see [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) documentation or the command-line help for each cmdlet.</span></span>

</div>

<div>

## <a name="logging-tool"></a><span data-ttu-id="c7fc4-147">Herramienta de registro</span><span class="sxs-lookup"><span data-stu-id="c7fc4-147">Logging Tool</span></span>

<span data-ttu-id="c7fc4-148">La herramienta de registro de Lync Server facilita la solución de problemas al capturar el registro y la información de seguimiento del producto mientras se ejecuta el producto.</span><span class="sxs-lookup"><span data-stu-id="c7fc4-148">The Lync Server Logging Tool facilitates troubleshooting by capturing logging and tracing information from the product while the product is running.</span></span> <span data-ttu-id="c7fc4-149">Puede usar la herramienta para ejecutar sesiones de depuración en cualquier rol de servidor de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c7fc4-149">You can use the tool to run debug sessions on any Lync Server server role.</span></span> <span data-ttu-id="c7fc4-150">Para obtener más información sobre la herramienta de registro, vea la documentación de la herramienta de registro de Lync [http://go.microsoft.com/fwlink/p/?linkId=199265](http://go.microsoft.com/fwlink/p/?linkid=199265)Server 2010 en la biblioteca de TechNet en.</span><span class="sxs-lookup"><span data-stu-id="c7fc4-150">For details about the Logging Tool, see the Lync Server 2010 Logging Tool documentation on the TechNet Library at [http://go.microsoft.com/fwlink/p/?linkId=199265](http://go.microsoft.com/fwlink/p/?linkid=199265).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c7fc4-151">El servicio de registro centralizado se recomienda para todas las colecciones de registro a través de la herramienta de registro de Lync Server en todas las circunstancias.</span><span class="sxs-lookup"><span data-stu-id="c7fc4-151">The Centralized Logging Service is recommended for all logging collection over the Lync Server Logging Tool in all circumstances.</span></span> <span data-ttu-id="c7fc4-152">La herramienta de registro de Lync Server seguirá funcionando, pero interferirá o se representará en su mayoría imefectivas si el servicio de registro centralizado ya se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="c7fc4-152">The Lync Server Logging Tool will still work, but it will interfere or be rendered mostly ineffective if the Centralized Logging Service is already running.</span></span> <span data-ttu-id="c7fc4-153">Solo debe usar el servicio de registro centralizado o la herramienta de registro de Lync Server, pero nunca ambos al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="c7fc4-153">You should use only the Centralized Logging Service or the Lync Server Logging Tool, but never both concurrently.</span></span> <span data-ttu-id="c7fc4-154">Para obtener más información sobre el servicio de registro centralizado y por qué debe usarlo de forma exclusiva, consulte <A href="lync-server-2013-using-the-centralized-logging-service.md">uso del servicio de registro centralizado en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="c7fc4-154">For more information on the Centralized Logging Service and why you should use it exclusively, see <A href="lync-server-2013-using-the-centralized-logging-service.md">Using the Centralized Logging Service in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c7fc4-155">En esta sección</span><span class="sxs-lookup"><span data-stu-id="c7fc4-155">In This Section</span></span>

  - [<span data-ttu-id="c7fc4-156">Requisitos de infraestructura de herramientas administrativas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c7fc4-156">Administrative tools infrastructure requirements in Lync Server 2013</span></span>](lync-server-2013-administrative-tools-infrastructure-requirements.md)

  - [<span data-ttu-id="c7fc4-157">Compatibilidad del sistema operativo con el servidor y las herramientas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c7fc4-157">Server and tools operating system support in Lync Server 2013</span></span>](lync-server-2013-server-and-tools-operating-system-support.md)

  - [<span data-ttu-id="c7fc4-158">Requisitos de software de herramientas administrativas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c7fc4-158">Administrative tools software requirements in Lync Server 2013</span></span>](lync-server-2013-administrative-tools-software-requirements.md)

  - [<span data-ttu-id="c7fc4-159">Permisos y derechos de administrador necesarios para la instalación y administración de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c7fc4-159">Administrator rights and permissions required for setup and administration of Lync Server 2013</span></span>](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)

  - [<span data-ttu-id="c7fc4-160">Requisitos para publicar una topología en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c7fc4-160">Requirements to publish a topology in Lync Server 2013</span></span>](lync-server-2013-requirements-to-publish-a-topology.md)

  - [<span data-ttu-id="c7fc4-161">Instalación de las herramientas administrativas de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c7fc4-161">Install Lync Server 2013 administrative tools</span></span>](lync-server-2013-install-lync-server-administrative-tools.md)

  - [<span data-ttu-id="c7fc4-162">Abrir las herramientas administrativas de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c7fc4-162">Open Lync Server 2013 administrative tools</span></span>](lync-server-2013-open-lync-server-administrative-tools.md)

  - [<span data-ttu-id="c7fc4-163">Solución de problemas del Panel de control de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c7fc4-163">Troubleshooting Lync Server 2013 Control Panel</span></span>](lync-server-2013-troubleshooting-lync-server-2013-control-panel.md)

  - [<span data-ttu-id="c7fc4-164">Uso del servicio de registro centralizado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c7fc4-164">Using the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-using-the-centralized-logging-service.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c7fc4-165">Vea también</span><span class="sxs-lookup"><span data-stu-id="c7fc4-165">See Also</span></span>


[<span data-ttu-id="c7fc4-166">Shell de administración de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c7fc4-166">Lync Server 2013 Management Shell</span></span>](lync-server-2013-lync-server-management-shell.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

