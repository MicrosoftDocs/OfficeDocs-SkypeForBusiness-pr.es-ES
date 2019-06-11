---
title: 'Lync Server 2013: Herramientas administrativas de Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync Server administrative tools
ms:assetid: 9b006f93-4f3d-461d-89b8-e80a34fdb3c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195756(v=OCS.15)
ms:contentKeyID: 48184972
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6756aee8d7c65b179fb5c1c15ca008b3bd205778
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834929"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-administrative-tools"></a><span data-ttu-id="35027-102">Herramientas administrativas de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35027-102">Lync Server 2013 administrative tools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="35027-103">_**Última modificación del tema:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="35027-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="35027-104">En este tema se describen las herramientas administrativas para Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="35027-104">This topic describes the administrative tools for Lync Server 2013.</span></span>

<span data-ttu-id="35027-105">Las herramientas administrativas se instalan de forma predeterminada en cada servidor de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="35027-105">The administrative tools are installed by default on each Lync Server server.</span></span> <span data-ttu-id="35027-106">Además, puede instalar las herramientas administrativas en otros equipos, como consolas administrativas dedicadas.</span><span class="sxs-lookup"><span data-stu-id="35027-106">Additionally, you can install the administrative tools on other computers, such as dedicated administrative consoles.</span></span> <span data-ttu-id="35027-107">Para obtener información sobre los procedimientos para instalar las herramientas administrativas, consulte [instalar herramientas administrativas 2013 de Lync Server](lync-server-2013-install-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="35027-107">For procedures to install the administrative tools, see [Install Lync Server 2013 administrative tools](lync-server-2013-install-lync-server-administrative-tools.md).</span></span> <span data-ttu-id="35027-108">Para obtener información sobre los procedimientos para abrir las herramientas para realizar tareas de administración, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="35027-108">For procedures to open the tools to perform management tasks, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

<span data-ttu-id="35027-109">Asegúrese de revisar los requisitos de los derechos de infraestructura, sistema operativo, software y administrador antes de instalar o usar las herramientas administrativas de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="35027-109">Ensure that you review infrastructure, operating system, software, and administrator rights requirements before you install or use the Lync Server administrative tools.</span></span> <span data-ttu-id="35027-110">Para obtener más información sobre los requisitos de infraestructura, consulte [requisitos de infraestructura de herramientas administrativas en Lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="35027-110">For details about infrastructure requirements, see [Administrative tools infrastructure requirements in Lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md).</span></span> <span data-ttu-id="35027-111">Para obtener más información sobre los requisitos del sistema operativo y del software para instalar las herramientas administrativas de Lync Server, consulte [compatibilidad del sistema operativo servidor y herramientas en Lync server 2013](lync-server-2013-server-and-tools-operating-system-support.md), [requisitos de software adicionales para Lync Server 2013](lync-server-2013-additional-software-requirements.md)y [ Requisitos y compatibilidad de servidor adicionales en Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="35027-111">For details about operating system and software requirements to install the Lync Server administrative tools, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md), [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md), and [Additional server support and requirements in Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md).</span></span> <span data-ttu-id="35027-112">Los derechos de usuario y los permisos necesarios para instalar y usar las herramientas se describen en [derechos de administrador y permisos necesarios para la configuración y administración de Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md).</span><span class="sxs-lookup"><span data-stu-id="35027-112">The user rights and permissions required to install and use the tools are described in [Administrator rights and permissions required for setup and administration of Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md).</span></span>

<span data-ttu-id="35027-113">Las herramientas administrativas son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="35027-113">The administrative tools consist of the following:</span></span>

  - <span data-ttu-id="35027-114">**Asistente para la implementación de Lync Server**   se usa para implementar Lync Server e instalar todas las herramientas administrativas.</span><span class="sxs-lookup"><span data-stu-id="35027-114">**Lync Server Deployment Wizard**   Use to deploy Lync Server and to install all administrative tools.</span></span>

  - <span data-ttu-id="35027-115">**El generador**   de topología de Lync Server se usa para definir componentes en la implementación.</span><span class="sxs-lookup"><span data-stu-id="35027-115">**Lync Server Topology Builder**   Use to define components in your deployment.</span></span>

  - <span data-ttu-id="35027-116">\*\*\*\*   Uso del panel de control de Lync Server para la administración continua de la implementación mediante una interfaz basada en Web.</span><span class="sxs-lookup"><span data-stu-id="35027-116">**Lync Server Control Panel**   Use for ongoing management of your deployment by using a web-based interface.</span></span>

  - <span data-ttu-id="35027-117">**Shell de administración de Lync Server**   para la administración continua de la implementación mediante la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="35027-117">**Lync Server Management Shell**   Use for ongoing management of your deployment by using the command line.</span></span>

  - <span data-ttu-id="35027-118">**Herramienta de registro de Lync Server**   use esta solución para solucionar problemas en la implementación.</span><span class="sxs-lookup"><span data-stu-id="35027-118">**Lync Server Logging tool**   Use to troubleshoot problems in your deployment.</span></span>

  - <span data-ttu-id="35027-119">**El servicio**   de registro centralizado recopila registros y rastrea archivos de un equipo, grupo, sitio o global.</span><span class="sxs-lookup"><span data-stu-id="35027-119">**Centralized Logging Service**   Collect logs and trace files from one computer, pool, site or global.</span></span> <span data-ttu-id="35027-120">Seleccione y defina escenarios que contengan proveedores, marcas y niveles de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="35027-120">Select and define scenarios that contain providers, flags and trace levels.</span></span> <span data-ttu-id="35027-121">El registro se recopila, se agrega y se muestra con herramientas como, por ejemplo, cualquier herramienta de texto o Snoop. exe.</span><span class="sxs-lookup"><span data-stu-id="35027-121">Logging is collected, aggregated and displayed with tools such as any text-based tool or Snooper.exe.</span></span>

<span data-ttu-id="35027-122">Para administrar la implementación, puede usar principalmente el generador de topología y el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="35027-122">You can manage your deployment by primarily using Topology Builder and Lync Server Control Panel.</span></span>

<div>

## <a name="deployment-wizard"></a><span data-ttu-id="35027-123">Asistente para la implementación</span><span class="sxs-lookup"><span data-stu-id="35027-123">Deployment Wizard</span></span>

<span data-ttu-id="35027-124">Debe usar el Asistente para la implementación de Lync Server incluido en el medio de instalación para instalar todas las herramientas administrativas en un equipo en el que no haya instalado ya Lync Server.</span><span class="sxs-lookup"><span data-stu-id="35027-124">You must use the Lync Server Deployment Wizard included on the installation media to install all administrative tools onto a computer on which you have not already installed Lync Server.</span></span> <span data-ttu-id="35027-125">Durante el proceso de instalación de herramientas administrativas, el Asistente para la implementación de Lync Server se instala localmente junto con el resto de las herramientas para que pueda usarla más adelante para instalar archivos de componentes adicionales o para quitar archivos de componentes que no desee en el sistema.</span><span class="sxs-lookup"><span data-stu-id="35027-125">During the administrative tools installation process, the Lync Server Deployment Wizard is installed locally along with the other tools so that you can later use it to install files for additional components or remove files for components that you do not want on the computer.</span></span>

<span data-ttu-id="35027-126">Para obtener más información sobre cómo ejecutar el Asistente para la implementación de Lync Server por primera vez desde los medios de instalación de Lync Server, consulte [instalar las herramientas administrativas 2013 de Lync Server](lync-server-2013-install-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="35027-126">For details about how to run the Lync Server Deployment Wizard for the first time from the Lync Server installation media, see [Install Lync Server 2013 administrative tools](lync-server-2013-install-lync-server-administrative-tools.md).</span></span>

</div>

<div>

## <a name="topology-builder"></a><span data-ttu-id="35027-127">Generador de topologías</span><span class="sxs-lookup"><span data-stu-id="35027-127">Topology Builder</span></span>

<span data-ttu-id="35027-128">Para obtener más información sobre las tareas de implementación que puede realizar con el generador de topologías, consulte la documentación de implementación de cada rol de servidor.</span><span class="sxs-lookup"><span data-stu-id="35027-128">For details about deployment tasks that you can you perform by using Topology Builder, see the Deployment documentation for each server role.</span></span>

</div>

<div>

## <a name="lync-server-control-panel"></a><span data-ttu-id="35027-129">Panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="35027-129">Lync Server Control Panel</span></span>

<span data-ttu-id="35027-130">Puede usar el panel de control de Lync Server 2013 para realizar la mayoría de las tareas administrativas necesarias para administrar y mantener Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="35027-130">You can use Lync Server 2013 Control Panel to perform most of the administrative tasks required to manage and maintain Lync Server 2013.</span></span> <span data-ttu-id="35027-131">El panel de control de Lync Server le proporciona una interfaz gráfica de usuario (GUI) para administrar la configuración de los servidores que ejecutan Lync Server, además de los usuarios, los clientes y los dispositivos de su organización.</span><span class="sxs-lookup"><span data-stu-id="35027-131">Lync Server Control Panel provides you with a graphical user interface (GUI) to manage the configuration of the servers running Lync Server, in addition to the users, clients, and devices in your organization.</span></span> <span data-ttu-id="35027-132">El shell de administración de Lync Server usa el panel de control de Lync Server como mecanismo subyacente para realizar la configuración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="35027-132">Lync Server Management Shell uses Lync Server Control Panel as the underlying mechanism to perform Lync Server configuration.</span></span>

<span data-ttu-id="35027-133">El panel de control de Lync Server se instala automáticamente en todos los servidores front-end de Lync Server o el servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="35027-133">Lync Server Control Panel is automatically installed on every Lync Server Front End Server or Standard Edition server.</span></span> <span data-ttu-id="35027-134">En esta versión, se administran servidores perimetrales de forma remota.</span><span class="sxs-lookup"><span data-stu-id="35027-134">In this release, you administer Edge Servers remotely.</span></span> <span data-ttu-id="35027-135">También puede instalar el panel de control de Lync Server en otro equipo, como una consola de administración desde la que desee administrar Lync Server de forma centralizada.</span><span class="sxs-lookup"><span data-stu-id="35027-135">You can also install Lync Server Control Panel on another computer, such as a management console from which you want to centrally manage Lync Server.</span></span> <span data-ttu-id="35027-136">Para obtener información detallada, consulte [instalar herramientas administrativas 2013 de Lync Server](lync-server-2013-install-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="35027-136">For details, see [Install Lync Server 2013 administrative tools](lync-server-2013-install-lync-server-administrative-tools.md).</span></span>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="35027-137">Para configurar la configuración con el panel de control de Lync Server, debe haber iniciado sesión con una cuenta asignada al rol CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="35027-137">To configure settings using Lync Server Control Panel, you must be logged in using an account that is assigned to the CsAdministrator role.</span></span> <span data-ttu-id="35027-138">Para obtener más información sobre los roles administrativos predefinidos disponibles en Lync Server 2013, consulte <A href="lync-server-2013-planning-for-role-based-access-control.md">planificación de control de acceso basado en roles en Lync server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="35027-138">For details about the predefined administrative roles available in Lync Server 2013, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="35027-139">Para configurar la configuración con el panel de control de Lync Server, también debe usar un equipo con una resolución de pantalla mínima de 1024 x 768.</span><span class="sxs-lookup"><span data-stu-id="35027-139">To configure settings using Lync Server Control Panel, you must also use a computer with a minimum screen resolution of 1024 x 768.</span></span></P></LI></UL>



</div>

</div>

<div>

## <a name="lync-server-management-shell"></a><span data-ttu-id="35027-140">Shell de administración de Communications Server</span><span class="sxs-lookup"><span data-stu-id="35027-140">Lync Server Management Shell</span></span>

<span data-ttu-id="35027-141">En Lync Server, el shell de administración de Lync Server proporciona un nuevo método de administración y administración.</span><span class="sxs-lookup"><span data-stu-id="35027-141">In Lync Server, the Lync Server Management Shell provides a new method for administration and management.</span></span> <span data-ttu-id="35027-142">El shell de administración de Lync Server es una eficaz interfaz de administración, creada en la interfaz de línea de comandos de Windows PowerShell, que incluye un conjunto completo de cmdlets específicos de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="35027-142">Lync Server Management Shell is a powerful management interface, built on the Windows PowerShell command-line interface, that includes a comprehensive set of cmdlets that are specific to Lync Server.</span></span> <span data-ttu-id="35027-143">Con el shell de administración de Lync Server, obtiene un conjunto completo de controles de configuración y automatización.</span><span class="sxs-lookup"><span data-stu-id="35027-143">With Lync Server Management Shell, you gain a rich set of configuration and automation controls.</span></span> <span data-ttu-id="35027-144">El generador de topología y el panel de control de Lync Server implementan subconjuntos de estos cmdlets para admitir la administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="35027-144">Topology Builder and Lync Server Control Panel both implement subsets of these cmdlets to support management of Lync Server.</span></span> <span data-ttu-id="35027-145">El shell de administración de Lync Server incluye cmdlets para todas las tareas de administración de Lync Server, y puede usar los cmdlets individualmente para administrar la implementación.</span><span class="sxs-lookup"><span data-stu-id="35027-145">The Lync Server Management Shell includes cmdlets for all Lync Server administration tasks, and you can use the cmdlets individually to manage your deployment.</span></span> <span data-ttu-id="35027-146">Para obtener más información, consulte la documentación del [Shell de administración de Lync Server 2013](lync-server-2013-lync-server-management-shell.md) o la ayuda de la línea de comandos para cada cmdlet.</span><span class="sxs-lookup"><span data-stu-id="35027-146">For details, see [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) documentation or the command-line help for each cmdlet.</span></span>

</div>

<div>

## <a name="logging-tool"></a><span data-ttu-id="35027-147">Herramienta de registro</span><span class="sxs-lookup"><span data-stu-id="35027-147">Logging Tool</span></span>

<span data-ttu-id="35027-148">La herramienta de registro de Lync Server facilita la solución de problemas al capturar el registro y la información de seguimiento del producto mientras se ejecuta el producto.</span><span class="sxs-lookup"><span data-stu-id="35027-148">The Lync Server Logging Tool facilitates troubleshooting by capturing logging and tracing information from the product while the product is running.</span></span> <span data-ttu-id="35027-149">Puede usar la herramienta para ejecutar sesiones de depuración en cualquier rol de servidor de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="35027-149">You can use the tool to run debug sessions on any Lync Server server role.</span></span> <span data-ttu-id="35027-150">Para obtener más información sobre la herramienta de registro, consulte la documentación de la herramienta de registro de Lync [http://go.microsoft.com/fwlink/p/?linkId=199265](http://go.microsoft.com/fwlink/p/?linkid=199265)Server 2010 en la biblioteca de TechNet en.</span><span class="sxs-lookup"><span data-stu-id="35027-150">For details about the Logging Tool, see the Lync Server 2010 Logging Tool documentation on the TechNet Library at [http://go.microsoft.com/fwlink/p/?linkId=199265](http://go.microsoft.com/fwlink/p/?linkid=199265).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="35027-151">El servicio de registro centralizado se recomienda para todas las colecciones de registro en la herramienta de registro de Lync Server en todas las circunstancias.</span><span class="sxs-lookup"><span data-stu-id="35027-151">The Centralized Logging Service is recommended for all logging collection over the Lync Server Logging Tool in all circumstances.</span></span> <span data-ttu-id="35027-152">La herramienta de registro de Lync Server seguirá funcionando, pero interferirá o se representará principalmente ineficaz si el servicio de registro centralizado ya se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="35027-152">The Lync Server Logging Tool will still work, but it will interfere or be rendered mostly ineffective if the Centralized Logging Service is already running.</span></span> <span data-ttu-id="35027-153">Debe usar solo el servicio de registro centralizado o la herramienta de registro de Lync Server, pero nunca ambos a la vez.</span><span class="sxs-lookup"><span data-stu-id="35027-153">You should use only the Centralized Logging Service or the Lync Server Logging Tool, but never both concurrently.</span></span> <span data-ttu-id="35027-154">Para obtener más información sobre el servicio de registro centralizado y por qué debería usarlo exclusivamente, consulte <A href="lync-server-2013-using-the-centralized-logging-service.md">usar el servicio de registro centralizado en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="35027-154">For more information on the Centralized Logging Service and why you should use it exclusively, see <A href="lync-server-2013-using-the-centralized-logging-service.md">Using the Centralized Logging Service in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="35027-155">En esta sección</span><span class="sxs-lookup"><span data-stu-id="35027-155">In This Section</span></span>

  - [<span data-ttu-id="35027-156">Requisitos de infraestructura de herramientas administrativas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35027-156">Administrative tools infrastructure requirements in Lync Server 2013</span></span>](lync-server-2013-administrative-tools-infrastructure-requirements.md)

  - [<span data-ttu-id="35027-157">Compatibilidad del sistema operativo con el servidor y las herramientas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35027-157">Server and tools operating system support in Lync Server 2013</span></span>](lync-server-2013-server-and-tools-operating-system-support.md)

  - [<span data-ttu-id="35027-158">Requisitos de software para herramientas administrativas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35027-158">Administrative tools software requirements in Lync Server 2013</span></span>](lync-server-2013-administrative-tools-software-requirements.md)

  - [<span data-ttu-id="35027-159">Derechos de administrador y permisos requeridos para la instalación y la administración de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35027-159">Administrator rights and permissions required for setup and administration of Lync Server 2013</span></span>](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)

  - [<span data-ttu-id="35027-160">Requisitos para publicar una topología en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35027-160">Requirements to publish a topology in Lync Server 2013</span></span>](lync-server-2013-requirements-to-publish-a-topology.md)

  - [<span data-ttu-id="35027-161">Instalar las herramientas administrativas de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35027-161">Install Lync Server 2013 administrative tools</span></span>](lync-server-2013-install-lync-server-administrative-tools.md)

  - [<span data-ttu-id="35027-162">Abrir las herramientas administrativas de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35027-162">Open Lync Server 2013 administrative tools</span></span>](lync-server-2013-open-lync-server-administrative-tools.md)

  - [<span data-ttu-id="35027-163">Solución de problemas del panel de control de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35027-163">Troubleshooting Lync Server 2013 Control Panel</span></span>](lync-server-2013-troubleshooting-lync-server-2013-control-panel.md)

  - [<span data-ttu-id="35027-164">Usar el servicio de registro centralizado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35027-164">Using the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-using-the-centralized-logging-service.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="35027-165">Vea también</span><span class="sxs-lookup"><span data-stu-id="35027-165">See Also</span></span>


[<span data-ttu-id="35027-166">Shell de administración de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35027-166">Lync Server 2013 Management Shell</span></span>](lync-server-2013-lync-server-management-shell.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

