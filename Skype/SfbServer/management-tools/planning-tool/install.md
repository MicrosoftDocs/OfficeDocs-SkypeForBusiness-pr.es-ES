---
title: Instalar la herramienta de planeación en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/5/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b95b3301-fa1e-4b96-9af4-05b43d39db8d
description: Antes de empezar a diseñar y planear la infraestructura de Skype Empresarial Server 2015 mediante la Herramienta de planeación de Skype Empresarial Server 2015, primero debe instalar la herramienta de planeación. La herramienta de planeación no necesita implementarse en una estación de trabajo o servidor que forme parte del dominio o la infraestructura donde tiene previsto instalar Skype Empresarial Server 2015. El archivo Léame que acompaña a la herramienta de planeación detalla información importante sobre la instalación y el uso de la herramienta. Alguna de la información del archivo Léame también aparece aquí por motivos de claridad.
ms.openlocfilehash: 29a3bd35191cf326cafd1f4ad4f14fab50e47ea3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122384"
---
# <a name="install-the-planning-tool-in-skype-for-business-server-2015"></a><span data-ttu-id="1e7a5-106">Instalar la herramienta de planeación en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="1e7a5-106">Install the Planning Tool in Skype for Business Server 2015</span></span>

<span data-ttu-id="1e7a5-107">Antes de empezar a diseñar y planear la infraestructura de Skype Empresarial Server 2015 mediante la Herramienta de planeación de Skype Empresarial Server 2015, primero debe instalar la herramienta de planeación.</span><span class="sxs-lookup"><span data-stu-id="1e7a5-107">Before you begin designing and planning your Skype for Business Server 2015 infrastructure by using the Skype for Business Server 2015 Planning Tool, you must first install the Planning Tool.</span></span> <span data-ttu-id="1e7a5-108">La herramienta de planeación no necesita implementarse en una estación de trabajo o servidor que forme parte del dominio o la infraestructura donde tiene previsto instalar Skype Empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="1e7a5-108">The Planning Tool does not need to be deployed to a workstation or server that is part of the domain or infrastructure where you plan to install Skype for Business Server 2015.</span></span> <span data-ttu-id="1e7a5-109">El archivo Léame que acompaña a la herramienta de planeación detalla información importante sobre la instalación y el uso de la herramienta.</span><span class="sxs-lookup"><span data-stu-id="1e7a5-109">The Readme file that accompanies the Planning Tool details important information about installing and using the tool.</span></span> <span data-ttu-id="1e7a5-110">Alguna de la información del archivo Léame también aparece aquí por motivos de claridad.</span><span class="sxs-lookup"><span data-stu-id="1e7a5-110">Some of the information in the Readme file is duplicated here for clarity.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1e7a5-111">La herramienta de planeación requiere la instalación de un usuario con derechos de administrador y permisos en el equipo en el que se va a instalar la herramienta.</span><span class="sxs-lookup"><span data-stu-id="1e7a5-111">The Planning Tool requires installation by a user with administrator rights and permissions on the computer on which the tool is to be installed.</span></span>

<span data-ttu-id="1e7a5-112">Los sistemas operativos compatibles para la instalación y el funcionamiento de la herramienta de planeación son:</span><span class="sxs-lookup"><span data-stu-id="1e7a5-112">The supported operating systems for installation and operation of the Planning Tool are:</span></span>

- <span data-ttu-id="1e7a5-113">Windows 10</span><span class="sxs-lookup"><span data-stu-id="1e7a5-113">Windows 10</span></span>

- <span data-ttu-id="1e7a5-114">Windows 8</span><span class="sxs-lookup"><span data-stu-id="1e7a5-114">Windows 8</span></span>

- <span data-ttu-id="1e7a5-115">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="1e7a5-115">Windows 8.1</span></span>

- <span data-ttu-id="1e7a5-116">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="1e7a5-116">Windows Server 2012</span></span>

- <span data-ttu-id="1e7a5-117">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="1e7a5-117">Windows Server 2012 R2</span></span>

- <span data-ttu-id="1e7a5-118">Edición de 32 bits de Windows 7</span><span class="sxs-lookup"><span data-stu-id="1e7a5-118">Windows 7, 32-bit edition</span></span>

- <span data-ttu-id="1e7a5-119">Edición de 64 bits de Windows 7 usando Windows en Win32 (WOW)</span><span class="sxs-lookup"><span data-stu-id="1e7a5-119">Windows 7, 64-bit edition using Windows on Win32 (WOW)</span></span>

- <span data-ttu-id="1e7a5-120">Windows Server 2008 R2 usando WOW</span><span class="sxs-lookup"><span data-stu-id="1e7a5-120">Windows Server 2008 R2, using WOW</span></span>

<span data-ttu-id="1e7a5-121">Además, la herramienta de planeación requiere Microsoft .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="1e7a5-121">Additionally, the Planning Tool requires Microsoft .NET Framework 4.5.</span></span>

<span data-ttu-id="1e7a5-122">Una vez que se cumplen los requisitos de preinstalación, puede instalar la herramienta de planeación.</span><span class="sxs-lookup"><span data-stu-id="1e7a5-122">After the preinstallation requirements are met, you can then install the Planning Tool.</span></span>



## <a name="to-install-the-planning-tool"></a><span data-ttu-id="1e7a5-123">Para instalar la Herramienta de planeación</span><span class="sxs-lookup"><span data-stu-id="1e7a5-123">To install the Planning Tool</span></span>

1. <span data-ttu-id="1e7a5-124">Inicie sesión en el equipo local como miembro del grupo Administradores.</span><span class="sxs-lookup"><span data-stu-id="1e7a5-124">Log on to the local computer as a member of the Administrators group.</span></span>

2. <span data-ttu-id="1e7a5-125">Con el Explorador de Windows o una ventana de comandos, busque el directorio donde descargó los archivos de instalación de la herramienta de planeación.</span><span class="sxs-lookup"><span data-stu-id="1e7a5-125">Using Windows Explorer or a command window, locate the directory where you downloaded the Planning Tool installation files.</span></span>

3. <span data-ttu-id="1e7a5-126">Busque el SkypeForBusinessPlanningTool.msi.</span><span class="sxs-lookup"><span data-stu-id="1e7a5-126">Locate the SkypeForBusinessPlanningTool.msi.</span></span> <span data-ttu-id="1e7a5-127">En el Explorador de Windows, haga doble clic en el archivo.</span><span class="sxs-lookup"><span data-stu-id="1e7a5-127">In Windows Explorer, double-click the file.</span></span> <span data-ttu-id="1e7a5-128">En la ventana de comandos, escriba el nombre del archivo y, a continuación, presione **ENTRAR** para ejecutar el archivo.</span><span class="sxs-lookup"><span data-stu-id="1e7a5-128">In the command window, type the name of the file, and then press **Enter** to run the file.</span></span>

4. <span data-ttu-id="1e7a5-129">En la página de bienvenida de **Skype Empresarial Server 2015, Asistente** para la configuración de herramientas de planeación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="1e7a5-129">On the Welcome page of the **Skype for Business Server 2015, Planning Tool Setup Wizard**, click **Next**.</span></span>

5. <span data-ttu-id="1e7a5-130">Lea el **Contrato de licencia para el usuario final**, seleccione **Acepto los términos del contrato de licencia**, si quiere aceptar los términos de uso del contrato de licencia, y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="1e7a5-130">Review the **End-User License Agreement**, select **I accept the terms in the License Agreement** if you choose to accept the terms of use in the license agreement, and then click **Next**.</span></span>

6. <span data-ttu-id="1e7a5-131">Elija donde quiere instalar los archivos de la Herramienta de planeación.</span><span class="sxs-lookup"><span data-stu-id="1e7a5-131">Choose where to install the Planning Tool files.</span></span> <span data-ttu-id="1e7a5-132">La ubicación predeterminada es C:\Archivos de programa (x86)\Skype Empresarial Server 2015\Planning Tool.</span><span class="sxs-lookup"><span data-stu-id="1e7a5-132">The default location is C:\Program Files (x86)\Skype for Business Server 2015\Planning Tool.</span></span> <span data-ttu-id="1e7a5-133">Si desea cambiar la ubicación de instalación, haga clic en **Cambiar**.</span><span class="sxs-lookup"><span data-stu-id="1e7a5-133">If you want to change the installation location, click **Change**.</span></span> <span data-ttu-id="1e7a5-134">En **Cambiar carpeta de destino**, busque o escriba la ubicación donde desea instalar los archivos; a continuación, haga clic en **Aceptar** y en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="1e7a5-134">On **Change destination folder**, browse or type the location to install the files, click **OK**, and then click **Next**.</span></span>

7. <span data-ttu-id="1e7a5-135">El instalador ya está listo para instalar la herramienta de planeación.</span><span class="sxs-lookup"><span data-stu-id="1e7a5-135">The installer is now ready to install the Planning Tool.</span></span> <span data-ttu-id="1e7a5-136">Haga clic en **Instalar** para comenzar el proceso de instalación.</span><span class="sxs-lookup"><span data-stu-id="1e7a5-136">Click **Install** to begin the installation process.</span></span>

8. <span data-ttu-id="1e7a5-137">La instalación se iniciará y se mostrará el progreso de la misma.</span><span class="sxs-lookup"><span data-stu-id="1e7a5-137">The installation will start, and the progress will be displayed.</span></span> <span data-ttu-id="1e7a5-138">Una vez completado el proceso de instalación, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="1e7a5-138">After the installation is successfully completed, click **Finish**.</span></span>

9. <span data-ttu-id="1e7a5-139">La herramienta de planeación está lista para su uso.</span><span class="sxs-lookup"><span data-stu-id="1e7a5-139">The Planning Tool is ready for use.</span></span>

## <a name="optional-software"></a><span data-ttu-id="1e7a5-140">Software opcional</span><span class="sxs-lookup"><span data-stu-id="1e7a5-140">Optional Software</span></span>
<span data-ttu-id="1e7a5-141"><a name="Optional_Software"> </a></span><span class="sxs-lookup"><span data-stu-id="1e7a5-141"><a name="Optional_Software"> </a></span></span>

<span data-ttu-id="1e7a5-142">La herramienta de planeación de Skype Empresarial Server 2015 está diseñada para exportar a Microsoft Excel y Microsoft Visio.</span><span class="sxs-lookup"><span data-stu-id="1e7a5-142">The Skype for Business Server 2015 Planning Tool is designed to export to Microsoft Excel and Microsoft Visio.</span></span> <span data-ttu-id="1e7a5-143">Aunque estas aplicaciones no son necesarias para el funcionamiento de la herramienta de planeación, sí agregan un valor significativo a la implementación y documentación del diseño.</span><span class="sxs-lookup"><span data-stu-id="1e7a5-143">While these applications are not required for the operation of the Planning Tool, they do add significant value to the deployment and documentation of your design.</span></span>

### <a name="microsoft-excel"></a><span data-ttu-id="1e7a5-144">Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="1e7a5-144">Microsoft Excel</span></span>

<span data-ttu-id="1e7a5-145">Al exportar el diseño a Microsoft Excel, se crea un informe que muestra siete pestañas en la hoja de cálculo:</span><span class="sxs-lookup"><span data-stu-id="1e7a5-145">Exporting your design to Microsoft Excel creates a report that displays seven tabs in the spreadsheet:</span></span>

- <span data-ttu-id="1e7a5-146">Resumen: muestra información sobre la configuración del sitio, incluido el recuento de usuarios, la configuración de capacidad y la información de perfil de servidor.</span><span class="sxs-lookup"><span data-stu-id="1e7a5-146">Summary - Displays information on site configuration, including user count, capacity settings, and server profile information.</span></span>

- <span data-ttu-id="1e7a5-147">Perfil de hardware: muestra un informe sobre las configuraciones de hardware recomendadas para los servidores especificados en la topología, incluida la CPU, la memoria, el disco y la interfaz de red.</span><span class="sxs-lookup"><span data-stu-id="1e7a5-147">Hardware Profile - Displays a report on the recommended hardware configurations for servers that are specified in the topology, including CPU, memory, disk, and network interface.</span></span> <span data-ttu-id="1e7a5-148">También se incluyen la cantidad y las especificaciones recomendadas para los componentes del servidor.</span><span class="sxs-lookup"><span data-stu-id="1e7a5-148">The quantity and recommended specifications for the server components are also included.</span></span> <span data-ttu-id="1e7a5-149">Además, cada servidor se define por sitio para proporcionar una representación completa de los requisitos del servidor por sitio.</span><span class="sxs-lookup"><span data-stu-id="1e7a5-149">In addition, each server is defined by site to provide a complete representation of server requirements by site.</span></span>

- <span data-ttu-id="1e7a5-150">Requisitos de puertos: muestra un informe de todos los puertos habilitados y la asociación al equilibrio de carga del sistema de nombres de dominio (DNS LB) y a los equilibradores de carga de hardware (HLB).</span><span class="sxs-lookup"><span data-stu-id="1e7a5-150">Ports Requirements - Displays a report of all ports that are enabled, and the association to Domain Name System load balancing (DNS LB) and hardware load balancers (HLB).</span></span> <span data-ttu-id="1e7a5-151">Debe usar este informe para planear el firewall y las configuraciones de DNS LB y HLB.</span><span class="sxs-lookup"><span data-stu-id="1e7a5-151">You should use this report to plan your firewall and DNS LB and HLB configurations.</span></span>

- <span data-ttu-id="1e7a5-152">Informe de resumen: muestra el resumen general de la configuración necesaria para configurar la red del servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="1e7a5-152">Summary Report - Displays the general summary of the settings that are required to set up your Edge Server network.</span></span>

- <span data-ttu-id="1e7a5-153">Informe de certificados: muestra el nombre del sujeto y los nombres alternativos de sujeto necesarios para los certificados necesarios para que se ejecuten los servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="1e7a5-153">Certificates Report - Displays the subject name and subject alternate names that are required for the certificates needed to get the Edge Servers running.</span></span>

- <span data-ttu-id="1e7a5-154">Informe de firewall: muestra los puertos de origen y de destino y las direcciones IP para las interfaces externas e internas.</span><span class="sxs-lookup"><span data-stu-id="1e7a5-154">Firewall Report - Displays the source and destination ports and IP addresses for both External and Internal interfaces.</span></span>

- <span data-ttu-id="1e7a5-155">Informe DNS: muestra el nombre de dominio completo (FQDN) y las direcciones IP/VIP necesarias para cada entrada DNS que cree.</span><span class="sxs-lookup"><span data-stu-id="1e7a5-155">DNS Report - Displays the fully qualified domain name (FQDN) and IP/VIP addresses required for each DNS entry that you create.</span></span>

### <a name="microsoft-visio"></a><span data-ttu-id="1e7a5-156">Microsoft Visio</span><span class="sxs-lookup"><span data-stu-id="1e7a5-156">Microsoft Visio</span></span>

<span data-ttu-id="1e7a5-157">Al exportar el diseño a Microsoft Visio, se crea un diagrama para usarlo en los fines de documentación de la infraestructura y la topología configuradas.</span><span class="sxs-lookup"><span data-stu-id="1e7a5-157">Exporting your design to Microsoft Visio creates a diagram for use in your documentation purposes of your configured topology and infrastructure.</span></span> <span data-ttu-id="1e7a5-158">El diagrama importado se puede editar y reorganizar para satisfacer sus necesidades de documentación.</span><span class="sxs-lookup"><span data-stu-id="1e7a5-158">The imported diagram can be edited and rearranged to meet your documentation needs.</span></span> <span data-ttu-id="1e7a5-159">El diagrama típico de Visio incluirá:</span><span class="sxs-lookup"><span data-stu-id="1e7a5-159">The typical Visio diagram will include:</span></span>

> [!NOTE]
> <span data-ttu-id="1e7a5-160">Si el diseño es lo suficientemente grande como para requerir más de tres servidores front-end, se creará una página adicional para el grupo de servidores front-end, los servidores front-end, el equipo que ejecuta SQL Server, direcciones IP y FQDN.</span><span class="sxs-lookup"><span data-stu-id="1e7a5-160">If your design is large enough to require more than three Front End Servers, an additional page will be created for the Front End pool, Front End Servers, the computer running SQL Server, IP addresses, and FQDNs.</span></span>

- <span data-ttu-id="1e7a5-161">Topología global: diagrama de sitios configurados de Skype Empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="1e7a5-161">Global Topology - Diagram of configured Skype for Business Server 2015 sites.</span></span>

- <span data-ttu-id="1e7a5-162">Pestaña Nombre del sitio: muestra la topología de configuración del sitio con servidor perimetral, firewall, red telefónica conmutada (RTC) con puertas de enlace e implementación del servidor interno.</span><span class="sxs-lookup"><span data-stu-id="1e7a5-162">Site Name tab - Displays the site configuration topology with Edge Server, firewall, public switched telephone network (PSTN) with gateways, and the internal server deployment.</span></span> <span data-ttu-id="1e7a5-163">La implementación interna consta de servidores y grupos configurados, incluidos los grupos de servidores front-end, los servidores basados en SQL Server, los servicios de dominio de Active Directory, los directores, los servidores de mensajería unificada (MU) de Exchange, los servidores de buzones de Exchange, los servidores de Office Web Apps, los servidores de mediación y los servidores de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="1e7a5-163">Internal deployment consists of configured servers and pools, including the Front End pools, SQL Server-based servers, Active Directory Domain Services, Directors, Exchange Unified Messaging (UM) servers, Exchange Mailbox Servers, Office Web Apps Servers, Mediation Servers, and Persistent Chat Servers.</span></span>

- <span data-ttu-id="1e7a5-164">Diagrama de red perimetral: diagrama que detalla la configuración del servidor perimetral con direcciones IP y FQDN asociados.</span><span class="sxs-lookup"><span data-stu-id="1e7a5-164">Edge Network Diagram - Diagram detailing the Edge Server configuration with associated IP addresses and FQDNs.</span></span> <span data-ttu-id="1e7a5-165">También se incluyen equilibradores de carga dns y equilibradores de carga de hardware.</span><span class="sxs-lookup"><span data-stu-id="1e7a5-165">DNS load balancing and hardware load balancers are also included.</span></span> <span data-ttu-id="1e7a5-166">Además, se muestran directores y el servidor front-end o grupo de servidores front-end, con DNS LB o HLB asociados y la dirección IP asignada (la Herramienta de planeación admite direcciones IPv4 e IPv6) y FQDN.</span><span class="sxs-lookup"><span data-stu-id="1e7a5-166">Additionally, Directors and the Front End Server or Front End pool are displayed, with associated DNS LB or HLB and the assigned IP address (the Planning Tool supports both IPv4 and IPv6 addresses) and FQDN.</span></span>

## <a name="see-also"></a><span data-ttu-id="1e7a5-167">Ver también</span><span class="sxs-lookup"><span data-stu-id="1e7a5-167">See also</span></span>
<span data-ttu-id="1e7a5-168"><a name="Optional_Software"> </a></span><span class="sxs-lookup"><span data-stu-id="1e7a5-168"><a name="Optional_Software"> </a></span></span>

[<span data-ttu-id="1e7a5-169">Instalación de la herramienta de planeación</span><span class="sxs-lookup"><span data-stu-id="1e7a5-169">Installing the Planning Tool</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-installing-the-planning-tool)